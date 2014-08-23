# JavaScript Style Guide
---

## Basics
* Use soft-tabs with a two space indent.
* Always use camelCase, never underscores.
* Don't ever use `$.get` or `$.post`. Instead use `$.ajax` and provide both a success handler and an error handler.
* Use `$.fn.on` instead of `$.fn.bind`, `$.fn.delegate` and `$.fn.live`.
* Always to prefix all javascript-based selectors with `js-`.
  (Taken from [slightly obtrusive javascript](http://ozmm.org/posts/slightly_obtrusive_javascript.html))


## Objects
* Use the literal syntax for object creation.

```
// bad
var item = new Object();

// good
var item = {};
```
* Don't use [reserved words](http://es5.github.io/#x7.6.1) as keys. It won't work in IE8.

## Arrays
* Use the literal syntax for array creation.

```
// bad
var items = new Array();

// good
var items = [];
```
* If you don't know array length use Array#push.

```
var someStack = [];

// bad
someStack[someStack.length] = 'abracadabra';

// good
someStack.push('abracadabra');
```
* Use single quotes `''` for strings.

```
// bad
var name = "Bob Parr";

// good
var name = 'Bob Parr';

// bad
var fullName = "Bob " + this.lastName;

// good
var fullName = 'Bob ' + this.lastName;
```
* Strings longer than 80 characters should be written across multiple lines using string concatenation.

```
// bad
var errorMessage = 'This is a super long error that was thrown because of Batman. When you stop to think about how Batman had anything to do with this, you would get nowhere fast.';

// bad
var errorMessage = 'This is a super long error that was thrown because \
of Batman. When you stop to think about how Batman had anything to do \
with this, you would get nowhere \
fast.';

// good
var errorMessage = 'This is a super long error that was thrown because ' +
  'of Batman. When you stop to think about how Batman had anything to do ' +
  'with this, you would get nowhere fast.';
```

## Function
* Function expressions:


```
// anonymous function expression
var anonymous = function() {
  return true;
};

// named function expression
var named = function named() {
  return true;
};

// immediately-invoked function expression (IIFE))
(function() {
  console.log('Welcome to the Internet. Please follow me.');
})();
```

## Variables
* Always use var to declare variables. Not doing so will result in global variables. We want to avoid polluting the global namespace.

```
// bad
superPower = new SuperPower();

// good
var superPower = new SuperPower();
```
* Use one `var` declaration for multiple variables and declare each variable on a newline.

```
// bad
var items = getItems();
var goSportsTeam = true;
var dragonball = 'z';

// good
var items = getItems(),
    goSportsTeam = true,
    dragonball = 'z';
```
* Declare unassigned variables last. This is helpful when later on you might need to assign a variable depending on one of the previous assigned variables.

```
// bad
var i, len, dragonball,
    items = getItems(),
    goSportsTeam = true;

// bad
var i, items = getItems(),
    dragonball,
    goSportsTeam = true,
    len;

// good
var items = getItems(),
    goSportsTeam = true,
    dragonball,
    length,
    i;
```
* Assign variables at the top of their scope. This helps avoid issues with variable declaration and assignment hoisting related issues.

```
// bad
function() {
  test();
  console.log('doing stuff..');

  //..other stuff..

  var name = getName();

  if (name === 'test') {
    return false;
  }

  return name;
}

// good
function() {
  var name = getName();

  test();
  console.log('doing stuff..');

  //..other stuff..

  if (name === 'test') {
    return false;
  }

  return name;
}

```
## Conditional Expressions & Equality
* Use `===` and `!==` over `==` and `!=`.
* Conditional expressions are evaluated using coercion with the ToBoolean method and always follow these simple rules:
    * __Objects__ evaluate to __true__
    * __Undefined__ evaluates to __false__
    * __Null__ evaluates to __false__
    * __Booleans__ evaluate to the value of the __boolean__
    * __Numbers__ evaluate to false if __+0, -0, or NaN__, otherwise __true__
    * __Strings__ evaluate to false if an empty string `''`, otherwise __true__

```
// bad
if (name !== '') {
  // ...stuff...
}

// good
if (name) {
  // ...stuff...
}

// bad
if (collection.length > 0) {
  // ...stuff...
}

// good
if (collection.length) {
  // ...stuff...
}
```
## Blocks
* Use braces with all multi-line blocks.

```
// bad
if (test)
  return false;

// good
if (test) return false;

// good
if (test) {
  return false;
}

// bad
function() { return false; }

// good
function() {
  return false;
}
```

### Comments

* Use `/** ... */` for multiline comments. Include a description, specify types and values for all parameters and return values.

```
// bad
// make() returns a new element
// based on the passed in tag name
//
// @param <String> tag
// @return <Element> element
function make(tag) {

  // ...stuff...

  return element;
}

// good
/**
 * make() returns a new element
 * based on the passed in tag name
 *
 * @param <String> tag
 * @return <Element> element
 */
function make(tag) {

  // ...stuff...

  return element;
}
```

* Use `//` for single line comments. Place single line comments on a newline above the subject of the comment. Put an empty line before the comment.

```
// bad
var active = true;  // is current tab

// good
// is current tab
var active = true;

// bad
function getType() {
  console.log('fetching type...');
  // set the default type to 'no type'
  var type = this._type || 'no type';

  return type;
}

// good
function getType() {
  console.log('fetching type...');

  // set the default type to 'no type'
  var type = this._type || 'no type';

  return type;
}
```

* Prefixing your comments with FIXME or TODO helps other developers quickly understand if you're pointing out a problem that needs to be revisited, or if you're suggesting a solution to the problem that needs to be implemented. These are different than regular comments because they are actionable. The actions are
`FIXME -- need to figure this out` or `TODO -- need to implement`.

```
function Calculator() {

  // FIXME: shouldn't use a global here
  total = 0;

  return this;
}

function Calculator() {

  // TODO: total should be configurable by an options param
  this.total = 0;

  return this;
}
```
## Whitespace
* Use soft tabs set to 2 spaces

```
// bad
function() {
∙∙∙∙var name;
}

// bad
function() {
∙var name;
}

// good
function() {
∙∙var name;
}
```
* Place 1 space before the leading brace.

```
// bad
function test(){
  console.log('test');
}

// good
function test() {
  console.log('test');
}

// bad
dog.set('attr',{
  age: '1 year',
  breed: 'Bernese Mountain Dog'
});

// good
dog.set('attr', {
  age: '1 year',
  breed: 'Bernese Mountain Dog'
});
```
* Use indentation when making long method chains.

```
// bad
$('#items').find('.selected').highlight().end().find('.open').updateCount();

// good
$('#items')
  .find('.selected')
    .highlight()
    .end()
  .find('.open')
    .updateCount();
```
## Semicolons

```
// bad
(function() {
  var name = 'Skywalker'
  return name
})()

// good
(function() {
  var name = 'Skywalker';
  return name;
})();

// good (guards against the function becoming an argument when two files with IIFEs are concatenated)
;(function() {
  var name = 'Skywalker';
  return name;
})();
```
## Naming Conventions
* Avoid single letter names. Be descriptive with your naming.

```
// bad
function q() {
  // ...stuff...
}

// good
function query() {
  // ..stuff..
}
```
* Use camelCase when naming objects, functions, and instances

```
// bad
var OBJEcttsssss = {};
var this_is_my_object = {};
function c() {}
var u = new user({
  name: 'Bob Parr'
});

// good
var thisIsMyObject = {};
function thisIsMyFunction() {}
var user = new User({
  name: 'Bob Parr'
});
```
* Use a leading underscore _ when naming private properties

```
// bad
this.__firstName__ = 'Panda';
this.firstName_ = 'Panda';

// good
this._firstName = 'Panda';
```
* When saving a reference to `this` use `_this`.

```
// bad
function() {
  var self = this;
  return function() {
    console.log(self);
  };
}

// bad
function() {
  var that = this;
  return function() {
    console.log(that);
  };
}

// good
function() {
  var _this = this;
  return function() {
    console.log(_this);
  };
}
```

##JSHint
* All Javascript will be validate using JSHint with the following settings:

```
{
  "node": true,
  "browser": true,
  "esnext": true,
  "bitwise": true,
  "camelcase": true,
  "curly": true,
  "eqeqeq": true,
  "immed": true,
  "indent": 2,
  "newcap": true,
  "noarg": true,
  "quotmark": "single",
  "undef": true,
  "unused": "vars",
  "strict": true,
  "trailing": true,
  "smarttabs": true
}

```
