---
name: output-vaad-bayit-guide
description: תוצר מוגמר - מדריך ועד בית (md + html + 3 תמונות)
metadata:
  type: project
---

# Output: מדריך ועד בית בישראל

## Overview

הפרסום הסופי של [[vaad-bayit-guide-israel]]. שני קבצים ב-`Output/`:
- `Output/2026-05-26-vaad-bayit-guide-israel.md` (~10.9KB) - גרסת Markdown עם `![alt](../yuval/outputs/<file>.png)`
- `Output/2026-05-26-vaad-bayit-guide-israel.html` (~13.6KB) - גרסת HTML עם RTL, פונט מערכת, תגי `<img>`

**שלוש התמונות של [[yuval-agent]]:**
1. `2026-05-26-vaad-bayit-01-building.png` (1.58MB) - בניין מגורים ישראלי 4-5 קומות עם דיירים, חצר, סגנון flat illustration עם solar dudim על הגג.
2. `2026-05-26-vaad-bayit-02-justice.png` (1.31MB) - מאזני צדק זהובים מול בניין עם חלונות מוארים. סמלי לרזולוציית סכסוכים.
3. `2026-05-26-vaad-bayit-03-section.png` (1.77MB) - חתך איזומטרי של בניין עם הפרדה צבעונית בין דירות פרטיות (חרדל), שטחים משותפים (תכלת) ואלמנטים מבניים (אפור).

**הזרימה המלאה:** [[chen-agent]] → [[yael-agent]] → [[yuval-agent]] × 3 → ראובן שילב.

## Open Questions
- האם הגרסאות הזמניות ב-`yael/2026-05-26-vaad-bayit-guide-israel.md/html` עם ה-placeholders עוד נחוצות, או שאפשר למחוק כעת שהשילוב סופי?

## Session Log

### 2026-05-26 — תיעוד הפרסום ב-vault [shipped]
- **What was done:** תועד הפלט הסופי - שני קבצים + שלוש תמונות עם פרטים.
- **Decisions:** סווג כ-project. הקובץ הזה הוא "post-mortem" של הפרסום.
- **Notes / Caveats:** התמונות עצמן ב-`yuval/outputs/` עם `.txt` נלווה (ה-prompt באנגלית).
- **Related:** [[vaad-bayit-guide-israel]], [[yael-agent]], [[yuval-agent]], [[yuval-outputs-as-reference]], [[chen-agent]]
