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
</style>

# הכנת ANDROID STUDIO לעבודה עם  Markdown 

Markdown הוא דרך פשוטה לכתיבת **תיעוד טכני מובנה באמצעות טקסט רגיל**.
במקום להשקיע זמן בעיצוב ובפורמט, משתמשים במספר קטן של כללים פשוטים ליצירת כותרות, רשימות, קישורים, תמונות, טבלאות וקטעי קוד.
קובצי Markdown נשארים קריאים וקלים לעריכה ישירות מתוך Android Studio או כל עורך טקסט אחר,
ולכן הם מתאימים במיוחד לכתיבת ספר פרויקט הכולל הסברים, תרשימים, צילומי מסך ודוגמאות קוד.

מכיוון ש-Markdown מבוסס על טקסט רגיל, הוא משתלב באופן טבעי עם **Git ועם תהליך פיתוח תוכנה**.
ניתן לעקוב אחר שינויים בדיוק כמו בקוד, לחלק את ספר הפרויקט למספר קבצים או פרקים,
ולבסוף להפיק מאותו תוכן **PDF, אתר HTML או מסמך בפורמט אחר**.
כך ניתן להפריד בין כתיבת התוכן לבין עיצוב והפקת המסמך הסופי, ולשמור את התיעוד כחלק בלתי נפרד מהפרויקט.

## Summary

- בדוק שיש לך גרסת חדשה של Android Studio. צריך להיות: Android Studio Quail 4 | 2026.1.4
- שנה את תצוגת ה MARKDOWN ל- Google Chromium
- התקן את "Mermaid Plugin" של JetBrain
- הגדר תקיית "DOCS" ל כתיבת מסמכים
- בדוק את השינויים

<div class="ltr"> 

## Details

### 1. Check Android Studio Version.

Use "Help ... About" to check the version of your Android Studio.
Should be `Androi Studio Quail 4 | 2026.1.4`

![Check Android Version](images/androdi-studio-version.png)

### 2. Configure the Chrome Preview 

The default runtime for Android Studio is not configured for working with complex HTML.
There is an option to leverage the Chrome engine, making it possible to view complex documents with images, Right-To-Left text, etc.  

1. Select **Ctrl/Shift/A**, and then choose "Choose Boot Runtime for the IDE",

![Choose Boot Java Runtime](images/jcef-runtime.png)

1. Select "25.0.4 JetBrains Runtime JBR with JCEF". Double check the you choose a version without "debug" or "fastdebug" !
2. Click "OK".
3. Android Studio will download he runtime, and after few seconds will offer to restart, accept the restart

![Select JCEF version](images/jcef-version.png)

After restart, change Android Studio to use Chrome for displaying markdown.

1. Select "File ... Setting ... Markdown".
2. In the "Preview Rendering Engine", choose "Chromimum Browser"

![choose-chrome-preview](images/Choose-Chrome.png)

### 3. Install the `Mermaid` plugin

The `Mermaid` tool supports diagrams such as flowcharts, sequence diagrams, state diagrams, class diagrams, and timelines. Because diagrams are stored as text, they are easy to edit, copy, and track with Git alongside the rest of the project documentation.

1. Choose "File ... Setting ... Plugins
2. Enter "Mermaid" - locate the `Mermaid` plugin provided by Jetbrains
3. Click "install".
4. Do not install any of the other plugins that are labeled "Mermaid".

![Mermaid Plugin](images/mermaid-plugin.png)

### 3. Create "docs" folder - next to the "app" folder

 Change to "Project File View", and use "File ... New ... Directory" to create a directory "docs" next to the "app" folder.

![Create docs folder](images/docs-folders.png)


## Test

Create "test.md" file inside the newly create "docs" folder, and paste the test file into it. It should look like below

![Setup Test](images/setup-test.png)

</div>