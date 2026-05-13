# Skill: Obsidian Vault Workflow

## Overview
סקיל לניהול vault הזיכרון ארוך-הטווח של הפרויקט — מופעל בתחילת **כל משימה** (לקריאת הקשר קיים) ובסוף כל משימה (לעדכון vault). הוא הזיכרון המתמשך של AI Content OS. מבנה: תיקייה אחת לנושא, קובץ אחד לנושא — עם Overview, Open Questions ו-Session Log. שונה מ-using-superpowers: הוא עוסק בתיעוד, לא בניווט סקילים.

## Open Questions
- האם להוסיף vault/Brand Guidelines/ ו-vault/Publishing Log/ עם תוכן מהפרויקט?
- האם ראובן צריך vault/Brand Guidelines/ לזהות הצוות?

## Session Log

### 2026-05-13 — התקנה ראשונה ויצירת vault [shipped]
- **What was done:** נמצא הסקיל ב-.claude/skills/ של הפרויקט הראשי; נוצר vault/ עם 20 קבצי תיעוד לכל קבצי הפרויקט
- **Decisions:** vault מאורגן ב-Meeting Notes/ (תשתית) ו-Content Briefs/ (סקילים); הסקיל נוסף לדרישות CLAUDE.md
- **Notes / Caveats:** הסקיל קיים ב-.claude/ של הפרויקט הראשי (לא ב-worktree) — ייתכן שיש לסנכרן
- **Related:** [[skill-using-superpowers]], [[claude-directory-structure]]

## פרטי הסקיל

| שדה | ערך |
|-----|-----|
| **נתיב** | `.claude/skills/obsidian-vault-workflow/` (בפרויקט הראשי) |
| **קובץ ראשי** | `SKILL.md` |
| **משויך ל** | ראובן (ניהול זיכרון הצוות) |
| **מקור** | פרויקט מותאם (לא מ-Superpowers) |
| **מתי להפעיל** | בתחילת וסוף כל משימה |

## מבנה ה-vault שנוצר

```
vault/
├── Meeting Notes/
│   ├── _index.md
│   ├── claude-md.md
│   ├── env-configuration.md
│   └── claude-directory-structure.md
└── Content Briefs/
    ├── _index.md
    └── skill-*.md (15 סקילים)
```

## קבצים קשורים

- [[skill-using-superpowers]] — סקיל שגם מופעל בתחילת סשן
- [[claude-md]] — CLAUDE.md שמחייב הפעלת הסקיל
- [[claude-directory-structure]] — .claude/ שמכיל את הסקיל
