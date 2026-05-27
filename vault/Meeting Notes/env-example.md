---
name: env-example
description: תיעוד .env.example - תבנית משתני סביבה לכל הסוכנים
metadata:
  type: project
---

# .env.example

## Overview

תבנית `.env.example` מגדירה את כל משתני הסביבה שהפרויקט יכול להזדקק להם, ללא ערכים אמיתיים. המשתמש יוצר ממנה `.env` מקומי וממלא ערכים. מסודר לפי סוכן:

- **Anthropic** — `ANTHROPIC_API_KEY` (לא חובה בתוך Claude Code עצמו, רק אם רץ SDK חיצוני).
- **יובל** — `OPENAI_API_KEY` ליצירת תמונות דרך `gpt-image-2`. `STABILITY_API_KEY` אופציונלי.
- **חן** — `TAVILY_API_KEY` / `BRAVE_SEARCH_API_KEY` / `SERPER_API_KEY` (מוכנים בהערה, חן עדיין משתמשת ב-WebSearch הפנימי של Claude).
- **יעל** — אין משתנים חיצוניים, עובדת רק עם Claude.

## Open Questions
- האם יובל צריך לתמוך גם ב-Stability AI כ-fallback? כרגע רק OpenAI.
- אם חן תעבור לשימוש ב-search API חיצוני (Tavily / Brave), זה ידרוש עדכון כאן ו-skill ייעודי.

## Session Log

### 2026-05-26 — תיעוד הקובץ ב-vault [shipped]
- **What was done:** נכתב קובץ תיעוד עבור `.env.example`.
- **Decisions:** סווג כ-project memory כי הוא מתעד את המבנה הסביבתי של הפרויקט וההחלטות על אילו שירותים נדרשים לכל סוכן.
- **Notes / Caveats:** הקובץ עצמו מתעדכן רק כשמוסיפים תלות חיצונית חדשה.
- **Related:** [[env-file]], [[gitignore]], [[yuval-agent]], [[chen-agent]], [[skill-gpt-image-gen]]
