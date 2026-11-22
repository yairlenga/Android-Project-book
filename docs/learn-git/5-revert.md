
<style>
body {
    direction: rtl;
    text-align: right;
}

.ltr {
    direction: ltr;
    text-align: left;
}

pre, code {
    direction: ltr;
    text-align: left;
}

img {
    border: 1px solid #888;
    padding: 4px;
}

h1 {
    color: MidnightBlue;
}

h2 {
    color: SteelBlue;
}

h3 {
    color: DarkSlateGray;
}

h4 {
    color: SlateGray;
}
</style>


# חלק 5 — שחזור גרסאות וביטול Commits

**משך משוער:** 15–20 דקות  
**סביבת עבודה:** Android Studio, Java  
**דרישות מוקדמות:** השלמת חלקים 1–4.

## 5.1 מטרות

בסיום חלק זה נדע:

1. לצפות בקובץ כפי שהיה ב-Commit קודם.
2. לשחזר קוד מגרסה קודמת.
3. לבטל Commit שכבר נשמר באמצעות Revert.
4. להבין כיצד אפשר לבטל Commit ישן בלי למחוק שינויים מאוחרים יותר.
5. להבין ש-Revert אינו מוחק את ההיסטוריה.

---

## 5.2 נקודות לשיחה — Rollback, Restore ו-Revert

בחלק הקודם למדנו כיצד לבטל שינויים שעדיין לא נשמרו ב-Commit.

אבל מה קורה אם כבר ביצענו Commit?

Git מאפשר לנו לשחזר קוד מגרסאות קודמות או לבטל שינוי שכבר נשמר.

| פעולה | שימוש |
|---|---|
| **Rollback** | ביטול שינויים שעדיין לא נשמרו ב-Commit |
| **Restore** | שחזור תוכן מתוך גרסה קודמת |
| **Revert** | יצירת Commit חדש שמבטל שינוי של Commit קודם |

### דוגמה

```text
A ─── B ─── C ─── D
                   ↑
                  main
```

אם נבצע Revert ל-Commit B, Git ייצור Commit חדש E:

```text
A ─── B ─── C ─── D ─── E
                         ↑
                        main
```

Commit E מבטל את השינוי שבוצע ב-B, בלי למחוק את B, ‏C או D מההיסטוריה.

**חשוב:** Revert מבטל את השינויים של Commit מסוים. הוא אינו מחזיר את כל הפרויקט לגרסה ההיא.

---

## 5.3 משימה ראשונה — שחזור שורה מגרסה קודמת

**מטרה:** לשחזר קוד ישן בלי לאבד שינויים אחרים בקובץ.

### שלב א — מציאת הגרסה הישנה

1. פתחו את חלון **Git → Log**.
2. מצאו את ה-Commit שבו נוספה הודעת ה-Toast לראשונה:

   `Update application title`

3. פתחו את `MainActivity.java` כפי שהיה באותו Commit.
4. מצאו את השורה:

   ```java
   Toast.makeText(this, "Welcome to Git Practice", Toast.LENGTH_LONG).show();
   ```

### שלב ב — שחזור השורה

1. העתיקו את השורה מהגרסה הישנה.
2. חזרו לקובץ `MainActivity.java` הנוכחי.
3. החליפו את הודעת הפתיחה בשורה שהעתקתם.
4. פתחו את חלון **Commit**.
5. בדקו באמצעות Diff שרק הודעת הפתיחה השתנתה.

### שלב ג — שמירת השחזור

בצעו Commit עם ההודעה:

```text
Restore original welcome message
```

### שאלות

1. האם שחזרנו את כל הקובץ או רק שורה אחת?
2. האם הקוד של הכפתור עדיין קיים?
3. האם ה-Commits הקודמים נמחקו?
4. מדוע השחזור מופיע כ-Commit חדש?

---

## 5.4 משימה שנייה — ביטול Commit ישן באמצעות Revert

**מטרה:** לבטל שינוי שכבר נשמר, בלי לבטל שינויים שבוצעו אחריו.

### שלב א — יצירת שני Commits

**Commit ראשון — שינוי XML**

1. פתחו את `activity_main.xml`.
2. מצאו את ה-TextView.
3. שנו את הטקסט שלו ל:

   ```xml
   android:text="Temporary XML Change"
   ```

4. בצעו Commit עם ההודעה:

   ```text
   Change XML text
   ```

**Commit שני — שינוי Java**

1. פתחו את `MainActivity.java`.
2. שנו את הודעת הכפתור ל:

   ```java
   Toast.makeText(this, "Button pressed!", Toast.LENGTH_SHORT).show();
   ```

3. בצעו Commit עם ההודעה:

   ```text
   Update button message
   ```

### שלב ב — בדיקת ההיסטוריה

פתחו את **Git → Log**.

שני ה-Commits האחרונים אמורים להיות:

```text
Update button message
Change XML text
```

שימו לב: שינוי ה-XML בוצע לפני שינוי ה-Java.

### שלב ג — Revert ל-Commit ה