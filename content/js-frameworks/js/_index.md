---
title: "Javascript"
date: 2020-06-02T17:49:23+02:00
# draft: true
---

## JavaScript

### Operations

#### Spread operator

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



#### Apply function

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply