# gulp-movilizer-report-html
Plugin to ease the extraction of the final html file from the Movilizer HTML5 Forms framework.

This plugin save

## Config
Add the following task to your `gulpfile.js`:

```javascript
gulp.task('report.html', ['build.debug'], function () {
    return gulp.src('build/index.html')
        .pipe(reportHtml({
            inject: 'scripts/print_brigde.js',
            timeout: 20000
        }))
        .pipe(gulp.dest('report/'));
});
```

## Output
The plugin returns a HTML file with the original name plus the following appendix '-return'.

## Options
These options are available in the plugin:

 - inject (optional): js file to be injected before running the html file through phantomjs (relative to cwd, project root)
 - timeout (optional): time in milliseconds to consider that phantomjs has failed in its execution. Default: 5000 milliseconds

## Requisites
Needed tools:
 - nodejs v5.x.x (https://nodejs.org/)
 - npm v3.x.x (https://www.npmjs.com/)
 - git

## Development setup
Open a command line in your projects folder and run the following commands:
```bash
git clone https://github.com/Movilizer/gulp-movilizer-report-html.git
cd gulp-movilizer-report-html
npm install
```

## Commands available

* `npm run clean` - Cleans the dist and build folders
* `npm run build` - Generates all files for the project in the build folder
