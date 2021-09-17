---
title: "Text Content"
teaching: 0
exercises: 0
questions:
- "How can I check for formatting issues in my written content?"
objectives:
- "Identify problematic formatting applied to text."
- "Check for content where formatting is used to convey meaning."
- "List types of content that require additional tests."
keypoints:
- "WAVE creates alerts for underlined text that is not part of a link."
- "WAVE creates errors for areas with insufficient contrast between background color and text color."
- "Text alignment can be checked manually."
- "Non-abbreviation text written in all caps can be checked manually."
- "Having the computer read text aloud (typically while you look away) can help with testing many kinds of text content."
---

What is text content?

## Problematic Formatting

Content creators typically have the ability to change various formatting options for words and phrases in text content. This may include changing color or size, as well as applying formatting options like bold, italic, or underlined.

Some formatting options may cause accessibility issues. WAVE can check for two of these: Underlined text and colors with low contrast. Other issues will likely require visual scans of the content.

The first sample page contains examples of several formatting problems.

### Underlined Text

WAVE will create an alert if it detects any underlined text. Underlines should be reserved for links to prevent confusion.

1. Activate WAVE
2. Go to Details to view information about alerts. There will be several alerts, but we are interested in any **_Underlined Text_** alerts.
3. When we find one, we can click on it to jump to the relevant location on the page. The icon associated with the alert is also on the page itself. Hovering over the icon will outline the underlined text.

Now that we've found an issue, we could go to the page's content editor and fix it immediately, or we could make a note of the issue and tackle everything we find after we have finished testing.

### Very Low Contrast

WAVE will also check for contrast issues, creating **_Very Low Contrast_** errors for every one it finds. There are a few limitations to this approach. For one, WAVE only checks to ensure that content meets WCAG AA standards. WCAG AAA provides more stringent contrast requirements. In addition, WAVE cannot check all types of contrast. For example, if text is placed over an image, WAVE cannot determine if the text has sufficient contrast at every point.

> ## Contrast with Background Images
>
> Overlaying images with text is reasonably common on the web, but it can be difficult to ensure appropriate contrast ratios. Here are a coupole of strategies you could employ:
>
> - Darken or lighten the background image, depending on the color of the text. Light text shows up much more clearly on darker images.
> - Give the text an outline in a contrasting color. That way, at any given point either the outline or the text will have good contrast with the image.
{: .callout}

Visually scanning the page may help us identify any issues WAVE unable to catch.

1. Go from Details to Contrast.
2. Investigate the various contrast errors. Click on a few and determine what the issue is.
3. Experiment with using the Lightness sliders to find colors that would not cause errors.
4. Conduct a visual scan of the page. There is text on top of an image at one point. How can we determine if the contrast is sufficient?

### Other Formatting Issues

We can conduct a visual scan of the page content to look for other potential formatting issues.

Some issues, like text alignment can be checked with a brief glance at each block of text.

Paragraphs should be aligned based on the language they are written in. If the language is read left to right (like English) the paragraph should be left-aligned. If it is read right to left (like Arabic) it should be right-aligned. A quick visual scan should be enough to notice any chunks of text with the wrong alignment.

Other tests, like checking for text written in all-caps, require a closer scan of text content.

> ## Finding Underlined Text with WAVE
>
> On the [testing sample page](), which word or phrase (that is not a link) is underlined? Hint: Use WAVE.
>
> > ## Solution
> >
> > TODO
> {: .solution}
{: .challenge}

## Using Formatting to Convey Meaning

Even when custom formatting does not create any accessibility issues directly, other issues can arise if the page content relies on that formatting to convey information.

TODO: Example (using bold/italics) Note how some elements, like code, strong, and em, don't typically provide any indication to screen reader users

A direct way to deal with this would be to copy the content into a plain text editor, like TextEdit or Notepad. That way you can read it without any formatting and ensure that nothing was lost.

A better approach is to have the computer read the text aloud (while you look away). This approach is more useful because it also helps you check the general flow and clarity of content, misspellings, etc.

TODO: How to make the computer read

> ## TODO: Relevant Heading
>
> Which of the following are accessible? TODO
>
> 1. Example that uses color. (If yes: Learner hasn't transferred not relying on bold/italics to not relying on other types of formatting)
> 2. Example that uses bold/italics and other non-formatting indicator. (If no: Learner is confusing using and relying on)
> 3. Example that uses only non-formatting indicator
>
> > ## Solution
> >
> > Options 2 and 3 are accessible, because they include non-formatting indicators.
> {: .solution}
{: .challenge}

## Special Content Types

You may need to test for other potential issues, depending on your content. For example, if you are testing instructional content, manually read through it to make sure no instructions rely solely on sensory characteristics.

Other text content that requires special consideration includes:

- Content in other languages (than the site/page)
- ASCII art and emoticons
- Equations

In general, having the computer read the content aloud will at least help you to identify issues. If the computer mangles words in other languages, gets hung up describing every character in ASCII art, or provides garbled numbers and symbols for equations, then something needs to be fixed.

{% include links.md %}

