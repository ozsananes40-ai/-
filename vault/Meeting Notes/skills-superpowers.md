---
name: skills-superpowers
description: תיעוד סקילי Superpowers (obra/superpowers v5.1.0) המותקנים בפרויקט
metadata:
  type: project
---

# Superpowers Skills (obra/superpowers v5.1.0)

## Overview

חבילת הסקילים `superpowers` (v5.1.0) הותקנה מ-`obra/superpowers` ב-commit `7937d12`. אלה סקילים גנריים לפיתוח תוכנה, חלקם רלוונטיים גם לזרימת תוכן.

**הסקילים המותקנים תחת `.claude/skills/`:**

| Skill | תפקיד | רלוונטיות לפרויקט |
|---|---|---|
| `brainstorming` | חקירת כוונה ודרישות לפני יצירה | ✅ גבוהה - לכל פיצ'ר חדש |
| `dispatching-parallel-agents` | הפעלת סוכנים במקביל | ✅ בינונית - כשראובן צריך כמה סוכנים יחד |
| `executing-plans` | ביצוע תוכנית כתובה | ⚠️ פחות - לא הרבה תוכניות פורמליות |
| `finishing-a-development-branch` | סיום branch (merge/PR) | ⚠️ לפעמים - יותר רלוונטי לפיתוח |
| `receiving-code-review` | קבלת ביקורת קוד | ⚠️ לפעמים |
| `requesting-code-review` | בקשת ביקורת קוד | ⚠️ לפעמים |
| `subagent-driven-development` | פיתוח דרך subagents | ✅ - הליבה של הפרויקט |
| `systematic-debugging` | דיבאג מסודר | ✅ - לתקלות בסקילים |
| `test-driven-development` | TDD | ⚠️ פחות - תוכן לא ממש בעל unit tests |
| `using-git-worktrees` | worktrees לעבודה מבודדת | ⚠️ פחות |
| `using-superpowers` | מטא-סקיל - איך להשתמש בסקילים | ✅ גבוהה - נטען בתחילת סשן |
| `verification-before-completion` | אימות לפני "סיימתי" | ✅ גבוהה - יובל מאמת ls -la, יעל מאמתת קבצים |
| `writing-plans` | כתיבת תוכניות | ✅ למשימות מורכבות |
| `writing-skills` | כתיבת סקילים חדשים | ✅ - נוצרו כבר 3 סקילי obsidian |

## Open Questions
- האם להוריד סקילים שלא בשימוש בכלל בפרויקט הזה (TDD, git-worktrees, finishing-branch) כדי להקטין רעש בקונטקסט?
- מה ה-trade-off בין "הכל זמין" לבין "נקי ותכליתי"?

## Session Log

### 2026-05-26 — תיעוד מפת הסקילים [shipped]
- **What was done:** מיפוי של כל סקילי Superpowers עם דירוג רלוונטיות.
- **Decisions:** השארה של כל הסקילים בינתיים - לא מורידים בלי החלטה מפורשת.
- **Notes / Caveats:** המקור הוא `obra/superpowers v5.1.0` (ראו commit 7937d12).
- **Related:** [[skills-overview]], [[skill-gpt-image-gen]], [[skill-obsidian-vault-workflow]]
