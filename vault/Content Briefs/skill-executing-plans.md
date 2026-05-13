# Skill: Executing Plans

## Overview
סקיל לביצוע תוכניות יישום מפורטות — מופעל כאשר קיים מסמך תוכנית כתוב ורוצים לבצע אותו ב-session נפרד עם נקודות ביקורת. מבטיח שהיישום עוקב נאמנה אחר התוכנית, ומאפשר סקירה בין שלבים. ראובן משתמש בו לניהול הביצוע של משימות גדולות.

## Open Questions
- none

## Session Log

### 2026-05-13 — תיעוד סקיל כחלק מ-vault ראשוני [wip]
- **What was done:** מיפוי הסקיל
- **Decisions:** משויך לראובן (ניהול) + כל הצוות (ביצוע)
- **Notes / Caveats:** דורש מסמך תוכנית מוכן מראש (ממשק עם writing-plans)
- **Related:** [[skill-writing-plans]], [[skill-subagent-driven-development]]

## פרטי הסקיל

| שדה | ערך |
|-----|-----|
| **נתיב** | `.claude/skills/executing-plans/` |
| **קובץ ראשי** | `SKILL.md` |
| **משויך ל** | ראובן (ניהול), כל הצוות (ביצוע) |
| **מקור** | [obra/superpowers](https://github.com/obra/superpowers) |
| **מתי להפעיל** | לאחר כתיבת תוכנית, לפני יישום |

## קבצים קשורים

- [[skill-writing-plans]] — שלב הכתיבה שקודם לביצוע
- [[skill-subagent-driven-development]] — ביצוע עם סוכני-משנה
- [[skill-verification-before-completion]] — אימות לאחר ביצוע
- [[skill-finishing-a-development-branch]] — סיום לאחר ביצוע מוצלח
