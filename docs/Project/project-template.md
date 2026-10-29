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


<a id="cover"></a>
# שער

**לוגו בית הספר:** === לוגו בית הספר ===

**שם בית הספר:** === שם בית הספר ===

**שם העבודה:** === שם הפרויקט ===

**שם התלמיד:** === שם התלמיד ===

**ת.ז. התלמיד:** === מספר תעודת זהות ===

**שם המנחה:** === שם המנחה ===

**שם החלופה:** === שם החלופה ===

**תאריך ההגשה:** === תאריך ההגשה ===


<a id="toc"></a>
# תוכן עניינים

- [שער](#cover)
- [תוכן עניינים](#toc)
- [מבוא](#introduction)
  - [הרקע לפרויקט](#project-background)
    - [שם הפרויקט](#project-name)
    - [תיאור קצר של הפרויקט](#project-description)
    - [קהל היעד](#target-audience)
    - [הסיבות לבחירת הנושא](#topic-selection)
  - [תהליך המחקר](#research)
    - [נקודות עיקריות במחקר לצורכי הפרויקט](#research-findings)
      - [מחקר על תחום ידע](#domain-research)
      - [בדיקת אפליקציות קיימות](#existing-applications)
      - [סקירת המצב הקיים בשוק](#market-review)
  - [אתגרים מרכזיים](#challenges)
    - [בעיות איתם הלומד התמודד במהלך פיתוח הפרויקט](#development-problems)
    - [על איזה צורך הפרויקט עונה / איזה פתרון הפרויקט הזה בא לתת](#project-need)
    - [הצגת פתרונות לבעיה (הפתרונות שנבחנו במסגרת המחקר המקדים)](#evaluated-solutions)
  - [חידושים, התאמות ועדכונים של אלמנטים טכנולוגיים, עיצוביים ואחרים בפרויקט](#innovations)
  - [תיאור תחום הידע - פרק מילולי](#domain-description)
    - [אובייקטים נחוצים](#required-objects)
    - [סוגי נתונים](#data-types)
    - [ייצוג מידע](#data-representation)
    - [תאור פעולות על המידע](#data-operations)
- [מבנה / ארכיטקטורה של הפרויקט](#architecture)
  - [תיאור מסך הפתיחה – מה הוא מכיל והאם משמש נקודת ניווט](#opening-screen)
  - [שלב תכנון ותיעוד מסכי הפרויקט](#screen-design)
    - [כותרת / שם / תפקיד המסך](#screen-name)
    - [תאור המסך (איזה מידע מציג, מה ניתן לבצע)](#screen-description)
    - [תמונת מסך](#screen-image)
  - [תרשים מסכים המתאר את היררכיית המסכים והמעברים ביניהם (Screen flow diagram)](#screen-flow)
  - [תיאור מחלקות הפרויקט](#class-design)
    - [תיאור UML של המחלקות לרבות קשרים ביניהם](#uml)
- [מימוש הפרויקט](#implementation)
  - [שם מחלקה](#class-name)
  - [תפקיד המחלקה](#class-purpose)
  - [הסבר כל תכונות המחלקה לרבות תכונות סטטיות](#class-properties)
    - [תחום הכרה](#property-scope)
    - [תפקיד ושימוש](#property-purpose)
  - [הסבר קצר של הפעולות במחלקה](#class-methods)
  - [בסיס נתונים](#database)
    - [סקירת בסיס הנתונים](#database-overview)
    - [פעולות על / עם בסיס הנתונים](#database-operations)
- [מדריך למשתמש](#user-guide)
  - [גרסאות עליהם נבדק הפרויקט (סוגי מכשירים / אמולטורים)](#tested-versions)
  - [תיאור אופן הפעולה של הפרויקט](#usage)
  - [הודעות למשתמש](#user-messages)
- [סיכום אישי / רפלקציה](#reflection)
  - [תיאור תהליך העבודה על הפרויקט, ההצלחות, האתגרים, הקשיים ודרכי הפתרון](#work-process)
  - [תהליך למידה - תיאור הלמידה שהתקיימה, תכולות חדשות שנלמדו באופן עצמאי](#learning-process)
  - [אילו כלים נלקחים להמשך](#future-tools)
  - [תובנות מהתהליך, לרבות עזרה ממומחים, שיתוף מידע ולמידת עמיתים](#insights)
  - [בראייה לאחור, האם היית מיישם אחרת חלקים בפרויקט](#retrospective)
  - [במידה והיו ברשותך משאבים נוספים, האם וכיצד ניתן לשפר את הפרויקט](#improvements)
- [ביבליוגרפיה](#bibliography)
- [נספחים](#appendices)
  - [קוד המחלקות של הפרויקט](#source-code)


---

<a id="introduction"></a>
# מבוא

<a id="project-background"></a>
## הרקע לפרויקט

<a id="project-name"></a>
### שם הפרויקט

=== שם הפרויקט ===

<a id="project-description"></a>
### תיאור קצר של הפרויקט

<a id="target-audience"></a>
### קהל היעד

<a id="topic-selection"></a>
### הסיבות לבחירת הנושא


<a id="research"></a>
## תהליך המחקר

<a id="research-findings"></a>
### נקודות עיקריות במחקר לצורכי הפרויקט

<a id="domain-research"></a>
#### מחקר על תחום ידע

<a id="existing-applications"></a>
#### בדיקת אפליקציות קיימות

<a id="market-review"></a>
#### סקירת המצב הקיים בשוק


<a id="challenges"></a>
## אתגרים מרכזיים

<a id="development-problems"></a>
### בעיות איתם הלומד התמודד במהלך פיתוח הפרויקט

<a id="project-need"></a>
### על איזה צורך הפרויקט עונה / איזה פתרון הפרויקט הזה בא לתת

<a id="evaluated-solutions"></a>
### הצגת פתרונות לבעיה (הפתרונות שנבחנו במסגרת המחקר המקדים)


<a id="innovations"></a>
## חידושים, התאמות ועדכונים של אלמנטים טכנולוגיים, עיצוביים ואחרים בפרויקט


<a id="domain-description"></a>
## תיאור תחום הידע - פרק מילולי

<a id="required-objects"></a>
### אובייקטים נחוצים

<a id="data-types"></a>
### סוגי נתונים

<a id="data-representation"></a>
### ייצוג מידע

<a id="data-operations"></a>
### תאור פעולות על המידע


---

<a id="architecture"></a>
# מבנה / ארכיטקטורה של הפרויקט

<a id="opening-screen"></a>
## תיאור מסך הפתיחה – מה הוא מכיל והאם משמש נקודת ניווט

<a id="screen-design"></a>
## שלב תכנון ותיעוד מסכי הפרויקט

<a id="screen-name"></a>
### כותרת / שם / תפקיד המסך

=== שם המסך ===

<a id="screen-description"></a>
### תאור המסך (איזה מידע מציג, מה ניתן לבצע)

<a id="screen-image"></a>
### תמונת מסך

=== תמונת מסך ===


<a id="screen-flow"></a>
## תרשים מסכים המתאר את היררכיית המסכים והמעברים ביניהם (Screen flow diagram)

=== תרשים מסכים ===


<a id="class-design"></a>
## תיאור מחלקות הפרויקט

<a id="uml"></a>
### תיאור UML של המחלקות לרבות קשרים ביניהם

=== תרשים UML ===


---

<a id="implementation"></a>
# מימוש הפרויקט

<a id="class-name"></a>
## שם מחלקה

=== שם המחלקה ===

<a id="class-purpose"></a>
## תפקיד המחלקה

<a id="class-properties"></a>
## הסבר כל תכונות המחלקה לרבות תכונות סטטיות

<a id="property-scope"></a>
### תחום הכרה

<a id="property-purpose"></a>
### תפקיד ושימוש

<a id="class-methods"></a>
## הסבר קצר של הפעולות במחלקה


<a id="database"></a>
## בסיס נתונים

<a id="database-overview"></a>
### סקירת בסיס הנתונים

<a id="database-operations"></a>
### פעולות על / עם בסיס הנתונים


---

<a id="user-guide"></a>
# מדריך למשתמש

<a id="tested-versions"></a>
## גרסאות עליהם נבדק הפרויקט (סוגי מכשירים / אמולטורים)

<a id="usage"></a>
## תיאור אופן הפעולה של הפרויקט

<a id="user-messages"></a>
## הודעות למשתמש


---

<a id="reflection"></a>
# סיכום אישי / רפלקציה

<a id="work-process"></a>
## תיאור תהליך העבודה על הפרויקט, ההצלחות, האתגרים, הקשיים ודרכי הפתרון

<a id="learning-process"></a>
## תהליך למידה - תיאור הלמידה שהתקיימה, תכולות חדשות שנלמדו באופן עצמאי

<a id="future-tools"></a>
## אילו כלים נלקחים להמשך

<a id="insights"></a>
## תובנות מהתהליך, לרבות עזרה ממומחים, שיתוף מידע ולמידת עמיתים

<a id="retrospective"></a>
## בראייה לאחור, האם היית מיישם אחרת חלקים בפרויקט

<a id="improvements"></a>
## במידה והיו ברשותך משאבים נוספים, האם וכיצד ניתן לשפר את הפרויקט


---

<a id="bibliography"></a>
# ביבליוגרפיה


---

<a id="appendices"></a>
# נספחים

<a id="source-code"></a>
## קוד המחלקות של הפרויקט
```

