# grunt-phantomas

[![Build Status](https://travis-ci.org/stefanjudis/grunt-phantomas.png?branch=master)](https://travis-ci.org/stefanjudis/grunt-phantomas) [![NPM version](https://badge.fury.io/js/grunt-phantomas.png)](http://badge.fury.io/js/grunt-phantomas) [![Dependency Status](https://gemnasium.com/stefanjudis/grunt-phantomas.png)](https://gemnasium.com/stefanjudis/grunt-phantomas) [![Code Climate](https://codeclimate.com/github/stefanjudis/grunt-phantomas.png)](https://codeclimate.com/github/stefanjudis/grunt-phantomas) [![Built with Grunt](https://cdn.gruntjs.com/builtwith.png)](http://gruntjs.com/)

> Grunt plugin for phantomas

## Getting Started
This plugin requires Grunt `~0.4.1`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-phantomas --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-phantomas');
```

## The "phantomas" task

### Overview
In your project's Gruntfile, add a section named `phantomas` to the data object passed into `grunt.initConfig()`.

```js
grunt.initConfig( {
  phantomas: {    	
    gruntSite : {
      options : {
        indexPath : './phantomas/',
        raw       : [],
        url       : 'http://gruntjs.com/'
      }
    }
  }
} )
```

### Options

#### options.indexPath
Type: `String`
Default value: `./phantomas/`

A string value that represents the relative path to the place where `phantomas` will render your metrics. Inside of this folder an `index.html`, a data folder and an assets folder will be created.

#### options.raw
Type: `Array`
Default value: `[]`

An array that represents raw commands that can be passed to `phantomas` executable. See usage examples later on.

#### options.url
Type: `String`
Default value: `http://gruntjs.com/`

A string value that represents the url of the site, which will be analyzed by `phantomas`.

### Usage Examples

#### Default Options
In this example, the default options are used to fetch metrics of `http://gruntjs.com` and render the visualized metrics at `./phantomas`.

```js
grunt.initConfig({
  phantomas: {},
})
```

#### Custom Options
In this example, custom options are used to fetch metrice of `http://yoursite.com` and render the visualized metrics at `./yoursite/`.

```js
grunt.initConfig( {
  phantomas: {    	
    yourSite : {
      options : {
        indexPath : './yoursite/',
        raw       : [],
        url       : 'http://yoursite.com/'
      }
    }
  }
} )
```

#### Raw phantomas options
In this example, the raw option is used to set `phantomas` execution parameters. In this case all external script except the defined ones are blocked by `phantomas`, what can become really handy, when dealing with a lot of third party scripts that influence your site performance.
```js
grunt.initConfig( {
  phantomas: {    	
    yourSite : {
      options : {
        indexPath : './yoursite/',
        raw       : [
            '--no-externals',
            '--allow-domain=cdn.yoursite.com.br,ajax.googleapis.com'
        ],
        url       : 'http://yoursite.com'
      }
    }
  }
} )
```

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [Grunt](http://gruntjs.com/).

## Release History
_(Nothing yet)_
