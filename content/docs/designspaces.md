---
title: "Design Spaces"
weight: 2
---

There is a great deal of jargon in the type development industry.  Terms like "variable font", "design axis", "static instance", and "partial instance" are technical and confusing.  To understand slicing, you need to understand the concepts referenced by these terms and how they relate to the space within which the type designer works, the "design space".

## What is a design space?

The Meriam-Webster dictionary includes the following definitions of the English words ["design"](https://www.merriam-webster.com/dictionary/design) and [“space”](https://www.merriam-webster.com/dictionary/space):

> **design**: the arrangement of elements or details in a product or work of art

> **space**: a set of mathematical elements and especially of abstractions of all the points on a line, in a plane, or in physical space

<small>Source: <a href="https://www.merriam-webster.com/dictionary">Merriam-Webster dictionary</a></small>

That's a good starting point for our purposes.  Let's combine the terms into a definition of a type design space:

{{< tip >}}
The "design space" is an n-dimensional arrangement of typeface elements where the number of design elements supported in the typeface and the relationships between those elements determines the value of n.
{{< /tip >}}

🤯 That's pretty abstract stuff.  The following example will hammer this concept home.

## Design space example

When you open a directory of fonts on your computer, you'll find files grouped as a typeface "family". Let's create two imaginary families on your system called "Small Sans" and "Big Sans".  Small Sans includes Regular and Bold fonts.  Big Sans has Thin, Light, Regular, Medium, Bold, SemiBold, and ExtraBold fonts. It so happens that the type designers also provide you with Italic forms.  The Small Sans family has Italic and Bold Italic fonts. The Big Sans family includes the full complement of Thin Italic through ExtraBold Italic styles.  But Big Sans takes it one step further (it wasn't called Big Sans for nothing!) and supports a width element, so there are also Condensed and Expanded fonts for every Roman, italic, and weight combination.

These are examples of two type design spaces with weight, italic, and width elements.  The elements are known as "design axes" and they define the design space.  Small Sans is a two-axis design space that includes weight and italic elements.  Big Sans is a three-axis design space that supports weight, width, and italic elements.

Design axes have dimensions.  The Regular to Bold weight axis range in Small Sans is smaller than the Thin to Black weight axis range in Big Sans.  The axis dimensions can overlap.  The Small Sans weight range is a subset of the Big Sans weight range.  And the combination of axes and axis dimensions provides the design space with a magnitude.  We think of Big Sans as having a more extensive design space than the one defined by Small Sans.  Larger design spaces generally support a wider range of typeface family styles.

## Static instance fonts

<figure>
 <img src="/images/font-dir-crunch.png" alt="Inter typeface static instances" />
 <figcaption>
 <small>Static instances in the <a href="https://github.com/rsms/inter">Inter typeface project</a></small>
 </figcaption>
</figure>

Design axes are continuous over the axis range.  This means that an axis start point, an axis end point, and all points in between are available in the space.  Type designers commonly draw forms at the axis extremes and use mathematical modeling to create intermediate forms between the extremes.  While they may exist, many intermediate forms are irrelevant.  A rare person needs a partial italic form or a weight that is one axis unit greater than the "Bold" value.

The Small Sans and Big Sans font examples above capture discrete parts of the design space that a type developer decided are the most useful to users.  They could have chosen a weight between the Medium and Bold and called that "Bold", but they didn't.  They decided on that exact weight axis definition and assigned the "Bold" style name to the font.

The fonts in these examples are known as "static instances" or "static instance fonts".  Here, the term "instance" means that discrete loci are defined across all axes in the design space. It's like taking a knife and slicing across the design axes.  Each point that the blade comes into contact with defines a discrete value on the axis that is part of its instance definition.  A font is compiled with those design axis locations, and a semantic name is assigned to the file so that a user understands what area of the design space the file represents.  A "Regular" font has a lighter weight than a "Bold" font.  And a "Bold Italic" font adds a slant and different italic letterforms to the weight defined in the "Bold" font.  These fonts differ based on the use of different discrete axis definition combinations.  The knife took a different path across the design axes for each font.

Static instance fonts are the most common format that you will find in the wild today.

## Variable fonts

Enter variable fonts.

The variable font format is a font technology revolution that makes the *entire design space* accessible in a single font.  So, all of those named static instance font designs that we discussed above? Yep, they are in there. But variable fonts take it a step further.  They also support interpolated definitions of every point on every axis *between those named instance values*.  Instead of axis instances, a variable font includes a multi-dimensional type design space that becomes increasingly complex as the axis number and axis-axis relationships increase.  Users have access to the total design space and can specify the locations that they want to use.  Variable fonts can significantly magnify the type design palette available to end-users and de-emphasize type designer instance decisions.

Type developers and font users are taking full advantage of this newfound dynamic axis freedom.  Some variable typefaces include numerous design axes with wide ranges that lead to incredibly expansive typographic expression capabilities in a single variable font file.

The [Roboto Flex project](https://github.com/TypeNetwork/Roboto-Flex) is an excellent example of an extensive, multi-axis variable design space.  The video below shows the breadth of forms that one variable font can cover.

<figure>
 <img src="/images/roboto-flex-demo.gif" alt="Roboto Flex design space example" />
 <figcaption>
 <small>Video source: <a href="https://videoproof.typenetwork.com">Type Network Video Proof application</a></small>
 </figcaption>
</figure>

Variable fonts define default, min, and max design axis values and expose axis settings to users with abbreviated **four-character axis tags**.

{{< tip >}}
Tag name casing defines the registered status of the axis. Lower case tags are [registered axis tags](https://docs.microsoft.com/en-us/typography/opentype/spec/dvaraxisreg#registered-axis-tags), and include `ital` (italic), `opsz` (optical size), `slnt` (slant), `wdth` (width), and `wght` (weight) axes.  Upper case tags are custom, unregistered axis tags.  There is no difference in how a user interacts with these two types of axes in a font.
{{< /tip >}}

Users access an area of the design space in a variable font by defining a numeric value for each design axis tag.  The way that you specify this differs based on where you are using the font.  

### Try a variable font!

Stephen Nixon's Recursive typeface CodePen example allows you to explore a variable font in HTML/CSS by editing CSS settings for the family's slant (`slnt`), casual (`CASL`), cursive (`CRSV`), and monospaced (`MONO`) design axes.  Click the "Run Pen" text in the right side view to see the font in action.  Hover over the text to see the design change according to the editor's CSS definitions on the left.  The CSS editor is not live on this page.  Click the "Edit on Codepen" link in the top right corner of the CodePen view to dive in and edit the `--MONO`, `--CASL`, `--slnt`, and `--CRSV` axis tag variable values on the CodePen site to see how the forms change with new definitions.

<br>

<iframe height="595" style="width: 100%;" scrolling="no" title="Recursive Mono &amp; Sans, all axes from Google Fonts API" src="https://codepen.io/thundernixon/embed/preview/dyGQZbx?height=595&theme-id=light&default-tab=css,result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/thundernixon/pen/dyGQZbx'>Recursive Mono &amp; Sans, all axes from Google Fonts API</a> by Stephen Nixon
  (<a href='https://codepen.io/thundernixon'>@thundernixon</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

<br>

For example, change the `<h1>` tag text style by editing the following CSS variable values:

```css
h1 {
  --CASL: 1; 
  --slnt: 0;
  --MONO: 1;
}
```

and change the `<h1>` hover text style animation by editing:

```css
h1:hover {
  --slnt: -7;
  --CRSV: 0;
}
```

When you define those axis values, you request a discrete design space location for use with `h1` heading text.  You can think of this as defining a "static instance" within the dynamic design space.  To request a different area of the space, set different axis tag values. As demonstrated in the CodePen example, it is possible to use multiple design space locations to format various text fields in the document.  This ability is akin to having a knob for each axis to dial in the exact design that you want from the space.  GUI graphics editors, text editors, and other applications that support variable fonts similarly expose axis settings. You'll commonly see the axis tag name and a text box or slider to select the axis value.

{{< tip >}}
What if you don't set a value on an axis?  Every variable font sets a default value on every axis to comply with the OpenType specification for the font format. In most environments, you get the default axis value when you do not explicitly define an axis value.  
{{< /tip >}}

## Sub-spaces from variable fonts

### How Slice fits into the picture

Hopefully, if you've reached this point, you have a better understanding of type design spaces, static instances, and how the variable font format differs from the static instance format.  We can now discuss the role that Slice plays in using a variable font design space to generate new font files with different design spaces.

Font compiler technology exists to create a new font from a "sub-space" of a variable font design space.  I like to think of this operation as "slicing" a design space, and this is how the application earned its name.  The Slice app is a [fonttools instancer](https://github.com/fonttools/fonttools) based GUI tool that allows you to slice a variable font to create new sub-space fonts.  The application supports the output of two types of sub-space font files.

Static instances are one type of output.  Slice provides a list of available axis tags (and axis names when you hover over the tag) as well as the default, min, and max axis values.  Use these data to determine and define a design space location for every axis in the variable font, and Slice creates a new static instance font at the location you specify.

But wait, there is more!  You may want to keep some of the variable axes.  Slice also allows you to create fonts that include combinations of variable and instanced axes.  This sub-space file is commonly known as a "partial instance font" because you do not instance all design axes.  So, you might slice a weight and width variable font so that the output file supports the entire variable weight axis but includes width defined at an instance value of 100 (standard width).

If slicing sounds like something that you might need to do, see the [Usage](../../docs/usage) docs to learn more about using the app to slice your variable fonts!

If you need some motivation to slice fonts, check out the [Why slice a font?](../../docs/#why-slice-a-font) docs.

And if no more guidance is required, the [Install docs](../../docs/install) are a click away and will show you how to get Slice up and running on your platform.
