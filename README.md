<p align="center">
  <img src="http://reboundjs.com/assets/images/logos/large.svg" alt="Rebound Logo" width="420px" />
</p>
<h1 align="center">gulp-rebound</h1>
Easily compile your Rebound templates using Gulp!

```Shell
$ npm install gulp-rebound
```

### Overview

In your project's Gulpfile, consume the Gulp Rebound module like this:
``` JavaScript
var gulp = require('gulp');
var rebound = require('gulp-rebound');

gulp.task('rebound', [],  function(){
  return gulp.src(["views/**/*.html", "!views/index.html"])
    .pipe(rebound({
      baseUrl: 'views/',
      baseDest: 'templates/'
    }))
    .pipe(gulp.dest('public/templates'));
});
```

### Options

#### options.baseUrl
Type: `String`
Default value: `''`

The root folder that all your uncompiled Rebound templates' HTML `<import>` tags are relative to. Ex: If your templates are all in the directory `/views` and your HTML import tags are written relative to that directory, then your baseUrl is `views/`. Please note the trailing slash.

#### options.baseDest
Type: `String`
Default value: `''`

A string value that is prefixed to all of your compiled Rebound templates' dependancy paths. Should be set to the directory path in your pubilc directory that the templates are installed. Ex: If your public directory is `/public` and your templates are compiled to `/public/templates` then your baseDest will be `templates/`. Please note the trailing slash.

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality.
