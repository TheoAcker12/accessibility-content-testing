---
title: "Images"
teaching: 0
exercises: 0
questions:
- "What is alternative text and why is it important?"
- "How can I check the alternative text of images in my content?"
objectives:
- "Describe the difference between alternative text and the alt attribute."
- "Identify any images without an alt attribute."
- "Check the alt attributes for all images on a page."
keypoints:
- "Alternative text can be provided through an image's alt attribute, image caption, text on the page, or a link to a longer description."
- "Alternative text should not be provided using an image's title attribute (hover text)."
- "WAVE will identify any images that do not have an alt attribute."
- "WAVE will provide the value for all image alt attributes."
- "Appropriate alternative text depends on the type of the image, so it is useful to have a resource to refer to that describes the different types of images."
---

## Alternative Text

Alternative text is essential for making images accessible. This refers to any text that is associated with the image and that conveys the necessary information otherwise conveyed visually by an image.

One of the most common forms of alternative text is the alt attribute, which is associated with HTML image elements. Content management systems provides ways for content creators to set this. Beyond its usage by screen readers, the alt attribute is displayed on the page in situations where the image fails to load

Another attribute that may sometimes be confused with alt is the title attribute. Content management systems will often provide a way to set this, as well, but it doees not share the useful functionality of alt text. Providing extra information with titles is problematic, since the content is only revealed on hover, meaning users who are not aware of a title's existence or who are not using a mouse will likely miss this content entirely. In the context of alternative text, alt typically provides better accessibility than title. Using only alt or both alt and title are both reasonable options, but only title is inadvisable.

The alt attribute is not the only way to provide alternative text. It can be provided in the standard page text before or after the image, in an image caption, or even in another page (assuming the link to the page is clearly associated with the image). Options that display the alternative text visually may be preferable if sighted-users would also benefit from the text. For example, the alternative text might draw attention to a specific part of the image or increase the user's understanding of a complex image.

## Missing Alternative Text

While the alt attribute is not the only way to provide alternative text, it must never be ignored. Alt text can be provided a value (for meaningful images) or set to empty or null (for decorative images), but if left out entirely it will cause accessibility issues.

Fortunately, WAVE will help us check for missing alt attributes by creating errors. The most common error to look for is _Missing alternative text_, but there may be some others.

_Spacer image missing alternative text_ will almost always indicate an image that should be marked as decorative. _Linked image missing alternative text_ and _Image button missing alternative text_ indicate functional images, which we considered in the episode about links.

We already made a note of the linked image on the sample page, but there are also a couple of non-interactive images that are missing alt text.

The first one appears to have alternative text adjacent to it in the page content. To fix this, we should either add an empty alt attribute or some brief alt text identifying the image and possibly indicating that it is described on the page. While this issue, unfixed, would be problematic, and screen reader users would likely wonder if they were missing sometehing important, users would at least be receiving all of the information they need. The second image, however, is an even more serious accessibility issue, since it has no alternative text whatsoever.

We should also pay attention to any _Image with title_ alerts from WAVE. The name of this alert is slightly misleading. It is not provided for every image with a title attribute, but only for images with a title attribute and without an alt attribute. We should treat these the same as _Missing alternative text_ errors.

## Other WAVE Image Checks

WAVE will also provide us with a number of alerts for potentially problematic alt text.

- _Suspicious alternative text_: As with the alert for suspcious link text, we cannot rely on this to help us find all "obvious" issues, but it should find most.
- _Redundant alternative text_: This checks within a very limited range, as explained in the reference info for the algorithm.
- _A nearby image has the same alterantive text_: Likely indicates incorrect alt text and almost certainly indicates unnecessary redundancy.
- _Long alternative text_: Alternative text should be relatively concise. In most cases, when long alternative text is required it should not be provided with the alt attribute.

Once we have checked the errors and alerts, we can run through all the images to check for other issues. WAVE can help with this, but it is primarily a manual process, much like checking heading structure with WAVE.

First, as we did with headings, we want to turn off everything from WAVE that is not relevant to images. This means some/many of the errors, alerts, and features, as well as all contrast errors, structure, and ARIA. Once we have done this we can check out each relevant feature listed by WAVE.

- _Alternative text_: For every image that has alt text, this feature will be included. WAVE will also show the alternative text on the page, so we can easily check that it is accessible. These will typically follow the rules for informative or complex images.
- _Null or empty alternative text_: These images will be ignored by screen readers. While the dominant view for some time has been to mark images as decorative in this way, some blind and low-vision users prefer short alt text identifying the image. We should make sure that these images are truly decorative and that adding even brief alternative text would be more annoying to screen reader users than it would be helpful.
- _Null or empty alternative text on spacer_: The alt text for spacer images should almost always (if not always) be null. We should make sure that any such images are indeed spacers.
- _Linked image with alternative text_: This indicates functional images (as does _Image button with alternative text_).

Determining the appropriate alternative text for an image can be complicated. Therefore, as we check images, we will want to either already be familiar with the various aspects to consider or have a resource to consult with (or both). WAI provides an excellent [images tutorial](https://www.w3.org/WAI/tutorials/images/) that can be useful to look over before testing and to refer to while testing.

A couple of things to remember when checking the image alt text:

- Make sure none of the images have source, copyright, or similar types of info in the alt attribute.
- Make sure words like "image of" are not included in the alt attribute. Variations that replace "image" with more descriptive information may be appropriate in some cases (e.g. diagram, bar chart, screenshot, etc.).

{% include links.md %}

