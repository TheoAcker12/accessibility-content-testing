---
title: "Images"
teaching: 0
exercises: 0
questions:
- "Key question (FIXME)"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---

TODO: Something about images?

## Alt Text

- What is alt text?
- `alt` attribute vs. alternative text?
- Mention title?
- WAVE: _Missing alternative text_ and related errors

## Checking Images

- WAVE - turn off everything other than images
- Note appropriate alerts
    - _Suspicious alternative text_
    - _Redundant alternative text_
    - _A nearby image has the same alternative text_
    - _Long alternative text_
    - _Image with title_?
- once determining that an image has appropriate alternative text, turn that off, until everything is off
- Is it an image of text?
    - If absolutely necessary, ensure alt text communicates exactly the text shown. Otherwise remove.
    - For larger blocks of text, such as a handwritten document, treat as a complex informative image (below).
- Is the image decorative?
    - Make sure alt text is null.
- Is the image functional?
    - This should have come up when checking link text. Ensure that the alt text provides the needed link text info and move on.
- All remaining images are informative in some manner
- Can necessary info be provided in 1-2 sentences?
    - Make sure alt text communicates what is needed.
- Otherwise:
    - Make sure there exists alternative text on the page or elsewhere that provides all information needed.
    - Make sure alt text points to that location (e.g. "screenshot of the blah blah blah, as described above/below" or "diagram of blah blah blah, as described in the link below").
- Note: Make sure things like source or copyright info are never included in alt attribute.
- Note: Make sure words like "image of" are not included. May be appropriate if providing additional information, however (e.g. diagram, bar chart, screenshot, etc.).

TODO: Exercises

- What is wrong with including an image of text with alt text that contains the text content? (probably a discussion) - consider: length of text, how easy it is to read or zoom compared to standard text, cases where the image is of a historical document and text content is also included in a transcript
- What information should be included in the alternative text for the following image?
- Which of the following are appropriate methods for providing alternative text?
- Discussion: Is this image informative or decorative?
- Indicate which images have accessible alternative text and which do not?

{% include links.md %}

