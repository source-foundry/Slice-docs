---
title: "Slice Documentation"
weight: 1
---

## What does Slice do?

### 1. Reduce the typographic design space in a font

Slice is a GUI app that takes a variable font as input and compiles a new font with a custom subset of the design space.  You define the slice of the design space that you want by setting values for each design axis that is available in your variable font.  This process reduces the design space coverage of the output font, creating a new font known as an "instance" in fancy font developer parlance.  

{{< tip >}}
Slice supports different types of design subspace builds.   Check out the [Design Spaces docs](designspaces) to learn more about output font types.
{{< /tip >}}

Font users with a limited use scope and no advanced, production distribution requirements can likely stop there.  The font should work for many simple, local use cases.

### 2. Font binary production tasks `(Optional Developer Features)`

{{< tip >}}
The app offers additional compile time binary editing support for developers who have production engineering needs such as defining different family names for A/B testing and setting the style mapping in a family of instances.  

These developer features are optional.
{{< /tip >}}

#### Edit font family and style names `(Developer Feature)`

Slice provides an OpenType name table editor that allows you to define instance font family and style names at compile time.  This feature currently supports `platform=1, encoding=1, language=1033` name records only. Please refer to [the OpenType name table specification](https://docs.microsoft.com/en-us/typography/opentype/spec/name) for additional details about how platform, encoding, and language ID's are used in text rendering environments.

### Edit style map bit flags `(Developer Feature)`

The app allows a user to set and clear font binary bits in the OpenType specification-defined bit flags used for family style mapping.

{{< tip >}}
Details on *how* to appropriately set name table records and bit flags in fonts are beyond the scope of these docs.  Please refer to [the OpenType specification](https://docs.microsoft.com/en-us/typography/opentype/spec/) for more information.
{{< /tip >}}

See the [Usage docs](usage) for instructions on how to make instances and use the advanced font editing features in Slice.

## Why slice a font?

Good question.  There are a number of reasons why you might want to do this:

- If you do not need the full design space offered by a variable font, instances that cover your needs may have a **smaller file size**. This can be important for many use cases, including web font distribution and embedding in applications.
- The applications that you use _**might not support the variable font format**_.
- The environment where you need to distribute fonts for use by others _**might not support the variable font format**_.
- You might need to _**name fonts that cover unique areas of the variable design space differently**_ so that they show up as separate families in menus. (e.g. monospaced and proportionally spaced families)
- You might want to _**restrict the breadth of the design space that a user is able to access**_.

## How does Slice slice a font?

The app is built with the PyQt5 GUI framework and supports cross-platform font compilation on recent versions of Linux distributions, macOS, and Windows. 

Font instantiation and font binary edits are performed with the [fonttools Python library](https://github.com/fonttools/fonttools).  This is a well-vetted library that is part of the free font compiler pipeline used by numerous professional and hobbyist type developers, and for the development of most typeface families in the Google Fonts program.

## Important considerations

{{< tip "warning" >}}
Slice output fonts are considered `derivatives of the original variable font software`.  Licensed font users should understand the conditions of their font software license before compiling derivative fonts with the application.
{{< /tip >}}
