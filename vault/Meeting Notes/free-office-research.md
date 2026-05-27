# Free Office Suite — Research & Download

## Overview

מחקר ובחירה של חבילת אופיס חינמית למחשב של המשתמש (Windows 11). הנושא נפתח כשהמשתמש ביקש לאתר חבילת אופיס עם Word ו-Excel, עם דרישה מפורשת לאימות מקסימלי לפני הורדה (מקור רשמי, ביקורות, VirusTotal, CVE recent, סטטוס תחזוקה). חן ביצעה את המחקר ובחרה ב-**LibreOffice 26.2.3**. ראובן ביצע הורדה מאומתת אל `אופיס\` (בהתחלה תחת `five agents\`, הועבר לאחר מכן לפי בקשת המשתמש אל `C:\Users\ozsan\OneDrive\Desktop\קלוד קוד\אופיס\`). ה-SHA256 של ה-MSI אומת מול הקובץ הרשמי של The Document Foundation והתאים.

## Open Questions

- האם המשתמש יתקין בעצמו דרך double-click על ה-MSI (UAC + החלטה ידנית) או שירצה שראובן יציע פקודת התקנה שקטה? — לא הוחלט.
- האם להפעיל CTL/RTL ל-עברית בהגדרות LibreOffice לאחר ההתקנה? המשתמש לא ביקש זאת מפורשות.

## Session Log

### 2026-05-27 — first research + verified download + folder move [shipped]
- **What was done:**
  - חן ביצעה Memory check + 3 WebSearches + WebFetch על PCMag/TechRadar/All Things Open/LibreOffice security advisories.
  - השוואה בין LibreOffice / OnlyOffice Desktop / WPS Office Free — בחרה ב-LibreOffice 26.2.3.
  - דוח אימות מלא נשמר ב-`Content/2026-05-27-free-office-suite-verification.md`.
  - רשומה ב-`chen/Memory/searches.md`.
  - ראובן הציג סיכום למשתמש, קיבל אישור מפורש להורדה + אימות SHA256.
  - הורדת `LibreOffice_26.2.3_Win_x86-64.msi` (372,604,928 bytes ≈ 355 MB) מ-`download.documentfoundation.org` אל `אופיס\` הצליחה תוך ~240 שניות.
  - הורדת `.sha256` במקביל. אימות: SHA256 מחושב = SHA256 רשמי (`468d1fb3880af3bcddac002e9054155912c70b45d105bfa1c82036f33456133d`).
- **Decisions:**
  - LibreOffice ולא OnlyOffice/WPS — בעיקר בגלל קוד פתוח אמיתי (MPL 2.0), העדר פרסומות, חבילה כוללת (Writer + Calc + Impress), ותחזוקה אקטיבית של The Document Foundation. CVE-2026-4430 הטרי (heap overflow ב-OOXML, 6.5.2026) תוקן ב-26.2.3, מה שאישש את הבחירה בגרסה הזו.
  - אימות SHA256 התבצע אוטומטית בצד ראובן (PowerShell `Get-FileHash`). לא הורד GPG signature נפרד — SHA256 התקבל מאותו דומיין כמו ה-MSI ונחשב מספיק עבור use case לא-משימתי-קריטי.
  - ראובן **לא** הריץ את ה-installer. ההתקנה היא צעד משתמש (UAC).
  - בקשה נוספת מהמשתמש: להעביר את `אופיס\` רמה אחת למעלה. בוצע Move-Item מ-`קלוד קוד\five agents\אופיס\` אל `קלוד קוד\אופיס\`. ה-MSI וה-SHA256 שם.
- **Notes / Caveats:**
  - הנתיב היעד `אופיס\` עברי — PowerShell טיפל בזה בלי בעיות (Invoke-WebRequest + Get-FileHash עבדו עם הנתיב כפי שהוא).
  - חן הזכירה שתאימות docx/xlsx טובה אבל לא מושלמת למסמכים מורכבים עם MS Word — שווה לבדוק במסמך לדוגמה לפני שמסתמכים.
  - עברית/RTL ב-LibreOffice דורשת הפעלה ידנית: Tools → Options → Languages → CTL.
- **Related:** [[chen-agent]], [[chen-memory-searches]], [[claude-md]]
