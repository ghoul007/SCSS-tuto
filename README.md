## SCSS

 0/ Compile files (inside input folder):

 ```sass --watch input:output```

1/ Nested Syntax

``` CSS
/* CSS */
#a .a-1 {
  background: yellow;
}
#a .a-1 .child {
  font-size: 12px;
}
#a .a-1 .child .child-1 {
  color: red;
}

```

```SCSS
/* SCSS */
#a {
	.a-1{
		background:yellow;
		.child{
			font-size:12px;
			.child-1{
				color:red
			}
		}
	}
}
```

2/ CSS Pseudo classses: a:hover , a:active , a:visited , a:first-letter , a:last-child
```CSS
/* CSS */

.hello .dropdown {
  display: none;
}
.hello:hover .dropdown {
  display: block;
}

```

```SCSS
/* SCSS */
.hello {
	.dropdown{
		display: none;
	}
  &:hover {
		.dropdown{
			display: block;
		}
	}
}
```

3/ Namespace
```CSS
/* CSS */
.funky {
  font-family: fantasy;
  font-size: 30em;
  font-weight: bold;
  border-radius: 20px;
  border-color: red;
}
```

```SCSS
/* SCSS */
.funky {
  font: {
    family: fantasy;
    size: 30em;
    weight: bold;
  }
  border: {
  	radius:20px;
  	color:red;
  }
}
```

4/ Comments

CSS: ``` /* */ ```

SCSS:  ``` /* */ and //```

5/CSS properties

```SCSS
/* SCSS */
$width: 10px;
#main {
  width: $width;
}
```

5/ Standard standard operations for numbers (plus + , minus - , multiply * , divide / and modulo % )

```SCSS
/* SCSS */
p {
  width: (1em + 2em) * 3;
}
```

6/ Interpolation: #{}

```CSS
p.foo {
  border-color: blue;
  content: "hello world foo";
}
```

```SCSS
/* SCSS */
$name: foo;
$attr: border;
p.#{$name} {
  #{$attr}-color: blue;
  content: "hello world #{$name}"
}
```

7/ The @if directive


```SCSS
/* SCSS */
p {
  @if 1 + 1 == 2 { border: 1px solid;  }
  @if true {background-image:url('')}
  @if 5 < 3      { border: 2px dotted; }
  @if null       { border: 3px double; }
}
$type: monster;
p {
  @if $type == ocean {
    color: blue;
  } @else if $type == matador {
    color: red;
  } @else if $type == monster {
    color: green;
  } @else {
    color: black;
  }
}
```


```CSS
/* CSS */
p {
  border: 1px solid;
  background-image: url("");
}

p {
  color: green;
}
```


8/ The @for directive

```SCSS
/* SCSS */
@for $i from 1 through 3 { //1,2,3
  .item-#{$i} { width: 2em * $i; }
}
```

```CSS
/* CSS */
.item-1 {
  width: 2em;
}

.item-2 {
  width: 4em;
}

.item-3 {
  width: 6em;
}
```



```SCSS
/* SCSS */
$i:6;
@for $i from 1 through $i{
  .col-#{$i}{
    width:$i/6*100%
  }
}

```


```CSS
/* CSS */
.col-1 {
  width: 16.6666666667%;
}

.col-2 {
  width: 33.3333333333%;
}

.col-3 {
  width: 50%;
}

.col-4 {
  width: 66.6666666667%;
}

.col-5 {
  width: 83.3333333333%;
}

.col-6 {
  width: 100%;
}

```


9/ The @each directive


```SCSS
/* SCSS */
@each $animal in farouk, hamza, malek, hajer, sana {
  .#{$animal}-icon {
    background-image: url('/images/#{$animal}.png');
  }
}

```


```CSS
/* CSS */
.farouk-icon {
  background-image: url("/images/farouk.png");
}

.hamza-icon {
  background-image: url("/images/hamza.png");
}

.malek-icon {
  background-image: url("/images/malek.png");
}

.hajer-icon {
  background-image: url("/images/hajer.png");
}

.sana-icon {
  background-image: url("/images/sana.png");
}
```


10/ function



