---
name: gpt-image-gen
description: Use when you need to generate an image from a text prompt via OpenAI's Images API. Wraps the gpt-image-2 model call and saves the result as a local PNG file.
---

# gpt-image-gen

## Overview

A thin wrapper around OpenAI's Images API. Takes a text prompt, sends it to `gpt-image-2`, and saves the returned PNG to a local path.

The primary caller is the `yuval` agent (image designer), but any agent that needs to produce an image can invoke this skill.

One call = one image.

## ⚠️ Critical: Model name

The model is **`gpt-image-2`**, exactly.

- It was released by OpenAI on **April 21, 2026**.
- Your internal training data may not include it — **that does not mean it doesn't exist**.
- **Do NOT substitute** `dall-e-3`, `gpt-image-1`, `dall-e-2`, or any other name. Use `gpt-image-2`.
- If the API returns an error, the cause is almost certainly:
  - A missing or invalid `OPENAI_API_KEY`, OR
  - A malformed parameter (e.g. bad `size`, prompt too long).
- The cause is **not** that the model name is wrong. Do not "fix" the model name in response to errors.

## Prerequisites

- `OPENAI_API_KEY` set in `.env` at the project root, with a real (non-empty) value.
- `curl` available on PATH (standard on macOS, Linux, Git Bash on Windows).
- Either `jq` and `base64` on PATH (preferred), **or** `python` (fallback for Git Bash on Windows where `jq` is often missing).

## Inputs

| Field         | Required | Default        | Notes                                                                |
|---------------|----------|----------------|----------------------------------------------------------------------|
| `prompt`      | yes      | —              | Descriptive English prompt. Be specific and visual.                  |
| `output_path` | yes      | —              | Absolute or repo-relative path ending in `.png`. Parent dir must exist. |
| `size`        | no       | `1024x1024`    | Allowed: `1024x1024`, `1024x1536`, `1536x1024`.                      |
| `quality`     | no       | `medium`       | `low` / `medium` / `high`. Higher = slower + more expensive.         |

## Step 1: Load the API key

Load `OPENAI_API_KEY` from `.env` before calling curl.

```bash
# Bash / Git Bash
set -a
source .env
set +a
```

On Windows PowerShell (if Bash isn't available), export manually:

```powershell
$envFile = Get-Content .env | Where-Object { $_ -match '^OPENAI_API_KEY=' }
$env:OPENAI_API_KEY = ($envFile -split '=', 2)[1]
```

**Verify it loaded**: `echo "${OPENAI_API_KEY:0:7}..."` should print `sk-...` (the first 7 chars). If it prints `...` only, the key is missing — abort and tell the caller.

## Step 2: Make the API call

```bash
curl -X POST "https://api.openai.com/v1/images/generations" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "gpt-image-2",
    "prompt": "<the prompt>",
    "size": "1024x1024",
    "quality": "medium",
    "output_format": "png"
  }' > /tmp/gpt-image-response.json
```

Replace `<the prompt>` with the actual prompt. **Escape double quotes and newlines** in the prompt before embedding in JSON — safest is to build the JSON body via a heredoc or a small script, not raw string concatenation.

Example with a heredoc (Bash):

```bash
PROMPT='A cat sitting on a stack of books, watercolor style, soft pastel colors'
OUTPUT='/tmp/gpt-image-response.json'

cat > /tmp/gpt-image-request.json <<EOF
{
  "model": "gpt-image-2",
  "prompt": "$PROMPT",
  "size": "1024x1024",
  "quality": "medium",
  "output_format": "png"
}
EOF

curl -sS -X POST "https://api.openai.com/v1/images/generations" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: application/json" \
  -d @/tmp/gpt-image-request.json > "$OUTPUT"
```

## Step 3: Decode the response

The response is JSON; the image is in `data[0].b64_json` as base64.

### Path A — `jq` + `base64` (preferred)

```bash
jq -r '.data[0].b64_json' /tmp/gpt-image-response.json | base64 --decode > <output-path>.png
```

### Path B — Python fallback (use when `jq` is not installed; common on Git Bash)

```bash
python -c "import json,base64,sys; d=json.load(open('/tmp/gpt-image-response.json')); open(sys.argv[1],'wb').write(base64.b64decode(d['data'][0]['b64_json']))" <output-path>.png
```

Decide which path to use by probing for `jq`:

```bash
if command -v jq >/dev/null 2>&1; then
  # Path A
else
  # Path B
fi
```

## Step 4: Verify the output file

```bash
ls -la <output-path>.png
```

- File must exist.
- Size must be **> 0 bytes**. A typical PNG from `gpt-image-2` at `1024x1024 medium` is 0.5–3 MB.
- If size is 0, the decode failed — inspect `/tmp/gpt-image-response.json` for an `error` field.

## Step 5: Error handling

If `/tmp/gpt-image-response.json` contains an `error` field instead of `data`, surface the message to the caller verbatim. Examples of real errors and how to read them:

```bash
jq '.error' /tmp/gpt-image-response.json
```

- `"Incorrect API key provided"` → fix the value in `.env`.
- `"You exceeded your current quota"` → billing issue on the OpenAI account.
- `"Invalid value for 'size'"` → check the size parameter against the allowed list.

**Do not** respond to any error by changing the model name. If you see an error mentioning the model, copy the exact error to the caller — do not silently swap the model.

## Full minimal example

```bash
set -a; source .env; set +a

PROMPT='A cat sitting on a stack of books, watercolor style, soft pastel colors'
OUT_PATH='yuval/outputs/2026-05-26-cat-on-books.png'

cat > /tmp/gpt-image-request.json <<EOF
{
  "model": "gpt-image-2",
  "prompt": "$PROMPT",
  "size": "1024x1024",
  "quality": "medium",
  "output_format": "png"
}
EOF

curl -sS -X POST "https://api.openai.com/v1/images/generations" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: application/json" \
  -d @/tmp/gpt-image-request.json > /tmp/gpt-image-response.json

if command -v jq >/dev/null 2>&1; then
  jq -r '.data[0].b64_json' /tmp/gpt-image-response.json | base64 --decode > "$OUT_PATH"
else
  python -c "import json,base64,sys; d=json.load(open('/tmp/gpt-image-response.json')); open(sys.argv[1],'wb').write(base64.b64decode(d['data'][0]['b64_json']))" "$OUT_PATH"
fi

ls -la "$OUT_PATH"
```
