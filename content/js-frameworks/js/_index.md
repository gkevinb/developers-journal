+++
title = "Javascript"
date = 2020-06-02T17:49:23+02:00
+++


## Regular Expressions

Good interactive [tutorial](https://regexone.com/) on Regex.

[Javascript Regex](https://www.w3schools.com/js/js_regexp.asp)

[Regex Article](https://eloquentjavascript.net/09_regexp.html)

```javascript
var state = "2x10";
var pattern = /\d+/g;
var result = state.match(pattern);
// result equals ['2', '10']
```


## Operations

### Spread operator

Spread operator is used to unpack an array an give the elements as parameters to a method. It is useful for things such as giving an array to the `Math.max` method to determine the element with the maximum value in the array.

```javascript
function getSecondLargest(nums) {
    let uniq = [...new Set(nums)]
    let index = uniq.indexOf(Math.max(...uniq))
    uniq.splice(index, 1)
    return Math.max(...uniq)
}
```
> https://www.hackerrank.com/challenges/js10-arrays/problem


### Fetch API

https://flaviocopes.com/fetch-api/

### Apply function

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply


### Template literals

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals

### Reverse string

https://www.freecodecamp.org/news/how-to-reverse-a-string-in-javascript-in-3-different-ways-75e4763c68cb/

### Strings

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals

### Promises

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then

### Arrow

https://www.w3schools.com/js/js_arrow_function.asp


