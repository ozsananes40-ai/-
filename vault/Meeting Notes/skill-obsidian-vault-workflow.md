---
name: skill-obsidian-vault-workflow
description: תיעוד הסקיל obsidian-vault-workflow - ניהול ה-vault הזה
metadata:
  type: project
---

# Skill: obsidian-vault-workflow

## Overview

הסקיל שמגדיר את הפרוטוקול לעבודה עם `vault/` כזיכרון ארוך-טווח של הפרויקט. נמצא ב-`.claude/skills/obsidian-vault-workflow/`. הסקיל הזה הוא הסיבה שכל ה-vault הזה קיים.

**עיקרון:** קובץ אחד לכל נושא. כל קובץ מכיל:
- `## Overview` קבוע - מה הנושא
- `## Open Questions` - מה לא נסגר
- `## Session Log` - רשומות מתוארכות עם status tags (`[shipped]`, `[wip]`, `[planned]`, `[debug]`, `[spiked]`, `[reverted]`).

**שתי פאזות:**
- **Phase 1 (לפני כל משימה):** זיהוי נושא, חיפוש קובץ, קריאה מלאה (Overview + Open Questions + כל ה-Session Log), קריאת 2-3 Meeting Notes אחרונים, סקירת Content Briefs ו-Brand Guidelines רלוונטיים. דיווח על מה שנטען.
- **Phase 2 (אחרי כל משימה):** בחירת תיקייה, קביעת שם, עדכון Overview במידת הצורך, עדכון Open Questions, צירוף `### YYYY-MM-DD — title [status]` בתחתית, קישור עם `[[wikilinks]]`, **קריאה חוזרת של הקובץ כאימות**.

**ארבע תיקיות סטנדרטיות:**
- `Meeting Notes/` - קוד, ארכיטקטורה, החלטות
- `Content Briefs/` - בריפים עורכיים
- `Publishing Log/` - פרסומים ופוסטמורטמים
- `Brand Guidelines/` - קול ויזואלי, טון, UI

כל תיקייה צריכה `_index.md` עם רשימה שטוחה של כל הנושאים בה.

## Open Questions
- האם להוסיף הוראה ב-[[claude-md]] שתפעיל את הסקיל הזה בתחילת כל סשן? (המשתמש ביקש זאת בסשן זה, נוסף ל-todo)
- האם כדאי לאחד את [[skill-obsidian-bases]] לכאן כדי שעבודה עם `.base` תהיה חלק מהפרוטוקול?

## Session Log

### 2026-05-26 — תיעוד הסקיל + הפעלה ראשונה [shipped]
- **What was done:** תועד הסקיל; הסקיל הופעל לראשונה כדי לבנות את ה-vault עצמו (ראו [[vault-bootstrap]]).
- **Decisions:** מבנה ה-vault שנבחר: ארבע תיקיות סטנדרטיות עם _index.md בכל אחת, וקובץ נושא לכל קובץ בפרויקט.
- **Notes / Caveats:** הסקיל אסר מפורש על "תאריך בשם קובץ" - כל שם נושא חסר תאריך.
- **Related:** [[vault-bootstrap]], [[skills-overview]], [[skill-obsidian-markdown]], [[skill-obsidian-bases]], [[claude-md]]
