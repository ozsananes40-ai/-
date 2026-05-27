---
name: crm-explainer-sample
description: בריף תוכן - מאמר לדוגמא על CRM (קלט ידני, יעל + יובל)
metadata:
  type: project
---

# Brief: מאמר לדוגמא - מה זה CRM

## Overview

מאמר על "מה זה CRM ולמה כל עסק צריך אותו". הקובץ הגולמי הוא **לא** מ-[[chen-agent]] אלא מהמשתמש ישירות - `Content/מאמר לדוגמא.txt`. שימש כמאמר ראשון לבדיקת הזרימה של [[yael-agent]] + [[yuval-agent]].

**הקלט:** טקסט בעברית, ~15.5KB, ללא frontmatter (כי לא הגיע מחן).

**העיבוד:**
1. [[yael-agent]] שכתבה לסגנון הצוות, עם placeholders של תמונות.
2. [[yuval-agent]] ייצר 2 תמונות: hero dashboard + automation workflow.
3. ראובן שילב ב-[[output-crm-explainer]].

**הערה ארכיטקטונית:** מקרה הזה מראה שהזרימה תומכת גם בקלט "ידני" מהמשתמש, לא רק מחן. שם הקובץ בעברית - `מאמר לדוגמא.txt` - עבד למרות האזהרה על עברית בנתיבים, כי זה היה קלט מהמשתמש ולא יצירה אוטומטית של סוכן.

## Open Questions
- האם צריך לתעד פורמט מינימלי לקבצי קלט ידני? כרגע לא חובה frontmatter.
- האם יעל צריכה לזהות בעצמה שאין מקור (אין frontmatter) ולהתאים את הטיפול?

## Session Log

### 2026-05-26 — בריף המאמר נכלל ב-vault [shipped]
- **What was done:** תיעוד הקלט הידני והזרימה דרך יעל + יובל.
- **Decisions:** סווג כ-project. שמירה בעברית בשם המקור היא חריגה מודעת - לא לחקות בקבצים אוטומטיים.
- **Notes / Caveats:** המקור הוא תוכן של המשתמש (לא חן), אז אין URL מקורי.
- **Related:** [[yael-agent]], [[yuval-agent]], [[output-crm-explainer]]
