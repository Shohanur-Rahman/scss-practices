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
// theme colors
$primary-color: #326dee;
$secondary-color: #1ac888;
$error-color: #d32752;
$info-color: #f6c31c;
$align-center: center;
$white-color: #fff;
$black-color: #000;

// spacing
$base-spacing: 0.75rem;
$base-margin: 0.75rem;


// borders
$base-border-thickness: 1px;
$base-border-radius: 20px;

// box-shadow
$base-box-shadow: 1px 3px 5px rgba(0,0,0,0.1);

// font-size
$base-font-size: 1rem;
$font-size-sm: $base-font-size * 0.75;
$font-size-lg: $base-font-size * 1.5;
$font-size-xl: $base-font-size * 2;
$font-size-xxl: $base-font-size * 3;

// text styling
$base-text-decoration: none;
$underline-text: underline;
$base-letter-spacing: 1px;
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
- Modify index.scss inside shinobi folder 
```
// variables & functions goes here
@import 'variables';

// base goes here
@import 'base';

// colors goes here

// compononent(button,card,navbar etc) goes here

// utilitiies goes here (margin class, paddign class, opacity etc)
```


# Nested Rules
**Lets start a component Like Card Component**
- Create a folder components under shinobi folder
- Create a .scss file called _card.scss
- Style a card design here

# SCSS Arithmetic operations
- SCSS Debug
```
@debug 'Hello World';
```
- SCSS Math functions
```
@use 'sass:math';
@debug math.div(50,5);
@debug math.floor(4.2);
@debug math.clamp(1px, -1px, 10px); // 1px
@debug math.max(50px, 30px, 100px);// 100px
@debug math.min(50px, 30px, 100px); // 30px
```
- More **https://sass-lang.com/documentation/modules/math**