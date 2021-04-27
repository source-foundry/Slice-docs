---
title: "Slice Documentation"
weight: 1
---

## Why slice a font?

Good question.  There are several reasons why you might want to do this:

- If you do not need the entire design space offered by a variable font, sub-spaces that cover your needs may have a **smaller file size**. This can be important for many use cases, including web font distribution and embedding in applications.
- The applications that you use _**might not support the variable font format**_.
- The environment where you need to distribute fonts for use by others _**might not support the variable font format**_.
- You might need to _**name fonts that cover unique areas of the variable design space differently**_ so that they show up as separate families in menus. (e.g., monospaced and proportionally spaced families)
- You might want to _**restrict the breadth of the design space that a user can access**_.

## What does Slice do?

### 1. Make a new font with a smaller design space

Slice is a GUI app that uses variable font input and compiles a new font with a custom design sub-space.  The new font can include any combination of variable axis and axis point location definitions.  You define the sub-space by setting values for the available design axes in the app's axis editor.

{{< tip >}}
Slice supports both static instance and variable design sub-space output fonts.  See the [Usage docs](usage) to learn how to create these output file types.
{{< /tip >}}

Font users with a limited use scope and no advanced production distribution requirements can likely stop there.  The font should work for many simple, local use cases.

### 2. Font binary production tasks `(Optional Developer Features)`

{{< tip >}}
The app offers additional compile-time binary editing support for developers with production engineering needs, such as defining different family names for A/B testing and setting the style mapping in a family of output fonts.

These developer features are optional.
{{< /tip >}}

#### Edit font family and style names `(Developer Feature)`

Slice provides an OpenType name table editor to define the output font family and style names.  This feature currently supports `platform=3, encoding=1, language=1033` name records only. Please refer to [the OpenType name table specification](https://docs.microsoft.com/en-us/typography/opentype/spec/name) for details about how the platform, encoding, and language ID's are used in text rendering environments.

### Edit style map bit flags `(Developer Feature)`

The app allows users to set and clear font binary bits in the OpenType specification-defined bit flags used for family style mapping.

{{< tip >}}
Details on *how* to appropriately set name table records and bit flags in fonts are beyond the scope of these docs.  Please refer to [the OpenType specification](https://docs.microsoft.com/en-us/typography/opentype/spec/) for more information.
{{< /tip >}}

See the [Usage docs](usage) for instructions on font slicing and the advanced font binary editing features in Slice.

## How does Slice slice a font?

The app is built with the PyQt5 GUI framework and supports cross-platform font compilation on recent Linux distribution, macOS, and Windows versions.

Font slicing, binary edits, and compilation are performed with the [fonttools Python library](https://github.com/fonttools/fonttools).  This is a well-vetted library that is part of the free font compiler pipeline used by numerous professional and hobbyist type developers and for the development of most typeface families in the Google Fonts program.

## Important considerations

{{< tip "warning" >}}
Slice output fonts are considered `derivatives of the original variable font software`.  Licensed font users should understand their font software license conditions before making derivative fonts with the application.
{{< /tip >}}
