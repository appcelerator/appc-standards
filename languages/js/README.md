# JavaScript

Standards and tooling related to JavaScript language use at Appcelerator.

## To Use

1. Create a Gruntfile.js file:
  
        module.exports = function (grunt) {
        // Project configuration.
          grunt.initConfig({
            appcJs: {
              src: ['Gruntfile.js', 'apidoc/**/*.js', '!apidoc/node_modules/**']
            },
                clangFormat: {
                    src: [] // unused ATM
                },
        	});
        
        	// Load grunt plugins for modules
          grunt.loadNpmTasks('grunt-appc-js');
    
          // register tasks
          grunt.registerTask('lint', ['appcJs']);
        
          // register tasks
          grunt.registerTask('default', ['lint']);
        };

2. Add the following lines to package.json:

      	"scripts": {
      		"test": "grunt"
      	},
      	...
        "devDependencies": {
          "grunt-cli": "*",
          "grunt-appc-js": "*"
        },

3. Run `npm install` to install new dependencies
4. Run `npm test` or whichever npm script will run the grunt task
