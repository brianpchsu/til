# Use Babel to start writing ES6

As I concluded in my [blog post](http://www.brianpchsu.com/what-i-learned-from-the-2016-fluent-conference/), ES6 is being adopted by lots of people and companies now. Start writing ES6 is easy, but you might also like to use Babel to transpile your ES6 to ES5 in order to have better browser support.

Here is my process to set up Babel for my Angular 1 + Grunt + Node app.

First, install necessary packages.

```bash
$ npm install --save-dev grunt-babel babel-preset-es2015
```

Then, create babelrc file in your app's root folder with this following line.
```
{
  "presets": ["es2015"]
}
```

And in the Gruntfile.js (assuming your ES6 files are using .es6.js format)

```
grunt.initConfig({
    babel: {
        es6: {
            files: [
                {
                    expand: true,
                    src: ['app/scripts/**/*.es6.js'],
                    ext: '.js'
                }
            ]
        }
    }
  });
```

Put the babel task into your Grunt registerTask.

```
grunt.registerTask('build', [
  'clean:dist',
  'babel:es6',
  'autoprefixer',
  'concat',
  'ng-annotate',
  'copy:dist',
  'cdnify',
  'cssmin',
  'uglify',
  'filerev',
  'usemin',
  'htmlmin'
]);
```

Finally, to watch all the changes in the .es6.js files (and re-transpile)

```
watch: {
  babel: {
    files: ['app/scripts/**/*.es6.js'],
    tasks: ['babel']
  }
}
```

If you use karma, you might also want to exclude pre-compile file out from test. (karma.conf.js)

```
exclude:['app/**/*.es6.js']
```
[source](http://blog.shinetech.com/2015/07/07/es6-with-babel-js/)
