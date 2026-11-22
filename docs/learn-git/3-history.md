
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

# חלק 3 — היסטוריה והשוואת גרסאות

**משך משוער:** 20–25 דקות  
**סביבת עבודה:** Android Studio, Java  
**דרישות מוקדמות:** פרויקט `GitPractice` מכיל חמישה Commits מהתרגול הקודם.

## 3.1 מטרות

בסיום חלק זה נדע:

1. לצפות בהיסטוריית ה-Commits של הפרויקט.
2. לזהות אילו קבצים השתנו בכל Commit.
3. לבדוק שינויים באמצעות Diff.
4. להשוות בין שתי גרסאות של הפרויקט.
5. לצפות בהיסטוריה של קובץ יחיד.
6. להשתמש ב-Git Blame כדי לזהות מי שינה שורה ומתי.
7. לחקור את ההיסטוריה של אותה שורה לאורך מספר Commits.

---

## 3.2 נקודות לשיחה — היסטוריית הפרויקט

בחלק הקודם יצרנו חמישה Commits:

```text
A ─── B ─── C ─── D ─── E
                         ↑
                        main
```

| Commit | הודעה | שינוי |
|---|---|---|
| A | Initial Android Studio project | יצירת הפרויקט |
| B | Update welcome message | שינוי טקסט ב-XML |
| C | Update application title | הוספת הודעת Toast |
| D | Add button with click handler | הוספת כפתור ופעולה |
| E | Update welcome message to version 2 | שינוי הודעת Toast קיימת |

### נקודות חשובות

- כל Commit מייצג תמונת מצב של הפרויקט.
- לכל Commit מזהה ייחודי (Hash).
- כל Commit מצביע על ה-Commit שקדם לו.
- `main` מצביע על ה-Commit האחרון בענף.
- אפשר לבחון כל גרסה קודמת בלי לשנות את הקוד הנוכחי.

**שאלה:** אם שינינו שורת קוד ב-Commit C ושוב ב-Commit E, כיצד נמצא את שתי הגרסאות שלה?

---

## 3.3 משימה ראשונה — צפייה בהיסטוריה באמצעות Git Log

**מטרה:** להכיר את היסטוריית הגרסאות של הפרויקט.

### הוראות לתלמיד

1. פתחו את הפרויקט `GitPractice`.
2. פתחו את חלון **Git**.
3. בחרו בלשונית **Log**.
4. מצאו את חמשת ה-Commits שביצעתם.

ההודעות אמורות להופיע בסדר דומה לזה:

```text
Update welcome message to version 2
Add button with click handler
Update application title
Update welcome message
Initial Android Studio project
```

### בדיקת פרטי Commit

1. בחרו את ה-Commit:

   `Update welcome message to version 2`

2. בדקו:
    - Commit Hash
    - Author
    - Date
    - Commit Message
3. מצאו את רשימת הקבצים שהשתנו.

### שאלות

1. מהו ה-Commit החדש ביותר?
2. מהו ה-Commit הראשון?
3. האם שני Commits יכולים לקבל אותה הודעה?
4. מדוע Git משתמש ב-Hash ולא במספר סידורי?

---

## 3.4 משימה שנייה — בדיקת שינויים באמצעות Diff

**מטרה:** לראות מה השתנה ב-Commit מסוים.

### הוראות לתלמיד

1. בחלון Git Log בחרו את ה-Commit:

   `Update welcome message to version 2`

2. מצאו את הקובץ `MainActivity.java`.
3. לחצו עליו פעמיים כדי לפתוח את חלון **Diff**.

### מה נראה?

**לפני השינוי:**

```java
Toast.makeText(this, "Welcome to Git Practice", Toast.LENGTH_LONG).show();
```

**אחרי השינוי:**

```java
Toast.makeText(this, "Welcome to Git Practice - Version 2", Toast.LENGTH_LONG).show();
```

בדרך כלל:

- שורות שנמחקו מסומנות באדום.
- שורות שנוספו מסומנות בירוק.
- שורות שלא השתנו מוצגות ללא סימון מיוחד.

### תרגול נוסף

1. בחרו את ה-Commit:

   `Update welcome message`

2. פתחו את Diff של `activity_main.xml`.
3. מצאו את שינוי הודעת הפתיחה.

### שאלות

1. האם Diff מציג את הקובץ כולו או את ההבדלים בין גרסאות?
2. כיצד מזהים שורה שנוספה?
3. כיצד מזהים שורה ששונתה?

---

## 3.5 משימה שלישית — Commit הכולל מספר קבצים

**מטרה:** לראות כיצד Git מתעד שינוי לוגי הכולל מספר קבצים.

### הוראות לתלמיד

1. בחלון Git Log בחרו את ה-Commit:

   `Add button with click handler`

2. בדקו את רשימת הקבצים ששונו.
3. ודאו שמופיעים:
    - `activity_main.xml`
    - `MainActivity.java`
