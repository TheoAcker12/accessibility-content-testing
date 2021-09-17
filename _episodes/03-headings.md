---
title: "Headings"
teaching: 0
exercises: 0
questions:
- "Key question (FIXME)"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---

TODO: What are headings?

## Quick Heading Checks

Using WAVE, we can quickly check if headings are being used at all and if there any obvious issues we need to deal with.

Check for the WAVE alert **_No heading structure_**. If we find this then the other checks are unnecessary, but there is a lot of work to do.

The sample page does not have this alert, but it does have other heading-related errors/alerts, which also indicate that there is a heading structure.

Check for the WAVE error **_Empty heading_**. Any empty headings found should be removed.

Check for the WAVE alerts **_Skipped heading level_** and **_Missing first level heading_**. If we find either of these, we need to adjust some heading levels.

## Fake Headings

A fake heading is text that functions as a heading and is formatted as heading, but is not actually a semantic (HTML) heading. We can use the WAVE alert **_Possible heading_** to check for these, but it does come with some limitations. If the text is longer than 50 characters, has a smaller text size than WAVE is looking for, or uses uncoventional formatting methods, WAVE may not be able to flag it as a possible heading.

We can check for any fake headings that may have slipped past WAVE when we review the overall heading structure.

## Reviewing Heading Structure

- fake headings

## Lists

- first question is does a heading structure exist
- then: are there any obvious issues with the structure
    - empty headings
    - skipped levels
    - missing first level

{% include links.md %}

