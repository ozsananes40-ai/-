---
name: chen-agent
description: תיעוד .claude/agents/chen.md - הגדרת חן, חוקרת הרשת
metadata:
  type: project
---

# חן - חוקרת הרשת (.claude/agents/chen.md)

## Overview

ההגדרה של חן יושבת ב-`.claude/agents/chen.md`. חן היא הסוכנת שאחראית על מציאת מאמרים, מקורות ומידע עכשווי מהרשת. הכלים שלה: `WebSearch, WebFetch, Read, Write, Edit, Glob, Grep`.

**זרימת עבודה מקודדת בקובץ:**
1. בדיקת זיכרון מול [[chen-memory-searches]] לפני כל חיפוש חדש.
2. WebSearch עם 2-3 זוויות שונות.
3. WebFetch על 3-5 התוצאות הטובות ביותר.
4. סינון לפי קריטריונים (מקורות ראשוניים, פרסומים מקצועיים, תאריך עדכני; דחיית אגרגטורים, clickbait, AI-generated).
5. שמירה ב-`Content/<YYYY-MM-DD>-<slug>.md` עם frontmatter מלא (source_url, title, author, date, retrieved_at, language).
6. תיעוד ב-[[chen-memory-searches]].
7. דיווח לראובן.

**גבולות חזקים:** לא יוצרת תמונות (יובל), לא משכתבת ([[yael-agent]]), לא מפעילה סוכנים אחרים. סיום במסירת קובץ לראובן.

**נושאים דינמיים** — חדשות, מחירים, סטטיסטיקות, גרסאות תוכנה — חן תמיד מחפשת מחדש גם אם יש cache.

## Open Questions
- האם להוסיף תמיכה ב-search API חיצוני (Tavily / Brave) כשה-WebSearch הפנימי לא מספיק? תלוי גם ב-[[env-example]].
- מערכת ה-cache של 30 יום היא אריתמטית פשוטה - אולי כדאי לעבור ל-[[skill-obsidian-bases]] עבור עבודה עם searches.md כמסד נתונים.

## Session Log

### 2026-05-26 — תיעוד הקובץ ב-vault [shipped]
- **What was done:** נכתב קובץ תיעוד שמסכם את ההגדרה, הכלים, זרימת העבודה והגבולות של חן.
- **Decisions:** סווג כ-project כי הקובץ עצמו הוא ארטיפקט פרויקט (לא feedback או רפרנס חיצוני).
- **Notes / Caveats:** הקובץ ב-`.claude/agents/chen.md` נכתב בעברית עם דוגמת זרימה מלאה - הוא הסמכותי, התיעוד כאן הוא תקציר.
- **Related:** [[claude-md]], [[chen-memory-searches]], [[yael-agent]], [[yuval-agent]], [[vaad-bayit-guide-israel]]
