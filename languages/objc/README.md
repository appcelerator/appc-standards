# Objective-C

Standards and tooling related to Objective-C language use at Appcelerator.

## From the Command-Line

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

## From XCode

1. Copy .clang-format into your project root
2. Install Alcatraz: https://github.com/supermarin/Alcatraz
3. Install clang-format via Alcatraz
4. Set format option to “File”. This will use the .clang-format file from the project root.
5. Select files and format
