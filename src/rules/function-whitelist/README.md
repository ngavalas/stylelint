# function-whitelist

Specify a whitelist of only allowed functions.

```css
a { transform: scale(1); }
/**            ↑
 * These functions */
```

## Options

`array`: `["array", "of", "unprefixed", "functions"]`

### `["array", "of", "unprefixed", functions"]`

Whitelisted functions are the only *allowed* functions.

Given:

```js
["scale", "rgba", "linear-gradient"]
```

The following patterns are considered warnings:

```css
a { transform: rotate(1); }
```

```css
a {
  color: hsla(170, 50%, 45%, 1)
}
```

```css
a {
  background:
    red,
    -webkit-radial-gradient(red, green, blue);
}
```

The following patterns are *not* considered warnings:

```css
a { background: red; }
```

```css
a { transform: scale(1); }
```

```css
a {
  color: rgba(0, 0, 0, 0.5);
}
```

```css
a {
  background:
    red,
    -moz-linear-gradient(45deg, blue, red);
}
```
