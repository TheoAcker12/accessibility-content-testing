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
- "Accessibility Insights for Web provides a list of all links to check how they will be identified."
- "Links that open in a new tab or window or that download content need to indicate this to users."
---

Links are the most common type of interactive element that people include in their content.

## Empty Links

An empty link (or button) is defined as one that does not have any text content. Screen reader users would know the link exists (hopefully), but would not have any idea where it would take them, since there would be no link text for the screen reader to give them. WAVE will indicate such links with either an _Empty link_ error or a _Linked image missing alternative text_ error.

On the [sample page](../../samples/index.html) (the same one we have been using), we can find examples of both these errors. Clicking the _Empty link_ error takes us to an icon (from the page, not produced by WAVE). Hovering over this icon gives use some more information, but title text (also sometimes called hover text) is not the same as link text. The _Linked image missing alternative text_ is a similar situation.

What is the difference between these two errors? _Empty link_ means that if anything is presented visually, it is not an image element. There are many ways to display images without using image elements: For example, an image can be used as the background for a different HTML element or a non-image icon could be displayed, as is the case here. _Linked image missing alternative text_, on the other hand, means that an actual image is being used as a link. The only thing typically needed to make these accessible is alt text that indicates where the link goes.

WAVE will also alert us of any empty buttons it finds, which will generally have the same considerations as empty links.

> ## Exercise: Fixing Empty Links
>
> Which of the following are accessible ways to fix the _Empty link_ error?
>
> 1. Remove the element entirely or make it no longer a link.
> 2. Hide the element from assistive technology (using `aria-hidden="true"`) so that the empty link is ignored.
> 3. Add text so the link becomes: `<icon> link destination`
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

While we will need to manually check the link text for all the links we have included in our content, WAVE can help us quickly identify the most obvious issues with _Suspicious link text_ alerts.

On the sample page, we can see there are two of these alerts. The first is an example of a bad link. In context, we can determine where clicking the link will take us, but out of context this not a helpful link. Recall from the screen reader demo how "click here" was meaningless within the VoiceOver rotor. An example of a better alternative is provided as the last item in the list of examples. Whether or not "for more information" is included, "check out the library website", where "library website" serves as the link text, is a good option.

Note that "library website" could be ambiguous. For example, if the page were about multiple institutions or libraries, the link could refer to any number of library websites. However, because the link text makes sense within the context of the page (a page about OU Libraries), it can be considered to make sense out of context.

The second alert is not necessarily an issue. In many cases WAVE provides alerts to indicate that there may or may not be a problem. In this case, "Links" accurately describes the link destination. On the other hand, it might still be confusing out of context. Changing it to something like "Link accessibility" might be clearer.

For a full idea of what link text is considered suspicious, we can view the reference information for the alert. The explanation of the algorithm has a list of phrases that WAVE checks for. The list is presumably based on the most common offenders for ambiguous link text, but we could certainly come up with others. What about "show details", "next", or "source"?

We can better examine link text by using Accessibility Insights for Web to list all the links along with their accessible names.

1. Turn off WAVE or refresh the page.
2. Turn on Accessibility Insights for Web.
3. Choose Assessment. If a notification indicates that an assessment is already in progress, choose _Start new_.
4. Click on _Links_ and then _Link Purpose_.

Scan the accessible names in the list of links provided and consider the following for each:

Does the link have a URL as part or all of the text? Going through the list of links with a screen reader might be especially helpful, since the mish-mash of letters in a link would most certainly stand out. It certainly stood out when VoiceOver started reading "h-t-t-p-s-colon-slash-slash" in the screen reader demo. Most likely any URLs will stand out in a visual scan, too. We can see the URL link text from the demo in this list. As with the ambiguous "Click here" link that WAVE alerted us to, "library website" would make much better link text.

Does the link make sense, even without knowing its context (where it is on the page and what text comes immediately before and after it)? Technically, as long as the link text makes sense in context then it meets minimum accessibility standards, but it is far better to have links make sense out of context (and out of order).

"Click here" is one of the more obvious examples of link text that does not make sense without context, though WAVE has already alerted us to it. As mentioned, however, there are plenty of phrases WAVE will not catch, so it is well worth checking the list ourselves. In this case, there is a link with the text "More info".

We might also find some links that do not have clearly suspicious phrases, but that are not really clear without context. If we have to read the URL, check back on the page, or use our memory as content creators, we should consider that a warning sign.

Is the link text concise? For example, one of the links in this list starts with the phrase _link to_, which is completely unnecessary. Links should always have clear formatting such that sighted users will not need a phrase to identify them, and screen readers will identify links as such to their users. Unnecessary words and phrases or unnecessarily detailed or lengthy description can quickly make going through a list of links unpleasant.

On a somewhat related noe, if only some of the link text identifies the link and distinguishes it from other links, is that identifying information at the beginning? Sometimes non-identifying information is useless filler that should be removed, as with the example of the link starting with _link to_, but sometimes there is information that does not necessarily distinguish the link from other links, but that is still important enough to be included. Examples of links where not all information is identifying:

- Library Carpentry, opens in new tab
- Book title, chapter x
- Book title, chapter y

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
> > 1. Errors: 1 linked image missing alternative text. Alerts: 1 suspicious link text, 1 redundant link.
> > 2. Yes: TBD
> > 3. TBD
> {: .solution}
{: .challenge}

## Link Behavior

Another thing to look for while scanning the list of links is any indication of link behavior. For example, a link might say that it opens in a new tab or downloads a Word document.

As content creators, we will hopefully be aware of whether or not we have added links that download content. If we know we have not, there is no need to worry about this. If we know we have (or think we might have), we should go through all the links to determine any that download content and ensure that those provide indication that they download content for both sighted and non-sighted users

Dealing with whether or not links open in new tabs is primarily something to check with the content management system. Manual checking should be performed if the CMS default is for links to open in the same page, but we have set some links not to, and the CMS does not indicate that these links open in new tabs (or windows). In this case, we need to identify all links that open in new tabs so that we can go back to the default.

## Other Link Issues

WAVE can provide alerts for any broken same-page (anchor) links. These links jump to specific content on the page rather than change the page, and this makes it possible to check them automatically. A broken link is confusing and irritating to all users, so any that are found should be dealt with and removed. Unfortunately, WAVE cannot check for broken external links, as this is far more complicated. For most pages, it is better to <kbd>tab</kbd> through the page and try each link.

WAVE also provides a _Redundant link_ alert when it detects two links to the same address close together. Sometimes this happens because an image and text are both used as links. In these cases, the image and text should be combined into one link. A more common situation we, as content creators, might encounter is referring to something several times, and linking to it each time. Most of the time it is best to remove all such redundant links in order to prevent confusion.

{% include links.md %}

