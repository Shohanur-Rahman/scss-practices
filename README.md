# scss-practices
Syntactically Awesome Style Sheets (Sass)

# Pre process
- Install Node JS
- Create a Folder Like scss-practices
- Create a index.html file
- Create a index.scss file
- Create gulpfile.js
- Init npm package.json
```
npm init
```
- Paste the following code to gulpfile.js

```
const {src, dest, watch, series} = require('gulp')
const sass = require('gulp-sass')(require('sass'))

function buildStyles() {
return src('*.scss')
    .pipe(sass())
    .pipe(dest('./css'));
};


function watchTask(){
watch(['*.scss'], buildStyles);
}

exports.default = series(buildStyles, watchTask)
```

- Install Gulp sass 
```
npm install sass gulp-sass --save-dev
```

- VS terminal type gulp and hit enter
```
gulp
```
-if error install following packages via CLI: Error

* Gulp - The term 'gulp' is not recognized as the name of a cmdlet
```
npm -g install gulp
```
then
```
npm -g install gulp-cli
```
then
```
npm install gulp gulp-cli
```

- Hit gulp again in your terminal

* Error: ps1 cannot be loaded because running scripts is disabled on this system
```
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy Unrestricted
```
- Hit gulp 
- Open index.html in browser.

# Variable Declearation in SCSS
- Declear a variable by using $
- Examples:
```
$primaryColor: #326dee;
$secondaryColor: #1ac888;
$errorColor: #d32752;
$infoColor: #f6c31c;
$alignCenter: center;
$h100: 100%;
$basePadding: 15px;
$whiteColor: #fff;
$textUppercase: uppercase;
```

# Import variables in SCSS
- Create a file like variable.scss
- Declear your variables here like
```
$themeColor: #000;
```
- Import variable files in your index.SCSS or any .SCSS files
```
@import 'variables';
```
Not need to file name extension

# Project Structure
- Create a folder for shinobi
- Create a .scss file in shinobi folder call _base.scss
- Make your _base.scss by your own code: Example
```
@import url('https://fonts.googleapis.com/css2?family=Barlow:wght@200&family=Roboto:wght@100&display=swap');
*{
    color: inherit;
    margin: 0;
}
html{
    padding: 0;
    margin: 0;
}
body{
    font-family: 'Barlow', sans-serif;
    margin: 0;
    padding: 0;
}
ul{
    padding: 0;
    list-style: none;
}
a{
    text-decoration: none;
    color: #000;
}
hr{
    border: 0;
    border-top: 1px solid #efefef;
}
```
- Modify your gulpfile.js
```
const {src, dest, watch, series} = require('gulp')
const sass = require('gulp-sass')(require('sass'))

function buildStyles() {
  return src('shinobi/**/*.scss')
    .pipe(sass())
    .pipe(dest('./css'));
};


function watchTask(){
  watch(['shinobi/**/*.scss'], buildStyles);
}

exports.default = series(buildStyles, watchTask)
```
- Modify _index.scss inside shinobi folder 
```
// variables & functions goes here
@import 'variables';

// base goes here
@import 'base';

// colors goes here

// compononent(button,card,navbar etc) goes here

// utilitiies goes here (margin class, paddign class, opacity etc)
```