---
title: "Special Content Types"
teaching: 0
exercises: 0
questions:
- "Key question (FIXME)"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---

There are a number of specialized types of content that require specific accessibility considerations. There may not be a good way to easily check for these with a tool like WAVE or Accessibility Insights for Web, but they are specialized enough that we will probably know whether or not they are relevant to our content.

## Animation and Movement

Animated content can be interesting and fun. It can also cause all kinds of potential accessibility issues.

When checking our content, we will most likely already know whether or not we included any moving, blinking, or flashing content. If not, however, we can scroll down the page and look for anything that moves. The most common things we might find are GIFs and carousels.

A carousel (on the web) is essentially a slideshow that cycles through a set of images. The issue is when the carousel cycles through the images automatically, rather than requiring user input. We can check this by waiting to see if it starts automatically. Then, if it does, we can look for a method to pause the cycle.

### GIFs

GIFs are not recommended, as they rarely meet minimum accessibility requirements. They may be implemented in a variety of ways, which means we must rely on memory and visual checks rather than looking for specific alerts or features in WAVE. If we find any GIFs, the best thing to do is to remove them and replace them with more accessible content, but we can check if an existing GIF is accessible by doing the following:

First, we have three questions to ask. We only need the answer to be "yes" to one of them, so as soon as we answer a question positively we can move on.

1. Does the GIF wait for us to manually start it instead of starting automatically?
2. Wait for five seconds. Does the GIF stop automatically?
3. Is there some way to pause it? The controls for pausing GIFs should be easy to find and use, so if we can't quickly pause the animation we can consider this question failed.

If we answered yes to one of the above questions, there are still a couple more things we have to check.

1. Does the GIF have accessible alternative text? Since implementation may vary, it would be easiest to check this using a screen reader and see what is communicated when it reaches the GIF.
2. Is it possible for the GIF to trigger seizures? This is described further in the next section.

These requirements are not specific to GIFs, so if we encounter any other moving content we will check for the same things.

### Blinking and Flashing Content

Deep discussion of seizure thresholds is out of scope for this episode. If we find any content that blinks or flashes, the best course of action would be to remove the content or prevent it from blinking or flashing.

If WAVE detects blinking content it will create a _Blinking content_ error. This only checks one specific method of making content blink, so we should always perform a manual visual check for such content.

## AV Media and Documents

Audio-only, video-only, or synchornized audio and video content have their own set of accessibility requirements. There is not a simple automated way to check for these, so if we have any content of this type we will have to go through the list of requirements and check manually check if each is met.

Any documents, whether embedded in the page or provided for download, should also be checked for accessibility. These require a different process than web content testing, which will be detailed in a different lesson.

## Math

Special attention must be paid to mathematical expressions and equations to ensure screen readers will read them correctly. In general, a straight reading of the numbers and symbols involved in the expression is insufficient to clearly communicate the full meaning of an expression.

This is best tested with a screen reader. We should be able to write out the expression accurately based on what we hear without worrying about any ambiguity. If we are concerned that our knowledge of what the expression is supposed to be is preventing us from detecting potential ambiguity, we could provide the text from the screen reader to someone else who has not seen the expression and see if it is clear and unambiguous to them.

{% include links.md %}
