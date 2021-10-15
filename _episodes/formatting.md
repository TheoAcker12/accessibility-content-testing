---
title: "Formatting"
teaching: 20
exercises: 0
questions:
- "How can I check for formatting issues in my written content?"
objectives:
- "Detect basic color contrast issues."
- "Understand when color contrast must be checked manually."
- "Identify problematic formatting applied to text."
- "Check for content where formatting is used to convey meaning."
- "Check for descriptions of content that rely on sensory characteristics."
keypoints:
- "WAVE creates errors for areas with insufficient contrast between background color and text color."
- "WAVE cannot check color variations, such as backgrounds with gradients or text overlaying images."
- "WAVE creates alerts for underlined text that is not part of a link."
---

## Modifying Default Formatting

Content creators typically have the ability to set various formatting options for their content, including changing color or size and making text bold, italic, or underlined. Some of these may cause accessibility issues, so it is important to check any formatting that we may have applied to our content.

If you know that you have not changed any formatting from the defaults, you can skip most of these tests. If you have not already, you will need to ensure that the defaults are accessible by testing the content management system, but that is a different process.

## Color Contrast

WAVE creates _Very low contrast_ errors when it finds text and background colors with insufficient contrast ratios. This is convenient, but there are a few limitations. The idea of "trust, but verify" will be a theme as we continue testing. We will want to mark anything WAVE does not catch for manual testing if it like it has low contrast or is otherwise hard to read.

<!--One comes from the fact that there are different contrast requirements for large text and normal text. Theoretically, WAVE takes text size into account, but it may sometimes treat normal text as large, which means it will accept a lower contrast ratio than it should. For another, WAVE cannot check all types of contrast. For example, if a background uses a gradient or an image instead of a single color, WAVE cannot determine if the text has sufficient contrast at every point.-->

