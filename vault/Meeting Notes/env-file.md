---
name: env-file
description: תיעוד .env - קובץ הסודות המקומי שאינו ב-git
metadata:
  type: project
---

# .env (סודות מקומיים)

## Overview

הקובץ `.env` בשורש הפרויקט מכיל את הערכים האמיתיים של ה-API keys (בעיקר `OPENAI_API_KEY` לטובת יובל). הוא נוצר ידנית על ידי המשתמש מתוך [[env-example]], והוא מוחרג ב-[[gitignore]] כדי שלא יידחף לרימוט.

המבנה מועתק מ-`.env.example`, רק עם ערכים בפועל. יובל בודק את הקובץ הזה בכל הפעלה (שלב 0 בזרימת העבודה שלו) - אם `OPENAI_API_KEY` ריק או חסר, הוא עוצר ומדווח לראובן בלי לקרוא ל-API.

## Open Questions
- none

## Session Log

### 2026-05-26 — תיעוד הקובץ ב-vault [shipped]
- **What was done:** נכתב תיעוד שמסביר את התפקיד של `.env` ואת היחס שלו לתבנית.
- **Decisions:** לא לקרוא את הקובץ עצמו ולתעד תכנים - הוא מכיל סודות. רק לתעד את התפקיד והמבנה.
- **Notes / Caveats:** אם הקובץ נמחק, יובל ייכשל מיד. הוא לא חוצה לסקיל ולא נשבר חרישית.
- **Related:** [[env-example]], [[gitignore]], [[yuval-agent]], [[skill-gpt-image-gen]]