```SCSS
/* SCSS */
$grid-width: 40px;
$gutter-width: 10px;

@function test($a){
	@return $a+10
}

@function grid-width($n) {
	$hello:1px ;
	@for $i from 1 through $n{
		$hello:$hello+$i
	}
	@if $hello > 10 {
		$hello:15px
	}
    @return $hello + test(2)
}

#sidebar { width: grid-width(5); }
```


```CSS
/* CSS */
#sidebar {
  width: 27px;
}
```

11/ Mixin Directives

11.1/ Basic

```SCSS
/* SCSS */
@mixin large-text {
  font: {
    family: Arial;
    size: 20px;
    weight: bold;
  }
  color: #ff0000;
}

```

11.2/ Re-used throughout the stylesheet

```SCSS
/* SCSS */
.page-title {
  @include large-text;
  padding: 4px;
  margin-top: 10px;
}
```


```CSS
/* CSS */
.page-title {
  font-family: Arial;
  font-size: 20px;
  font-weight: bold;
  color: #ff0000;
  padding: 4px;
  margin-top: 10px;
}


```



11.3/ Included in the document

```SCSS
/* SCSS */
@mixin silly-links {
  a {
    color: blue;
    background-color: red;
  }
}

@include silly-links;
```


```CSS
/* CSS */
a {
  color: blue;
  background-color: red;
}

```



```SCSS
/* SCSS */

@mixin compound {
  @include highlighted-background;
  @include header-text;
}

@mixin highlighted-background { background-color: #fc0; }
@mixin header-text { font-size: 20px; }
.test{
  @include compound
}

```
```CSS
/* CSS */
.test {
  background-color: #fc0;
  font-size: 20px;
}
```



11.4/ With arguments

```SCSS
/* SCSS */
@mixin generic-border($color, $width) {
  border: {
    color: $color;
    width: $width;
    style: dashed;
  }
}
p { @include generic-border(blue, 10px); }

```

```CSS
/* CSS */
p {
  border-color: blue;
  border-width: 10px;
  border-style: dashed;
}
```


```SCSS
/* SCSS */
$b:box-shadow;
@mixin box-shadow($shadows...) {
  -moz-#{$b}: $shadows;
  -webkit-#{$b}: $shadows;
  #{$b}: $shadows;
}

.shadows {
  @include box-shadow(0px 4px 5px #666, 2px 6px 10px #999);
}

```

```CSS
/* CSS */
.shadows {
  -moz-box-shadow: 0px 4px 5px #666, 2px 6px 10px #999;
  -webkit-box-shadow: 0px 4px 5px #666, 2px 6px 10px #999;
  box-shadow: 0px 4px 5px #666, 2px 6px 10px #999;
}

```
12/ @extends

12.1/ Basic


```SCSS
/* SCSS */
.error {
  border: 1px #f00;
  // Other  rules  that  use  .error  will  work  for  .seriousError  as  well.
  &.intrusion {
	  background-image: url("/image/hacked.png");
	}
}
.seriousError {
  @extend .error;
}
```

```SCSS
/* SCSS */
.error, .seriousError {
  border: 1px #f00;
}
.error.intrusion, .intrusion.seriousError {
  background-image: url("/image/hacked.png");
}
```
12.2/ Multiple @extends

```SCSS
/* SCSS */
.error {
  border: 1px #f00;
  background-color: #fdd;
}
.attention {
  font-size: 3em;
  background-color: #ff0;
}
.seriousError {
  // ===>
  @extend .error;
  @extend .attention;
  border-width: 3px;
}
```

```CSS
/* CSS */
.error, .seriousError {
  border: 1px #f00;
  background-color: #fdd;
}

.attention, .seriousError {
  font-size: 3em;
  background-color: #ff0;
}

.seriousError {
  border-width: 3px;
}

```
12.2/ Chaining @extends

```SCSS
/* SCSS */
.error {
  border: 1px #f00;
  background-color: #fdd;
}
.seriousError {
  @extend .error;
  border-width: 3px;
}

.criticalError {
  @extend .seriousError;
  position: fixed;
  top: 10%;
  bottom: 10%;
  left: 10%;
  right: 10%;
}
```



```CSS
/* CSS */
.error, .seriousError, .criticalError {
  border: 1px #f00;
  background-color: #fdd;
}

.seriousError, .criticalError {
  border-width: 3px;
}

.criticalError {
  position: fixed;
  top: 10%;
  bottom: 10%;
  left: 10%;
  right: 10%;
}
```
