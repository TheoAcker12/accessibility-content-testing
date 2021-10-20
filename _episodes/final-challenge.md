---
title: "Final Challenge"
teaching: 5
exercises: 30
---

## Testing Recap

The items prefaced with "your content" are for issues that should be tested for, but that are not going to be included in any of the practice pages due to the difficulty of testing.

1. Check for formatting issues:
    1. Use WAVE to find color contrast errors.
    2. Your content: Investigate any lower contrast areas that WAVE ignored manually, in case WAVE was unable to check them.
    3. Use WAVE to find underlined text that is not part of a link.
    4. Your content: Go through the page with a screen reader to check for issues where formatting is used to convey meaning. (It may also indicate other issues that will be covered in this list.)
    5. Your content: Read through the page to check for any other types of problematic formatting <!-- TODO: link --> or instances where an element is referred to using only sensory characteristics.
2. Check the page's heading structure:
    1. Use WAVE to check for any heading-related errors or alerts.
    2. With WAVE on, scroll through the page to manually check each heading. (You may want to turn off all non-heading related errors, alerts, and structural elements, as well as all contrast errors, features, and ARIA.)
3. Check for link accessibility:
    1. Use WAVE to check for link-related errors and alerts, including **Empty link** and **Suspicious link text**.
    2. Use Accessibility Insights for Web to access a list of the accessible names for all links on the page. (Remember to turn WAVE off, first. The list of links can be found under Links: Link Purpose.)
    3. Make sure that any links that open in new tabs or windows or that download content are properly identified so that users expect that behavior before clicking.
4. Check images and alternative text:
    1. Use WAVE to check for any images missing alternative text, including any that have the **Image with title** alert.
    2. Use WAVE to check for other image-related alerts, like **Suspicious alternative text**.
    3. With WAVE on, scroll through the page to manually check each image. (You may want to turn off all non-image related errors, alerts, and features, as well as all contrast errors, structural elements, and ARIA). Pay special attention to **Alternative text** and **Null or empty alternative text** features. Keep something like WAI's [images tutorial](https://www.w3.org/WAI/tutorials/images/) available for reference.
    4. Make sure the page does not have any images with text.
5. Your content: Check for special types of content that require additional attention:
    1. Animated or moving content: Make sure any content meets minimum accessibility requirements or remove it.
    2. Audio and video media: Follow WCAG [Guideline 1.2 - Time-based Media](https://www.w3.org/WAI/WCAG21/quickref/#time-based-media).
    3. Documents: Test these separately. <!-- TODO: link -->
    4. Math
<!-- TODO: languages, tables, forms -->

## Pages to Test

- Link to sample page
- Give some direction on what to look for?
- Provide answer key

Would it be helpful to have multiple samples?

{% include links.md %}