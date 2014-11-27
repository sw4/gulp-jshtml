gulp-jshtml
======

Gulp plugin to convert passed HTML streams to Javascript


Usage
---
```javascript
jshtml = require('gulp-jshtml'),
gulp.task('jshtml', function() {
	return gulp.src('src/**/*.html', {
            base: './'
        })
        .pipe(jshtml({
        	varname:"templates"
        }))        
        .pipe(gulp.dest('dist/'))		
});
```


Options
---
`invoke` (Optional) Function to invoke, passed compiled HMTL and template location. Defaults to `jshtml`. e.g. the content of `C:\MyPath\MyDirectory\MyFile.html` is passed to `jshtml(compiledHTML, 'C:\MyPath\MyDirectory\MyFile.html')`
