# Skill: gpt-image-gen

מעטפת לקריאת OpenAI Images API עם המודל `gpt-image-2`.

---

## שימוש

קבל prompt ו-output path, שלח לAPI, שמור את התמונה.

### פרמטרים

| פרמטר | תיאור | ברירת מחדל |
|-------|-------|------------|
| `PROMPT` | תיאור התמונה המלא | חובה |
| `OUTPUT_PATH` | נתיב לשמירת קובץ ה-PNG | חובה |

---

## קריאה לAPI

### שיטה 1 — bash + curl + jq (מומלץ)

```bash
source .env 2>/dev/null || true

curl -s -X POST "https://api.openai.com/v1/images/generations" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: application/json" \
  -d "{
    \"model\": \"gpt-image-2\",
    \"prompt\": \"$PROMPT\",
    \"size\": \"1024x1024\",
    \"quality\": \"medium\",
    \"output_format\": \"png\"
  }" | jq -r '.data[0].b64_json' | base64 --decode > "$OUTPUT_PATH"
```

### שיטה 2 — Python fallback (כאשר jq לא מותקן)

```python
import base64, json, os, sys
import urllib.request

api_key = os.environ.get("OPENAI_API_KEY", "")
prompt  = sys.argv[1]
out     = sys.argv[2]

payload = json.dumps({
    "model": "gpt-image-2",
    "prompt": prompt,
    "size": "1024x1024",
    "quality": "medium",
    "output_format": "png"
}).encode()

req = urllib.request.Request(
    "https://api.openai.com/v1/images/generations",
    data=payload,
    headers={
        "Authorization": f"Bearer {api_key}",
        "Content-Type": "application/json",
    },
)
with urllib.request.urlopen(req) as resp:
    data = json.load(resp)

b64 = data["data"][0]["b64_json"]
with open(out, "wb") as f:
    f.write(base64.b64decode(b64))

print(f"Saved: {out} ({os.path.getsize(out)} bytes)")
```

הרץ: `python .claude/skills/gpt-image-gen/decode.py "$PROMPT" "$OUTPUT_PATH"`

---

## הוראות לסוכן המשתמש בסקיל

1. **טען את ה-API key** — קרא `.env` בשורש הפרויקט ואמת ש-`OPENAI_API_KEY` קיים ולא ריק. אם חסר, הפסק ובקש מהמשתמש להוסיף אותו.

2. **הכן את ה-prompt** — ה-prompt צריך להיות מפורט: סגנון, צבעים, קומפוזיציה, מצב רוח. ככל שמפורט יותר — תוצאה טובה יותר.

3. **הרץ את הפקודה** — נסה קודם bash+jq. אם jq לא מותקן (שגיאה `jq: command not found`), עבור ל-Python fallback.

4. **אמת פלט** — ודא שהקובץ קיים ו-size > 0 bytes. אם הקובץ ריק, בדוק:
   - שגיאות ב-API response (הדפס את ה-JSON המלא לפני ה-pipe)
   - תקינות ה-`OPENAI_API_KEY`
   - פרמטרים לא חוקיים

5. **טיפול בשגיאות** — אם ה-API מחזיר שגיאה:
   - `401` — API key שגוי או חסר
   - `400` — פרמטר לא חוקי (גודל/quality לא נתמך)
   - `429` — rate limit, המתן ונסה שוב
   - אל תשנה את שם המודל `gpt-image-2` — הוא קיים ותקין

---

## הערות

- המודל `gpt-image-2` הוא מודל אמיתי של OpenAI (יצא 21 באפריל 2026).
- הגדלים הנתמכים: `1024x1024`, `1536x1024`, `1024x1536`.
- quality אפשרויות: `low`, `medium`, `high`.
