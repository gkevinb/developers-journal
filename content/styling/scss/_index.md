+++
title = "SCSS"
date = 2020-06-06T20:00:16+02:00
weight = 2
+++

SCSS is stricter more popular better, than SASS.


## Partials

Partial SCSS files to link into main SCSS file, naming convention: (Use underscore infront of name)
_partial.scss
_partial2.scss

When importing files use:
@import "partial";
No, underscore, no file extension

## Inheritance and @extend

Works just like in any other programming language.

## Mixins

They are like functions in CSS, pretty cool if you ask me :D

[Sass Guidelines](https://sass-guidelin.es/)

## Examples

### Inheritance

```scss
.panel{
    border: 3px solid dodgerblue;
    background: lightgreen;
    margin: 10px;
}
.little_panel{
    @extend .panel;
    font-size: 12px;
    padding: 5px;
}
.big_panel{
    @extend .panel;
    font-size: 32px;
    padding: 20px;
}
```

### Nesting

```scss
nav{
    ul{
        background-color: $bg_color;
        margin: 0;
        padding: 0;
        list-style: none;
    }
    li{
        display: inline-block;
    }
    a{
        color: $text_color;
        display: inline-block;
        padding: 10px 16px;
        text-decoration: none;
    }
    a:hover{
        background-color: $hover_color;
    }
}
```

### Variables

```scss
$primary-color: green;
$bg_color: #2c3e50;
$hover_color: #160bc0;
$text_color: white;
```

### Operators and Inheritance

```scss
$button_background: #16A085;
$button_color: #FFFFFF;
$button_padding: 5px;

.button{
    background: $button_background;
    border-radius: 8px;
    color: $button_color;
    display: inline-block;
    padding: $button_padding;
    text-decoration: none;

}

.jumbo_button{
    @extend .button;
    padding: $button_padding + 30;
    /*
    Don't need units on 30, but its okay to write 30px as well
    */
}

.light_button{
    @extend .button;
    background: $button_background * 1.5;
    /*
    Multplying color > 1, lightens it
    < 1, darkens it
    */
}
```

### Mixin

```scss
@mixin borderRadius($radius){
    -webkit-border-radius: $radius;
    -moz-border-radius: $radius;
    -ms-border-radius: $radius;
    border-radius: $radius;
}
.panel{
    border: 3px solid dodgerblue;
    background: lightgreen;
    margin: 10px;
}
.little_panel{
    // Extend used for inheritance
    @extend .panel;
    // Include used as a method or function
    @include borderRadius(8px);
    font-size: 12px;
    padding: 5px;
}
.big_panel{
    @extend .panel;
    @include borderRadius(200px);
    font-size: 32px;
    padding: 20px;
}
```



### For Loop

`#{$i}` is how you place the variable.

```scss
@for $i from 1 through 24 {
    #dec#{$i}--date {
        @include datePositioning(2, visible);
        grid-area: d#{$i};
    }

    #dec#{$i}--content {
        @include datePositioning(1, hidden);
        @include dateBackgroundImage("../img/#{$i}.png");
        grid-area: d#{$i};
    }
}

// Produces this 24 times, 1...24

#dec1--date {
  height: 100%;
  width: 100%;
  position: absolute;
  z-index: 2;
  visibility: visible;
  grid-area: d1; }

#dec1--content {
  height: 100%;
  width: 100%;
  position: absolute;
  z-index: 1;
  visibility: hidden;
  background-image: url("../img/1.png");
  background-repeat: no-repeat;
  background-size: 112px 112px;
  grid-area: d1; }
  #dec1--content:hover {
    opacity: 0.3; }
```



## Snippets

When passing in name of image into a mixin. Similar to for loop when passing in argument and then using it in a string.

```scss
@mixin bgimage($name) {
  $url:"../images/#{$name}.png";
  background: url($url);
}
```


