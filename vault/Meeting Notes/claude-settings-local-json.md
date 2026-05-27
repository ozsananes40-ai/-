---
name: claude-settings-local-json
description: תיעוד .claude/settings.local.json - הרשאות מקומיות שלא נדחפות
metadata:
  type: project
---

# .claude/settings.local.json

## Overview

קובץ ההרשאות המקומי של הפרויקט. מכיל `permissions.allow` עם רשימת פקודות שאושרו על ידי המשתמש בסשנים קודמים - לדוגמה `Bash(claude plugin *)`, `PowerShell(claude plugin install skill-creator...)`, וכמה פקודות אד-הוק שאישרנו (xxd על מאמר לדוגמא, Get-ChildItem על תיקיית agents).

הקובץ הזה אישי, לא משותף - כל מי שמפעיל את Claude Code על הפרויקט ייתן הרשאות משלו.

## Open Questions
- האם להעביר חלק מההרשאות ל-[[claude-settings-json]] (משותף)? כרגע הגיוני להישאר אישיים - הם ספציפיים לסשן הפרסום הקודם.

## Session Log

### 2026-05-26 — תיעוד הקובץ ב-vault [shipped]
- **What was done:** תיעוד מבנה הקובץ.
- **Decisions:** סווג כ-project.
- **Notes / Caveats:** הקובץ מתעדכן אוטומטית כשהמשתמש מאשר פקודות חדשות.
- **Related:** [[claude-settings-json]], [[claude-md]]
