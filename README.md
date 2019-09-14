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



```SCSS
/* SCSS */

```