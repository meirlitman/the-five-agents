# Skill: Brainstorming

## Overview
סקיל לסיעור מוחות יצירתי — מחייב הפעלה **לפני כל עבודה יצירתית** (פיצ'רים, קומפוננטות, פונקציונליות חדשה). מחקיר את כוונת המשתמש, דרישות ועיצוב לפני המימוש. כולל ויזואליה אינטראקטיבית דרך שרת Node.js מקומי. ייחודי בחבילת Superpowers בשל הרכיב הגרפי.

## Open Questions
- none

## Session Log

### 2026-05-13 — תיעוד סקיל כחלק מ-vault ראשוני [wip]
- **What was done:** מיפוי הסקיל לתוך vault הפרויקט
- **Decisions:** משויך בעיקר ליעל (תוכן) ויובל (עיצוב) — שניהם עובדים על רעיונות יצירתיים
- **Notes / Caveats:** הסקיל דורש Node.js פעיל לרכיב הויזואלי (scripts/server.cjs)
- **Related:** [[skill-using-superpowers]], [[claude-directory-structure]]

## פרטי הסקיל

| שדה | ערך |
|-----|-----|
| **נתיב** | `.claude/skills/brainstorming/` |
| **קובץ ראשי** | `SKILL.md` |
| **משויך ל** | יעל (תוכן), יובל (עיצוב גרפי) |
| **מקור** | [obra/superpowers](https://github.com/obra/superpowers) |
| **מתי להפעיל** | לפני כל עבודה יצירתית |

## קבצים בסקיל

| קובץ | תיאור |
|------|--------|
| `SKILL.md` | הוראות הסקיל הראשיות |
| `scripts/frame-template.html` | תבנית HTML לממשק הויזואלי |
| `scripts/helper.js` | פונקציות עזר לשרת |
| `scripts/server.cjs` | שרת Node.js לסיעור מוחות |
| `scripts/start-server.sh` | סקריפט הפעלת השרת |
| `scripts/stop-server.sh` | סקריפט עצירת השרת |
| `spec-document-reviewer-prompt.md` | פרומפט לסקירת מסמכי spec |
| `visual-companion.md` | הוראות לרכיב הויזואלי |

## קבצים קשורים

- [[skill-writing-plans]] — לאחר הסיעור, כותבים תוכנית
- [[skill-executing-plans]] — לאחר התוכנית, מבצעים
- [[skill-using-superpowers]] — מדריך כללי לשימוש בסקילים