4. פתחו את Diff של קובץ ה-XML.
5. מצאו את הגדרת הכפתור.
6. פתחו את Diff של קובץ ה-Java.
7. מצאו את הקוד המטפל בלחיצה על הכפתור.

### שאלות

1. מדוע שני הקבצים נכללו באותו Commit?
2. האם Git מחייב שכל Commit יכלול קובץ אחד בלבד?
3. מה היתרון של Commit המתעד שינוי לוגי אחד?

---

## 3.6 משימה רביעית — השוואה בין שתי גרסאות

**מטרה:** להשוות בין שתי גרסאות של הפרויקט, גם כאשר בוצעו ביניהן מספר Commits.

### הוראות לתלמיד

1. פתחו את Git Log.
2. בחרו את ה-Commit הראשון:

   `Initial Android Studio project`

3. החזיקו `Ctrl` ובחרו גם את ה-Commit האחרון:

   `Update welcome message to version 2`

4. לחצו בכפתור הימני ובחרו **Compare Versions** או אפשרות ההשוואה המקבילה.
5. בדקו את רשימת הקבצים שהשתנו.
6. פתחו את Diff של `MainActivity.java`.

### שאלות

1. מה ההבדל בין Diff של Commit יחיד לבין השוואת שני Commits?
2. האם ההשוואה מציגה את השינויים המצטברים בין הגרסאות?
3. האם אפשר להשוות בין כל שני Commits בהיסטוריה?

---

## 3.7 משימה חמישית — היסטוריה של קובץ יחיד

**מטרה:** לראות כיצד קובץ מסוים השתנה לאורך זמן.

### הוראות לתלמיד

1. בחלון Project מצאו את `MainActivity.java`.
2. לחצו עליו בכפתור הימני.
3. בחרו **Git → Show History**.
4. בדקו את רשימת ה-Commits שבהם הקובץ השתנה.

אתם אמורים למצוא לפחות:

```text
Update welcome message to version 2
Add button with click handler
Update application title
Initial Android Studio project
```

שימו לב שה-Commit ששינה רק את קובץ ה-XML אינו מופיע בהיסטוריה של קובץ Java.

### תרגול

1. בחרו את ה-Commit שבו נוספה הודעת ה-Toast.
2. פתחו את הגרסה הישנה של הקובץ.
3. מצאו את הודעת ה-Toast המקורית.
4. השוו אותה להודעה הנוכחית.

**חשוב:** אנחנו רק צופים בגרסאות קודמות. איננו משנים את הקוד הנוכחי.

---

## 3.8 משימה שישית — זיהוי מקור השינוי באמצעות Git Blame

**מטרה:** לזהות מי שינה לאחרונה כל שורה בקובץ, מתי ובאיזה Commit.

### נקודות לשיחה

Git Blame מאפשר לענות על השאלות:

- מי שינה את השורה לאחרונה?
- מתי בוצע השינוי?
- באיזה Commit הוא בוצע?
- מה הייתה סיבת השינוי?

Git Blame מציג את ה-Commit האחרון ששינה כל שורה בקובץ.

### שלב א — הפעלת Git Blame

1. פתחו את `MainActivity.java`.
2. לחצו בכפתור הימני על השוליים השמאליים של חלון העריכה, ליד מספרי השורות.
3. בחרו **Annotate with Git Blame** או **Annotate**.
4. לצד שורות הקוד יופיע מידע על ה-Commit האחרון ששינה אותן.

### מה נראה?

לדוגמה:

```text
Initial project   | public class MainActivity extends AppCompatActivity {
Initial project   |     @Override
Initial project   |     protected void onCreate(Bundle savedInstanceState) {
Initial project   |         super.onCreate(savedInstanceState);
Initial project   |         setContentView(R.layout.activity_main);
Commit E          |         Toast.makeText(this, "Welcome to Git Practice - Version 2", Toast.LENGTH_LONG).show();
Commit D          |         Button button = findViewById(R.id.actionButton);
Commit D          |         button.setOnClickListener(v -> {
```

זו המחשה בלבד. Android Studio עשוי להציג שם מחבר, תאריך או Hash במקום הודעת ה-Commit.

### שלב ב — הצגת מידע נוסף

1. לחצו בכפתור הימני על עמודת ה-Annotations.
2. בדקו אילו אפשרויות תצוגה זמינות, למשל:
    - Show Author
    - Show Date
    - Show Commit Message
3. הפעילו את האפשרויות הרצויות, אם הן נתמכות בגרסת Android Studio שלכם.

### שאלות

1. מדוע שורות שונות באותו קובץ משויכות ל-Commits שונים?
2. לאיזה Commit משויכת הודעת ה-Toast?
3. מדוע היא אינה משויכת ל-Commit שבו נוספה לראשונה?
4. לאיזה Commit משויך הקוד של הכפתור?

---

## 3.9 משימה שביעית — מעקב אחר אותה שורה בגרסאות קודמות

