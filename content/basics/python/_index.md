---
title: "Python"
date: 2020-04-28T17:09:23+02:00
# draft: true
---


## Lessons

### strip() Method

The `strip` method and its cousins, `lstrip` and `rstrip` can cause bugs if used without knowing how exactly it works. One can assume that it strips a sequence of character from a string, and `lstrip` and `rstrip` strips the leading and trailling character sequence, respectively. However this is not how it works, these `strip` methods take a set of character, meaning it will check each character separately and remove them from the string.

#### Example

For example, you might want to remove the `path/` substring from the string `path/panther.xml`. If you decide to use `lstrip` it will cause unintended consequences, since it will remove the set of characters `p`, `a`, `t`, `h`, and `/` from the string if they are the leading characters. Since the `p` and `a` characters of the `panther.xml` substring fall into the set of characters to strip, it will remove those as well, and you will be left with the string `nther`. 

In a scenario like this, I would suggest to use the `replace` method, and replace the `path/` substring with an empty string. You should also set the `count` argument to `1` to make sure only the first occurence is replaced, to safeguard from any other unintented consequences.

```python
panther = "path/panther.xml"

panther.lstrip("path/") # Prints: nther.xml

panther.replace("path/", "", 1) # Prints: panther.xml
```

#### Usage

What `strip` is really good at is removing leading and trailing whitespaces, when no arguments are given and removing  sets of characters, but just be careful it does as you intend it to work.

So the lesson here is to always read the official documentation to know exactly how a given method works.


## Automating mouse

https://automatetheboringstuff.com/chapter18/



## Anti Patterns

https://docs.quantifiedcode.com/python-anti-patterns/

