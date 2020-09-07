# HW Review


# Beginning Javascript
* Brief taxonomy of programming languages (compiled versus scripted)
* Brief history of Javascript
  - "Javascript is to Java as Ham is to Hamster"
  - "Best viewed in [browser]"  (modernly, the use of "polyfill")
* Describe Javascript
  - Javascript is a "curly brace language"
  - Javascript is a prototype language
  - Javascript is object-oriented : https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics
  - Was initially client only, but modernly on servers too (e.g., Node.js)

## Conventions, and how to use
* camelCase (PascalCase for class definitions)
  - some projects use snake_case; just pick one one style stick with it
* The Console, and developer tools
* Error messages

## Useful things
* console.log()
* alert()
* variable declarations, scope
* if blocks, functions

* `document.getElementById()`
* `document.getElementsByClassName()`
* `$()`  (In jQuery, returns an array)

* Dataset attributes
  - https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes
  - In jQuery: https://stackoverflow.com/questions/13524107/how-to-set-data-attributes-in-html-elements
    ```javascript
    var a = $('#myDiv').data('myVal'); //getter

    $('#myDiv').data('myVal',20); //setter
    ```

## Functions can be stored in variables, and passed around

Functions in Javascript are "[first class][firstclass]", meaning that functions are treated like any other object, and can be stored in variables, passed as function arguments, and returned from functions.

[firstclass]:https://medium.com/launch-school/javascript-weekly-an-introduction-to-first-class-functions-9d069e6fb137

```javascript

var someValue = function(a, b) {
  return a + b;
};

var otherVal = someValue;

console.log(someValue(3,5));
```

This leads to some really neat possibilities, such as custom sorting comparators without having to write sort functions. (This is moderately advanced stuff.)
```javascript
var arr = ["IU", "Arkansas", "Michigan", "Wyoming"];

console.log(arr.sort()); // Sort is "in-place"

var comparator = (a, b) => {
  if (a == b) {
    return 0;
  }
  if (a == "IU") {return -1}
  if (b == "IU") {return 1}
  if (a < b) {return -1}
  return 1
}

console.log(arr.sort(comparator));
```

# Next Time
Come to class next week with a) a Group Recommendation on what to use as a data store (RDMS or NoSQL), and b) a possible schema to use.


## Data stores to discuss

We discussed these common hierarchical data structures in class or in readings
* Hierarchical DB
* File systems
* LDAP

## Adding a sortable script
We’ll flesh out the table on our Dashboard, then I’ll ask them to add a script to sort their tables in their dashboard app.

Probably this one, because it’s easy: http://tristen.ca/tablesort/demo/ , although I also like this one: https://github.hubspot.com/sortable/docs/welcome/
