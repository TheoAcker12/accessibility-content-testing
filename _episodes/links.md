---
title: "Links"
teaching: 15
exercises: 15
questions:
- "How can I make sure my links are accessible?"
objectives:
- "Detect any empty links and buttons."
- "Identify basic issues in link text."
- "Ensure that link text indicates link behavior."
keypoints:
- "WAVE can detect empty links and buttons."
- "WAVE can identify some instances of problematic link text."
- "Accessibility Insights for Web provides a list of all links to check how they will be identified."
- "Links that open in a new tab or window or that download content need to indicate this to users."
- "More info about [accessible links](https://guides.ou.edu/accessibility-reference/content/semantic-elements#s-lg-box-wrapper-31175045)"
---

## Empty Links

An empty link is defined as a link that does not have any text content. Screen reader users would (hopefully) know the link exists, but would not have any idea where it would take them, since there would be no link text for the screen reader to pass on. WAVE will indicate such links with either an **Empty link** error or a **Linked image missing alternative text** error.

On the [sample page](https://accessibility.oucreate.com/samples/sample) (the same one we have been using), we can find examples of both these errors.

Clicking the **Empty link** error takes us to an icon. Hovering over the icon reveals title text (also sometimes called hover text) that states: "Links section". This text may be presented to screen readers, but real link text is needed for full accessibility.

The **Linked image missing alternative text** is a similar situation. The only real difference between these two errors is that this time an image is used for the link (the "i" icon on the sample page is a special font character, not an image).

For our purposes, **Empty link** is a much harder problem to fix than **Linked image missing alternative text**. If the link is an image, any reasonable content management system will provide a method for adding alt text so we should be able to indicate where the link goes with little trouble. Without an image, however, we may have to find more creative ways to add visually hidden text, or we may have to add visible text to the link.

WAVE will also alert us of any empty buttons it finds, which will generally have the same considerations as empty links.

> ## Exercise: Fixing Empty Links
>
> Which of the following are accessible ways to fix the **Empty link** error?
>
> 1. Remove the element entirely or make it no longer a link.
> 2. Hide the element from assistive technology (using `aria-hidden="true"`) so that the empty link is ignored.
> 3. Add text so the link becomes: `[icon] link destination`
> 4. Replace the icon with text indicating the link destination.
> 5. Replace the icon with an image and give the image alternative text describing the image.
> 6. Replace the icon with an image and give the image alternative text indicating the link destination.
>
> > ## Solution
> >
> > 3, 4, and 6 are accessible ways to fix the error. 1 might be, though it sidesteps the issue.
> >
> > 1. Removing the element certainly means there is no longer an empty link, but now no users have access to the link. If the link is important, this is not a good solution.
> > 2. This is not accessible because screen reader users will be denied a link that others will have access to.
> > 3. This is accessible.
> > 4. This is accessible.
> > 5. This is not accessible. While the link will no longer be empty, a description of the image will not tell screen reader users where it will take them.
> > 6. This is accessible.
> {: .solution}
{: .challenge}

## Link Text

### Checking Links with WAVE

While we will need to manually check the link text for all the links we have included in our content, WAVE can help us quickly identify the most obvious issues with **Suspicious link text** alerts.

On the sample page, we can see there is one of these alerts. The link in question is specifically an example of a bad link. In context, we can determine where clicking the link will take us, but out of context this is not a helpful link, as we can recall from the screen reader demo.

Note that "library website" could be ambiguous, depending on the overall subject of the page. For a page about OU Libraries, it makes sense out of context from the rest of the page, but for a page about multiple libraries, it would not.

For a full idea of what link text WAVE considers suspicious, we can view the reference information for the alert. The explanation of the algorithm has a list of phrases that WAVE checks for. This list is presumably based on the most common offenders for ambiguous link text, but we could certainly come up with other clearly ambiguous words or phrases.

<!-- WAVE can provide alerts for any broken same-page (anchor) links. These links jump to specific content on the page rather than change the page, and this makes it possible to check them automatically. A broken link is confusing and irritating to all users, so any that are found should be dealt with and removed.

There is a broken anchor link directly below the linked image missing alternative text.

Unfortunately, WAVE cannot check for broken external links, as this is far more complicated. For most pages, it is better to <kbd>tab</kbd> through the page and try each link. -->

WAVE can provide alerts for any broken same-page (or anchor) links, but it cannot check for broken external links. For most pages, the best option may be to <kbd>tab</kbd> through the page and try each link.

WAVE also provides a **Redundant link** alert when it detects two links to the same address close together. One of the primary reasons this might occur is if we refer to something multiple times, and link to it each time. Most of the time it is best to remove all such redundant links in order to prevent confusion.

> ## Discussion: Suspicious Link Text
>
> The WAVE reference info describes what types of link text will receive an alert for being suspicious. What are some obvious examples of bad or ambiguous link text that would not be caught by WAVE?
{: .discussion}

### Checking Links with Accessibility Insights

We can better examine link text by using Accessibility Insights for Web to list all the links along with their accessible names. We can also get some useful information using a screen reader: Recall the screen reader demo and how we were able to get a list of all links on the page.

1. Turn off WAVE or refresh the page.
2. Turn on Accessibility Insights for Web.
3. Choose Assessment. If a notification indicates that an assessment is already in progress, choose Start new.
4. Click on Links and then Link Purpose.

Scan the accessible names in the list of links provided and consider the following for each:

- Does the link have a URL as part or all of the text?
- Does the link make sense, or is it ambiguous? Ideally, it should make sense out of context.
- Is the link text reasonably concise?
- Does identifying link information come at the beginning?

Going through the list:

- Some good or okay links
- Click here: WAVE already let us know about this one.
- https://libraries.ou.edu: Link text should not have the URL. Recall how the screen reader started reading this link as "h-t-t-p-s-colon-slash-slash" in the demo.
- Link to the library website: "Link to" is unnecessary and redundant filler. And becaue the identifying information (library website) is at the end, screen reader users will have to listen to the whole link to know where it goes. Links with unnecessarily long link text, whether due to filler phrases or overly detailed explanations, can quickly make navigating links on a site unpleasant.
- library website: A much better option of link text for the three above.
- Links and Hypertext, Opens in new tab: This is a good link. The identifying information is at the beginning, and the link informs listeners that it will open in a new tab, rather than the same page. Ideally, it would also indicate this visually so sighted users would benefit from the information.
- Monarch butterfly links, as discussed earlier.
- Links section (first one): This is the empty link identified by WAVE. In this case, the title (hover text) is serving as its "accessible name" but this is bad practice and cannot be relied on
- (no value): The linked image missing alternative text
- ...
- More info: Ambiguous link text not caught by WAVE.

> ## Exercise: Testing Links
>
> Use the [sample testing page](../../test-sample-1/index.html) for this exercise.
>
> 1. What link-related errors and alerts does WAVE provide for this page?
> 2. Are there any ambiguous links on the page that WAVE did not catch?
> 3. Are there any links with URLs in the link text?
>
> > ## Solution
> >
> > 1. Errors: 1 **Linked image missing alternative text**. Alerts: None.
> > 2. Yes: The link for color resources labeled `here.`
> > 3. Yes: The link at the bottom of the page to the Accessibility Reference Guide.
> >
> > Note that typically WAVE will catch links labeled `here`. However, because the period at the end of the sentence was included in this link, it did not trigger an alert.
> {: .solution}
{: .challenge}

## Link Behavior

Another thing to look for while scanning the list of links is any indication of link behavior. For example, a link might say that it opens in a new tab or downloads a Word document.

As content creators, we will hopefully be aware of whether or not we have added links that download content. If we know we have not, there is no need to worry about this. If we know we have (or think we might have), we should go through all the links to determine any that download content and ensure that those provide indication that they download content for both sighted and non-sighted users

Dealing with whether or not links open in new tabs is primarily something to check with the content management system. Manual checking should be performed if the CMS default is for links to open in the same page, but we have set some links not to, and the CMS does not indicate that these links open in new tabs (or windows). In this case, we need to identify all links that open in new tabs so that we can go back to the default.

{% include links.md %}

