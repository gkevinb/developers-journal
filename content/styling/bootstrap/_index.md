+++
title = "Bootstrap"
date = 2020-06-06T19:45:40+02:00
+++


Mobile-first development responsive framework.

## CDN

```html
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">

<!-- jQuery library -->
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>

<!-- Popper JS -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js"></script>

<!-- Latest compiled JavaScript -->
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js"></script>
```



## npm install

Run `npm install bootstrap --save-dev` to be able to use SCSS mixins.

## Grid System

Default is based on 12 columns, so the numbers in each row add up to 12, if it needs to be in one row. 

```html
<div class="container" style="margin-top:30px;">
	<div class="row">
		<div class="col-sm-6 col-md-3">column</div>
		<div class="col-sm-6 col-md-3">column</div>
		<div class="col-sm-6 col-md-3">column</div>
		<div class="col-sm-6 col-md-3">column</div>
	</div>
</div>
```

`col` are columns in a `row` 

## Size abbreviations

- `col` - extra small screens (mobile phones)
- `col-sm` - small screens
- `col-md` - medium screens (tablets)
- `col-lg` - large screens (laptops)

## Navigation Bar



```html
// navbar-light color scheme, bg-light is background light 
// navbar-expand-lg when large screen itt expands and doesn't collapse
// fixed top keeps navbar on top when scrolling
<nav class="navbar navbar-light bg-light navbar-expand-lg fixed-top">
  // navbar-brand the logo on website
	<a href="#" class="navbar-brand">My Website</a>
  // name the button the navbar-toggler to make it collapse
  // then identify what to collapse with data-target
  <button class="navbar-toggler" data-toggle="collapse" data-target="#navbarCollapse">
    // the three line icon
		<span class="navbar-toggler-icon"></span>
  </button>
  // Makes this part collapse in mobile
  <div class="collapse navbar-collapse" id="navbarCollapse">
    // ml-auto, margin left auto
  	<ul class="navbar-nav ml-auto">
    	<li class="navbar-item">
      	<a href="#" class="nav-link">Homepage</a>
      </li>
      <li class="navbar-item">
      	<a href="#" class="nav-link">Blog</a>
      </li>
      <li class="navbar-item">
      	<a href="#" class="nav-link">About Me</a>
      </li>
      <li class="navbar-item">
      	<a href="#" class="nav-link">Contact</a>
      </li>
    </ul>
	</div>
</nav>
```


## Example

```html
<!doctype html>
<html lang="en">
    <head>
        <!-- Required meta tags -->
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
        <!-- Bootstrap CSS -->
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">
        <title>Hello, world!</title>
        <style type="text/css">
            .row div {
                border: 1px solid silver;
            }
        </style>
    </head>
    <body>
        <nav class="navbar navbar-light bg-light navbar-expand-lg">
            <a href="#" class="navbar-brand">My Website</a>
            <button class="navbar-toggler" data-toggle="collapse" data-target="#navbarCollapse">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarCollapse">
                <ul class="navbar-nav ml-auto">
                    <li class="navbar-item">
                        <a href="#" >Homepage</a>
                    </li>
                    <li class="navbar-item">
                        <a href="#">Blog</a>
                    </li>
                    <li class="navbar-item">
                        <a href="#" >About Me</a>
                    </li>
                    <li class="navbar-item">
                        <a href="#" >Contact</a>
                    </li>
                </ul>
            </div>
        </nav>

        <!-- <div class="container">
            <div class="row">
                <div class="col-6 col-sm-3 col-md-2 bg-dark">column</div>
                <div class="col-6 col-sm-3 col-md-2">column</div>
                <div class="col-6 col-sm-3 col-md-2">column</div>
                <div class="col-6 col-sm-3 col-md-2">column</div>
            </div>
        </div> -->

        <!-- Optional JavaScript -->
        <!-- jQuery first, then Popper.js, then Bootstrap JS -->
        <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js" integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN" crossorigin="anonymous"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js" integrity="sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q" crossorigin="anonymous"></script>
        <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js" integrity="sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl" crossorigin="anonymous"></script>

    </body>
</html>
```
