## Syntax

### Comment
```scss
// Can't be compiled
/* Can be compiled */
```

<br />

### Variable
```scss
$name: value;
```

<br/>

### Nesting
```scss
/* Scss */
.section {
  width: 100%;
  .center {
    padding: 20px;
    h1 {
      float: left;
    }
  }
}
```

```css
/* Css */
.section {
  width: 100%;
}
.section .center {
  padding: 20px;
}
.section .center h1 {
  float: left;
}
```

<br />

### Ampersand
```scss
/* Scss */
.list {
  li {
    &:last-child {
      margin-right: 0;
    }
  }
}

.fs {
  &-small { font-size: 12px; }
  &-medium { font-size: 14px; }
  &-large { font-size: 16px; }
}
```

```css
/* Css */
.list li:last-child {
  margin-right: 0;
}

.fs-small {
  font-size: 12px;
}
.fs-medium {
  font-size: 14px;
}
.fs-large {
  font-size: 16px;
}
```

<br />

### Nested Property
```scss
/* Scss */
.box {
  font: {
    weight: bold;
    size: 10px;
  };
  margin: {
    top: 10px;
  };
  padding: {
    bottom: 40px;
  };
}
```

```css
/* Css */
.box {
  font-weight: bold;
  font-size: 10px;
  margin-top: 10px;
  padding-bottom: 40px;
}
```

<br />

### Operation
```scss
/* Scss */
div {
  width: 20px + 20px;
  height: 40px - 10px;
  font-size: 10px * 2;
  margin: (30px / 2);
  padding : 20px % 7;
}
```

```css
/* Css */
div {
  width: 40px;
  height: 30px;
  font-size: 20px;
  margin: 15px;
  padding : 6px;
}
```

<br />

### Mixin
```scss
/* Scss */
@mixin center {
  display: flex;
  justify-content: center;
  align-items: center;
}

@mixin box($width: 150px, $height: 100px) {
  width: $width;
  height: $height;
}

.box {
  @include center;
  @include box(150px, 200px);
  // Or
  @include box($height: 200px);
}
```

```css
/* Css */
.box {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 150px;
  height: 200px;
}
```

<br />

```scss
/* Scss */
@mixin top {
  top: 0;
  @content;
}

.box {
  @include top{
    bottom: 0;
    right: 0;
    margin: auto;
  }
}
```

```css
/* Css */
.box {
  top: 0;
  bottom: 0;
  right: 0;
  margin: auto;
}
```