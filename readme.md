# nasin nanpa (Safari fix)

This modifies the font "nasin nanpa" so that it displays correctly in Safari.

## Technical details

WebKit has a bug where a ligature of the form `p o n a space` will be correctly replaced[^1], but the space will then be rendered again. This affects every iOS browser, as well as Safari for macOS.

As far as anyone has been able to determine, the only workarounds are:
1. Avoid putting spaces between words, by using UCSUR text, orbytypinglikethis.
2. Author a font such that the `space` character is zero-width, and spaces can be inserted some other way, like U+3000 ideographic space, or `space space` or `z z` ligatures.

This repo modifies nasin nanpa by reducing the `space` character to be zero-width, with no other changes. You can still insert a space with the `space space` and `z z` ligatures, which look like `  ` and `zz`, respectively. (If you disable ligatures, then you can only insert spaces with codepoints like U+3000 IDEOGRAPHIC SPACE.)

[^1]: I tested it with a custom font; the `p o n a space` ligature is being used, not the `p o n a` one.
