---
name: vault-bootstrap
description: בניית ה-vault הראשונית - תיעוד מסודר של כל קבצי הפרויקט
metadata:
  type: project
---

# Vault Bootstrap

## Overview

הסשן שבו ה-vault נבנה מאפס. המשתמש ביקש קובץ MD תיעודי לכל קובץ בפרויקט, עם wikilinks בין קבצים קשורים, וגם ביקש שה-[[skill-obsidian-vault-workflow]] ירוץ בתחילת כל סשן ופקודה.

**מה נבנה:**
- ארבע תיקיות סטנדרטיות תחת `vault/` (Meeting Notes, Content Briefs, Publishing Log, Brand Guidelines), כל אחת עם `_index.md`.
- 20 קבצי נושא שמתעדים את כל קבצי הפרויקט.
- עדכון [[claude-md]] עם הוראה להפעיל את הסקיל בתחילת כל סשן.

**עקרונות שהונחו:**
1. קובץ אחד לנושא, שם בלי תאריך.
2. כל קובץ עם Overview / Open Questions / Session Log + status tag.
3. כל קובץ מקושר ל-2-5 קבצים אחרים דרך `[[wikilinks]]`.
4. _index.md בכל תיקייה עם רשימה שטוחה לאיתור מהיר.

## Open Questions
- האם המבנה מספיק? המשתמש עשוי לרצות חלוקה אחרת (לדוגמה תיקייה ייעודית לסקילים, או לסוכנים).
- כדאי לשקול יצירת `.base` ראשון שמציג את כל קבצי `Meeting Notes/` כטבלה - יקל על ניווט.
- המדריך של יעל ([[yael-style-guide]]) עדיין שלד - כשהמשתמש ימלא, יהיה צריך לחזור ולעדכן את ה-Overview.

## Session Log

### 2026-05-26 — בניית vault ראשונית [shipped]
- **What was done:**
  - מופה כל הפרויקט (5 קבצי שורש, 3 סוכנים, 4 סקילים ייעודיים + Superpowers, 14 תיקיות עבודה, 5 תמונות + prompts).
  - נוצרו 4 תיקיות תחת `vault/` עם `_index.md` בכל אחת.
  - נוצרו 20 קבצי נושא: [[claude-md]], [[env-example]], [[env-file]], [[gitignore]], [[response-json]], [[chen-agent]], [[yael-agent]], [[yuval-agent]], [[claude-settings-json]], [[claude-settings-local-json]], [[skills-overview]], [[skill-gpt-image-gen]], [[skill-obsidian-vault-workflow]], [[skill-obsidian-markdown]], [[skill-obsidian-bases]], [[skills-superpowers]], [[chen-memory-searches]], [[vaad-bayit-guide-israel]], [[crm-explainer-sample]], [[output-vaad-bayit-guide]], [[output-crm-explainer]], [[yael-style-guide]], [[yael-reference]], [[yuval-reference]], [[yuval-outputs-as-reference]] (סה"כ 25 נושאים).
  - עודכן `CLAUDE.md` בשורש כך שכל סשן יפעיל את [[skill-obsidian-vault-workflow]] מההתחלה.
- **Decisions:**
  - חלוקה לארבע תיקיות סטנדרטיות מהסקיל, גם אם פרויקט תוכן לא משתמש בכולן באותה דחיפות.
  - "Brand Guidelines" כולל גם את `yael/style-guide.md` (טקסט) וגם את ה-reference של יובל (ויזואלי) - שתי פנים של אותו מותג.
  - כל קובץ קיבל `## Open Questions` עם פתיחים אמיתיים, לא `- none` ריק - יקל על סשנים עתידיים.
- **Notes / Caveats:**
  - יש קישורים שצריכים תוכן עתידי (`yael-style-guide` כשלד; `yael-reference` ו-`yuval-reference` ריקים).
  - מבנה ה-frontmatter עוקב אחרי הסקיל של auto-memory (name/description/metadata.type) למרות שזה לא חובה בסקיל ה-vault עצמו - כך אפשר להפיק את ה-vault גם לזיכרון אישי בעתיד.
- **Related:** [[skill-obsidian-vault-workflow]], [[claude-md]], [[skills-overview]]
