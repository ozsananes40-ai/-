---
name: output-crm-explainer
description: תוצר מוגמר - מאמר CRM לדוגמא (md + html + 2 תמונות)
metadata:
  type: project
---

# Output: מה זה CRM ולמה כל עסק צריך אותו

## Overview

הפרסום הסופי של [[crm-explainer-sample]]. שני קבצים ב-`Output/`:
- `Output/מאמר לדוגמא.md` (~14.6KB) - גרסת Markdown
- `Output/מאמר לדוגמא.html` (~17KB) - גרסת HTML עם RTL

**שתי התמונות של [[yuval-agent]]:**
1. `2026-05-26-crm-dashboard-hero.png` (1.33MB) - דאשבורד CRM נקי, כרטיסי לקוחות וקווי קישור, סגנון איזומטרי, פלטת לבן/כחול/כתום חמים. Hero image לפתיחת המאמר.
2. `2026-05-26-crm-automation-workflow.png` (1.04MB) - 5 צמתים על מסלול עקום: טופס ליד → וואטסאפ → קלנדר → חשבונית → לקוח מחייך. גוונים turquoise/סגול/קרם/כתום. לסעיף האוטומציות.

**הזרימה:** קלט ידני מהמשתמש → [[yael-agent]] → [[yuval-agent]] × 2 → ראובן שילב.

זה הפרסום הראשון שעבר את הזרימה - בלי [[chen-agent]], כי המקור היה מהמשתמש ולא מהרשת.

## Open Questions
- שם הקובץ ב-Output בעברית (`מאמר לדוגמא`) - האם לעבור ל-slug אנגלי גם כאן בעתיד, או להישאר עקבי עם שם המקור?

## Session Log

### 2026-05-26 — תיעוד הפרסום ב-vault [shipped]
- **What was done:** תועד הפלט - שני קבצים + שתי תמונות עם פרטי הפרומפט.
- **Decisions:** סווג כ-project.
- **Notes / Caveats:** ה-`.txt` הנלווה לכל תמונה כולל גם הקשר ("for Yael's article: ...") - מידע שימושי לאיתור הקשר עתידי.
- **Related:** [[crm-explainer-sample]], [[yael-agent]], [[yuval-agent]], [[yuval-outputs-as-reference]]
