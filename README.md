# Webpack - The Good Parts

* Network: concat - concat18

* [Slides](https://presentations.survivejs.com/webpack-the-good-parts/#/1)
* [Book](https://survivejs.com/webpack/)

## Schedule

**02.03.2018**

* 13:00-16:00 - Session, break somewhere in between
* 16:00-17:00 - Freeform and Tobias

## Goals

* Webpack and Angular - CLI. Check it out.
* Basics - can it replace RequireJS? Yes. Look into aliasing! [amd-to-es6](https://www.npmjs.com/package/amd-to-es6), [requirejs-es2015](https://www.npmjs.com/package/requirejs-es2015)?
* [Packaging and delivering applications.](https://survivejs.com/maintenance/packaging/)
* create-react-app - check out configuration.
* Ionic and webpack.
* ~~Difference compared to Grunt.~~
* Vue and webpack.

## Examples

### Resolve

```javascript
const config = {
  resolve: {
    alias: { // import foo from "foo";
      foo: path.join(__dirname, "foo")
    },
    extensions: [ // import foo from "foo";
      ".jsx"
    ],
    modules: [ // import foo from "foo"
      "my_modules", "node_modules",
    ],
  },
};
```

### Loader

```javascript
module.exports = input => input + input;
```

### Loader Order

```javascript
use: ["style-loader", "css-loader"]
```

read as

```javascript
styleLoader(cssLoader(input))
```

### `oneOf` and `resourceQuery`

```
import "./bar.png?internal";
import "./foo.png?external";
```