*This repository is a mirror of the [component](http://component.io) module [timoxley/get](http://github.com/timoxley/get). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/timoxley-get`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# get

Create functions for use with functional methods like  `map`, `reduce`,
`filter`, etc. that get object properties without need of anonymous wrappers.

[![NPM](https://nodei.co/npm/timoxley-get.png)](https://nodei.co/npm/timoxley-get/)

[![Build Status](https://travis-ci.org/timoxley/get.png?branch=master)](https://travis-ci.org/timoxley/get)
[![Dependency Status](https://david-dm.org/timoxley/get.png)](https://david-dm.org/timoxley/get)

## Installation

### Browser
    $ component install timoxley/get

See [Components](https://github.com/component/component/)

### Node
    $ npm install timoxley-get

_Sorry for namespaced package, all good names taken._

## Examples

### Before:
Horrible anonymous wrapper is required to map the `length` property.

```js
['apple', 'banana', 'pineapple'].map(function(str) {
 return str.length
})
// => [5, 6, 9]
```

### After
Wow. Much cleaner.

```js
['apple', 'banana', 'pineapple'].map(get('length'))
// => [5, 6, 9]
```

### Use `get` to evaluate methods

```js
// Calls the 'italics' method on each supplied item
['apple', 'banana', 'pineapple'].map(get('italics'))
// => ['<i>apple</i>', '<i>banana</i>', '<i>pineapple</i>']
```

### Use `get` to evaluate methods, passing in arguments

```js
// Calls the 'substr' method, passing in arguments
['apple', 'banana', 'pineapple'].map(get('substr', 0, 1))
// => ['a', 'b', 'p']
```

## Convoluted Description:
Takes a property name, `prop` along with any number of additional
arguments, and returns a function, that takes an object of any type, and
returns the value of `prop` on that object. If `prop` is a method, the
returned value with be the result of evaluating that method, passing in
the the additional arguments.

Turns out this is hard to describe.

## License

  MIT
