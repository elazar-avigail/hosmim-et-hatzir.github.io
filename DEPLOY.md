# פריסה ל-GitHub Pages

אם מתקבל מסך `404 — הקובץ לא נמצא`, זה בדרך כלל אומר שהקובץ עוד לא נמצא בענף שממנו GitHub Pages מפרסם, או שהכתובת לא מתאימה לסוג ה-repo.

## 1. אם זה repo ראשי של המשתמש או הארגון

שם ה-repo חייב להיות בדיוק:

```text
USERNAME.github.io
```

ואז הכתובות יהיו:

```text
https://USERNAME.github.io/
https://USERNAME.github.io/city.html
```

## 2. אם זה repo רגיל / repo של פרויקט

אם שם ה-repo הוא למשל:

```text
hosmim-et-hatzir
```

אז הכתובות יהיו עם שם ה-repo באמצע:

```text
https://USERNAME.github.io/hosmim-et-hatzir/
https://USERNAME.github.io/hosmim-et-hatzir/city.html
```

במקרה כזה כתובת כמו `https://USERNAME.github.io/city.html` תחזיר 404, כי GitHub Pages יחפש את הקובץ ב-root של אתר המשתמש ולא בתוך אתר הפרויקט.

## 3. בדיקת הגדרות Pages

ב-GitHub צריך להיכנס ל:

```text
Settings → Pages
```

ולוודא:

1. GitHub Pages פעיל.
2. ה-branch הנכון נבחר, למשל `main` או `gh-pages`.
3. התיקייה הנכונה נבחרה, למשל `/root` או `/docs`.
4. הקובץ `city.html` נמצא באותו branch ותיקייה שמוגדרים לפריסה.

## 4. מה נוסף כאן

בגרסה הזאת יש שני עמודים:

```text
index.html  — העמוד הרגיל
city.html   — עותק עצמאי של גרסת העיר המלאה
```

אם רוצים לראות את גרסת העיר, צריך לפתוח את `city.html` בכתובת שמתאימה לסוג ה-repo לפי סעיפים 1 או 2.

## 5. אם האתר כבר פורסם ועדיין רואים 404

נסו:

1. להמתין דקה-שתיים אחרי merge / push.
2. לרענן בכוח: `Ctrl + Shift + R` או `Cmd + Shift + R`.
3. לפתוח בחלון גלישה בסתר.
4. לבדוק ב-`Actions` או ב-`Settings → Pages` אם הפריסה נכשלה.


## 6. פריסה אוטומטית דרך GitHub Actions

נוסף workflow בשם:

```text
.github/workflows/pages.yml
```

כדי להשתמש בו בריפו שלך:

1. ודא שהקבצים נמצאים ב-branch `main`, `master` או `work`.
2. היכנס ל-`Settings → Pages`.
3. תחת `Build and deployment`, בחר `Source: GitHub Actions`.
4. חזור ללשונית `Actions` והרץ את `Deploy static site to GitHub Pages`, או בצע push חדש.
5. בסיום הריצה, GitHub יציג את כתובת האתר שפורסם.

אם רואים הודעה באנגלית `There isn't a GitHub Pages site here`, זה סימן ש-GitHub Pages עוד לא הופעל לריפו/חשבון הזה או שלא הסתיימה פריסה מוצלחת.
