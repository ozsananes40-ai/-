---
name: skill-obsidian-markdown
description: תיעוד הסקיל obsidian-markdown - כתיבת Obsidian Flavored Markdown
metadata:
  type: project
---

# Skill: obsidian-markdown

## Overview

סקיל לכתיבה ועריכה של Obsidian Flavored Markdown - הסינטקס המורחב של Obsidian. נמצא ב-`.claude/skills/obsidian-markdown/`. כולל wikilinks (`[[note]]`), embeds (`![[note]]`), callouts (`> [!info]`), properties (frontmatter YAML), tags, ועוד.

הסקיל הזה משלים את [[skill-obsidian-vault-workflow]] - בעוד שהאחרון מגדיר את הפרוטוקול והמבנה, זה נותן את הסינטקס המעמיק לכתיבת התוכן בתוך הקבצים.

## Open Questions
- האם להשתמש ב-callouts (`> [!note]`, `> [!warning]`) בתיעוד הקבצים? כרגע פחות נדרש - הקבצים פשוטים יחסית.

## Session Log

### 2026-05-26 — תיעוד הסקיל ב-vault [shipped]
- **What was done:** תיעוד קצר של הסקיל.
- **Decisions:** סווג כ-project. תיעוד מינימלי כי הסקיל עצמו לא בשימוש פעיל עדיין.
- **Notes / Caveats:** ייתכן שיהיה רלוונטי יותר כשהמשתמש יעבוד מול ה-vault דרך אפליקציית Obsidian עצמה ולא רק דרך Claude Code.
- **Related:** [[skill-obsidian-vault-workflow]], [[skill-obsidian-bases]], [[skills-overview]]
