# Skill: Writing Skills

## Overview
סקיל לאוטו-יצירה — מופעל כאשר רוצים ליצור סקילים חדשים, לערוך קיימים, או לאמת שסקיל עובד לפני deployment. כולל best practices של Anthropic, עקרונות שכנוע, קונבנציות גרפיזה, ומדריך בדיקות עם subagents. הסקיל שמאפשר לצוות לגדול ולהרחיב את יכולותיו. ראובן ויעל הם המשתמשים העיקריים.

## Open Questions
- none

## Session Log

### 2026-05-13 — תיעוד סקיל כחלק מ-vault ראשוני [wip]
- **What was done:** מיפוי הסקיל
- **Decisions:** משויך לראובן (יצירת סקילים תשתיתיים) ויעל (סקילי תוכן)
- **Notes / Caveats:** הסקיל המטא השני בחבילה (אחרי using-superpowers) — עוסק בהרחבה עצמית
- **Related:** [[skill-using-superpowers]], [[skill-brainstorming]]

## פרטי הסקיל

| שדה | ערך |
|-----|-----|
| **נתיב** | `.claude/skills/writing-skills/` |
| **קובץ ראשי** | `SKILL.md` |
| **משויך ל** | ראובן (תשתית), יעל (תוכן) |
| **מקור** | [obra/superpowers](https://github.com/obra/superpowers) |
| **מתי להפעיל** | ביצירה/עריכה/בדיקה של סקילים |

## קבצים בסקיל

| קובץ | תיאור |
|------|--------|
| `SKILL.md` | הוראות הסקיל |
| `anthropic-best-practices.md` | Best practices מ-Anthropic |
| `persuasion-principles.md` | עקרונות שכנוע בכתיבת סקילים |
| `graphviz-conventions.dot` | קונבנציות גרפיות |
| `render-graphs.js` | סקריפט רינדור גרפים |
| `testing-skills-with-subagents.md` | בדיקת סקילים עם subagents |
| `examples/CLAUDE_MD_TESTING.md` | דוגמת בדיקה ב-CLAUDE.md |

## קבצים קשורים

- [[skill-using-superpowers]] — מדריך שימוש בסקילים קיימים
- [[skill-obsidian-vault-workflow]] — דוגמה לסקיל שנוצר לפרויקט זה
- [[skill-brainstorming]] — לפני יצירת סקיל חדש — סיעור מוחות
