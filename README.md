gulp-jshtml
======

[![Build Status](https://img.shields.io/travis/sw4/gulp-jshtml.svg?style=flat-square)](https://travis-ci.org/sw4/gulp-jshtml)
[![Dependency Status](https://img.shields.io/david/sw4/gulp-jshtml.svg?style=flat-square)](https://david-dm.org/sw4/gulp-jshtml)
[![devDependency Status](https://img.shields.io/david/dev/sw4/gulp-jshtml.svg?style=flat-square)](https://david-dm.org/sw4/gulp-jshtml#info=devDependencies)
[![License](http://img.shields.io/badge/license-MIT-green.svg?style=flat-square)](https://github.com/sw4/gulp-jshtml/blob/master/LICENSE-MIT.md)
[![Issues](https://img.shields.io/github/issues/sw4/gulp-jshtml.svg?style=flat-square)](https://github.com/sw4/gulp-jshtml/issues)
[![Release](https://img.shields.io/github/release/sw4/gulp-jshtml.svg?style=flat-square)](https://github.com/sw4/gulp-jshtml/releases)


[![Status](https://badge.fury.io/gh/sw4%2Fgulp-jshtml.png)]()
[![NPM](https://badge.fury.io/js/gulp-jshtml.png)]()

Gulp plugin to convert passed HTML streams to Javascript


Usage
---
```javascript
jshtml = require('gulp-jshtml'),
gulp.task('jshtml', function() {
	return gulp.src('src/**/*.html')
        .pipe(jshtml({
        	invoke:"templates.add"
        }))        
        .pipe(gulp.dest('dist/'))		
});
```

####Considerations

The plugin escapes all relevant characters in the source HTML, collapses tabs / whitespace into a single space and trims the result.

####Options
`invoke` 

(Optional) Function to invoke, passed compiled HMTL and template location. Defaults to `jshtml`. e.g. the content of `C:\MyPath\MyDirectory\MyFile.html` is passed to `jshtml(compiledHTML, 'C:\MyPath\MyDirectory\MyFile.html')`

####Example

######Gulp

```javascript

gulp.src('myDirectory\myFile.html', {
  .pipe(jshtml({
      invoke:"templates.add"
  }))  
```

######HTML (of `myDirectory\myFile.html`)

```html
<div id='myDiv' class='myDiv-css'>
       Some content "here"...can be {anything}	   
</div>
```
######Output JS
```javascript
templates.add("<div id='myDiv' class='myDiv-css'>Some content \"here\"...can be {anything}</div>", "myDirectory\myFile.html");
```
