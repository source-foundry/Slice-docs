---
title: "Usage"
weight: 3
---

Slice is a cross-platform GUI app that works on recent Linux distros, macOS, and Windows. It supports otf, ttf, woff, and woff2 format variable font input files.

The app supports output fonts with combinations of:

- Fixed axis locations
- **Restricted** variable axis ranges that are smaller than the range in the original font (new range must include the **default axis value**!)
- **Full** variable axis ranges that are present in the original font

The instructions below describe how to define these values and compile fonts.

## Quick Start Guide

Drag and drop a variable font onto the Font Path text field.

 <img src="/images/usage-dragdrop2.gif" style="width: 75%; height: 75%" alt="Slice drag and drop font animation example" />

The variable design axes appear in the Axis Editor with corresponding range and default values.

Define each axis row with one of the following definitions:

|Axis definition | Axis Editor Syntax  | Example |
| --- | --- | --- |
| Fixed axis location| Integer or float value | `400.0` |
| Restricted axis range | Colon-delimited min:max integer or float range | `200:700` |
| Full axis range | Leave field blank | n/a |

{{< tip >}}
You may use any combination of axis definition types across the full set of axes in the font so long as you define at least one axis row with a fixed axis location or a restricted axis range.
{{< /tip >}}

 <img src="/images/usage-axisedit2.gif" style="width: 75%; height: 75%" alt="Slice Axis Editor settings example" />

*(Optional developer step)* Click on a Name Editor row and enter a new family or style name.

 <img src="/images/usage-nameedit2.gif" style="width: 75%; height: 75%" alt="Slice Name Editor settings example" />

*(Optional developer step)* Click on a setting in the Bit Flag Editor to set or clear bit flags.

 <img src="/images/usage-bitflagedit2.gif" style="width: 75%; height: 75%" alt="Slice Bit Flag Editor settings example" />

Click the Slice button and enter a file path for your new font.

 <img src="/images/usage-sliceclick2.gif" style="width: 75%; height: 75%" alt="Slice button click example" />
