---
title: "Headings"
teaching: 0
exercises: 0
questions:
- "How can I check the heading structure of a page?"
objectives:
- "Check for the existence of headings."
- "Detect errors in heading strucutre."
- "Ensure all headings and non-headings are marked appropriately."
keypoints:
- "WAVE will create an alert when a page does not have headings."
- "WAVE creates errors for any empty headings that should be removed."
- "WAVE creates several useful alerts for potential issues in heading structure."
- "WAVE indicates all headings (and their levels) on the page."
---

<!--
Concepts/issues:
- Headings are used to organize content.
- Headings are not empty.
- There is one (and only one) heading level one (in general).
- There are no skipped heading levels (in general).
- Headings are "real" headings.
- Headings are not used to apply formatting to non-heading text.

Plan:
- Check for heading structure and empty headings with WAVE.
- Make note of missing h1, skipped level, and possible heading alerts from WAVE.
- Use WAVE structure to make sure all headings are as they should be.
-->

Headings:

- form the outline of a page
- used to organize content
- semantic HTML elements
- help sighted readers conduct a visual scan of the page
- when coded appropriately, help blind or low-vision readers scan the page (reference screen reader demo)

## Quick Heading Checks

Because headings are so useful, it is important to make sure that we use them and that we do so appropriately. WAVE can help us detect some of the most obvious heading issues.

1. Go to the appropriate sample page and activate WAVE.
2. Check for the WAVE alert _No heading structure_. If found, the other checks listed here are unnecessary.
3. Fortunately, the alert is not present. As soon as we run into another heading-related error or alert, we can stop looking, as such error or alerts indicate that there is a heading structure.

An empty heading is a heading element that does not have any text content. A screen reader user will typically know that the heading exists, but have no idea what content it contains, or even if it contains content they cannot see. We can find these with WAVE by checking for the _Empty heading_ error.

If an empty heading is empty visually, as well, it should be removed to prevent confusing screen reader users. If the heading has content that is presented visually, however, text should be added as needed. For example, if an image is used as a heading, the image will require alt text, as discussed in the episode about images.

## Heading Structure

There are six levels of heading, which form a hierarchy of page content. The top level, also know as the first level heading or **h1**, serves as the heading for all of the page's content. After that, lower levels (higher numbers) indicate further divisions of content.

### Alerts

The first level heading makes it clear to all users, regardless of vision, what to expect from the page. It typically doubles as the page title. Therefore, it is important to make sure that it exists. We can check for an _h1_ when we examine the structure in the next section, but WAVE will provide an alert for _Missing first level heading_ if it cannot find one.

WAVE may also provide _Skipped heading level_ alerts. While there are some situations where this may be appropriate, more often it will mean that there is an issue. Examples include a heading element being used purely for formatting, an missing intermidate heading, or a heading that needs to have a higher level. These alerts will need to viewed in context of the overall heading structure.

> ## When is skipping a heading level appropriate?
>
> In general, skipped heading levels should be avoided, but it is more important to use the appropriate level of heading for the level of detail of the given content. Consider the following example for a page about food:
>
> - Fruits (h2)
>   - Berries (h3)
>       - Strawberries (h4)
>       - Blackberries (h4)
>   - Citrus (h3)
>       - Oranges (h4)
>       - Limes (h4)
> - Vegetables (h2)
>   - Carrots (??)
>   - Peas (??)
>
> The fruit section establishes that h4 indicates a topic limited to one specific food item (e.g. strawberries or oranges), while h3 indicates a subcategory (e.g. berries or citrus). Carrots and peas are each specific food items, so they should be level four headings in order to maintain a consistent hierarchy, even if this means skipping a heading level by jumping from h2 to h4. The ideal solution might be to find a suitable category to serve as a level three heading, but if that is not possible, skipping a heading level is the better choice.
{: .callout}

Another alert that helps point out potential problems is the _Possible heading_ alert. This indicates text that may be a **fake heading**. A fake heading is text that function as a heading and is formatted as a heading, but is not actually a semantic (HTML) heading.

The alert does come with a few limitations. If the text is longer than 50 characters, has a smaller text size than WAVE is looking for, or uses uncoventional formatting methods, WAVE may not be able to flag it as a possible heading. Therefore, while the alert is useful, we will not want to rely on it fully. We can check for fake headings that may or may not have slipped past WAVE when we review the structure as a whole.

### Structure

To make life easier, we can hide various WAVE errors, alerts, and so forth that might otherwise get in the way. We can turn off everything in a given category, or we can turn off only certain types of item in a given category. This is mostly useful to declutter icons on the page, making the ones we are interested in stand out more.

1. Turn off all non-heading-related errors.
2. Turn off all non-heading-related alerts.
3. Turn off all features.
4. Turn off all ARIA.
5. Turn off all non-heading structural elements.

After we have finished, we can go from the Details tab to the Structure tab. This tab will show headings and page regions. The headings, which we are interested in, have circular symbols: We can ignore everything that is not a circle.

There are several things we are checking here:

1. Is everything marked by as a heading actually a heading? If there is any content that does not function as a heading, it should not be coded as one (e.g. page subtitles). Formatting can be applied directly to text, so there is no need to use headings to format non-heading content.
2. Is the outline WAVE provides missing anything? In other words, is everything that should be a heading coded as one?
3. Are all headings at the appropriate level for their content?

> ## TODO: Exercise/Challenge
>
> (Testing page needs to be developed so this can refer to it)
>
> 1. Identify heading-related issues on the sample page. What did you find?
> 2. What needs to be done to make the heading structure accessible? Discuss with a partner.
>
> > ## Solution
> > 
> > 1. The page has the following heading-related issues:
> >     - There are multiple level one headings.
> >     - There is at least one skipped heading level (TODO: where?)
> >     - There are two headings that are actually just formatted text. (TODO: where?)
> >     - There is a heading that should not actually be a heading. (TODO: Where?)
> > 2. To make the heading structure accessible:
> >     - None of the current h1s describe the whole page content, so a proper h1 should be added.
> >     - The current h1s should become h2s, and everything else moved down a level with them.
> >     - Something about the skipped heading level(s)
> >     - The formatted text should be turned into actual headings.
> >     - The other heading should be turned into formatted text.

{% include links.md %}

