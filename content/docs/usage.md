---
title: "Usage"
weight: 3
---

Slice is a cross-platform GUI app that works on recent Linux distros, macOS, and Windows.

## Quick Start Guide

Drag and drop a variable font onto the Font Path text field.

 <img src="/images/usage-dragdrop.gif" style="width: 75%; height: 75%" alt="Slice drag and drop font animation example" />

The variable design axes appear in the Axis Editor with corresponding range and default values.

Click on an Axis Editor row and enter a numeric value for a location in the design space.

- Axis rows <span style="text-decoration: underline">with values</span> define a new axis point location in the output font.  The axis will not be variable in the new font.
- Axis rows <span style="text-decoration: underline">without values</span> define an axis that will remain variable in the output font

You must define a point location for at least one design axis.  Static instance output fonts are defined by setting values for all axes displayed in the Axis Editor.  Define sub-space variable fonts by keeping one or more of the design axes variable.

 <img src="/images/usage-axisedit.gif" style="width: 75%; height: 75%" alt="Slice Axis Editor settings example" />

*(Optional developer step)* Click on a Name Editor row and enter a new family or style name.

 <img src="/images/usage-nameedit.gif" style="width: 75%; height: 75%" alt="Slice Name Editor settings example" />

*(Optional developer step)* Click on a setting in the Bit Flag Editor to set or clear bit flags.

 <img src="/images/usage-bitflagedit.gif" style="width: 75%; height: 75%" alt="Slice Bit Flag Editor settings example" />

Click the Slice button and enter a file path for your new font.

 <img src="/images/usage-sliceclick.gif" style="width: 75%; height: 75%" alt="Slice button click example" />
