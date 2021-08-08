## Control

### @If
```scss
/* Scss */
@if (cond) {
  /* exp */
} @else if (cond) {
  /* exp */
} @else {
  /* exp */
}
```

<br />

### @For
```scss
/* Scss */
@for $i from 1 through 3 {
  .box:nth-child(#{$i}) {
    width : 20px * $i
  }
}
```

```css
/* Css */
.box:nth-child(1) { width: 20px; }
.box:nth-child(2) { width: 40px; }
.box:nth-child(3) { width: 60px; }
```

<br />

### @While
```scss
/* Scss */
@while cond {
  /* exp */
}
```

<br />

### @Each
```scss
/* Scss */
$fruits: (apple, orange, banana);

@each $fruit in $fruits {
  li.#{$fruit} {
    background: url("./#{$fruit}.png");
  }
}
```

```css
/* Css */
li.apple {
  background: url("./apple.png");
}
li.orange {
  background: url("./orange.png");
}
li.banana {
  background: url("./banana.png");
}
```

<br />

```scss
/* Scss */
$fruits-country: (
  apple: korea,
  orange: china
);

@each $fruit, $country in $fruits-country {
  .box-#{$fruit} {
    background: url("./#{$country}.png");
  }
}
```

```css
/* Css */
.box-apple {
  background: url("./korea.png");
}
.box-orange {
  background: url("./china.png");
}
```

<br />

### Function
```scss
/* Scss */
@function ratio($size, $ratio) {
  @return $size * $ratio
}

.box {
  width: ratio(500px, 1/2);
}
```

<br />

### Import
```scss
/* Scss */
@import "./sub.css";
@import "./sub";

@import "./header", "./footer";
```