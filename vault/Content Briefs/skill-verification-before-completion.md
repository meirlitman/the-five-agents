# Skill: Verification Before Completion

## Overview
סקיל אימות לפני הכרזת השלמה — מופעל **לפני** כל טענה שעבודה הושלמה, תוקנה, או עוברת בדיקות. מחייב הרצת פקודות אימות בפועל ואישור הפלט לפני הצהרת הצלחה. עקרון היסוד: "ראיות לפני טענות". אנטי-פטרן נפוץ שהסקיל נלחם בו: הצהרת הצלחה ללא הרצה בפועל. חובה על כל הצוות.

## Open Questions
- none

## Session Log

### 2026-05-13 — תיעוד סקיל כחלק מ-vault ראשוני [wip]
- **What was done:** מיפוי הסקיל
- **Decisions:** משויך לכל הצוות — חובה על כולם לפני הכרזת סיום
- **Notes / Caveats:** הסקיל הכי "משמעתי" בחבילה — מונע תביעות שקריות
- **Related:** [[skill-systematic-debugging]], [[skill-finishing-a-development-branch]]

## פרטי הסקיל

| שדה | ערך |
|-----|-----|
| **נתיב** | `.claude/skills/verification-before-completion/` |
| **קובץ ראשי** | `SKILL.md` |
| **משויך ל** | כל הצוות (חובה) |
| **מקור** | [obra/superpowers](https://github.com/obra/superpowers) |
| **מתי להפעיל** | לפני כל הכרזת הצלחה/השלמה |

## קבצים קשורים

- [[skill-systematic-debugging]] — מה לעשות כשהאימות נכשל
- [[skill-finishing-a-development-branch]] — לאחר האימות — סיום
- [[skill-requesting-code-review]] — אחרי אימות — ביקורת
- [[skill-test-driven-development]] — TDD כאמצעי אימות מובנה
