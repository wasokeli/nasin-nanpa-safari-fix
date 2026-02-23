# nasin nanpa (Safari fix)

This modifies the font "nasin nanpa" so that it displays correctly in Safari.

## Technical details

WebKit has a bug where a ligature of the form `p o n a space` will be correctly replaced[^1], but the space will then be rendered again. This affects every iOS browser, as well as Safari for macOS.

As far as anyone has been able to determine, the only workarounds are:
1. Avoid putting spaces between words, by using UCSUR text, orbytypinglikethis.
2. Author a font such that the `space` character is zero-width, and spaces can be inserted some other way, like U+3000 ideographic space, or `space space` or `z z` ligatures.

This repo modifies nasin nanpa in two ways:
1. Reduce the `space` character to be zero-width
2. Allow `|` to enter a space

You can insert a space with the `bar`, `space space`, `z z`, ligatures, which look like `|`, `  `, `zz`, respectively.

[^1]: I tested it with a custom font; the `p o n a space` ligature is being used, not the `p o n a` one.
