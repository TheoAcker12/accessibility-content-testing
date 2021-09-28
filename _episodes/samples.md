---
title: "Samples"
---

<style>
    #special-div {
        border: 1px solid #494dca;
        border-radius: 4px;
        background: linear-gradient(to bottom, #c8ccef, #d0d2f1);
        color: #494dca;
        padding: 10px;
    }
    #low-contrast-text {
        color: #23af4d;
    }
    #low-contrast-code {
        color: #c7254e;
        background-color: #e7e7e7;
    }
    .underline {
        text-decoration: underline;
    }
    #fake-h3-p, #fake-h3-div {
        margin: 40px 0 16px;
        font-size: 24px;
        font-weight: 500;
        line-height: 1.1;
    }
    .subtitle {
        text-align: center;
    }
</style>

<h3 class="subtitle">Practice finding errors</h3>

TODO: Make back to top link empty.

## Headings

TODO: Put the heading on top of an image.

Headings are a useful visual aid, allowing readers to quickly skim a page to identify the content they are looking for. What you may not realize is that headings provide the same function to screen reader users, assuming they have been implemented correctly. As a matter of fact, almost 70% of screen reader uses say navigating through the headings if the first thing they do when looking for information on a lengthy web page ([WebAIM survey - Finding Information](http://webaim.org/projects/screenreadersurvey8/#finding)).

<span id="low-contrast-text">The main points to remember about headings are as follows:</span>

1. Format all headings as "real" headings. That is, formatting text to look like a heading is not sufficient.
2. Do not use headings to apply formatting to text that is not a heading. (The most common offender is a page subtitle.)
3. Maintain an appropriate heading hierarchy. Do not skip heading levels.

### Formatting Headings

For the web, headings come in six levels - h1 through h6. The HTML code for a heading level two looks like: <code id="low-contrast-code"><h2>This is a Level Two Heading</h2></code>. Other text editors (e.g. Google Docs, Microsoft Word) and content management systems (e.g. Canvas, WordPress) allow users to add meaningful headings, as well. It is absolutely essential to make sure that all headings are actually coded as headings, or screen reader users will not be able to identify them. <span class="underline">Do not use manual formatting</span> (e.g. font size, bold) to make text look like a heading.

<div id="special-div">Because headings apply formatting, sometimes it can be tempting to use a heading to format some other section of text. Do not do this, as the text will then be coded as a heading, and will be listed when screen reader users skim through the page's headings.</div>

### Heading Hierarchy

In general, every page should have a level one heading (h1) with the title of the page. Except for special situations (typically involving embedded pages and iframes), that should be the only level one heading (h1) on the entire page. After that, increasing heading levels provide further specificity to page content. It may be helpful to plan out your heading structure before writing the page. This will help you both to ensure that the heading hierarchy is correct and to organize your thoughts.

<h4></h4>

1. Do not skip heading levels to be more specific (for example, do not skip from h2 to h5). It is perfectly acceptable, however, to skip headings in the other direction (for example, from h5 to h2).
2. Do not select heading levels based on their appearance. Select the appropriate heading rank in your hierarchy.

## Links

An accessible link is usable, has good link text, and does not cause any unexpected behavior.

Links must have a non-empty href attribute. A link with href="#" that uses javascript to define its behavior is not considered accessible.

<!-- heading at wrong level (won't cause WAVE error) -->
## Link Text

Screen reader users may navigate from link to link. Their screen reader may even provide a list of links in alphabetical, rather than page, order. Thus, links should make sense out of context and out of order. Avoid using "click here" or "read more" as these are meaningless without context.

While links do need to make sense out of context, they should not be overly wordy. Keep link text short and to the point.

Some other points to remember:

TODO: Add button to expand/collapse the following content, but do not give the button any text, just an image or icon.

<p>1. Do not use the URL as link text. Not all URLs provide clear information about where they lead. Even in cases where the URL is clear, it is still harder to read for both sighted users and screen reader users.</p>
<p>2. Put identifying information about a link at the beginning. For example, if a link opens in a new window, indicate that after the normal link text. This makes it easier for screen reader users to distinguish between links and saves them time and frustration.</p>
<p>3. Do not write "link" or "link to" in the link text or in the alt text of an image link. Screen readers will announce that it is a link, and the formatting should already make it clear visually that it is a link.</p>


<!-- WAVE: Skipped heading level. Actual issue is the h2 above that should be h3 -->
#### Link Examples

- Bad: [Click here](https://libraries.ou.edu) to access our website. (Ambiguous link text)
- Bad: Check out the library website: [https://libraries.ou.edu](https://libraries.ou.edu) (URL as link text)
- Bad: [Link to the library website.](https://libraries.ou.edu) (Includes "link to" in link text)
- Good: For more information, check out the [library website](https://libraries.ou.edu).

### Expected Behavior

Links should never do anything unexpected. What may be merely irritating for sighted users may cause a lot of difficulty for screen reader users. The main issues are links that open in new tabs and links that automatically download files.

1. Always indicate when a link opens in a new tab. If you cannot provide this indication, make sure the link will open in the same tab, instead.
2. Always indicate when a link opens a PDF or downloads content. Your sighted users will also thank you.

There are several strategies for providing this kind of indication. Web developers may use a span only presented to screen readers with text indicating that the link will open in a new tab. When this is included along with the external link icon, the link behavior will be clear to all users. If content creators do not have this option, they may include text indicating the link behavior directly within the link itself. This strategy is much easier when it comes to automatic downloads. For example, for a link that downloads a word (docx) document called Being Awesome, you could provide "Download Being Awesome (docx)" as the link text.

<p id="fake-h3-p">Links and Images</p>

Sometimes an image may be used as a link, or an image may be included as part of a link. These require some special considerations.

1. If a link involves only an image, make sure the alt text provides the needed link text, so that screen reader users still know what to expect.
2. If a a link involves both link text and an image, make sure these are bundled together as one link, rather than as two separate links to the same location.
3. Link text/alt text for these kind of links can be tricky. The Alternative Text section will have more detailed advice for how to deal with this.

<div id="fake-h3-div">Other Link Considerations</div>

1. Avoid and remove empty or broken links.
2. Make sure links are underlined and a different color than the rest of the text, to make them clear to sighted users.
3. Do not use buttons as links. It is fine to format a link to look like a button, as long as it is still coded to look like a link.
4. Do not use links as buttons. If the link provides a special function instead of opening a new page, it should be coded as a button.
5. Pay extra attention to pagination or alphabetized links. You will need to ensure that the link text provided to screen reader users conveys the necessary information about where the link goes.
6. Do not include extra information in a title attribute. The title attribute is not accessible for all users. (If you are not writing HTML/do not know what this means, you should be fine.)

### Checking for Empty or Broken Links

[WAVE](https://wave.webaim.org/) (a very useful testing tool) can check for empty links, but it cannot check for broken ones. There are various tools that can be used to check for broken links, though many of these cost money. Some content management systems may also have tools built into them. Of course, you can always manually check by clicking on each link, but that can be a pain if you have a lot of links. W3C (the World Wide Web Consortium) offers a [free link checking tool](https://validator.w3.org/checklink) that may be worth trying out.

## Read More

- [Headings and Subheadings](https://accessibility.psu.edu/headings/)
- <a href="https://www.w3.org/WAI/tutorials/page-structure/headings/" target="_blank">Headings Tutorial<span class="sr-only">, Opens in new tab</span></a>
- [Easy Checks - A First Review of Web Accessibility, Headings, by W3C WAI (Web Accessibility Initiative)](https://www.w3.org/WAI/test-evaluate/preliminary/#headings)
- [Links and Hypertext](https://webaim.org/techniques/hypertext/)
- [Making Accessible Links: 15 Golden Rules For Developers](https://www.sitepoint.com/15-rules-making-accessible-links/)

{% include links.md %}