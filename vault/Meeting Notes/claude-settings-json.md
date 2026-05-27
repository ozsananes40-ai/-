---
name: claude-settings-json
description: תיעוד .claude/settings.json - הגדרות פרויקט שנדחפות ל-git
metadata:
  type: project
---

# .claude/settings.json

## Overview

קובץ ההגדרות הציבורי של הפרויקט שנדחף ל-git. נכון לעכשיו (2026-05-26) הוא כולל:

- **`extraKnownMarketplaces`** — רישום של `claude-plugins-official` כ-marketplace ממקור github (`anthropics/claude-plugins-official`).
- **`enabledPlugins`** — `skill-creator@claude-plugins-official: true` (הסקיל המובנה ליצירת סקילים מותקן ב-scope פרויקט).

הקובץ קצר במכוון - הוא רק הגדרות שכל מי שעובד על הפרויקט אמור לקבל. הרשאות אישיות יושבות ב-[[claude-settings-local-json]].

## Open Questions
- האם להפעיל גם plugins נוספים מה-marketplace? כרגע רק skill-creator.

## Session Log

### 2026-05-26 — תיעוד הקובץ ב-vault [shipped]
- **What was done:** תיעוד הקובץ.
- **Decisions:** סווג כ-project.
- **Notes / Caveats:** ההבחנה בין settings.json (משותף) ל-settings.local.json (אישי) חשובה - כל אחד צריך לעדכן את הקובץ הנכון.
- **Related:** [[claude-settings-local-json]], [[skills-overview]], [[claude-md]]
