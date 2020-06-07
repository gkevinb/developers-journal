+++
title = "Markdown"
date = 2020-06-07T16:50:11+02:00
draft = true
+++

## Table of contents

[TOC]

Below is a tutorial on how to format Markdown files, typically `ReadMe.md`. More information on [this page](https://guides.github.com/features/mastering-markdown/).


## Escape character

Use \ as escape character when using symbols that are intented as keywords but need to be used as plain text.

## Code

You can also simply indent your code by four spaces or two tabs.

    Example code...


## Syntax Highlighting

```javascript
function fancyAlert(arg) {
  if(arg) {
    $.facebox({div:'#foo'})
  }
}
```

## Italics and Bold

_Italic_ is made by surrounding words with \_Italic_

**Bold** is made by surrounding words with \*\*Bold**

Both **_italic and bold_** can be used on the same words.

`Monospace` is made by surrounding words with \`Monospace\`



## Headers

Headers are made by adding # infront of the words. There are six level of headers H1 to H6, like in html.



## Links

### Inline Links

    [Search for it on Google.](www.google.com)

Surround link text in [ ] and then actual link in ( ).

That's all there is to writing inline links.

### Reference Links

The other link type is called a reference link. As the name implies, the link is actually a reference to another place in the document. Here's an example of what we mean:

    Here's [a link to something else][another place].
    Here's [yet another link][another-link].
    And now back to [the first link][another place].
    
    [another place]: www.github.com
    [another-link]: www.google.com



## Images

Images work almost exactly like links, but with an ! infront.

    ![A representation of Octdrey Catburn](http://octodex.github.com/images/octdrey-catburn.jpg)

### Reference links to images

    ![The first father][First Father]
    [First Father]:http://octodex.github.com/images/founding-father.jpg
    
    ![The second first father][Second Father]
    [Second Father]: http://octodex.github.com/images/foundingfather_v2.png


​    
## Tables

| First Header                | Second Header                |
| --------------------------- | ---------------------------- |
| Content from cell 1         | Content from cell 2          |
| Content in the first column | Content in the second column |



## Checkbox

```
- [ ] Mercury
- [x] Venus
- [x] Earth (Orbit/Moon)
- [x] Mars
```

- [ ] Mercury
- [x] Venus
- [x] Earth
- [ ] Mars



## Flowchart

```flow
st=>start: Start:>http://www.google.com[blank]
e=>end:>http://www.google.com
op1=>operation: My Operation
sub1=>subroutine: My Subroutine
cond=>condition: Yes or No?:>http://www.google.com
io=>inputoutput: catch something…
st->op1->cond
cond(yes)->io->e
cond(no)->sub1(right)->op1
```



## Sequence

```sequence
Title: Here is a title
A -> B: Normal line
B -> C: Dashed line
C -> D: Open arrow
D -> A: Dashed open arrow
```