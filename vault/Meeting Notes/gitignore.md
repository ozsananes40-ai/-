---
name: gitignore
description: תיעוד .gitignore - דפוסי קבצים שלא נכנסים ל-git
metadata:
  type: project
---

# .gitignore

## Overview

הקובץ `.gitignore` בשורש מוציא מ-git שלוש קטגוריות:

1. **סודות** — `.env`, `.env.local`, `.env.*.local`. זה הקריטי שביותר; ראה [[env-file]].
2. **קבצי OS / IDE** — `.DS_Store`, `Thumbs.db`, `*.swp`, `.vscode/`, `.idea/`.
3. **לוגים** — `*.log`.

הקובץ נשאר רזה במכוון. תוצרים של הצוות (תמונות, מאמרים) **כן** נדחפים — `yuval/outputs/`, `Output/`, `Content/` כולם נכנסים ל-git כי הם תוצר עבודה ולא ארטיפקטים.

## Open Questions
- האם `response.json` בשורש (קובץ זמני שנוצר על ידי יובל) צריך להתווסף ל-gitignore? נכון לעכשיו הוא נדחף.
- כדאי לבדוק אם `.tmp/` (שמופיע ב-git status הראשוני) צריך להיכנס לכאן.

## Session Log

### 2026-05-26 — תיעוד הקובץ ב-vault [shipped]
- **What was done:** נכתב תיעוד של הקובץ.
- **Decisions:** סווג כ-project כי הוא מתעד החלטה ארכיטקטונית - מה כן ומה לא נדחף.
- **Notes / Caveats:** ייתכן שצריך להוסיף עוד דפוסים בעתיד (`response.json`, `.tmp/`).
- **Related:** [[env-example]], [[env-file]], [[response-json]]
