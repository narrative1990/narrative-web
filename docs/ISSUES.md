# NARRATiVE — בעיות ידועות + תוכנית לבנייה מחדש

## בעיות נוכחיות

### 1. וידאויים — GitHub Releases אינו CDN
**בעיה:** GitHub releases לא מיועד לסטרימינג וידאו.
- אין range requests (חייב להוריד מהתחלה)
- אין CDN — שרתים רחוקים
- Rate limiting
- מובייל דוחה redirects על וידאו

**פתרון מומלץ לבנייה מחדש:** Bunny.net (~$1/חודש) או Cloudflare Stream

---

### 2. YouTube Embed חסום
**בעיה:** שגיאה 153 — YouTube חוסם embed מאתרים חיצוניים.
- `youtube-nocookie.com` לא עזר
- iframe מציג מסך שחור

**פתרון נוכחי:** קישור ישיר `<a href="youtu.be/...">` — פותח YouTube בטאב חדש  
**פתרון לבנייה מחדש:** Vimeo (embed עובד מצוין) או Bunny.net player

---

### 3. Dreep — Content ID Warning
**בעיה:** YouTube מזהה תוכן מוגן ב-Dreep video
- אזהרה: "יש הגבלה פוטנציאלית על הרווחים"
- ייתכן שימנע הפצה מסוימת

**פתרון:** בדוק ב-YouTube Studio → Copyright → dispute אם הclip הוא שלך

---

### 4. Placeholder URLs שנשארו
**בעיה:** כמה URLs עדיין עם placeholders:
- `YOUR_HERO_POSTER_URL` — poster לוידאו ה-hero
- `YOUR_SCRUB_POSTER_URL` — poster לוידאו ה-scrub
- `YOUR_REEL_1_POSTER_URL`, `YOUR_REEL_2_POSTER_URL`, `YOUR_REEL_3_POSTER_URL`

**פתרון:** לצלם frame ראשון מכל וידאו ולהעלות כ-JPG

---

### 5. לוגואות פרטנרים חסרות
**בעיה:** `assets/partners/*.png` — נתיבים יחסיים, הקבצים לא קיימים
- luma-mono.png, seedance-mono.png, kling-mono.png, runway-mono.png
- higgsfield-mono.png, artlist-mono.png, magnific-mono.png

**פתרון:** להוסיף את הקבצים לתיקיית `assets/partners/` ולעשות commit

---

## תוכנית לבנייה מחדש

### ארכיטקטורה מומלצת

```
narrative-studio.ai
├── וידאו CDN: Bunny.net / Cloudflare Stream
├── embed: Vimeo (לא YouTube — embedding בעייתי)
├── קוד: React/Next.js (קל יותר לתחזוקה מ-single HTML)
└── hosting: Vercel (להשאיר)
```

### סדר עדיפויות

1. ✅ תיקיית פרויקט מסודרת — **בוצע**
2. ✅ GitHub repo לקוד — **בוצע**
3. ⏳ CDN לוידאויים — **לבנייה מחדש**
4. ⏳ לוגואות פרטנרים — **TODO**
5. ⏳ Poster images לכל וידאו — **TODO**
6. ⏳ חיבור Vercel ↔ GitHub (auto-deploy) — **TODO**
