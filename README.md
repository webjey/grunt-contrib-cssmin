# grunt-contrib-cssmin [![Build Status](https://secure.travis-ci.org/gruntjs/grunt-contrib-cssmin.png?branch=master)](http://travis-ci.org/gruntjs/grunt-contrib-cssmin)

> Compress CSS files.



## Getting Started
This plugin requires Grunt `~0.4.0`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-contrib-cssmin --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-contrib-cssmin');
```

*This plugin was designed to work with Grunt 0.4.x. If you're still using grunt v0.3.x it's strongly recommended that [you upgrade](http://gruntjs.com/upgrading-from-0.3-to-0.4), but in case you can't please use [v0.3.2](https://github.com/gruntjs/grunt-contrib-cssmin/tree/grunt-0.3-stable).*



## Cssmin task
_Run this task with the `grunt cssmin` command._

Task targets, files and options may be specified according to the grunt [Configuring tasks](http://gruntjs.com/configuring-tasks) guide.

Files are compressed with [clean-css](https://github.com/GoalSmashers/clean-css).
### Options

#### banner

Type: `String`
Default: `null`

Prefix the compressed source with the given banner, with a linebreak inbetween.

#### keepSpecialComments

Type: `String` `Number`
Default: `'*'`

To keep or remove special comments, exposing the underlying option from [clean-css](https://github.com/GoalSmashers/clean-css).. `'*'` for keeping all (default), `1` for keeping first one, `0` for removing all.

#### report
Choices: `false`, `'min'`, `'gzip'`
Default: `false`

Either do not report anything, report only minification result, or report minification and gzip results.
This is useful to see exactly how well clean-css is performing but using `'gzip'` will make the task take 5-10x longer to complete.

Example ouput using `'gzip'`:

```
Original: 198444 bytes.
Minified: 101615 bytes.
Gzipped:  20084 bytes.
```
### Usage Examples

```js
cssmin: {
  compress: {
    files: {
      'path/to/output.css': ['path/to/input_one.css', 'path/to/input_two.css']
    }
  },
  with_banner: {
    options: {
      banner: '/* My minified css file */'
    },
    files: {
      'path/to/output.css': ['path/to/**/*.css']
    }
  }
}
```


## Release History

 * 2013-03-13   v0.5.0   Support for 'report' option (false by default)
 * 2013-03-09   v0.4.2   Add banner option Support clean-css keepSpecialComments
 * 2013-02-16   v0.4.1   Update clean-css dependency to ~0.10.0
 * 2013-02-14   v0.4.0   First official release for Grunt 0.4.0.
 * 2013-01-22   v0.4.0rc7   Updating grunt/gruntplugin dependencies to rc7. Changing in-development grunt/gruntplugin dependency versions from tilde version ranges to specific versions.
 * 2013-01-08   v0.4.0rc5   Updating to work with grunt v0.4.0rc5. Switching to this.files api.
 * 2012-10-31   v0.3.2   Update clean-css dep.
 * 2012-10-11   v0.3.1   Rename grunt-contrib-lib dep to grunt-lib-contrib.
 * 2012-09-22   v0.3.0   Options no longer accepted from global config key.
 * 2012-09-09   v0.2.0   Refactored from grunt-contrib into individual repo.

---

Task submitted by [Tim Branyen](http://goingslowly.com/)

*This file was generated on Thu Mar 14 2013 17:50:54.*