**מטרה:** לחקור את ההיסטוריה של שורה שהשתנתה יותר מפעם אחת.

### נקודות לשיחה

בחלק הקודם שינינו את הודעת ה-Toast פעמיים.

**Commit C — הוספת ההודעה:**

```java
Toast.makeText(this, "Welcome to Git Practice", Toast.LENGTH_LONG).show();
```

**Commit E — שינוי ההודעה:**

```java
Toast.makeText(this, "Welcome to Git Practice - Version 2", Toast.LENGTH_LONG).show();
```

כאשר מפעילים Blame על הגרסה הנוכחית, Git מצביע על Commit E.

אבל אנחנו רוצים לדעת גם מתי השורה נוספה במקור.

### שלב א — מעבר לגרסה הקודמת

1. פתחו את `MainActivity.java`.
2. הפעילו Git Blame.
3. מצאו את השורה המכילה:

   `Welcome to Git Practice - Version 2`

4. לחצו בכפתור הימני על ההערה של אותה שורה.
5. חפשו את האפשרות **Annotate Previous Revision**.
6. בחרו בה, אם היא זמינה.

### מה נראה?

Git יציג את הקובץ כפי שהיה לפני Commit E.

הודעת ה-Toast תחזור לגרסה הקודמת:

```java
Toast.makeText(this, "Welcome to Git Practice", Toast.LENGTH_LONG).show();
```

כעת ה-Blame של השורה יצביע על Commit C — ה-Commit שבו נוספה ההודעה במקור.

### שלב ב — בדיקת השינוי באמצעות Diff

1. מצאו את Commit E בחלון Git Log.
2. פתחו את Diff של `MainActivity.java`.
3. בדקו את ההבדל בין שתי הגרסאות של השורה.
4. חזרו לגרסה הנוכחית של הקובץ.

### שלב ג — אם האפשרות אינה זמינה

אם Android Studio אינו מציג **Annotate Previous Revision**:

1. פתחו את Git Log.
2. בחרו את Commit D — הגרסה שלפני שינוי ההודעה.
3. פתחו את `MainActivity.java` כפי שהיה ב-Commit D.
4. בדקו שהודעת ה-Toast עדיין מכילה את הטקסט המקורי.
5. פתחו את Commit C ובדקו את ה-Diff שבו נוספה השורה.

כך אפשר להגיע לאותו מידע גם ללא הפקודה הישירה.

### שאלות

1. מדוע Blame בגרסה הנוכחית מצביע על Commit E?
2. מדוע Blame בגרסה הקודמת מצביע על Commit C?
3. האם Commit D שינה את הודעת ה-Toast?
4. מה ההבדל בין מי שהוסיף שורה לבין מי ששינה אותה לאחרונה?

### מסקנה

**Git Blame מציג את ה-Commit האחרון ששינה שורה בגרסה הנבדקת.**

כדי לחקור שינויים מוקדמים יותר, אפשר לעבור לגרסאות קודמות ולבדוק את ה-Blame וה-Diff שלהן.

---

## 3.10 בדיקת הצלחה

לפני שממשיכים, ודאו:

- [ ] פתחנו את Git Log.
- [ ] מצאנו את חמשת ה-Commits.
- [ ] בדקנו את פרטי אחד ה-Commits.
- [ ] פתחנו Diff של שינוי ב-XML.
- [ ] פתחנו Diff של שינוי ב-Java.
- [ ] בדקנו Commit הכולל מספר קבצים.
- [ ] השווינו בין שני Commits.
- [ ] צפינו בהיסטוריה של קובץ יחיד.
- [ ] הפעלנו Git Blame.
- [ ] זיהינו את ה-Commit האחרון ששינה את הודעת ה-Toast.
- [ ] מצאנו את הגרסה הקודמת של אותה שורה.
- [ ] הבנו כיצד לעקוב אחר שורה לאורך מספר Commits.
- [ ] לא שינינו את קובצי הפרויקט.

---

## 3.11 סיכום

בחלק זה למדנו כיצד לחקור את היסטוריית הגרסאות של הפרויקט.

| יכולת | שימוש |
|---|---|
| Git Log | צפייה בהיסטוריית ה-Commits |
| Diff | בדיקת השינויים ב-Commit |
| Compare Versions | השוואה בין שתי גרסאות |
| File History | צפייה בהיסטוריה של קובץ מסוים |
| Git Blame | זיהוי ה-Commit האחרון ששינה כל שורה |
| Annotate Previous Revision | חקירת השורה בגרסה קודמת, כאשר האפשרות זמינה |

ראינו שאפשר לא רק לזהות מי שינה שורה לאחרונה, אלא גם לחקור את ההיסטוריה שלה ולגלות כיצד השתנתה לאורך זמן.

### בחלק הבא

[חלק 4 — ביטול שינויים באמצעות Rollback](4-rollback.md)

נלמד כיצד לבטל שינויים שביצענו בקוד ועדיין לא שמרנו ב-Commit.