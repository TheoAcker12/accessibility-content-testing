---
title: "Images"
teaching: 0
exercises: 0
questions:
- "Key question (FIXME)"
objectives:
- "Identify any images without an alt attribute."
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---

<!--
Concepts/Issues:
- All images have alt attributes.
- No images of text are included.
- All decorative images are hidden from assistive technology.
- Image alt attributes are short and to the point.
    - No source/copyright info
    - Don't repeat text on page
- Alt text for functional images describes function, not image.
- All informative images have alternative text that provides the same meaning/information as the image.
- Images/non-text content that is part of an exercise or test at least has descriptive identification.
- Complex images have thorough descriptions either on the same page or on a linked page.

Plan:
- Note:
    - What is alternative text?
    - Alt attribute vs. title attribute vs. alternative text
- Check for missing alt text with WAVE.
- Go through each image with WAVE:
    - Image of text?
    - Any alerts?
    - Decorative, functional, or informative?
    - Complex?

Refer:
- ASCII art and emoticons (callout?)
- Resources to help determine the type of image and the appropriate alt text
-->

- Images and importance of alternative text
    - Blind and low-vision readers
    - Colorblindness (probably only if visible)
    - Increased understanding of image/what is important in image for sighted readers (only if visible)
- Alt attribute:
    - CMS should provide a way to set this
    - Displayed if image cannot load on the page for any reason
    - Read by screen readers
- Title attribute:
    - CMS may provide a way to set this
    - Displayed on hover
    - Cannot be counted on to be provided in place of alt text
    - Not all users will be aware of it or able to access hover text
- Alternative text:
    - Does not have to provided with alt attribute
    - Sometimes can benefit sighted users, too

## Missing Alternative Text

- There are other ways to provide alternative text, but the alt attribute can never be ignored. It must always be set (even if it is set to null).
    - If alt is null, screen readers will ignore the image
    - if alt does not exist, screen readers will do things like read the image URL - not very helpful!

WAVE will create errors for any image lacking alt text. It will not create errors for null alt text.

The most common error to look for is _Missing alternative text_, but there may be some others:

- _Linked image missing alternative text_
- _Spacer image missing alternative text_
- _Image button missing alternative text_
- _Image map area missing alternative text_?
- _Image map missing alternative text_?

TODO: On the sample page, note what issues we find.

## Checking Images with WAVE

As we did with headings, we can turn off everything in WAVE except for the errors, alerts, and features we are currently interested in.

1. Turn off all errors except for those about missing alternative text.
2. Turn off all alerts except for the following:
    - _Suspicious alternative text_: Will quickly alert us of the most obvious issues in alternative text.
    - _Redundant alternative text_: Has a limited range, and is only checking for exact matches, but still useful.
    - _A nearby image has the same alternative text_: Likely indicates incorrect alt text and almost certainly indicates unnecessary redundancy.
    - _Long alternative text_: Sometimes longer alt text may be appropriate, but it is generally best to keep it as short as possible.
    - _Long description_?
    - _Image with title_: Titles are not a suitable replacement for alt text.
3. We can go through each of the images on the page. WAVE will show the image alt text next to the image. (Look for the _Alternative text_ feature, or a related feature).
4. If there are a lot of images, we can turn each image off once we have determined whether or not it has any issues.

As we go through each image, we first must determine what type of image it is so that we know exactly what to check for. Each type will be briefly described in its section. TODO: Link to more in-depth resource?

### Images of Text

Is it essential that the text is provided as an image?

- Yes: Ensure that the alt text for the image exactly matches the text shown.
- No: Replace the image with the text itself.

Note: There may be situations where there is a large image of text that is needed, like a scan of a handwritten document. In this case, the text is too long to be provided in reasonably short alt text, so it is better to provide the alternative text the way we would a complex informative image (described further below).

Point out the logo as an example of essential image of text. Point out the h1 as an example of non-essential image of text.

### Functional Images

A functional image is one that performs some kind of interactive function. Typically this would be an image that serves as a link or button or as part of a link or button. If the image is a link, this will already have come up to some degree when checking link text, but it never hurts to doublecheck.

WAVE may helpfully indicate alt text for functional images with the following features:

- _Linked image with alternative text_
- _Image button with alternative text_

Does the functional element (e.g. link or button) consist of only the image, or of an image and text?

- Only the image: The alt text should indicate the function (e.g. the destination of the link or action performed by the button).
- Image and text: As long as the text adequately indicates the function, the image alt text should be null.

Note: In rare cases the content of the image may be important, but normally is is better not to describe the image in order to avoid cluttering up the link (or other interactive element) text.

### Decorative Images

Most images content creators add would not be considered decorative. Decorative does not mean an image included because it is pretty. If an image is included because it is pretty, it will typically be considered informative, if only because it helps create interest or contributes to the modd of the page. A decorative image would be something like a star icon separating words in a list or ... TODO: Better explanation/examples?

Look for a _Null or empty alternative text_ or _Null or empty alternative text on spacer_ feature.

### Informative Images

Most images will probably be informative to some degree.

If the content from the image can be communicated in maybe 1-2 sentences, make sure the alternative text WAVE shows provides the appropriate information. Otherwise, make sure the appropriate information is included elsewhere and that the alt text indicates where it can be found (e.g. "screenshot of the blah blah blah, as described above/below" or "diagram of blah blah blah, as described in the link below").

Notes:
- When do you provide a descriptive identifier instead of full alternative text?
- Make sure things like source or copyright info are never included in alt attribute.
- Make sure words like "image of" are not included. May be appropriate if providing additional information, however (e.g. diagram, bar chart, screenshot, etc.).

TODO: Exercises

- What is wrong with including an image of text with alt text that contains the text content? (probably a discussion) - consider: length of text, how easy it is to read or zoom compared to standard text, cases where the image is of a historical document and text content is also included in a transcript
- What information should be included in the alternative text for the following image?
- Which of the following are appropriate methods for providing alternative text?
- Discussion: Is this image informative or decorative?
- Indicate which images have accessible alternative text and which do not?

{% include links.md %}