1. Go to the [sample page](https://accessibility.oucreate.com/samples/admin/pages/sample).
2. Activate WAVE by clicking the WAVE icon in the browser extensions bar, or by clicking the Extensions (puzzle piece) icon and selecting _WAVE Evaluation Tool_.
3. In the WAVE sidebar that appears, go to the Contrast tab.

There are several contrast errors. We can click on the icons to jump to the relevant section on the page. The icon associated with the error is also on the page itself. Hovering over this icon will outline the text with very low contrast.

In this first error, the green text is too light. The contrast shows the text color (foreground color) and the background color, along with lightness sliders so we can experiment with adjusting the contrast. As we darken the foreground color, WAVE shows us the current contrast ratio, along with which WCAG (Web Content Accessibility Guidelines) requirements it does or does not meet.

> ## Web Content Accessibility Guidelines
>
> The most official guidelines for accessibility are the Web Content Accessibility Guidelines (WCAG), published by the World Wide Web Consortium (W3C). These guidelines come in three levels, from _A_, which lists the bare minimum requirements, to _AAA_, which goes above and beyond. Level A is not generally sufficient for accessibility, so most organizations strive to meet WCAG AA.
>
> Level AAA has more stringent requirements for color contrast ratios (7:1 for normal text and 4.5:1 for large), but WAVE only tests for AA contrast levels (4.5:1 for normal text and 3:1 for large).
{: .callout}

WAVE also changes the color of the text on the page, so we can see what the text would look like if we did modify the color. As soon as we refresh the page the color will go back to its previous state. WAVE cannot actually fix errors we find: We would need to edit the page from our content management system to do that.

Once we have made a note of the contrast error, we can move on and take a look at the other one. This time, we have more options for increasing contrast: We can darken the foreground color, lighten the background color, or both.

<!-->> ## Color Hex Codes
>
> Colors on the web use several different potential formats, including HSL, RGB, and hex. Like units of measurement, these can be converted, as long as you know the value for one format. Perhaps the most common format is the hex code, which is what WAVE provides when it finds contrast errors.
> 
> The hex code is a direct representation of RGB color. RGB codes define the amount of red, green, and blue, using a range from 0 to 255. A hex code consists of a hashtag followed by six characters, two each for red, green, and blue. These characters are actually all numbers, but they use the hexadecimal numbering system, instead of the standard decimal. There is no need to be able to read or write in hexadecimal: The important thing to remember is that, in addition to 0-9, A-F are also valid numeric characters in hex codes.
{: .callout}-->

> ## Exercise: Checking Contrast
>
> For the second contrast error on the sample page:
>
> 1. What background color (hex code) would satisfy WCAG AA, if the foreground color remained the same?
> 2. What foreground color (hex code) would satisfy WCAG AA, if the background color remained the same?
>
> Hint: Clicking on the icon for the contrast error will reset the colors.
>
> > ## Solution
> >
> > 1. A background color of `#E8E8E8` or lighter (`#EBEBEB`, `#EDEDED`, anything beginning with _F_: `#F?F?F?`) would satisfy WCAG AA with the current foreground (text) color of `#C7254E`.
> > 2. A foreground (text) color of `#C6244D` or darker (`#C2244B`, `#BE2349`, `#B92248`, etc.) would satisfy WCAG AA with the current background color of `#E7E7E7`.
> {: .solution}
{: .challenge}

As mentioned, there are some places where WAVE is unable to check for contrast errors. Conducting a visual scan of the page may help us find colors that should probably be checked manually.

The bluish box under the two contrast errors we looked at on the sample page seems like something that could have low contrast. Maybe WAVE missed it because the contrast is sufficient, but it is suspicious enough to take a closer look.

Unfortunately, we cannot test this with WAVE. There are some tools that can be used to find colors on a website, but if we are the content creators it may be easier to get them directly from the content management system. We may not remember what colors we have applied, but we should be able to find them when we try editing the page. Once we have found the colors we want to check, we can find the contrast between them using the [contrast checker](https://webaim.org/resources/contrastchecker/) that WebAIM (Web Accessibility In Mind) provides. In fact, since WebAIM produces WAVE, this is the same contrast checker that is embedded in WAVE.

In this case, the text color is `#494dca` and the background color is a linear gradient from `#c8ccef` to `#d0d2f1`. This means that the background color will transition from one of those colors to the other, so we should check the contrast of each of them. If both have sufficient contrast, then any color between them should also have sufficient contrast. As we can see, however, the contrast here is too low.

The sample page also has some text over an image, which represents another potential contrast issue WAVE cannot check. WAVE actually thinks there is a contrast issue between the text and background, which helps to illustrate what is going on. WAVE thinks the background is the same white as the rest of the page: It is not checking the image at all.

> ## Contrast with Background Images
>
> Our options may be limited by the content management system, but here are two ways we might ensure that the contrast ratio is sufficient for text overlaying an image:
>
> - Darken or lighten the background image, depending on the color of the text. Light text shows up much more clearly on darker images.
> - Give the text an outline in a contrasting color. That way, at any given point either the outline or the text will have good contrast with the image.
{: .callout}

## Underlined Text

In WAVE, go from Contrast to Details to view information about errors and alerts. There will be several, but we are interested in any Underlined text alerts. We can click on these to see what text is underlined that probably should not be. Hovering over or clicking on the icon (in the WAVE sidebar or on the page) outlines the text: underlined text should be avoided.

If we are not sure why underlined text would be an issue, we can click on the "i" next to the icon in the WAVE sidebar, to see information about the alert in the reference tab. In this case, we see that underlines are associated with linked text. Underlining text that is not a link may confuse readers, and it may also obscure which parts of the content are actually links and which are not.

> ## Exercise: Finding Underlined Text
>
> On the [testing sample page](https://accessibility.oucreate.com/samples/test-sample), which word or phrase (that is not a link) is underlined? Hint: Use WAVE.
>
> > ## Solution
> >
> > The word _relative_ is underlined. It can be found under the _Table Styling_ heading in the fourth list item.
> {: .solution}
{: .challenge}

> ## Other Problematic Formatting
>
> Underlined text is not the only type of formatting that can cause issues, but it is one of the few that can be easily tested for. Other issues, like writing (non-abbreviated) words in all capital letters to emphasize them or using centered or justified text alignment will typically have to be checked manually.
{: .callout}

## Meaningful Formatting

Even when custom formatting does not create any accessibility issues directly, other issues can arise if the page content relies on formatting, rather than text or meaningful elements, to convey information or structure.

Here is an example of relying on formatting to convey meaning: An instructor provides a paragraph for their students to read. In the paragraph certain words are in bold: The students are to make note of these words and do something with them. (Maybe study their definitions because they'll be on a test?)

If we look at the HTML for the paragraph, we find that the bolded words use the `<strong>` element. In other words, bold is not applied purely through formatting (though it can be). However, screen readers typically do not indicate when an element is bolded this way. There are several formatting options content creators can use that create meaningful HTML elements. Three examples are **bold** (`<strong>`), _italics_ (`<em>`), and `code` (`<code>`).

In this example, how could the instructor make the content more accessible? One option would be to include a list of all the important words at the end of the paragraph.

Some related issues would be:

- Using punctuation to convey meaning. Punctuation may not be considered formatting, but it is rarely announced by screen readers.
- Using whitespace characters (e.g. spaces or tabs) to create space between letters in a word or to create visual structure, like columns.
- Creating lists purely with text, rather than using meaningful list elements.

### Referring to an Element's Formatting

There are a couple things to watch out for with formatting conveying meaning. One is as mentioned, where formatting is applied to content in order to convey additional information beyond that provided in the text, but another can occur when writing instructions that refer to interactive elements on the page or elsewhere. If the elements are described using solely sensory characteristics (shape, color...), then whether or not the element is accessible, screen reader users will not know what to search for.

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

