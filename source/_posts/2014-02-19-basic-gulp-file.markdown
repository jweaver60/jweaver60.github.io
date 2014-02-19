---
layout: post
title: "Basic Gulp Setup"
date: 2014-02-19 10:23:33 -0500
comments: true
categories: [JavaScript, Automation, Tasks] 
---

[Gulp](http://www.gulpjs.com) is a JavaScript task runner designed to automate repetitive tasks in your development workflow, so you can focus on the important things in your app. Gulp is very flexible, but for most of us, there are some things we use in almost all of our projects. Personally, I'm always going to use SCSS, minify and lint my JS, and optimize images. To make that easier, I have a basic Gulp file that I use for my projects. This lets me get up and running even more quickly. I thought I'd share this with you. Tweak it to your own preferences and workflow, and if you have anything to add let me know!
<!--more-->
First, make sure you have gulp installed globally. Gulp requires [Node.js](http://www.nodejs.org), so if you don't have that install it first. It's easy to install, Mac users can even use Homebrew: 

`brew install node`

And then:

`npm install -g gulp`

This will install the gulp CLI tool and all of it's dependencies globally.

Next, create a `package.json` file in the root of your project directory. It should look something like this:
``` json
{
  "title": "Your Title",
  "devDependencies": {
    "gulp": "~3.5.1",
    "gulp-minify-css": "~0.2.0",
    "gulp-sass": "~0.6.0"
  }
}
```
Now run `npm install` from your project directory. After that you can create your `gulpfile.js`, or copy this one:
``` javascript
var gulp = require('gulp');
var minifycss = require('gulp-minify-css');
var sass = require('gulp-sass');

gulp.task('css', function() {
	return gulp.src('assets/styles/scss/app.scss')
		.pipe(sass())
		.pipe(minifycss())
		.pipe(gulp.dest('assets/styles/min'));
});

gulp.task('js', function() {
	return gulp.src(['assets/libs/foundation/js/foundation.min.js', 'assets/libs/moment/min/moment.min.js'])
		.pipe(gulp.dest('assets/js'));
});

gulp.task('default', function() {
	gulp.watch('assets/styles/scss/*.scss', ['css']);
});
```
This is a simple setup, designed to watch and compile SCSS files, as well as copy over any necessary packages installed from Bower. Obviously, change your paths to match your project structure.
