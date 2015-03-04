# Objective-C

Standards and tooling related to Objective-C language use at Appcelerator.

## To Use

1. Copy .clang-format into your project root
2. Create a Gruntfile.js file:
  
    	module.exports = function (grunt) {
    	
        	// Project configuration.
        	grunt.initConfig({
        		clangFormat: {
              src: ['ios/Classes/*.*']
            },
        	});
        
        	// Load grunt plugins for modules
        	grunt.loadNpmTasks('grunt-clang-format');

        	// register tasks. You might do this under a test 'test'
        	grunt.registerTask('format', ['clangFormat']);
        };
3. Add the following lines to package.json:

        "scripts": {
          "test-format": "grunt format"
        },
      	...
        "devDependencies": {
          "grunt-clang-format": "^0.3.0"
        },
4. Run `npm install` to install new dependencies
5. Run `npm test-format` or `grunt format` or whichever npm script will run the grunt task
