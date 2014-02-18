---
layout: post
title: "Task Runners: Grunt vs. Gulp"
date: 2014-02-18 13:38:13 -0500
comments: true
categories: 
---

I've been a CodeKit user for a pretty long time, and while it's been very useful, the rise of JavaScript task runners like
Grunt and Gulp have given me a chance to rethink how I automate my workflow. CodeKit is great for compiling SASS/LESS?CoffeeScript,
but what it can't do is more project specific tasks, for example, run my tests. Thanks to Node.js, Grunt and Gulp can do everything
CodeKit can, while also having access to the CLI which allows it to automatically run your tests and perform other tasks. 

So that begs the question, Grunt or Gulp? I used Grunt for a while and didn't really see a need to use anything else, it got the
job done. But after I took some time to dig into Gulp, I realized that it was equally powerful but with a much cleaner, more precise
syntax for doing the same things. Let's take the same task, compiling SASS, minifying and concatenating it. In Grunt, that would look
something like this:
``` javascript
module.exports = function(grunt) {

	grunt.initConfig({
	  sass: {
	    dist: {
	      options: {
	        style: 'expanded'
	      },
	      files: {
	        'main.css': 'main.scss',
	        'widgets.css': 'widgets.scss'
	      }
	    }
	  }
	  mincss: {
   		'myproject': {
      	files: {
        	'build/cssoutput.min.css': [ 'src/css/file1.css', 'src/css/file2.css' ]
      	}
    	}
  	},
	});

};
```
Not bad, but look at how much cleaner all of this can be in Gulp:
``` javascript
gulp.task('css', function() {
	return gulp.src('assets/styles/scss/app.scss')
		.pipe(sass())
		.pipe(minifycss())
		.pipe(gulp.dest('assets/styles/min'));
});
```
That's substantially shorter, but how? The answer is in that `.pipe` method, which allows you to send the result of one task into another. 
What this means is that we can put all of our CSS related tasks into one, and just pipe the result of sass compiling into minifying, then minifying
into the destination file. The same is true for JavaScript, images or any other asset. For me, I think it's pretty clear that I'll be using Gulp
as my default task runner for the time being. If you've been using Grunt, give Gulp a try. I think you'll be surprised by just how much time it can 
save you.


