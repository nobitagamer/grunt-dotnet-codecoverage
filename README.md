# grunt-dotnet-codecoverage
[![Gitter](https://badges.gitter.im/Join Chat.svg)](https://gitter.im/marcofranssen/grunt-dotnet-codecoverage?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

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

#### options.target
Type: `String`
Default value: ``

A string value pointing to the target being executed by opencover executable. Files provided in the source will be used as the arguments for this target.

#### options.output
Type: `String`
Default value: `reports/codecoverage`

A string value pointing to the folder where the reports should be generated.

#### options.registerUser
Type: `Boolean`
Default value: `undefined`

A boolean value indictating if the `-register:user` switch should be added to the generated command.

#### options.reportTypes
Type: `Array`
Default value: `undefined`

An Array value indicating which report types should be generated by reportgenerator.

### Usage Examples

The toolsPath in this example points to the opencover nuget package tools folder. The report will be stored in the reports folder relative to your grunt file. The specs target will execute all dll's ending with `Spec.dll` located in all `bin/Debug` folders within the `test/src` folder. 

```js
grunt.initConfig({
  codecoverage: {
    options: {
      opencoverExe: 'test/src/packages/OpenCover.4.5.2316/OpenCover.Console.exe',
      reportGeneratorExe: 'test/src/packages/ReportGenerator.1.9.1.0/ReportGenerator.exe',
      target: 'test/src/packages/Machine.Specifications.0.6.2/tools/mspec-clr4.exe',
      output: 'reports/codecoverage',
      registerUser: true,
      reportTypes: ['html', 'xml']
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
