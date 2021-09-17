---
title: "Test Results"
teaching: 0
exercises: 0
questions:
- "Key question (FIXME)"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---

## Color Contrast Issues

These should all be pretty straightforward fixes. They involve modifying syntax.css and lesson.scss.

### Code Highlighting

- "Comment" color
- "Comment.Preproc" color
- "Generic.Error" color
- "Generic.Inserted" color
- "Generic.Output" color
- "Name.Attribute" color
- "Name.Entity" color
- "Name.Exception" color
- "Name.Label" color
- "Text.Whitespace" color
- "Literal.String.Escape" color
- "Literal.String.Interpol" color

Colors for all but Text.Whitespace are suggested below. I am not sure what the point of a whitespace color is, since whitespace inherently has no color. It should either be changed to the new Generic.Output color (since it is grayscale) or it should be removed entirely.

<div class="language-plaintext">
    <pre class="highlight">
        <code>
    <span class="c">Current Comment color</span>
    <span class="c" style="color: #377B7B">Comment color for AA (#377B7B)</span>
    <span class="c" style="color: #295B5B">Comment color for AAA (#295B5B)</span>
    <span class="cp">Current Comment.Preproc color</span>
    <span class="cp" style="color: #9E6700">Comment.Preproc color for AA (#9E6700)</span>
    <span class="cp" style="color: #754C00">Comment.Preproc color for AAA (#754C00)</span>
    <span class="gr">Current Generic.Error color</span>
    <span class="gr" style="color: #E60000">Generic.Error color for AA (#E60000)</span>
    <span class="gr" style="color: #AD0000">Generic.Error color for AAA (#AD0000)</span>
    <span class="gi">Current Generic.Inserted color</span>
    <span class="gi" style="color: #008500">Generic.Inserted color for AA (#008500)</span>
    <span class="gi" style="color: #006100">Generic.Inserted color for AAA (#006100)</span>
    <span class="go">Current Generic.Output color</span>
    <span class="go" style="color: #707070">Generic.Output color for AA (#707070)</span>
    <span class="go" style="color: #545454">Generic.Output color for AAA (#545454)</span>
    <span class="na">Current Name.Attribute color</span>
    <span class="na" style="color: #687722">Name.Attribute color for AA (#687722)</span>
    <span class="na" style="color: #4D561A">Name.Attribute color for AAA (#4D561A)</span>
    <span class="ni">Current Name.Entity color</span>
    <span class="ni" style="color: #707070">Name.Entity color for AA (#707070)</span>
    <span class="ni" style="color: #545454">Name.Entity color for AAA (#545454)</span>
    <span class="ne">Current Name.Exception color</span>
    <span class="ne" style="color: #D13B33">Name.Exception color for AA (#D13B33)</span>
    <span class="ne" style="color: #9E2A24">Name.Exception color for AAA (#9E2A24)</span>
    <span class="nl">Current Name.Label color</span>
    <span class="nl" style="color: #757500">Name.Label color for AA (#757500)</span>
    <span class="nl" style="color: #575700">Name.Label color for AAA (#575700)</span>
    <span class="se">Current Literal.String.Escape color</span>
    <span class="se" style="color: #A85D1F">Literal.String.Escape color for AA (#A85D1F)</span>
    <span class="se" style="color: #7D4517">Literal.String.Escape color for AAA (#7D4517)</span>
    <span class="si">Current Literal.String.Interpol color</span>
    <span class="si" style="color: #B04F76">Literal.String.Interpol color for AA (#B04F76)</span>
    <span class="si" style="color: #863C5A">Literal.String.Interpol color for AAA (#863C5A)</span>
        </code>
    </pre>
</div>

### Other Contrast Issues

- Caution blockquote: This is not detected automatically because the background uses a linear gradient. The best colors to switch to depend on whether the red should be significantly lightened and the text potentially darkened, or the text significantly lightened and the red potentially darkened.
- Visited link color: Change to `#147FA9` (AA) or `#0F5C7B` (AAA). Could also go from blue to something like purple if it needs to stand out more compared to unvisited links.
- Navbar contrast: Change text color to `#707070` (AA) or `#545454` (AAA).
- Testimonial blockquote (low priority): Already meets AA, but could change to `#FCABCE` to meet AAA.
- Default link color (low priority): Already meets AA, but could change to `#145999` to meet AAA.

## Navigation

### Keyboard Navigation

Very serious issue: Challenge solutions are unreachable by keyboard. They also aren't as obvious as they should be for mouse users.

Recommended course of action:

1. Wrap heading in a button and make the button what activates the code for expanding/collapsing. This will also require CSS changes to make things look the same. Giving heading `role="button"` may not require the CSS changes, but tabindex would also need to be set, the expand/collapse code might need to be modified to allow keypresses to activate it, and it is bad practice not to use HTML elements when they apply.
2. Change CSS as needed so the new button element doesen't mess up the appearance.
3. Change CSS on hover to `cursor: pointer`.

### Navbar

Issues:

- The focus order for the navigation toggle button (on small screens) does not match visual presentation, which also means that the content it shows or hides does not come directly after it.
- Navbar dropdown menus (Episodes and Extras) do not have sufficient focus indication.

Recommendations:

1. Move the button element to after the two initial header links. This does not mess up functionality or formatting.
2. Remove or overwrite the following from dropdowns.less:
```css
.dropdown-toggle:focus {
    outline: 0;
}
```

### Bypass Block

There is no bypass block.

1. Add a skip link in the HTML at the very beginning of the page (before the life-cycle div) that goes to the main content.
2. Use CSS so that the link is only visible when tabbed to.

Sample CSS:

```css
.skip-link {
  position: absolute;
  top: -70px;
  left: 20px;
  padding: 15px 10px;
  text-decoration: underline;
  color: #004fa3;
  background-color: #fff;
  transition: top 0.5s ease;
  box-shadow: 0 0 2px 2px #4c4c4c;
  box-shadow: 0 0 2px 2px rgba(76, 76, 76, 0.5);
  z-index: 10;
  border: 2px solid #333;
  border-radius: 10px;
}
.skip-link:focus, .skip-link:active {
  top: 15px;
}
.skip-link:visited {
  color: #004fa3;
}
```

## Headings and Landmarks

### Landmark Roles

Issues:

- There is no main landmark.
- Current navigation landmark might be better suited as a header with navigation within.
- Previous page/next page navigation sections do not have nagivation landmark

Recommendations:

1. Replace `<article>` element with `<main>` element.
2. Replace `<nav>` element with `<header>` element.
3. Wrap `<ul class="nav navbar-nav">` in `<nav aria-label="Primary">` element.
4. Replace both previous/next page navigation `<div>` elements with `<nav>` elements and give them both `aria-label="Page"`.

Note: The first page navigation element contains a link to the site home page, making it slightly different. This might be fine, but I would check with Donna, first.

### Headings

Issues:
- Previous page/next page navigation links are marked as headings
- Home link (between the first prev/next page links) is marked as a heading

Recommendations:

1. Change all headings `<h3>` in page navigation sections to divs. (This has the added benefit of not making them utterly useless anchor links.)
2. Discuss what to do about special blockquotes as a whole (see relevant section).

## Anchor Links

Current anchor link implementation is not great. Because the link is part of each heading, it makes listing the headings with a screen reader (tested with VoiceOver) rather weird. There are two potential routes as referenced in the article [Are your anchor links accessible?](https://amberwilson.co.uk/blog/are-your-anchor-links-accessible/) Both have pros and cons. I listed a few pros for each, but there could be others worth thinking about. I think I might personally lean toward option 2 at the moment.

### Option 1

Instead of making the anchor link a child of the heading, have it come after the heading. Make sure the icon is hidden from screen readers and that the heading information is provided.

```html
<h2 id="overview">Overview</h2>
<a href="#overview">
  <i aria-hidden="true"></i> <!-- Add appropriate class to display anchor icon -->
  <span class="sr-only">Overview anchor</span> <!-- There should be a lot of reasonable options for phrasing -->
</a>
```

Pros:
- Separates headings from the anchor links
- Allows different text in anchor link and heading (e.g. "Overview" vs. "Overview anchor")
- May be the more familiar option

### Option 2

Make the whole heading the anchor link.

```html
<h2 id="overview">
    <a href="#overview">
        <i aria-hidden="true"></i> <!-- Add appropriate class to display anchor icon -->
        Overview
    </a>
</h2>
```

Pros:
- Bigger tap area for mobile
- Avoids potential Google SERP, RSS, and Reader Mode issues
- Can hide anchor icon when desired without hiding the anchor

## Special Blockquotes

The blockquotes are the most complicated issue to consider. They currently have the following issues:

- The `<blockquote>` element is used to style non-quote text. I'm not sure how much this matters or not, but semantically it is an incorrect usage of the element.
- The block visually distinguishes important text, but does not fully indicate this to screen reader users. The headings may help with this, but they don't indicate exactly what text belongs to the block and what text comes after the block has finished. I am not sure to what extent this is an issue: It would be helpful to ask an accessibility expert.
- The blocks require level two headings, even though that heading level will not always be appropriate. This is especially an issue when considering there may be text after the block that belongs under the previous heading level two.
- The block headings do not have the same style as regular h2s. This may or may not be an issue.
- The icons added to the block headings are not fully hidden from screen readers.

Addressing these may be complicated in two ways. For one, it may require somewhat significant (but necessary) template code and style changes. For the other, determining the most appropriate implementation has a lot of factors to consider.

Goals:

1. Use an element other than `<blockquote>` to style these special blocks. Complications arise due to the fact that existing lessons use blockquotes in Markdown and that the blocks should be writable with Markdown (no HTML). Potential solution: When generating HTML from the Markdown, find all blockquote instances (or all blockquote instances with specific classes) and switch these to the appropriate element.
2. Ensure that the blocks stand out to screen reader users. Headings may be sufficient for this purpose. Of concern is that these headings are differentiated in some manner from other headings (see goal 4).
3. Ensure that screen reader users can determine the start **_and the end_** of the blocks. While headings may identify the start, there is not a corresponding ending element. Could test if `role="note"` announces this to screen reader users or not. Another option would be to automatically add in a sr-only span indicating the end of that particular content type (callout, challenge, etc.). This should probably go hand-in-hand with a similar sr-only span indicating the beginning of the content type (see goal 4).
4. Ensure that the block type (as indicated by color and icon) is detectable by screen readers. This isn't an issue for some of these. Blocks with headings of "Key Points" or "Overview" are already self-explanatory. However, various notes added by users may or may not indicate the block type in the heading. For those that do not, adding an indication, perhaps to the heading itself, could be helpful. Adding text to the heading wouldn't be very hard. The tricky bit is only adding it when necessary to prevent, for example, a heading that states: Challenge Challenge. Maybe this is something content creators would need to indicate, or maybe it is something that should be determined programmatically, or maybe even some combination of the two.
5. Ensure that the blocks do not mess up proper heading structure. Forcing all blocks to start with h2 makes it impossible to use them effectively and accessibly. Likewise, forcing them all to start with some other heading level would also cause problems. However, if multiple heading levels are allowed, perhaps even h2-h6, there is a potential issue with keeping the formatting consistent, since theoretically h2 should never have the same style as h3, and so forth. This is an issue where we really need to consult with an accessibility expert (or several).
6. Ensure that the heading icons are properly hidden from screen readers. Solution: Instead of attaching the icon CSS to the heading itself, attach it to an element like `<i class="appropriate_class_goes_here" aria-hidden="true"></i>`.

## Assorted Issues

- Markdown task list introduces error due to lack of form label. Solution: Make a note in handbook and in workshop template to avoid using this. (I haven't noticed people using it, but it doesn't hurt to let people know about the issue.)
- Link to relevant Carpentries website (in header) describes image, rather than link destination. Solution: Remove the word logo. (e.g. "Data Carpentry logo" becomes "Data Carpentry")
- Search uses aria-label, which should only be used when there isn't another option. Solution: Change code to provide form label directly:
```html
    <div class="form-group">
        <label for="google-search" class="sr-only">Google site search</label>
        <input type="text" id="google-search"  placeholder="Search...">
    </div>
```
- Potentially an issue that search does not allow activation via mouse. Solution: Add a submit button to activate search that can be clicked with a mouse (or activated with keyboard, of course). Button could say Search, which would remove need for placeholder text in the input. Or the button could show a magnifying glass icon and indicate its function using a sr-only span.

### Formatting

- Increase `<kbd>` font size. 11px is annoyingly small.
- Potentially increase overall font size slightly.
- Potentially switch to using relative font sizes (this might be too much effort to be worth it).
- Change body font (code block font is fine) so that I, l, and 1 are easily distinguished, as well as O and 0.
- Consider giving tables the "table-bordered" class by default. Not too hard to add `{: .table-bordered}` manually, though.
- Give ordered lists different styles at different levels (e.g. 1,2,3 followed by a,b,c).

{% include links.md %}

