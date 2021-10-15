---
title: "Headings"
teaching: 15
exercises: 0
questions:
- "How can I check the heading structure of a page?"
objectives:
- "Check for the existence of headings."
- "Detect errors in heading structure."
- "Ensure all headings and non-headings are marked appropriately."
keypoints:
- "WAVE will create an alert when a page does not have headings."
- "WAVE creates errors for any empty headings that should be removed or fixed."
- "WAVE creates several useful alerts for potential issues in heading structure."
- "WAVE indicates all headings (and their levels) on the page."
---

## Importance of Headings

Headings are one of the most important structural elements of a webpage (or document). They allow sighted users to glance at a page and quickly get an idea of what it contains, and they break up content into more manageable chunks. When coded correctly, they provide the same functions to assistive technology users, as we heard in the screen reader demo.

## Quick Heading Checks

Because headings are so useful, it is important to make sure that we use them and that we do so appropriately. WAVE can help us detect some of the most obvious heading issues.

1. Go to the [sample page](https://accessibility.oucreate.com/samples/sample) (the same one we have been using) and activate WAVE.
2. Check for the WAVE alert _No heading structure_. If found, the other checks listed here are unnecessary.
3. Fortunately, the alert is not present. As soon as we run into another heading-related error or alert, we can stop looking, as such error or alerts indicate that there is a heading structure of some sort.

An empty heading is a heading element that does not contain any text content. We can find these with WAVE by checking for the _Empty heading_ error.

The empty heading on this page is truly empty: That is, sighted users do not receive any information, either. Since there is no reason for it to be here and it may create complications for people who use screen readers, it should be removed. An even more problematic situation would be if an icon or image were used as heading, without any identifying text. In that case, only sighted users would be receiving the needed information.

## Heading Structure

There are six levels of heading, which form a hierarchy of page content. The top level, also know as the first level heading or **h1**, serves as the heading for all of the page's content. After that, lower levels (higher numbers) indicate further divisions of content.

### Alerts

The first level heading makes it clear to all users, regardless of vision, what to expect from the page. It typically doubles as the page title, so it is important to make sure that it exists. We can check for an _h1_ when we examine the structure in the next section, but WAVE will provide an alert for _Missing first level heading_ if it cannot find one.

WAVE may also provide _Skipped heading level_ alerts. While there are some situations where skipping a heading level may be appropriate, more often it will mean that there is an issue that needs correcting. Examples include a heading element being used purely for formatting, a missing intermidate heading, a heading that needs to have a higher level, or a preceding heading that needs a lower level. These alerts will need to viewed in context of the overall heading structure.

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

To make life easier, we can hide various WAVE errors, alerts, and other icons that might otherwise get in the way. We can turn off everything in a given category, or we can turn off only certain types of item in a given category. This declutters the page, making the icons we are interested in stand out more.

1. Turn off all non-heading-related errors. Click the checkbox next to each errors except for _Empty heading_.
2. Turn off all contrast errors.
3. Turn off all alerts except for _Skipped heading level_ and _Possible heading_.
4. Turn off all features by clicking the top checkbox instead of each of the feature checkboxes.
5. Turn off all non-heading structural : Everything except _Heading level X_.
6. Turn off all ARIA.

After we have finished, we can go from the Details tab to the Structure tab. This tab will show headings and page regions. The headings, which we are interested in, have circular symbols: We can ignore everything that is not a circle.

There are several things we are checking here:

1. Is everything marked by as a heading actually a heading? If there is any content that does not function as a heading, it should not be coded as one (e.g. page subtitles). Formatting can be applied directly to text, so there is no need to use headings to format non-heading content.
2. Is the outline WAVE provides missing anything? In other words, is everything that should be a heading coded as one?
3. Are all headings at the appropriate level for their content?

As we scroll through the page, the first thing we find is the _Heading level 1_, which is as it should be. Right after that, however, we see a _Heading level 4_, which means we have skipped a heading level. More importantly, this is not actually a heading, but a subtitle. Subtitles are one of the most common offenders for non-heading content formatted using headings.

The next few headings are fine, all the way down to the empty heading we noted previously. WAVE does mark the text on top of the image as a possible heading, but we can ignore that, since it does not function as a heading.

After the empty heading, we reach the obvious heading "Formatting Headings" and find that it is not coded as a heading. In this case, WAVE has marked it with a _Possible heading_ alert. This time, WAVE is correct: We need to change this to be a heading. Right after that, however, is Heading Hierarchy, which is also a fake heading (something that is formatted as and functions as a heading, but is not coded as one). It even has the same formatting as the previous fake heading, but because the underlying HTML is slightly different, WAVE is not giving us an alert. The important takeaway here is that we cannot rely on WAVE to always indicate possible headings for us. The alerts are useful, but we still need to pay careful attention to whether or not WAVE markes each heading as a heading.

Next, we need to pay careful attention or we may miss the next issue: Link Text should really be a subheading of Links. This becomes especially obvious when we notice the headings further down that are also about links, though not necessarily limited to link text. Therefore, this heading level needs to be changed. As a bonus, this will solve the next issue, which is the _Skipped heading level_ for _Link Examples_. Once _Link Text_ becomes level 3, the structure will no longer go directly from 2 to 4.

> ## Exercise: Testing Headings
>
> Use the [sample testing page](https://accessibility.oucreate.com/samples/test-sample) for this exercise.
>
> 1. What heading-related errors and alerts does WAVE indicate for this page?
> 2. Are there any heading-related issues that WAVE does not indicate? It might help to visually scan the page and determine what the heading outline should look like (with WAVE turned off), then compare that to WAVE's structure.
> 3. For each of the issues in the above questions, what can be done to make the heading structure accessible?
>
> > ## Solution
> >
> > 1. WAVE errors: None. WAVE alerts: 1 skipped heading level and 1 possible heading.
> > 2. WAVE does not indicate the following issues:
> >     - There are multiple level one headings, none of which could accurately serve as a heading for all the page content.
> >     - There is an additional heading that is just formatted text that does not cause an alert (_Images and Alternative Text_).
> >     - There is a heading that should not actually be a heading (the skipped heading level right after _Tables_). (It would also be reasonable to consider this caught by WAVE.)
> > 3. To fix the issues:
> >     - For WAVE's skipped heading level (and the heading that should not be a heading): Change the text from a heading to a paragraph (with formatting applied, if desired).
> >     - For WAVE's possible heading (and the additional possible heading WAVE did not catch): Change the text to headings.
> >     - For the multiple level one headings: Adjust all heading levels down by one.
> >     - Since none of the (former) level one headings describe the page content: Create a new heading level one.
> >
> > An example accessible structure that fixes the issues:
> >
> > - h1: Appropriate page title
> >     - h2: Formatting
> >         - h3: Text
> >         - h3: Color
> >             - h4: Contrast
> >             - h4: Resources
> >     - h2: Identifying Languages
> >     - h2: Images and Alternative Text
> >     - h2: Tables
> >         - h3: Table Styling
> >         - h3: Complex Tables
> {: .solution}
{: .challenge}

{% include links.md %}

