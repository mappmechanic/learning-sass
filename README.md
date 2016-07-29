# learning-sass
Learning SASS Tutorial by Rahat Khanna

# Steps for Running SASS Normally and then using GULP

## Step 1: Install Gulp Globally

`npm install -g gulp`

## Step 2: Install Ruby for SASS if you do not having
For Windows, download Ruby from:
`http://rubyinstaller.org/`

For Mac: Ruby is preinstalled. If not then run,

`brew install ruby`

## Step 3:
Install SASS Gem for Ruby

`gem install sass`
`sass -v`

## Step 4:
Make a new File custom.scss and run this following command:
`sass --watch custom.scss:custom.css`

## Step 5:
Install gulp and gulp-sass as local dependency

`npm install gulp --save-dev`

## Step 6:

Make a new Gulpfile.js

```javascript
var gulp = require('gulp');
var sass = require('gulp-sass');

gulp.task('styles', function() {
    gulp.src('sass/**/*.scss')
        .pipe(sass().on('error', sass.logError))
        .pipe(gulp.dest('./css/'))
});

//Watch task
gulp.task('default',function() {
    gulp.watch('sass/**/*.scss',['styles']);
});
```
