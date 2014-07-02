# [gulp](http://gulpjs.com)-loopback-sdk-angular [![Build Status](https://travis-ci.org/zimlin/gulp-loopback-sdk-angular.svg?branch=master)](https://travis-ci.org/zimlin/gulp-loopback-sdk-angular)

> gulp plugin for auto-generating Angular $resource services for LoopBack.
> It is a port from their Grunt plugin [here](https://github.com/strongloop/grunt-loopback-sdk-angular)

Since strongloop didn't get around to this yet, I just quickly put this together. I'll maintain this until they fork it and take over.

## Install

```sh
$ npm install --save-dev gulp-loopback-sdk-angular
```


## Usage

```js
var gulp = require('gulp');
var rename = require('gulp-rename');
var loopbackAngular = require('gulp-loopback-sdk-angular');

gulp.task('default', function () {
	return gulp.src('./server/app.js')
		.pipe(loopbackAngular())
    .pipe(rename('lb-services.js'))
		.pipe(gulp.dest('./client/js'));
});
```


## API

### loopbackAngular(options)

#### options

##### options.ngModuleName

Type: `String`
Default: `lbServices`

Name for the generated AngularJS module.

##### options.apiUrl

Type: `String`
Default: The value configured in the LoopBack application via app.set('restApiRoot') or `/api`

## Everything Else

[http://docs.strongloop.com/display/LB/AngularJS+JavaScript+SDK]


## License

MIT © [Zi Ming Lin](https://github.com/zimlin)
