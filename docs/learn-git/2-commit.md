
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


# חלק 2 — שמירת שינויים באמצעות Commit

**משך משוער:** 25–30 דקות  
**סביבת עבודה:** Android Studio, Java  
**דרישות מוקדמות:** פרויקט `GitPractice` פועל, ומאגר Git מכיל Commit ראשוני.

## 2.1 מטרות

בסיום חלק זה נדע:

1. לזהות קבצים ששונו בפרויקט.
2. לבדוק שינויים באמצעות Diff.
3. לבצע Commit ולכתוב הודעה המתארת את השינוי.
4. לבצע Commit של קובץ יחיד.
5. לבצע Commit הכולל מספר קבצים הקשורים לאותה יכולת.

---

## 2.2 משימה ראשונה — שינוי בקובץ XML בלבד

**מטרה:** שינוי ממשק המשתמש ושמירתו ב-Commit.

נשנה את הודעת הפתיחה המוצגת באפליקציה.

### הוראות לתלמיד

1. פתחו את הקובץ:

   `app/src/main/res/layout/activity_main.xml`

2. עברו לתצוגת **Code**.

3. מצאו את הגדרת ה-`TextView` ואת המאפיין:

   ```xml
   android:text="Hello World!"
   ```

4. החליפו אותו ב:

   ```xml
   android:text="My First Git Project"
   ```

   אם הטקסט מוגדר באמצעות הפניה ל-`strings.xml`, החליפו את ההפניה בטקסט הישיר המופיע למעלה, כדי שהשינוי יתבצע בקובץ XML אחד בלבד.

5. פתחו את חלון **Commit**.
6. ודאו שרק `activity_main.xml` מופיע כקובץ ששונה.
7. לחצו על הקובץ כדי לפתוח את חלון **Diff**.
8. בדקו את השורה שנמחקה ואת השורה שנוספה.

### ביצוע Commit

1. סמנו את `activity_main.xml`.
2. כתבו:

   ```text
   Update welcome message
   ```

3. לחצו **Commit**.

### בדיקת הצלחה

- [ ] רק קובץ XML אחד השתנה.
- [ ] בדקנו את השינוי באמצעות Diff.
- [ ] בוצע Commit המתעד את השינוי.

---

## 2.3 משימה שנייה — שינוי בקובץ Java בלבד

**מטרה:** שינוי התנהגות האפליקציה באמצעות Java ושמירתו ב-Commit נפרד.

נשנה את הכותרת המוצגת בראש האפליקציה.

### הוראות לתלמיד

1. פתחו את הקובץ `MainActivity.java`.

2. מצאו את המתודה `onCreate`.

   היא אמורה להיראות בערך כך:

   ```java
   @Override
   protected void onCreate(Bundle savedInstanceState) {
       super.onCreate(savedInstanceState);
       setContentView(R.layout.activity_main);
   }
   ```

   ייתכן שהמתודה מכילה שורות נוספות.

3. הוסיפו אחרי `setContentView` את השורה:

```java
    Toast.makeText(
        this,
        "Welcome to Git Practice",
        Toast.LENGTH_LONG
    ).show();
```
4. הוסף import כפי שמדרש
5. פתחו את חלון **Commit**.
6. ודאו שרק `MainActivity.java` מופיע כקובץ ששונה.
7. פתחו את חלון Diff ובדקו את השינוי.

### ביצוע Commit

1. סמנו את `MainActivity.java`.
2. כתבו:

   ```text
   Update application title
   ```

3. לחצו **Commit**.

### בדיקת הצלחה

- [ ] רק קובץ Java אחד השתנה.
- [ ] בוצע Commit נוסף.
- [ ] אין שינויים ממתינים.

---

## 2.4 משימה שלישית — שינוי במספר קבצים

**מטרה:** להבין ש-Commit אחד יכול לכלול מספר קבצים הקשורים לאותה יכולת.

נוסיף לאפליקציה כפתור, ונגדיר פעולה שתתבצע כאשר לוחצים עליו.

השינוי ידרוש עריכה של שני קבצים:

- `activity_main.xml` — הוספת הכפתור לממשק.
- `MainActivity.java` — הגדרת הפעולה של הכפתור.

### שלב א — הוספת כפתור ב-XML

1. פתחו את `activity_main.xml`.
2. עברו לתצוגת **Design**.
3. מתוך חלון **Palette**, גררו רכיב **Button** אל המסך.
4. הגדירו:

   | מאפיין | ערך |
      |---|---|
   | id | `actionButton` |
   | text | `Click Me` |
   | layout_width | `wrap_content` |
   | layout_height | `wrap_content` |

