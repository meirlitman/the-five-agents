# Environment Configuration (.env / .env.example)

## Overview
שני קבצים המגדירים את משתני הסביבה של הפרויקט. `.env` הוא הקובץ הפעיל עם ערכים אמיתיים (לא מועלה ל-git במצב תקין — אך הועלה כאן בכוונה). `.env.example` הוא תבנית לשיתוף עם הצוות, עם ערכי placeholder. שניהם מכילים: `ANTHROPIC_API_KEY`, `DEFAULT_MODEL`, `OUTPUT_DIR`, ו-`LOG_LEVEL`.

## Open Questions
- האם להוסיף `.env` ל-`.gitignore` בעתיד (כרגע הוא commit-ראוי לפי הוראת המשתמש)
- האם נדרשים משתני סביבה נוספים כשהפרויקט יתפתח (API keys לשירותים נוספים?)

## Session Log

### 2026-05-13 — יצירת קבצי env ראשוניים [shipped]
- **What was done:** נוצרו `.env` ו-`.env.example` עם 4 משתני סביבה בסיסיים
- **Decisions:** הוחלט לכלול את `.env` עצמו ב-git לפי בקשת המשתמש (לא רק `.env.example`)
- **Notes / Caveats:** `ANTHROPIC_API_KEY` ריק ב-`.env` — יש למלא ידנית
- **Related:** [[claude-md]]

## פרטי הקבצים

| שדה | `.env` | `.env.example` |
|-----|--------|----------------|
| **נתיב** | `.env` | `.env.example` |
| **משויך ל** | ראובן (תשתית) | כל הצוות |
| **סוג** | קונפיגורציה פעילה | תבנית לדוגמה |
| **נטען ע"י** | Runtime / Claude Code | עיון ידני |

## משתני הסביבה

| משתנה | ערך ברירת מחדל | תיאור |
|--------|----------------|--------|
| `ANTHROPIC_API_KEY` | (ריק) | מפתח API לשירות Claude |
| `DEFAULT_MODEL` | `claude-opus-4-7` | מודל ברירת מחדל לסוכנים |
| `OUTPUT_DIR` | `./output` | תיקיית פלט |
| `LOG_LEVEL` | `info` | רמת לוגינג |

## קבצים קשורים

- [[claude-md]] — הנחיות ראובן שמשתמשות בהגדרות אלו
- [[claude-directory-structure]] — .claude/ שמכיל את הסוכנים שישתמשו ב-API key
