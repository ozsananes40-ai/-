# Meeting Notes — Index

תיעוד פר-קובץ של תשתית הפרויקט: הוראות לראובן, הגדרות סוכנים, סקילים, הגדרות, וקבצי קונפיגורציה. גם פוסט-מורטמים של סשנים ארכיטקטוניים.

## Topics

### תשתית פרויקט (קבצי שורש)
- [[claude-md]] — הוראות הניהול של ראובן, ההגדרה של הפרויקט והצוות
- [[env-example]] — תבנית משתני סביבה (API keys לכל הסוכנים)
- [[env-file]] — קובץ הסודות המקומי שלא נדחף ל-git
- [[gitignore]] — דפוסי קבצים שלא נכנסים ל-git
- [[response-json]] — קובץ זמני מקריאת API של יובל (לא חלק מהזרימה הקבועה)

### סוכנים (.claude/agents/)
- [[chen-agent]] — הגדרת חן, חוקרת הרשת
- [[yael-agent]] — הגדרת יעל, כותבת התוכן
- [[yuval-agent]] — הגדרת יובל, מעצב התמונות

### הגדרות (.claude/)
- [[claude-settings-json]] — settings.json הגלובלי של הפרויקט (plugins)
- [[claude-settings-local-json]] — settings.local.json (הרשאות שאושרו)

### Skills (.claude/skills/)
- [[skills-overview]] — תמונת-על של כל הסקילים המותקנים בפרויקט
- [[skill-gpt-image-gen]] — הסקיל של יובל ליצירת תמונות מול gpt-image-2
- [[skill-obsidian-vault-workflow]] — הסקיל הזה: ניהול ה-vault
- [[skill-obsidian-markdown]] — סקיל לכתיבת Obsidian Flavored Markdown
- [[skill-obsidian-bases]] — סקיל לעבודה עם Obsidian Bases
- [[skills-superpowers]] — שאר סקילי Superpowers (brainstorming, TDD, וכו')

### זיכרון של סוכנים
- [[chen-memory-searches]] — יומן החיפושים של חן (cache למניעת חיפושים כפולים)

### סשנים ארכיטקטוניים
- [[vault-bootstrap]] — בניית ה-vault הראשונית (הסשן הזה)
- [[free-office-research]] — מחקר חן + הורדה מאומתת של LibreOffice 26.2.3 לתיקיית `אופיס\`