5. אם הפריסה משתמשת ב-`ConstraintLayout`, הגדירו אילוצים למיקום הכפתור, כך שלא יישארו אילוצים חסרים.

### שלב ב — הוספת פעולה ב-Java

1. פתחו את `MainActivity.java`.

2. הוסיפו את ה-imports הבאים, אם אינם קיימים:

   ```java
   import android.widget.Button;
   import android.widget.Toast;
   ```

3. בתוך `onCreate`, אחרי `setContentView`, הוסיפו:

   ```java
   Button button = findViewById(R.id.actionButton);

   button.setOnClickListener(v -> {
       Toast.makeText(
           this,
           "Button clicked!",
           Toast.LENGTH_SHORT
       ).show();
   });
   ```

4. הריצו את האפליקציה.
5. לחצו על הכפתור.

### תוצאה צפויה

בלחיצה על הכפתור תופיע הודעה קצרה:

`Button clicked!`

### שלב ג — בדיקת השינויים

1. פתחו את חלון **Commit**.
2. ודאו שמופיעים שני קבצים ששונו:
    - `activity_main.xml`
    - `MainActivity.java`
3. פתחו את חלון Diff של כל אחד מהם.
4. בדקו את השינויים.

### שלב ד — Commit משותף

1. סמנו את שני הקבצים.
2. כתבו:

   ```text
   Add button with click handler
   ```

3. לחצו **Commit**.

### בדיקת הצלחה

- [ ] האפליקציה פועלת.
- [ ] הכפתור מופיע במסך.
- [ ] לחיצה על הכפתור מציגה הודעה.
- [ ] בוצע Commit אחד הכולל שני קבצים.

### שאלה לדיון

מדוע כדאי לשמור את הוספת הכפתור ואת הקוד שמפעיל אותו באותו Commit?

---


## 2.5 משימה רביעית — שינוי נוסף בשורה קיימת

**מטרה:** להבין שאותה שורת קוד יכולה להשתנות במספר Commits, וש-Git שומר את ההיסטוריה של השינויים.

### הוראות לתלמיד

1. פתחו את `MainActivity.java`.
2. מצאו את השורה המציגה את הודעת הפתיחה:

   ```java
   Toast.makeText(this, "Welcome to Git Practice", Toast.LENGTH_LONG).show();
   ```

3. שנו את ההודעה ל:

   ```java
   Toast.makeText(this, "Welcome to Git Practice - Version 2", Toast.LENGTH_LONG).show();
   ```

4. פתחו את חלון **Commit**.
5. בדקו באמצעות **Diff** שהשינוי היחיד הוא בטקסט ההודעה.
6. בצעו Commit עם ההודעה:

   ```text
   Update welcome message to version 2
   ```

### שאלות לדיון

1. באיזה Commit נוספה השורה במקור?
2. באיזה Commit היא שונתה לאחרונה?
3. האם Git שומר את שתי הגרסאות של השורה?
4. כיצד נוכל למצוא את התוכן הקודם של השורה?

**בחלק הבא:** נשתמש ב-Git Log וב-Git Blame כדי לחקור את ההיסטוריה של השורה ולגלות מתי היא נוספה ומתי שונתה.

## 2.6 סיכום התרגול

בסיום החלק אמורים להיות בפרויקט ארבעה Commits, כולל ה-Commit הראשוני שבוצע בחלק הקודם.

| מספר | הודעת Commit | קבצים ששונו |
|---|---|---|
| 1 | Initial Android Studio project | קובצי הפרויקט הראשוניים |
| 2 | Update welcome message | XML |
| 3 | Update application title | Java |
| 4 | Add button with click handler | XML + Java |

### שאלות לסיכום

1. האם Commit יכול לכלול שינוי בקובץ אחד בלבד?
2. האם Commit יכול לכלול מספר קבצים?
3. מה היתרון של Commit המתעד שינוי לוגי אחד?
4. מה קורה אם משנים קובץ ולא מבצעים Commit?
5. מדוע חשוב לבדוק Diff לפני ביצוע Commit?

---

## 2.6 סיכום

ביצענו שלושה שינויים בפרויקט ושמרנו כל אחד מהם ב-Commit נפרד.

ראינו ש:

- Git מזהה קבצים ששונו.
- אפשר לבדוק שינויים לפני שמירתם.
- Commit יכול לכלול קובץ אחד או מספר קבצים.
- כדאי לארגן Commits לפי שינויים לוגיים, ולא בהכרח לפי קבצים.

### בחלק הבא

[חלק 3 — היסטוריה והשוואת גרסאות](3-history.md)

נלמד כיצד להשתמש ב-Git Log וב-Diff כדי לבחון את הגרסאות שיצרנו ולהשוות ביניהן.