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

# חלק 0 — יצירת פרויקט Android ראשוני

**מטרה:** יצירת פרויקט Android בסיסי בשפת Java, הרצת האפליקציה וביצוע Commit ראשון של הפרויקט כפי שנוצר על ידי Android Studio.

**זמן משוער:** 10–15 דקות, בהנחה שסביבת הפיתוח כבר מותקנת ומוגדרת.

## 0.1 יצירת פרויקט חדש

1. פתחו את **Android Studio**.
2. במסך הפתיחה בחרו **New Project**.
    - אם כבר פתוח פרויקט, בחרו **File → New → New Project**.
3. בחרו בקטגוריה **Phone and Tablet**.
4. בחרו בתבנית **Empty Views Activity**.
    - שימו לב: יש לבחור **Empty Views Activity** ולא **Empty Activity**.
    - התבנית שבחרנו משתמשת בממשק XML ולא ב-Jetpack Compose.
5. לחצו **Next**.
6. הגדירו את הפרויקט:

   | שדה | ערך |
      |---|---|
   | Name | GitPractice |
   | Package name | com.example.gitpractice |
   | Language | Java |
   | Minimum SDK | API 24 |
   | Build configuration language | Kotlin DSL (build.gradle.kts) |

7. בחרו תיקייה לשמירת הפרויקט.
8. לחצו **Finish**.
9. המתינו לסיום תהליך **Gradle Sync**.

> **שימו לב:** בפעם הראשונה שפותחים פרויקט, Android Studio עשוי להוריד רכיבים נוספים. יש להמתין לסיום התהליך לפני שממשיכים.

## 0.2 הכרת מבנה הפרויקט

בחלון **Project**, בחרו בתצוגת **Android**.

אתרו את הקבצים הבאים:

| קובץ | תפקיד |
|---|---|
| `MainActivity.java` | קוד Java של המסך הראשי |
| `activity_main.xml` | הגדרת ממשק המשתמש |
| `strings.xml` | טקסטים המוצגים באפליקציה |
| `AndroidManifest.xml` | הגדרות בסיסיות של האפליקציה |
| `build.gradle.kts` | הגדרות בנייה ותלויות |
| `.gitignore` | הגדרת קבצים שלא ייכללו בניהול הגרסאות |

### שאלות

1. באיזה קובץ מוגדר הממשק הגרפי?
2. באיזה קובץ נמצא קוד Java?
3. מדוע כדאי להפריד בין קוד האפליקציה לבין הגדרת הממשק?

## 0.3 הרצת האפליקציה

1. ודאו שתהליך Gradle Sync הסתיים בהצלחה.
2. בחרו מכשיר Android מחובר או Emulator מתוך רשימת המכשירים.
3. לחצו על כפתור **Run ▶**.
4. המתינו לבניית האפליקציה ולהפעלתה.

### תוצאה צפויה

האפליקציה תיפתח ותציג מסך בסיסי עם ההודעה:

**Hello World!**

אין צורך לשנות את הקוד בשלב זה.

### בדיקת הצלחה

- [ ] הפרויקט נוצר בהצלחה.
- [ ] תהליך Gradle Sync הסתיים.
- [ ] האפליקציה נבנתה ללא שגיאות.
- [ ] האפליקציה פועלת במכשיר או ב-Emulator.
- [ ] מופיעה ההודעה Hello World!

