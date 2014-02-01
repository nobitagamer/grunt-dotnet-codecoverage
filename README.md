# grunt-dotnet-codecoverage

> Grunt plugin to generate code coverage report using opencover and reportgenerator

## Getting Started
This plugin requires Grunt `~0.4.2`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-dotnet-codecoverage --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-dotnet-codecoverage');
```

## The "codecoverage" task

### Overview
In your project's Gruntfile, add a section named `codecoverage` to the data object passed into `grunt.initConfig()`.

```js
grunt.initConfig({
  codecoverage: {
    options: {
      // Task-specific options go here.
    },
    your_target: {
      // Target-specific file lists and/or options go here.
    },
  },
});
```

### Options

#### options.opencoverExe
Type: `String`
Default value: ``

A string value pointing to the open cover executable.

#### options.reportGeneratorExe
Type: `String`
Default value: ``

A string value pointing to the report generator executable.

#### options.output
Type: `String`
Default value: `reports/codecoverage`

A string value pointing to the folder where the reports should be generated.

### Usage Examples

The toolsPath in this example points to the opencover nuget package tools folder. The report will be stored in the reports folder relative to your grunt file. The specs target will execute all dll's ending with `Spec.dll` located in all `bin/Debug` folders within the `test/src` folder. 

```js
grunt.initConfig({
  codecoverage: {
    options: {
      opencoverExe: 'test/src/packages/OpenCover.4.5.2316/OpenCover.Console.exe',
      reportGeneratorExe: 'test/src/packages/ReportGenerator.1.9.1.0/ReportGenerator.exe',
      output: 'reports/codecoverage'
    },
    specs: {
      src: ['test/src/**/bin/Debug/*Specs.dll']
    }
  },
});
```

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [Grunt](http://gruntjs.com/).

## Release History
_(Nothing yet)_
