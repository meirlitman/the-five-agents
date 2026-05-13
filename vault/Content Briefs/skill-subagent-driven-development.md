# Skill: Subagent-Driven Development

## Overview
סקיל לפיתוח מונחה סוכני-משנה — מופעל לביצוע תוכניות יישום עם משימות עצמאיות ב-session הנוכחי. שונה מ-dispatching-parallel-agents בכך שהוא מנהל את הסוכנים ישירות (לא מפנה לsession חדש). כולל פרומפטים מוכנים: implementer, spec-reviewer, ו-code-quality-reviewer. ראובן משתמש בו לתיאום פיתוח מורכב.

## Open Questions
- none

## Session Log

### 2026-05-13 — תיעוד סקיל כחלק מ-vault ראשוני [wip]
- **What was done:** מיפוי הסקיל
- **Decisions:** משויך לראובן — אורקסטרציה של פיתוח מורכב
- **Notes / Caveats:** כולל 3 פרומפטים מובנים לתפקידים שונים
- **Related:** [[skill-dispatching-parallel-agents]], [[skill-executing-plans]]

## פרטי הסקיל

| שדה | ערך |
|-----|-----|
| **נתיב** | `.claude/skills/subagent-driven-development/` |
| **קובץ ראשי** | `SKILL.md` |
| **משויך ל** | ראובן (אורקסטרציה) |
| **מקור** | [obra/superpowers](https://github.com/obra/superpowers) |
| **מתי להפעיל** | ביצוע תוכניות עם משימות עצמאיות |

## קבצים בסקיל

| קובץ | תיאור |
|------|--------|
| `SKILL.md` | הוראות הסקיל |
| `implementer-prompt.md` | פרומפט לסוכן המיישם |
| `spec-reviewer-prompt.md` | פרומפט לסוקר ה-spec |
| `code-quality-reviewer-prompt.md` | פרומפט לסוקר איכות הקוד |

## קבצים קשורים

- [[skill-dispatching-parallel-agents]] — הפצה לסוכנים חיצוניים (שונה)
- [[skill-executing-plans]] — ביצוע תוכניות (משלים)
- [[skill-writing-plans]] — יצירת התוכנית שמבוצעת
