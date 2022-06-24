# scss-practices
Syntactically Awesome Style Sheets (Sass)

# Pre process
- Install Node JS
- Create a Folder Like scss-practices
- Create a index.html file
- Create a index.scss file
- Create gulpfile.js
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
  watch('*.scss', buildStyles);
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
