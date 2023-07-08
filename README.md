# pdfmagic

Tool(s) to transform PDFs for printing multiple pages on a sheet.

## Usage
```bash
pdfmagic -o <output-pdf> <input-pdf-1> <input-pdf-2> ...
```

For more options, see
```bash
pdfmagic -h
```

## Examples

Following PDF files are used as sample inputs:
* [1.pdf](samples/1.pdf)
* [2.pdf](samples/2.pdf)
* [3.pdf](samples/2.pdf)
* [4.pdf](samples/2.pdf)

## Default options
```bash
pdfmagic -o samples/1-4-default.pdf \
    samples/1.pdf samples/2.pdf samples/3.pdf samples/4.pdf
```
Here is how result will look: [1-4-default.pdf](samples/1-4-default.pdf)

## Change spacing between minipages
Default spacing is 0. To chang it to 10pt use this command:
```bash
pdfmagic -o samples/1-4-spacing.pdf \
    -s 10 \
    samples/1.pdf samples/2.pdf samples/3.pdf samples/4.pdf
```
Here is how result will look: [1-4-default.pdf](samples/1-4-spacing.pdf)

## Change page margin
Default page margin is 20pt. To change it to 0pt use this command:
```bash
pdfmagic -o samples/1-4-margin.pdf \
    -m 0 \
    samples/1.pdf samples/2.pdf samples/3.pdf samples/4.pdf
```
Here is how result will look: [1-4-default.pdf](samples/1-4-margin.pdf)

## Keep aspect ratio of the original
By default, original mini-pages will be shrinked and stretched to fit the target sheet location,
**independently in X and Y direction***.
If you want to preserve original aspect, do this:
```bash
pdfmagic -o samples/1-4-keep-aspect.pdf \
    -m 0 \
    -k \
    samples/1.pdf samples/2.pdf samples/3.pdf samples/4.pdf
```
Here is how result will look: [1-4-keep-aspect.pdf](samples/1-4-keep-aspect.pdf)

## TODO
1. Support other paper sizes (currently hardcoded to US Letter)
2. Support other number of mini-pages per paper sheet (2, 6, 8). Currently do only 4 mini-pages per paper sheet.
3. Support page re-ordering. Currently mini-pages are placed in a fixed order (left-to-right, top-to-bottom).

## License
MIT
