## SCSS

 0/ To Compile files inside input folder:

 ```sass --watch input:output```

1/ Syntax

``` CSS
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

.hello .dropdown {
  display: none;
}
.hello:hover .dropdown {
  display: block;
}

```

```SCSS
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
.funky {
  font-family: fantasy;
  font-size: 30em;
  font-weight: bold;
  border-radius: 20px;
  border-color: red;
}
```

```SCSS
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