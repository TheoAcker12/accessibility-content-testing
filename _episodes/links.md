---
title: "Links"
teaching: 0
exercises: 0
questions:
- "How can I make sure my links are accessible?"
objectives:
- "Detect any empty links or buttons."
- "Identify basic issues in link text."
- "Ensure that link text indicates link behavior."
keypoints:
- "WAVE can detect empty links and buttons."
- "Accessibility Insights for Web provides a list of all links so you can check how they will be identified."
- "Links that open in a new tab or window or download content need to indicate this to users."
---

<!--
Concepts/issues:
- Links and buttons are not empty.
- Link text is short and to the point.
    - URLs are not part of link text.
    - Links do not use click here, read more, link to, etc.
- Identifying information for a link is at the beginning.
- Link text makes sense either with or without context (preferably out of context and out of order).
- Links always indicated when they will open in a new tab/window or download content.

Plan:
- Check for empty links (and buttons) with WAVE.
- Check for suspicious link text with WAVE (won't necessarily catch everything, but a good start).
- Check link text more thoroughly with Insights.
- Check for link text and link behavior with Insights.

Refer:
- Testing document accessibility.
- Ways to indicate link behavior.
-->

Links are the most common type of interactive element that people include in their content.

## Empty Links

An empty link (or button) is defined as one that does not have any text content. For example, an image with no alternative text that functions as a link would be considered an empty link. This would be highly problematic for screen reader users, who would know the link exists (hopefully), but have no idea where it would take them.

WAVE can help us quickly identify empty links (and buttons, for good measure).

1. Go to appropriate sample page and activate WAVE.
2. Check for _Empty link_ errors.
3. Note why the links are empty.
4. Note that WAVE can also give use _Empty button_ errors.

TODO: Exercise or discussion on how to fix the empty links identified above. One empty link might be an image

## Link Text

While we will need to manually check the link text for all links we add, WAVE can help us quickly identify the most obvious issues with _Suspicious link text_ alerts.

Note what links are given this alert on the sample page.

We can better examine link text by using Accessibility Insights for Web to list all the links along with their accessible names.

1. Turn off WAVE or refresh the page.
2. Turn on Accessibility Insights for Web.
3. Choose Assessment. If a notification indicates that an assessment is already in progress, choose _Start new_.
4. Click on _Links_ and then _Link Purpose_.

Scan the accessible names in the list of links provided. (TODO: Fill out examples)

Are any of them very long? This link and that link stand out as much longer than the others. Imagine having to listen to all that every time you wanted to go through the links on the page. How can we make the text for these links shorter while still indicating where the link will go?

Do any of the links have URLs as part or all of the text? Going through the list of links with a screen reader might be especially helpful, since the mish-mash of letters in a link would most certainly stand out, but they will most likely stand out in a visual scan, as well. Which of these links have URLs in the link text? How could we rephrase the content to give the links accessible names?

Do any of the links consist of suspicious phrases like _"click here"_ or _"read more"_ or include unnecessary text like _"link to"_? WAVE has already caught most of these, but it never hurts to quickly glance through for any that it did not catch. And if we miss any after this first pass, we will surely notice them when we read through the links more slowly. TODO: Point out link with suspicious text.

Make a slower second pass. This time read through each accessible name and consider the following:

Does this link make sense, even without knowing its context (where it is on the page and what text comes immediately before and after it)? Technically, as long as the link text makes sense in context than it meets minimum accessibility standards, but it is far better to have links make sense out of context (and out of order). TODO: Consider this link. Out of context, what does it seem to indicate? How could it be adjusted to be more accessible?

If only some of the link text identifies the link and distinguishes it from other links, is that identifying information at the beginning? Examples of links where not all information is identifying:

- Library Carpentry, opens in new tab
- Book title, chapter x
- Book title, chapter y

TODO: See if these are good examples

## Link Behavior

Another thing to look for while scanning the list of links is any indication of link behavior. For example, a link might indicate that it opens in a new tab or downloads a Word document.

### Download Links

You will hopefully be aware whether or not you have added links that download content. If you know you have not, there is no need to worry about this. If you know you have, or think you might have:

1. Go through all of the links and determine which ones download content.
2. Make sure the accessible names of those links indicates that they are download links.

### Links that Open in New Tabs

TODO: Would it be better to simply include this when considering the CMS as a whole?

- Insights will show us any text the link provides to indicate behavior (e.g. link text, opens in new tab)
- In a CMS, there will be a default setting. You can click on any link (as long as you know you did not change the default for it) to see if it opens in the same tab or a new one. If new one, links need to indicate that.
- If you have set the link target for any links:
    - You can check an ordinary link where you set the target to open in new tab and make sure that it indicates it will
    - Do you also need to ensure that if you set target for the same tab that it does not indicate new tab?
    - If it doesn't indicate, you will need to do more thorough checking to make sure that you have manually added some kind of indication - might be a link for more info?

## Other Link Issues?

- _Broken same-page link_
- Mention how to check for broken external links??
- _Redundant link_

TODO: Exercises

- Which of these links are accessible?
- How many links are on sample page?
- What are accessible ways to indicate when a link opens in a new tab? (or downloads content)
- Identify link-related issues on a sample page

{% include links.md %}

