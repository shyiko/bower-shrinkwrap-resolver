# bower-shrinkwrap-resolver

Missing shrinkwrap for Bower.

## Integration

> Bower must be >= **1.5** (tested on Bower 1.7.7).

1. (within project directory) `npm install bower-shrinkwrap-resolver --save-dev`
2. Add `bower-shrinkwrap-resolver` [resolver](http://bower.io/docs/pluggable-resolvers) to `.bowerrc`, like so:
```json 
{
  "resolvers": [
    "bower-shrinkwrap-resolver"
  ]
}
```

That's it.

> If `bower` is installed globally - `bower-shrinkwrap-resolver` have to `npm i -g ...` too.
  Otherwise you'll get `Cannot find module 'bower-shrinkwrap-resolver'`. 

## Usage

`bower install` (with or without parameters) will automatically generate (and update) `bower-shrinkwrap.json`.  

**CLI**
* `--no-shrinkwrap` - ignore an available shrinkwrap file.
* `--strict-shrinkwrap` - fail if bower tries to install dependency that is missing in `bower-shrinkwrap.json`.
* `--reset-shrinkwrap` - regenerate `bower-shrinkwrap.json` 
(e.g. `bower i --reset-shrinkwrap` is equivalent to `rm bower-shrinkwrap.json && bower i`).

> Debug logging can be turned with `NODE_DEBUG=bower-shrinkwrap-resolver bower ...`.

## Configuration

You can turn off shrinkwrap generation by default by changing your `.bowerrc` to
```json 
{
  "resolvers": [
    "bower-shrinkwrap-resolver"
  ],
  "bower-shrinkwrap-resolver": {
    "shrinkwrap": false
  }
}
```
Adding `--shrinkwrap` after `bower install` will force shrinkwrap generation.  

You can also set the value of `strict-shrinkwrap` (`false` by default).

## License

[MIT License](https://github.com/shyiko/bower-shrinkwrap-resolver/blob/master/mit.license)
