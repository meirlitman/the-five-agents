# Skill: Systematic Debugging

## Overview
סקיל לדיבאג שיטתי ומעמיק — מופעל בכל מפגש עם באג, כשל בדיקות, או התנהגות בלתי צפויה, **לפני** הצעת פתרונות. כולל מתודולוגיות מתקדמות: root-cause tracing, defense-in-depth, condition-based waiting, ומציאת "מזהמי" מצב. הסקיל העשיר ביותר בקבצי עזר בחבילה. רלוונטי לכל חבר צוות.

## Open Questions
- none

## Session Log

### 2026-05-13 — תיעוד סקיל כחלק מ-vault ראשוני [wip]
- **What was done:** מיפוי הסקיל
- **Decisions:** משויך לכל הצוות — כל אחד עשוי להתמודד עם באגים
- **Notes / Caveats:** הסקיל הכי עשיר בקבצים — 10 קבצים כולל CREATION-LOG וסקריפטים
- **Related:** [[skill-verification-before-completion]], [[skill-test-driven-development]]

## פרטי הסקיל

| שדה | ערך |
|-----|-----|
| **נתיב** | `.claude/skills/systematic-debugging/` |
| **קובץ ראשי** | `SKILL.md` |
| **משויך ל** | כל הצוות |
| **מקור** | [obra/superpowers](https://github.com/obra/superpowers) |
| **מתי להפעיל** | בכל מפגש עם באג או כשל |

## קבצים בסקיל

| קובץ | תיאור |
|------|--------|
| `SKILL.md` | הוראות הסקיל |
| `CREATION-LOG.md` | היסטוריית יצירת הסקיל |
| `root-cause-tracing.md` | מתודולוגיית מעקב לשורש הבעיה |
| `defense-in-depth.md` | אסטרטגיית הגנה רב-שכבתית |
| `condition-based-waiting.md` | המתנה מבוססת-תנאי |
| `condition-based-waiting-example.ts` | דוגמת TypeScript |
| `find-polluter.sh` | סקריפט לאיתור מזהם מצב |
| `test-academic.md` | דפוסי בדיקה אקדמיים |
| `test-pressure-1/2/3.md` | תרחישי לחץ לבדיקה |

## קבצים קשורים

- [[skill-test-driven-development]] — TDD כאמצעי מניעה
- [[skill-verification-before-completion]] — אימות לאחר תיקון
- [[skill-receiving-code-review]] — ביקורת שלעיתים מגלה באגים
