# Skill: Requesting Code Review

## Overview
סקיל לבקשה ותיאום ביקורת קוד — מופעל בסיום משימות, לאחר יישום פיצ'רים גדולים, או לפני merge כדי לאמת שהעבודה עומדת בדרישות. כולל קובץ `code-reviewer.md` עם הנחיות לסוקר. ראובן משתמש בו לפני שחרור כל תוצר.

## Open Questions
- none

## Session Log

### 2026-05-13 — תיעוד סקיל כחלק מ-vault ראשוני [wip]
- **What was done:** מיפוי הסקיל
- **Decisions:** משויך בעיקר לראובן — הוא מתאם ביקורות לפני שחרורים
- **Notes / Caveats:** כולל פרומפט מוכן לסוקר (code-reviewer.md)
- **Related:** [[skill-receiving-code-review]], [[skill-finishing-a-development-branch]]

## פרטי הסקיל

| שדה | ערך |
|-----|-----|
| **נתיב** | `.claude/skills/requesting-code-review/` |
| **קובץ ראשי** | `SKILL.md` |
| **משויך ל** | ראובן (ניהול איכות) |
| **מקור** | [obra/superpowers](https://github.com/obra/superpowers) |
| **מתי להפעיל** | בסיום משימות לפני merge |

## קבצים בסקיל

| קובץ | תיאור |
|------|--------|
| `SKILL.md` | הוראות הסקיל |
| `code-reviewer.md` | פרומפט מוכן לסוקר הקוד |

## קבצים קשורים

- [[skill-receiving-code-review]] — הצד המקבל של הביקורת
- [[skill-finishing-a-development-branch]] — שלב הסיום שבא אחרי
- [[skill-verification-before-completion]] — אימות קודם לביקורת
