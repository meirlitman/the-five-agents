---
tags: [agents, chen, research, sub-agent]
aliases: ["חן", "Chen", "חוקרת הרשת"]
---

# Chen — Research Agent

## Overview
חן היא ה-sub-agent השלישי של הצוות (אחרי יעל ויובל) ו-pipeline-entry-point למחקר חיצוני. תפקידה: לקבל מראובן בקשה חופשית (נושא / מילות מפתח / סוג מאמר), לבדוק זיכרון חיפושים מתמשך, לבצע `WebSearch + WebFetch`, לסנן לפי קריטריוני איכות, ולהפיק קובץ ב-`Content/` עם frontmatter של המקור + שורת ציטוט גלויה. חן לא מפעילה סוכנים אחרים — היא מסיימת ומדווחת לראובן, וראובן מחליט אם להמשיך ל-pipeline המלא (יעל → יובל → Output).

הסיבה להוספתה: עד עכשיו ראובן יכול היה רק לקבל קובץ Content מהמשתמש או להסתמך על ידע פנימי של המודל. חן מבטלת את שני המגבלות — מידע עכשווי, מקורות מאומתים, ללא הזיות.

## Open Questions
- ההבחנה בין "רק מצא" ל"מצא ושכתב" נשענת על parsing של ראובן את הבקשה. אם זה לא מספיק חד באופן עקבי — האם להוסיף flag מפורש מהמשתמש?
- היוריסטיקת "30 יום" בזיכרון חן: שרירותית. כדאי לכייל לפי שימוש בפועל (אולי 7 ימים לנושאים דינמיים, 90 ימים לevergreen).
- האם להוסיף שדה `topic_type: dynamic | evergreen` ב-frontmatter של searches.md entry כדי שחן תוכל לסנן יותר חכם?

## Architecture

```
משתמש → ראובן → חן (WebSearch/WebFetch)
                  ↓
             Content/<date>-<slug>.md  (frontmatter + ציטוט + תוכן)
             chen/Memory/searches.md   (entry)
                  ↓
              דיווח לראובן
                  ↓
        ראובן מחליט: עצור / המשך ל-יעל
```

**עיקרון מפתח:** הסוכנים לא מפעילים זה את זה. ראובן הוא ה-orchestrator הבלעדי. זה תואם לדפוס יעל ↔ יובל הקיים.

## Files

- [`.claude/agents/chen.md`](.claude/agents/chen.md) — הגדרת הסוכן (frontmatter עם 7 tools, גוף בעברית עם 7-step flow)
- [`chen/Memory/searches.md`](chen/Memory/searches.md) — seed עם הסבר פורמט; entries יצטברו עם השימוש
- [`CLAUDE.md`](CLAUDE.md) — עודכן עם folder structure, סקשן ניתוב לחן, ו-flow משולב

## Source File Format (חוזה עם יעל)

```markdown
---
source_url: https://...
source_title: "..."
source_author: "..."
fetched_at: YYYY-MM-DD HH:MM
language: he | en
---

> **מקור:** [<title>](<url>) — נדלה ב-YYYY-MM-DD

# <כותרת>

<תוכן...>
```

**למה דו־שכבתי:** ה-frontmatter עמיד לשכתוב של יעל (גם אם תוריד את הציטוט הגלוי כ"פרסומת של המחבר", הקרדיט נשמר ב-metadata). שורת הציטוט הגלויה מוסיפה ניראות אנושית למי שקורא את הקובץ ידנית.

## Memory Format (פנימי לחן)

```
## YYYY-MM-DD HH:MM | <נושא>
**מילות מפתח:** ...
**שאילתות שנעשו:** "...", "..."
**מקורות שנמצאו:** [כותרת](URL) - ⭐⭐⭐⭐ - הערה
**נבחר:** ...
**קובץ ב-Content:** <filename>.md
---
```

חן מריצה `Grep -i <keyword> chen/Memory/searches.md` לפני כל חיפוש. אם יש hit לא-דינמי מ-30 הימים האחרונים — שואלת את ראובן אם לעבוד על הקיים.

## Session Log

### 2026-05-13 — יצירה ראשונית של חן [shipped]
- **What was done:** נוצרו `.claude/agents/chen.md`, `chen/Memory/searches.md`, ו-CLAUDE.md עודכן (folders + routing + flow). vault: עודכן team-roster, נוצר קובץ topic זה.
- **Decisions:**
  - כלים: WebSearch, WebFetch, Read, Write, Edit, Glob, Grep. **בלי Bash** (הוראה מפורשת מהמשתמש).
  - `name` ב-frontmatter בעברית ("חן") תואם ליעל/יובל; שם הקובץ באנגלית (`chen.md`).
  - Content file format דו־שכבתי (frontmatter + ציטוט גלוי) — תשובת המשתמש בשאלת clarification.
  - חן לא מפעילה את יעל ישירות; ראובן מנתב.
- **Notes / Caveats:**
  - לא נבדק בפועל עם בקשת WebSearch אמיתית — verification יקרה בסשן הבא של המשתמש.
  - חן רואה את ה-Memory רק עם Grep — אם הקובץ יהיה גדול מאוד (אלפי entries), כדאי לשקול ארכוב לפי חודש.
- **Related:** [[team-roster]], [[claude-md]]
