---
name: skills-overview
description: תיעוד תיקיית .claude/skills/ - מפת כל הסקילים בפרויקט
metadata:
  type: project
---

# Skills Overview (.claude/skills/)

## Overview

תיקיית `.claude/skills/` מכילה את כל הסקילים הזמינים לסוכני הפרויקט. נכון לעכשיו (2026-05-26) מותקנים:

**סקילים ייעודיים לפרויקט הזה:**
- [[skill-gpt-image-gen]] — מעטפת ל-OpenAI Images API ליצירת תמונות (בשימוש על ידי יובל).
- [[skill-obsidian-vault-workflow]] — ניהול ה-vault הזה.
- [[skill-obsidian-markdown]] — כתיבת Obsidian Flavored Markdown.
- [[skill-obsidian-bases]] — עבודה עם Obsidian Bases (.base files).

**Superpowers (סקילים גנריים שהותקנו מ-obra/superpowers v5.1.0):**
ראו פירוט ב-[[skills-superpowers]]:
- brainstorming, dispatching-parallel-agents, executing-plans
- finishing-a-development-branch, receiving-code-review, requesting-code-review
- subagent-driven-development, systematic-debugging, test-driven-development
- using-git-worktrees, using-superpowers, verification-before-completion
- writing-plans, writing-skills

## Open Questions
- כמה מסקילי ה-Superpowers באמת בשימוש בפרויקט הזה? חלק מהם (TDD, git-worktrees) פחות רלוונטיים לזרימת תוכן ויותר לפיתוח קוד.
- כדאי לבחון אם להוריד סקילים שלא בשימוש כדי להקטין רעש בקונטקסט של הסוכנים.

## Session Log

### 2026-05-26 — תיעוד הקובץ ב-vault [shipped]
- **What was done:** נכתבה תמונת-על של כל הסקילים הזמינים.
- **Decisions:** הפרדה בין סקילים ייעודיים לפרויקט לבין Superpowers הגנריים.
- **Notes / Caveats:** כל סקיל קיבל קובץ תיעוד נפרד; כאן רק מפה.
- **Related:** [[skill-gpt-image-gen]], [[skill-obsidian-vault-workflow]], [[skill-obsidian-markdown]], [[skill-obsidian-bases]], [[skills-superpowers]], [[claude-settings-json]]
