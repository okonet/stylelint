# selector-id-pattern

Specify a pattern for id selectors.

```css
.foo, #bar.baz a, #hoo[disabled] { color: pink; }
/**   ↑           ↑
 * These id selectors */
```

## Options

`regex|string`

A string will be translated into a RegExp — `new RegExp(yourString)` — so *be sure to escape properly*.

The selector value *after `#`* will be checked. No need to include `#` in your pattern.

Given the string:

```js
"foo-[a-z]+"
```

The following patterns are considered warnings:

```css
#foop {}
#foo-BAR {}
div > .zing + #foo-BAR {}
```

The following patterns are *not* considered warnings:

```css
#foo-bar {}
div > .zing + #foo-bar {}
.foop {}
[foo='bar'] {}
```
