---
title: "Formatting/Text"
teaching: 0
exercises: 0
questions:
- "How can I check for formatting issues in my written content?"
objectives:
- "Detect basic color contrast issues."
- "Identify problematic formatting applied to text."
- "Check for content where formatting is used to convey meaning."
- "Check for content where formatting is used to convey structure."
keypoints:
- "WAVE creates errors for areas with insufficient contrast between background color and text color."
- "WAVE creates alerts for underlined text that is not part of a link."
- "Text alignment can be checked manually."
- "Having the computer read text aloud (typically while you look away) can help with testing many kinds of text content."
- "WAVE identifies structural elements, like lists."
---

<!--
Concepts/issues:
- Background and foreground colors have sufficient contrast.
- Non-link text is not underlined.
- Formatting (e.g. color, misc elements) is never the sole method of conveying info or relationships.
- Whitespace is not used to create space between letters in a word (or to create structure).
- All lists are "real" lists.
- Punctuation is not necessary for understanding text content.
- Instructions do not solely rely on sensory characteristics like shape, color, or position.

Plan:
- Test color contrast with WAVE.
- Test for underlined text with WAVE.
- Test lists with WAVE.
- Check formatting, whitespace, and puctuation with a screen reader.
- Manually check instructions (callout).

Reference:
- Other formatting considerations, provide link
-->

Content creators typically have the ability to set various formatting options for their content, including changing color or size and making text bold, italic, or underlined. Some of these may cause accessibility issues, so it is important to check any formatting that we may have applied to our content.

If you know that you have not changed any formatting from the defaults, you can skip most of these tests. Of course, you will first need to ensure that the defaults are accessible by testing the content management system, but that is a different process.

## Color Contrast

WAVE creates _Very low contrast_ errors when it finds text and background colors with insufficient contrast ratios. This is very convenient, but there are a few limitations to keep in mind. One comes from the fact that there are different contrast requirements for large text and normal text. Theoretically, WAVE takes text size into account, but it may sometimes treat normal text as large, which means it will accept a lower contrast ratio than it should. For another, WAVE cannot check all types of contrast. For example, if a background uses a gradient or an image instead of a single color, WAVE cannot determine if the text has sufficient contrast at every point.

> ## Web Content Accessibility Guidelines
>
> The most official guidelines for accessibility are the Web Content Accessibility Guidelines (WCAG), published by the World Wide Web Consortium (W3C). These guidelines come in three levels, from _A_, which lists the bare minimum requirements, to _AAA_, which goes above and beyond. Level A is not generally sufficient for accessibility, so most organizations strive to meet WCAG AA.
>
> Level AAA has more stringent requirements for color contrast ratios (7:1 for normal text and 4.5:1 for large), but WAVE only tests for AA contrast levels (4.5:1 for normal text and 3:1 for large).
{: .callout}

1. Go to the appropriate sample page.
2. Activate WAVE.
3. Go to the Contrast tab.
4. There are several contrast errors. We can click on the icons to jump to the relevant section on the page. The icon associated with the error is also on the page itself. Hovering over this icon will outline the text with very low contrast.

Colors on the web use several different potential formats, including HSL, RGB, and hex. Like units of measurement, these can be converted, as long as you know the value for one format. Perhaps the most common format is the hex code, which is what WAVE provides when it finds contrast errors.

The hex code is a direct representation of RGB color. RGB codes define the amount of red, green, and blue, using a range from 0 to 255. A hex code consists of a hashtag followed by six characters, two each for red, green, and blue. These characters are actually all numbers, but they use the hexadecimal numbering system, instead of the standard decimal. There is no need to be able to read or write in hexadecimal: The important thing to remember is that, in addition to 0-9, A-F are also valid numeric characters in hex codes.

When wew click on a contrast error in WAVE, the background and foreground colors are provided as hex codes. There are also two lightness sliders, which we can use to find suitably similar colors with sufficient contrast.

> ## Exercise: Checking Contrast
>
> For (TODO: specify contrast error):
>
> 1. What background color would satisfy WCAG AA, if the foreground color remained the same?
> 2. What foreground color would satisfy WCAG AA, if the background color remained the same?
>
> > ## Solution
> >
> > 1. TODO
> > 2. TODO
> {: .solution}
{: .challenge}

As mentioned, there are some places where WAVE is unable to check for contrast errors. Conducting a visual scan of the page may help us find text that is harder to read than it should be, as well as obvious places that need to be manually checked.

TODO: Mention inspect element?

