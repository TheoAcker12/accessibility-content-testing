---
title: "Special Content Types"
teaching: 10
exercises: 0
questions:
- "What are other types of content that are often inaccessible?"
objectives:
- "Identify some major content types that need special attention."
- "Get resources for more information about these content types."
keypoints:
- "Animated content can cause serious accessibility issues."
- "GIFs are rarely accessible."
- "AV (audio and video) media have to be checked manually."
- "Documents follow a different testing process than web pages."
---

## Animation and Movement

Animated content can be interesting and fun. It can also cause all kinds of potential accessibility issues. We need to be very careful with any moving, blinking, flashing, or otherwise animated content we have included on a page. The most common elements we might find are GIFs and carousels.

A carousel (on the web) is essentially a slideshow that cycles through a set of images. When we find one, the best way to test is to ask the following questions:

1. Does the carousel cycle through the images automatically? If it does, there needs to be a method to pause the cycle. Otherwise it is not accessible.
2. Is the carousel accessible using keyboard navigation or a screen reader? This should be tested when testing the content management system.

GIFs are not recommended, as they rarely meet minimum accessibility requirements. While the best option is to remove any GIFs we find and replace them with more accessible content, we can check for accessibility using the process below, which is the same process we would typically use for any animated content we find.

First, at least one of the following must be true:

1. The GIF (or other content) waits for the user to manually start it, rather than starting automatically.
2. The GIF (or other content) stops automatically within five seconds.
3. There is a relatively easy to find and use method to pause the GIF (or other content).

If none of those statements are true, then the content is not accessible. If at least one is true, however, we still have two more questions to ask before we can continue.

1. Does the GIF (or other content) have accessible alternative text? It may be best to test this with a screen reader.
2. Is it possible for the GIF (or other content) to trigger seizures? Any blinking or flashing content needs to be carefully checked for this!

If you do have any blinking or flashing content, read through [Guideline 2.3 - Seizures and Physical Reactions.](https://www.w3.org/WAI/WCAG21/quickref/#seizures-and-physical-reactions)

## AV Media

Audio, video, or combined audio and video content have their own set of accessibility requirements, which must each be checked manually. Read [Guideline 1.2 - Time-based Media](https://www.w3.org/WAI/WCAG21/quickref/#time-based-media) for more information.

## Documents

Any documents, whether embedded in the page or provided for download, should also be checked for accessibility. These require a different process than web content testing, which will be detailed in a different lesson.

## Math

Special attention must be paid to mathematical expressions and equations to ensure screen readers will read them correctly. In general, a straight reading of the numbers and symbols involved in the expression is insufficient to clearly communicate the full meaning of an expression.

This is best tested with a screen reader. We should be able to write out the expression accurately based on what we hear without worrying about any ambiguity. If we are concerned that our knowledge of what the expression is supposed to be is preventing us from detecting potential ambiguity, we could provide the text from the screen reader to someone else who has not seen the expression and see if it is clear and unambiguous to them.

Read more about [accessible math](https://guides.ou.edu/accessibility-reference/content/text#s-lg-box-wrapper-31201148)

## Tables and Forms

There are additional tests we must perform if we have included any tables or form elements in our content. More information on these will be provided soon.

{% include links.md %}
