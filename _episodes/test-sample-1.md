---
title: "Test Sample 1"
teaching: 0
exercises: 0
questions:
objectives:
keypoints:
---

<style>
    .underline {
        text-decoration: underline;
    }
    #fake-h2-p, #fake-h2-div {
        margin: 48px 0 16px;
        font-size: 30px;
        font-weight: 500;
        line-height: 1.25;
    }
</style>

<!--:

- underlined text
- multiple level one headings (that should be level two)
- skipped heading level(s)
- two headings that are just formatted text
- heading that should not be a heading
- at least one empty link
- links that say "more info" or some such
- links that say "Anchor"?
- Link that has what might be reasonable link text but is ambiguous in this case
- image list with some errors to identify
- heading that is an image of text (but is a legit heading)
-->

# Formatting

## Text

1. Avoid underlining text, as underlines are typically reserved for indicating links.
2. Be wary of using strikethrough. This formatting will not be passed to screen readers, and the line can make the text harder to read. Making the text slightly larger may help with the latter issue.
3. Use left alignment. Left-aligned text maintains consistent character and word spacing. Inconsistently spaced words in justified text can make it difficult to read, and the inconsistent left alignment of centered or right-aligned text is often mistaken for meaningful tab indentations. (If you are writing in text that is supposed to be read from right to left, right alignment will likely be the better choice.)
4. Both sans serif and serif fonts can be accessible or inaccessible, based on a variety of characteristics. Highly recommended fonts include Verdana, Lucida Sans or Lucida Grande, and Georgia. Check out Penn State University's [font sample list](https://accessibility.psu.edu/fontfacehtml/#sample) for more options and comparisons.
5. Italics can be hard to read on digital platforms. Consider using bold or bold and italics instead.

<p id="fake-h2-p">Color</p>

Color can be a great tool, but it must be used with care when creating accessible content. Beyond color contrast, here are a few other issues to consider when choosing colors:

1. Avoid communicating concepts with color alone. Readers who are blind, low vision, or colorblind may miss out on important information if it is only shown via color. Secondary indications, such as icons, underlines or contrast changes may be needed to differentiate elements visually. You will also need to consider what screen reader users will hear to make sure they will receive the necessary concepts.
2. Consider colorblindness when determining color schemes, especially when using any sort of color coding. Use colorblindness simulators to see what your color palette will look like to people with various kinds of colorblindness.
3. Avoid large blocks of brightly colored text. These may be too distracting, or even cause a vibration afterimage effect.
4. Keep backgrounds subtle. Bright or strongly textured/patterned backgrounds can make web pages hard to read.

### Contrast

Accessible content needs to meet a minimum acceptable level of color contrast. Fortunately, you don't have to figure out the ratios yourself, as there are many tools on the web you can use (although you can check the WCAG specifications to find the ratios, if you like). Several are included in the color resources section further down. Bookmark your favorite so you can refer to it whenever you need.

