# JavaScript

Standards and tooling related to JavaScript language use at Appcelerator.

## To test

1. Copy `.jshintrc` and `.jscsrc` into your project root
2. Create a `Gruntfile.js` file:
	
		module.exports = function (grunt) {

			// make sure to update this to point to your files
			var files = ['*.js'];

			// Project configuration.
			grunt.initConfig({
				jshint: {
					options: {
						jshintrc: true
					},
					src: files
				},
				jscs: {
					options: {
						config: '.jscsrc',
						reporter: 'inline'

					},
					src: files
				}
			});

			// Load grunt plugins for modules
			grunt.loadNpmTasks('grunt-contrib-jshint');
			grunt.loadNpmTasks('grunt-jscs');

			// register tasks. You might do this under a test 'test'
			grunt.registerTask('default', ['jshint', 'jscs']);
		};

3. Add the following lines to package.json:

		"scripts": {
			"test": "grunt"
		},
		...
		"devDependencies": {
			"grunt-cli": "*",
			"grunt-contrib-jshint": "^0.10.0",
			"grunt-jscs": "^1.5.0",
			"jscs-jsdoc": "^0.4.5",
		},

4. Run `npm install` to install new dependencies
5. Run `npm test` or whichever npm script will run the grunt task

## Sublime Text

1. Copy `.jsbeautifyrc` into your project root
2. Use [HTML-CSS-JS Prettify](https://packagecontrol.io/packages/HTML-CSS-JS%20Prettify) to auto-format with `.jsbeautifyrc`
3. Use [SublimeLinter-jshint](https://packagecontrol.io/packages/SublimeLinter-jshint) to lint with `.jshintrc`
4. Use [SublimeLinter-jscs](https://packagecontrol.io/packages/SublimeLinter-jscs) to lint with `.jscrc`