If we want to check the contrast between two given colors, WebAIM provides a [contrast checker](https://webaim.org/resources/contrastchecker/) that accepts hex codes. In fact, since WebAIM produces WAVE, this is the same contrast checker that is embedded in WAVE.

TODO: Challenge? - Conduct a visual scan of the page. There is text on top of an image at one point. How can we determine if the contrast is sufficient?

> ## Contrast with Background Images
>
> Overlaying images with text is reasonably common on the web, but it can be difficult to ensure appropriate contrast ratios. Here are a coupole of strategies you could employ:
>
> - Darken or lighten the background image, depending on the color of the text. Light text shows up much more clearly on darker images.
> - Give the text an outline in a contrasting color. That way, at any given point either the outline or the text will have good contrast with the image.
{: .callout}

## Underlined Text

TODO: How much is it worth including this?

In WAVE, go from Contrast to Details to view information about errors and alerts. There will be several, but we are interested in any _Underlined text_ alerts. We can click on these to see what text is underlined that probably should not be.

If we are not sure why underlined text would be an issue, we can click on the _i_ icon, which will switch us to the Reference tab and provide additonal information about the alert. In this case, we see that underlines are associated with linked text. Underlining text that is not a link may confuse readers, and it may also obscure which parts of the content are actually links and which are not.

> ## Exercise: Finding Underlined Text with WAVE
>
> On the [testing sample page](), which word or phrase (that is not a link) is underlined? Hint: Use WAVE.
>
> > ## Solution
> >
> > TODO
> {: .solution}
{: .challenge}

TODO: Callout noting other types of problematic formatting?

## Meaningful Formatting

Even when custom formatting does not create any accessibility issues directly, other issues can arise if the page content relies on formatting, rather than text or meaningful elements, to convey information.

Here is an example of relying on formatting to convey meaning: An instructor provides a paragraph for their students to read. In the paragraph certain words are in bold: The students are to make note of these words and do something with them. (Maybe study their definitions because they'll be on a test?)

If we look at the HTML for the paragraph, we will see that the bolded words use the `<strong>` element. In other words, bold is not applied purely through formatting (though it can be). However, screen readers typically do not indicate when an element is bolded this way. There are several formatting options content creators can use that create meaningful HTML elements. Three examples are bold (`<strong>`), italics (`<em>`), and code (`<code>`). (TODO: Make sure people will understand code in this context. I know it's a standard formatting option in markdown, but I'm not sure about rich text editors.)

In the above example, how could the instructor make the content more accessible? One option would be to include a list of all the important words at the end of the paragraph.

Some related issues would be:

- Using punctuation to convey meaning. Punctuation may not be considered formatting, but it is rarely announced by screen readers.
- Using whitespace characters (e.g. spaces or tabs) to create space between letters in a word or to create visual structure, like columns.
- Creating lists purely with text, rather than using meaningful list elements.

TODO: How much do lists and meaningful elements need to be explained?
- should probably include text or discussion on how one might accidentally make a fake list

### Screen Reader Testing

- best way to test is with screen reader
- why?
    - will test all the issues mentioned - formatting, punctuation, or whitespace conveying meaning or structure, lists
    - will test other accessibility issues - there's no end to the things you can catch with a screen reader
    - helps demonstrate the importance of some of the other things we'll look at (e.g. headers, links)
    - will help you check other things like flow and clarity of content, misspellings, etc.
- include demonstration with they why
- how?
    - which screen reader depends on which operating system
    - recommend some basic (built-in) screen readers, and link to information on how to use them
    - note that you don't need to do anything very fancy with these - the most important thing is to walk through all of the content step by step to catch the kinds of things we mentioned
    - of course, you can do things like demonstrated with the VoiceOver rotor, etc., but don't feel like you have to

- callout: how to test without a screen reader
    - not going to be as good/useful, but there are alternatives
    - To check for content relying on formatting: Copy and paste the content into a plain text editor, like TextEdit or Notepad. That way you can read it without any formatting and ensure that nothing was lost.
    - Use WAVE to look for lists.
    - Not much you can do about other things, beyond reading through content

### Referring to Formatting

TODO: Not sure this is the best way to do this

- there are a couple things to watch out for with formatting conveying meaning
    - one is as mentioned, where formatting is applied to content in order to convey additional information beyond that provided in the text
    - but another occurs when writing instructions that refer to interactive elements on this page or elsewhere - if an element is described only with its formatting, it doesn't even matter if the element is accessible, since either way it isn't being referred to accessibly.

TODO: Include challenge on conveying meaning?

<!-- For this exercise, there are three goals:
    1. Learners can transfer what they've learned about one type of formatting to other types of formatting.
    2. Learners can recognize the difference between using and relying on formatting to convey meaning.
    3. Learners can transfer what they've learned in one context (e.g. color-coding words to indicate which category they belong to) to a different context (e.g. referencing other elements by referring to formatting). -->

> ## Exercise: Formatting and Meaning
>
> 1. A list of words that are color-coded to indicate which category they belong to.
> 2. Italics used to highlight a word that we are talking about: We want to output the lines that do not contain the word *the*.
> 3. Instructions to click the blue square button at the top right of the page with the pencil icon on it.
> 4. Instructions to click the *Next* button.
>
> > ## Solution
> >
> > Options 2 and 4 are accessible.
> >
> > 1. Not accessible: This option relies purely on color to indicate the category for each word.
> > 2. Accessible: This option uses formatting in a way that, while visually useful, does not convey additional meaning.
> > 3. Not accessible: This option uses a lot of different formatting aspects to refer to a button, but does not include any non-formatting indicators. It could be made accessible by finding the button's name and including it.
> > 4. Accessible: Refers to a button's name, which does not rely on formatting. Including some formatting would probably be helpful for some users, however. For example: Click the green *Next* button at the bottom of the page.
> {: .solution}
{: .challenge}

{% include links.md %}

