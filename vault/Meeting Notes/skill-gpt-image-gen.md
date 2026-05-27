---
name: skill-gpt-image-gen
description: תיעוד הסקיל gpt-image-gen - מעטפת OpenAI Images API
metadata:
  type: project
---

# Skill: gpt-image-gen

## Overview

הסקיל הזה הוא מעטפת דקה סביב OpenAI Images API. הוא לוקח prompt טקסטואלי, שולח ל-`gpt-image-2`, ושומר PNG מוחזר לנתיב מקומי. הקובץ ב-`.claude/skills/gpt-image-gen/SKILL.md`.

**המשתמש העיקרי:** [[yuval-agent]]. כל סוכן יכול לקרוא לסקיל הזה אם הוא צריך תמונה.

**אזהרה קריטית בסקיל:** המודל הוא `gpt-image-2` בדיוק. הוא יצא על ידי OpenAI ב-21.4.2026. גם אם נראה ל-LLM שהוא לא מכיר את המודל, **אין להחליף** ל-`dall-e-3` / `gpt-image-1` / `dall-e-2`. שגיאות מה-API הן כמעט תמיד API key חסר או פרמטר פגום, לא שם מודל.

**זרימה (5 שלבים):**
1. Load API key מ-`.env` (bash `source` או PowerShell parse).
2. POST ל-`https://api.openai.com/v1/images/generations` עם המודל, prompt, size, quality.
3. Decode התגובה (jq+base64 preferred; python fallback ל-Git Bash על Windows).
4. Verify הקובץ הנשמר (size > 0, ~0.5-3MB).
5. Error handling - הצף את ה-`error` מהתגובה verbatim, **בלי להחליף שם מודל.**

**פרמטרים:**
- `prompt` (חובה, אנגלית, descriptive)
- `output_path` (חובה, ends in `.png`)
- `size` (default `1024x1024`; אופציות: `1024x1024`, `1024x1536`, `1536x1024`)
- `quality` (default `medium`; `low`/`medium`/`high`)

## Open Questions
- האם להוסיף תמיכה בפרמטרים נוספים של ה-API (style, response_format)? כרגע מינימליסטי.
- האם להחליף את `/tmp/gpt-image-response.json` ל-`.tmp/` מקומי? יצא [[response-json]] בשורש ב-debug session.

## Session Log

### 2026-05-26 — תיעוד הסקיל ב-vault [shipped]
- **What was done:** תועד SKILL.md המלא - מודל, פרמטרים, זרימה, error handling.
- **Decisions:** הדגשתי במיוחד את הכלל על שם המודל - זה הכלל הכי קריטי בסקיל.
- **Notes / Caveats:** הסקיל נוצר ב-`.claude/skills/gpt-image-gen/` כחלק מההקמה של יובל (commit 530ec6e).
- **Related:** [[yuval-agent]], [[env-file]], [[env-example]], [[response-json]], [[yuval-outputs-as-reference]]
