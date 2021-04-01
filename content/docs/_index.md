---
title: "Slice Documentation"
weight: 1
---

## What does Slice do?

### Reduce the font design space

Slice is a GUI app that takes a variable font as input and compiles a new font with a custom subset ("slice") of the design space.  You define the slice of the design space that you want by setting values for each design axis that is available in your variable font.  This process reduces the design space coverage of the output font, creating a new font known as an "instance" in fancy font developer parlance.  Slice supports different types of instances.   Check out the [Instances docs](instances) to learn more about output font types.

Font users with a limited use scope and no advanced, production distribution requirements can likely stop there.

Slice offers additional compile time binary editing support for developers who have advanced font production needs such as definining different family names for A/B testing and setting the style mapping in a family of instances.

### Edit font family and style names `(Developer Feature)`

Slice provides an OpenType name table editor that allows you to define the instance font family and style names at compile time.

### Edit style map bit flags `(Developer Feature)`

The app also sets and clears font binary bits in the OpenType specification defined bit flags that are used for style mapping.

Details of *how* to appropriately set name table values and bit flags in fonts is beyond the scope of the documentation here.  Please refer to [the OpenType specification](https://docs.microsoft.com/en-us/typography/opentype/spec/) for additional details.

See the [Usage docs](usage) for details on how to make instances and use the advanced font editing features in Slice.

## Why slice a font?

Good question.  There are a number of reasons why you might want to do this:

- If you do not need the full design space offered by a variable font, instances that cover your needs may have a smaller file size. This can be important for many use cases, including web font distribution and embedding in applications.
- The applications that you use might not support the variable font format.
- The environment where you need to distribute fonts might not support the variable font format.
- You might need to name fonts that cover unique areas of the variable design space *differently* so that they show up as separate families in menus. (e.g. monospaced and proportionally spaced families)
- You might want to restrict the breadth of the design space that a user is able to access.

## How does Slice slice?

The app is built with PyQt5 and supports cross-platform use on Linux, macOS, and Windows. Instance fonts are generated with the [fonttools Python library](https://github.com/fonttools/fonttools).  This is a vetted library that is part of the free font compiler pipeline used by numerous professional type developers and the Google Fonts program.

## Important considerations when you slice

Slice output fonts are considered `derivatives of the original variable font software`.  Licensed font users should understand the conditions of their font software license before compiling derivative fonts with the application.
