# Gulp-TypeDoc

[![NPM version](https://badge.fury.io/js/gulp-typedoc.svg)](http://badge.fury.io/js/gulp-typedoc)

## Synopsis


Gulp plugin to execute the TypeDoc tool by Sebastian Lenz
http://typedoc.org
https://github.com/TypeStrong/typedoc

## Installation

Install both gulp-typedoc and typedoc:

```
npm install --save-dev gulp-typedoc typedoc
```

The reason for installing typedoc separately is that it allows you to choose the version of typedoc, independent from the version of gulp-typedoc.

## Usage

The plugin takes an object, of which all properties are passed transparently to typedoc. Pipe in TypeScript files. The documentation files are not piped out.

## Code Example

```javascript
var typedoc = require("gulp-typedoc");

gulp.task("typedoc", function() {
	return gulp
		.src(["data/*.ts"])
		.pipe(typedoc({
			// TypeScript options (see typescript docs)
			module: "commonjs",
			target: "es5",
			includeDeclarations: true,

			// Output options (see typedoc docs)
			out: "./out",
			json: "output/to/file.json",

			// TypeDoc options (see typedoc docs)
			name: "my-project",
			theme: "/path/to/my/theme",
			plugins: ["my", "plugins"],
			ignoreCompilerErrors: false,
			version: true,
		}))
	;
});
```

## Changelog

### 2.0.3

* Don't error when there are no files

### 2.0.2

* Catch any synchronous exceptions from typedoc

### 2.0.1

* Update typedoc URL in README.md (thanks @pascalberger)

### 2.0.0

* Have typedoc as peer dependency (thanks @mizunashi-mana)
* Ensure it works with https://github.com/TypeStrong/typedoc
* Upgrade all packages, replace "del" by "rimraf"
* Fix bugs in README.md

### 1.2.0

* Don't start a child process anymore.
* FIX: having many .ts files no longer causes "command line too long" error.

### 1.1.0

* Allow specifying boolean arguments for typedoc;
* Replace module "gulp-clean" by "del"

### 1.0.6

* Moved to typedoc version 0.2.x

### 1.0.5

* Moved to typedoc version 0.1.x

### 1.0.3

* Use require.resolve() to find typedoc more reliably

### 1.0.2

* Allow any typedoc version 0.0.x

## Contributors

* Rogier Schouten
* Daan Wissing
* Mizunashi Mana
* Pascal Berger

## License

ISC
