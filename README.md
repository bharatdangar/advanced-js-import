## INSTALL

```
npm install advanced-js-import --save-dev
```
## USAGE

First, install `advanced-js-import` as a devDependency:

Then add it to the gulpfile.js:


```
var gulp = require('gulp');
var jsImport = require('advanced-js-import');

gulp.task('import', function() {
  return gulp.src('index.js')
        .pipe(jsImport({
            hideConsole: true,
            importStack: true
        }))
        .pipe(gulp.dest('dist'));
});
```

Final, run import task where you need, eg: `gulp import`

## DEMO

you can get all code [here](https://github.com/bharatdangar/advanced-js-import)

### File Tree

this is the file tree:

```
demo
|
-- widget
|   |
|   -- widget.js
|   |
|   -- config.js
|   
-- index.js
|   
-- gulpfile.js
|   
-- package.json
```
### Brief Intorduce
index.js:


```
// index.js

@import './widget/widget.js'

output(config);

// index.js end
```

in `index.js`, you can use `@import 'xxx.js'` when you want import a js file

### Run

Enter the `demo` directory in command

```
cd demo
```
Install `gulp` `advanced-js-import` 

```
gulp install
```
Compile files

```
gulp import
```
You could see a js file `dist/index.js` like this:

```
// index.js
// widget.js
// config.js
var config = 'this is config value';
// config.js end

function output(str) {
  console.log(str);
}
// widget.js end

output(config);
// index.js end
```
