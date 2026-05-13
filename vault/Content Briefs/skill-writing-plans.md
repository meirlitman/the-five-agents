# Skill: Writing Plans

## Overview
סקיל לכתיבת תוכניות יישום — מופעל כאשר יש spec או דרישות למשימה מרובת-שלבים, **לפני** כל נגיעה בקוד. מייצר מסמכי תוכנית מובנים שמשמשים אחר כך את executing-plans ו-subagent-driven-development. כולל פרומפט לסקירת מסמכי התוכנית. יעל ישתמש בו לתכנון תוכן, ראובן לתכנון פיתוח.

## Open Questions
- none

## Session Log

### 2026-05-13 — תיעוד סקיל כחלק מ-vault ראשוני [wip]
- **What was done:** מיפוי הסקיל
- **Decisions:** משויך לראובן (פיתוח) ויעל (תוכן) — שניהם מתכננים לפני ביצוע
- **Notes / Caveats:** כולל plan-document-reviewer-prompt.md — פרומפט לסוקר התוכנית
- **Related:** [[skill-executing-plans]], [[skill-brainstorming]]

## פרטי הסקיל

| שדה | ערך |
|-----|-----|
| **נתיב** | `.claude/skills/writing-plans/` |
| **קובץ ראשי** | `SKILL.md` |
| **משויך ל** | ראובן (תכנון פיתוח), יעל (תכנון תוכן) |
| **מקור** | [obra/superpowers](https://github.com/obra/superpowers) |
| **מתי להפעיל** | לפני כל משימה מרובת-שלבים |

## קבצים בסקיל

| קובץ | תיאור |
|------|--------|
| `SKILL.md` | הוראות הסקיל |
| `plan-document-reviewer-prompt.md` | פרומפט לסקירת מסמך התוכנית |

## קבצים קשורים

- [[skill-brainstorming]] — לעיתים קודם לכתיבת התוכנית
- [[skill-executing-plans]] — ביצוע התוכנית שנוצרה
- [[skill-subagent-driven-development]] — ביצוע עם סוכנים
