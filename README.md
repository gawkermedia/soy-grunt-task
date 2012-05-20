# soy-grunt-task

Grunt task to compile Soy / Closure Templates

## Getting Started
Install this grunt plugin next to your project's [grunt.js gruntfile][getting_started] with: `npm install grunt-soy`

Then add this line to your project's `grunt.js` gruntfile:

```javascript
grunt.loadNpmTasks('grunt-soy');
```

Configure the soy task in your initConfig call (everything is optional, these are the defaults):

```javascript
grunt.initConfig({
    ...
    soy : {
    	myTargetName : {
	    	src: [ '**/*.soy' ],
	    	inputPrefix : '',
	    	outputPathFormat : 'public/{INPUT_DIRECTORY}/{INPUT_FILE_NAME}.js',
		    codeStyle : 'stringbuilder',
		    locales : [],
		    messageFilePathFormat : undefined,
		    shouldGenerateJsdoc : false,
		    shouldProvideRequireSoyNamespaces : false,
		    compileTimeGlobalsFile : undefined,
		    shouldGenerateGoogMsgDefs : false,
		    bidiGlobalDir : 1
    	}
	}
	...
});
```

* src : an array of glob patterns for finding input files.  matches standard GruntMultiTask syntax.
* inputPrefix : your src patterns will be resolved against this. It will also be passed to the compiler such that the {INPUT_DIRECTORY} format variable is relative to inputPrefix
* All other options are passed directly to the compiler - use [Closure Template docs][https://developers.google.com/closure/templates/docs/javascript_usage#compilation] as a reference for these options.


[grunt]: https://github.com/cowboy/grunt
[getting_started]: https://github.com/cowboy/grunt/blob/master/docs/getting_started.md


## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [grunt][grunt].

## Release History
0.2.0 - basic support - src, inputPrefix, and outputPathPrefix

## Roadmap
- support all the compiler flagsfrom help text - not just ones documented online.
- Include MsgExtractor support? Might be conflating two different tools...


## License
Copyright (c) 2012 Adam Ahmed  
Licensed under the MIT license.
