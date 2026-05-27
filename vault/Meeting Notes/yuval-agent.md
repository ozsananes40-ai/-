---
name: yuval-agent
description: תיעוד .claude/agents/yuval.md - הגדרת יובל, מעצב התמונות
metadata:
  type: project
---

# יובל - מעצב התמונות (.claude/agents/yuval.md)

## Overview

ההגדרה של יובל יושבת ב-`.claude/agents/yuval.md`. יובל אחראי על יצירת תמונות לתוכן. הכלים שלו: `Read, Write, Bash, Glob`.

**זרימת עבודה:**
0. בדיקת [[env-file]] - אם `OPENAI_API_KEY` ריק, עוצר ומדווח. **לא קורא ל-API בלי key.**
1. סריקת [[yuval-reference]] (Glob + Read) פעם אחת בסשן - חילוץ פלטה, מדיום, אווירה.
2. בחירת רכיבים רלוונטיים מה-reference לבקשה הספציפית.
3. ניסוח prompt **באנגלית** (gpt-image-2 עובד הכי טוב באנגלית), 2-5 משפטים.
4. קריאה ל-[[skill-gpt-image-gen]] דרך Bash.
5. שמירת שני קבצים ב-`yuval/outputs/`: `<YYYY-MM-DD>-<slug>.png` + `<slug>.txt` (ה-prompt).
6. אימות עם `ls -la` (size > 0, ~0.5-3MB) ודיווח.

**גבולות נוקשים:** תמונה אחת בכל קריאה (לא batch). אסור להחליף את שם המודל (`gpt-image-2`, יצא 21.4.2026). אסור להמציא תמונות "במחשבה" - חייב לעבור דרך ה-API. Slugs באנגלית בלבד (עברית שוברת Windows paths). Prompt באנגלית.

## Open Questions
- [[yuval-reference]] ריק כרגע - חוצן את הסגנון מ-prompts קודמים. כדאי להוסיף תמונות reference מפורשות בעתיד.
- האם יש סיבה לעבור ל-Stability AI כ-fallback? נראה ב-[[env-example]] כאופציה אבל לא מומש.

## Session Log

### 2026-05-26 — תיעוד הקובץ ב-vault [shipped]
- **What was done:** נכתב תיעוד שמסכם את ההגדרה, הזרימה, והכללים הקריטיים (במיוחד הכלל על שם המודל).
- **Decisions:** הדגשתי במיוחד את הכלל "לא להחליף את שם המודל" - זו תקלת LLM קלאסית שיובל מנוע מלעשות.
- **Notes / Caveats:** הקובץ עצמו ארוך וכולל דוגמת זרימה מלאה.
- **Related:** [[claude-md]], [[skill-gpt-image-gen]], [[yuval-reference]], [[yuval-outputs-as-reference]], [[env-file]], [[env-example]], [[yael-agent]]
