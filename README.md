## SCSS

 0/ To Compile files inside input folder:

 ```sass --watch input:output```

1/ Syntax

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

2/  a:hover , a:active , a:visited , a:first-letter , a:last-child
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

4/ comments

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

5/ standard standard operations for numbers (plus + , minus - , multiply * , divide / and modulo % )

```SCSS
/* SCSS */
p {
  width: (1em + 2em) * 3;
}
```

6/Interpolation: #{}

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


9/ The @each rule


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



```SCSS
/* SCSS */

```


```SCSS
/* SCSS */

```