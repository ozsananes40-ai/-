---
name: yael-agent
description: תיעוד .claude/agents/yael.md - הגדרת יעל, כותבת התוכן
metadata:
  type: project
---

# יעל - כותבת התוכן (.claude/agents/yael.md)

## Overview

ההגדרה של יעל יושבת ב-`.claude/agents/yael.md`. יעל אחראית על שכתוב מאמרי גלם מ-`Content/` לסגנון הצוות. הכלים שלה: `Read, Write, Edit, Glob, Grep`.

**זרימת עבודה:**
1. משיכת מאמר מ-`Content/` (Glob → Read).
2. קריאת [[yael-style-guide]] + כל הקבצים תחת [[yael-reference]] פעם אחת בסשן.
3. שכתוב התוכן בעברית בקול הצוות.
4. שמירת שני קבצים ב-`Output/` עם אותו שם בסיס: `<name>.md` ו-`<name>.html` (תבנית HTML עם RTL).
5. דיווח לראובן עם סיכום + רשימת `{{IMAGE_NEEDED: "..."}}` placeholders.

**סימון תמונות** — יעל לא יוצרת תמונות, היא רק מסמנת איפה צריכה תמונה בפורמט המדויק `{{IMAGE_NEEDED: "תיאור מפורט בעברית"}}` כשורה משלה. ראובן מאתר אותם אוטומטית ומעביר ל-[[yuval-agent]].

**כללים נוקשים:** בלי CTAs, בלי קישורים שיווקיים, בלי הפניות לבלוג/ניוזלטר של המקור. מותגים בתוך הסיפור (כמו "אני משתמש ב-Notion") נשארים. תמיד עברית, אלא אם המשתמש ביקש אחרת.

## Open Questions
- [[yael-style-guide]] הוא כרגע שלד (TBD) - צריך להתמלא על ידי המשתמש.
- [[yael-reference]] ריק כרגע - לא נצברו עדיין דוגמאות לסגנון.

## Session Log

### 2026-05-26 — תיעוד הקובץ ב-vault [shipped]
- **What was done:** נכתב תיעוד שמסכם את ההגדרה, הזרימה, ה-placeholders ותבנית ה-HTML של יעל.
- **Decisions:** סווג כ-project memory.
- **Notes / Caveats:** הקובץ ב-`.claude/agents/yael.md` כולל את כל ה-HTML template - כאן רק קישרתי, לא העתקתי.
- **Related:** [[claude-md]], [[yael-style-guide]], [[yael-reference]], [[yuval-agent]], [[chen-agent]], [[output-vaad-bayit-guide]], [[output-crm-explainer]]
