# תיקיית .claude/ — מבנה ותת-תיקיות

## Overview
תיקיית `.claude/` היא ה"מטה-תיקייה" של הפרויקט — מכילה את הגדרות הסוכנים, הפקודות המותאמות, והסקילים. כרגע מכילה שלוש תת-תיקיות עיקריות: `agents/`, `commands/`, `skills/`. כל תת-תיקייה מכילה `.gitkeep` (placeholder) ואחריה הסקילים שהותקנו מ-Superpowers. זו הבסיס האדריכלי שעליו יבנה כל הצוות.

## Open Questions
- מתי יתאכלסו `agents/` ו-`commands/` בתוכן אמיתי?
- האם נדרש קובץ `settings.json` ב-.claude/ לקונפיגורציה נוספת?

## Session Log

### 2026-05-13 — אתחול מבנה .claude/ [shipped]
- **What was done:** נוצרו תת-תיקיות agents/, commands/, skills/ עם .gitkeep placeholders
- **Decisions:** המבנה הראשוני מבוסס על קונבנציית Claude Code הסטנדרטית
- **Notes / Caveats:** כל שלוש התיקיות ריקות מתוכן פונקציונלי
- **Related:** [[skill-using-superpowers]]

### 2026-05-13 — התקנת Superpowers ב-skills/ [shipped]
- **What was done:** הועתקו 14 סקילים מ-https://github.com/obra/superpowers לתוך .claude/skills/
- **Decisions:** התקנה ידנית (clone + copy) בגלל שמערכת /plugin לא זמינה
- **Notes / Caveats:** לא קיימים commands/ ו-agents/ ב-Superpowers, רק skills/
- **Related:** [[skill-using-superpowers]], [[skill-brainstorming]], [[skill-systematic-debugging]]

## פרטי תת-התיקיות

### agents/
| שדה | ערך |
|-----|-----|
| **נתיב** | `.claude/agents/` |
| **משויך ל** | ראובן (ניהול) — תכיל הגדרות יעל, יובל, חן |
| **סטטוס** | ריק (רק .gitkeep) |

### commands/
| שדה | ערך |
|-----|-----|
| **נתיב** | `.claude/commands/` |
| **משויך ל** | ראובן (ניהול) — פקודות slash מותאמות |
| **סטטוס** | ריק (רק .gitkeep) |

### skills/
| שדה | ערך |
|-----|-----|
| **נתיב** | `.claude/skills/` |
| **משויך ל** | כל הצוות — יכולות משותפות |
| **סטטוס** | מכיל 14 סקילים מ-Superpowers + obsidian-vault-workflow |

## קבצים קשורים

- [[claude-md]] — CLAUDE.md שמפנה למבנה זה
- [[env-configuration]] — .env שמספק קונפיגורציה לסוכנים
- [[skill-using-superpowers]] — המדריך לשימוש בסקילים
- [[skill-obsidian-vault-workflow]] — הסקיל שמנהל את ה-vault הזה