1. Ensure background and foreground colors have sufficient contrast.
2. Ensure background images have sufficient contrast with text. This is often done by darkening the image and using light text or lightening the image and using dark text.
3. Avoid using contrast that is too extreme. For example, pure black (#000) against pure white (#FFF) can actually be worse for some users, especially those with dyslexia or light sensitivity.

### Resources

- [Vibrating Color Combinations](https://accessibility.psu.edu/color/brightcolors/): Examples of bright color combinations to avoid
- [Vischeck](http://www.vischeck.com/vischeck/vischeckImage.php): A tool for uploading images to see what they look like to a colorblind person
- [Contrast Checker](https://webaim.org/resources/contrastchecker/)

TODO: Others

# Identifying Languages

The WAI (Web Accessibility Initiative) recommends the following:

1. Identify the primary language of a web page, such as Arabic, Dutch, or Korean.
2. Identify the language of text passages, phrases, or other parts of a web page.

Your content management system should do the first. You can easily check for this on a given page by using WAVE. WAVE will provide an error if the page language is missing or invalid.

The second is a bit more difficult. Your content management system may provide a way to do this, or it may allow you to edit the HTML directly. If you are editing the HTML, you can wrap the passage with the `span` tag and give the tag the `lang` (language) attribute. You may also want to set the `dir` (direction) attribute, particularly if the language reads from right to left. You can use this [HTML Language Code Reference](https://www.w3schools.com/tags/ref_language_codes.asp) to look up the appropriate value for the `lang` attribute. The `dir` attribute can take either `"LTR"` (left to right) or `"RTL"` (right to left).

Example: `<span lang="en" dir="LTR">This sentence is written in English.</span>`

<div id="fake-h2-div">Images and Alternative Text</div>

Images are a very common form of non-text content. Accessibility for images is centered around providing alternative text, as blind and low-vision users will not be able to view them.

The WAI [Images tutorial](https://www.w3.org/WAI/tutorials/images/) identifies the various types of images and how to develop appropriate alternative text for them. It also includes a helpful alt decision tree and a page with tips and tricks.

When reading the section about complex images, note that approach 4 is not recommended, as longdesc should not be used.
Information about the image that does not describe its content or function, such as copyright or source information, does not belong in the alternative text, but should be placed in the image caption. Image captions may also be used for alternative text, depending on the situation.

If you are familiar with the HTML `longdesc` attribute, you will want to know that it is not recommended as an accessible alternative. Instead, consider including the description in the normal text of the page next to the image. For reference, see [Longdesc Test Cases - WebAIM](https://webaim.org/techniques/alttext/longdesctestcases.htm).

Title text is the text that appears when you hover the mouse over an object. It may also be called hover text. While it does not introduce any accessibility issues simply by existing, it is not generally accessible for anyone using a screen reader, mobile device, or keyboard (instead of a mouse). If you do include title text, ensure that the content is also presented normally in the page text.

Note that `title` and `alt` are the names of attributes in HTML. Other programs, like Microsoft Word, may refer to these differently.

# Tables

Tables are a useful way to structure data, both visually and semantically. Historically, tables have also sometimes been used for formatting content, before CSS provided better options. These tables are often referred to as layout tables or formatting tables. Penn State University has some useful [tips for implementing formatting tables](https://accessibility.psu.edu/multicolumn/#tips).

<h4>Simple tables have at most one header row and one header column, and they do not contain any merged cells.</h4>

1. Define column and row headers. The HTML should use the `<th>` tag and the `scope` attribute for this. This helps the screen reader organize the data to be read in a logical order and identify data types.
2. Do not leave any table header cells empty. The most common offender is the top left cell in tables with both a row and column header.
3. Do not put multiple values in the same cell. Each separate piece of data should have its own cell.
4. Use a title or caption to display a title for the table. Ideally, the `<caption>` tag containing the title should be above the table (visually) as the first thing after the opening `<table>` tag (in the code).
5. If necessary, use the `summary` attribute to clarify the organization of the table or provide a quick summary of its content. The summary should not repeat information in the caption, but can be used to supplement that information. Unlike the caption, the summary will only be presented to screen readers.
6. The `<thead>` and `<tfoot>` elements define header and footer rows for tables. Like the `<tbody>` tag, these do not provide additional accessibility, but they are not inaccessible, either. They may be useful for long tables, and they are certainly helpful for styling the table.

## Table Styling

1. Align text to the left and numeric data to the right (in left-to-right languages). This is especially helpful for people using larger text sizes or smaller screens. It is also a good idea to give column headers the same alignment as the data in the cells below.
2. Styling even and odd rows in a different way can act as a helpful visual guide, especially for people who have reading difficulties or who enlarge text. Also consider highlighting the cell (and row/column) on mouseover (hover) and keyboard focus to help people see where they are. Make sure that the contrast ratio between the text and background is good for both headers and data cells.
3. Tables may be too wide for people using higher zoom levels or smaller screens. Make sure text is not cut off. Horizontal scrolling is typically frowned upon, but using `overflow: scroll` (instead of `overflow: hidden`) is a reasonable way to ensure users will still be able to access the table.
4. Let the browser window determine the width of the table whenever possible, to reduce the horizontal scrolling required of those with low vision. If cell widths need to be defined, use <span class="underline">relative</span> values, such a percentages, rather than pixel values. Avoid defining cell heights to allow cells to expand downward to accommodate their content.
5. Do not use empty cells to visually format the table, such as to indicate a division in various sections of the table. One alternative in that situation would be to use multiple tables, instead.

## Complex Tables

Ideally, complex tables should be avoided. If at all possible, consider replacing one complex table with a series of simple tables. If you must use a complex table, it is theoretically possible to make the table accessible, but this can be very time consuming to implement and may not end up being accessible in practice.

1. Avoid merging cells.
2. [Use the id and headers attributes to associate data cells with header cells.](https://www.w3.org/TR/WCAG20-TECHS/H43.html)

TODO: Add note for the guides this info came from

{% include links.md %}

