# Minimal MathML fake implementation in CSS

MathML support in browsers is kind of sketchy so I had made some CSS file
to allow some of the basic stuff to show up as intended. This is by no means
even remotely complete (and there was some stuff I couldn't figure out how
to do right, my CSS skills aren't that great), but it may still be useful.
See below for what's implemented.

Just grab `math.css` and include it. No restrictions nor credit needed, just
do whatever you want. (pretty much public domain or unlicense)

## Warning

**Note: if you use this stylesheet, you should avoid using the `<math>`
element (against the spec), or it may conflict with browsers that support
it.**

It becomes particularly bad with Firefox, since not only there's a
conflict with CSS, but also it doesn't understand some of the elemnts the
stylesheet implements and outright throws out an error when it finds one of
those. Seeing as all the MathML elements are unique (don't conflict with
HTML), maybe in the future it'll be best if parsers just see the `<math>`
element as optional and assume MathML starts when they find one of the other
elements.

## Supported elements

An asterisk means support is not perfect.

- `<mi>`, `<mn>`, `<mo>`
- `<mtext>`, `<merror>`
- `<msup>`, `<msub>`
- `<mfrac>`
- `<msqrt>`, `<mroot>`*
- `<mfenced>`*
- `<mphantom>`
- `<mtable>`, `<mtr>`, `<mtd>`

## Limitations

- The left side of `<mroot>` will not expand to accomodate the index if it's
  too wide to fit in the root.

- `<mfenced>` only supports `(` `[` `{` for open and `)` `]` `}` for close.
  Anything else will show up as parenthesis.

- When a symbol such as a parenthesis is supposed to stretch to cover an
  entire row or the like, it doesn't work and instead gets centered.
