---
title: "Testing Tools"
teaching: 15
exercises: 0
questions:
- "How can I use tools to make testing easier?"
objectives:
- "Activate and use WAVE and Accessibility Insights for Web."
- "Show where an error identified by WAVE appears on the page."
- "Demonstrate how to find more information about the features WAVE identifies."
- "Start an assessment with Accessibility Insights for Web."
keypoints:
- "Running automated tests is an essential first step in accessibility testing."
- "WAVE is an automated testing tool that can also help with some types of manual testing."
- "WAVE provides information and explanations for each error, alert, or other feature that it identifies."
- "You can turn off indidividual items in WAVE if the page becomes too cluttered to find what you need."
- "Accessibility Insights for Web has an assessment tool that provides in-depth assistance with a variety of manual tests."
---

## Tools and Automated Testing

There are many tools that can help us when testing our content for accessibility issues. Some of these tools perform automated tests, some assist with manual testing, and some do both. In this lesson, we will primarily use WAVE Web Accessibility Evaluation Tool and briefly use Accessibility Insights for Web, though these are not the only good tools available.

As mentioned before, we cannot rely on automated tests to catch all or even most potential accessibility errors. That does not mean that automated tests are worthless! In general, running an automated tool is the first step in testing. Automated tools only become a problem when they are both the first and last step in our testing process.

## WAVE

WAVE (sort of) stands for Web Accessibility Evaluation Tool. It performs standard automated tests that find obvious errors as well as potential issues that require human analysis. It also provides assistance with some manual checks by identifying certain types of features, like headings and images, so that we do not have to examine every piece of content or dig into the website code.

While we will get quite a bit of practice using WAVE throughout the rest of the lesson, we will briefly practice using it now to get familiar with it.

1. Make sure you are using the Google Chrome browser.
2. If you have not already, install the [WAVE extension](https://chrome.google.com/webstore/detail/wave-evaluation-tool/jbbplnpkjmmeebjpijfedlgcdilocofh) for Google Chrome.
3. Navigate to the [sample page](https://accessibility.oucreate.com/samples/sample). We will use this page throughout the lesson to examine the various issues we can check with WAVE.
4. Find and activate the WAVE extension at the top right of the browser. It should be a circular symbol with a wavy "W" and is identified as WAVE. If you cannot find it, you can instead click on the puzzle-piece icon labelled Extensions and find the dropdown menu item marked WAVE Evaluation Tool.

Activating WAVE may mess up the formatting of the page we are on. It may mess some pages up more than others, though this does not mean that they are inaccessible pages. The way WAVE adds identifying icons to the page does not always play nicely with existing formatting.

There are two things WAVE has added to the page. The first is a set of icons identifying various features and problems on the page itself. As mentioned, this may mess with the formatting of the page to some extent. The other is a sidebar on the left side of the page providing an overview of everything WAVE has found. The sidebar starts on the Summary tab, but we can go straight to the Details tab, which provides more useful information.

First, we can see that the various items WAVE has found are divided into several groups. There are errors, contrast errors, alerts, features, structural elements, and ARIA. We will make use of all of these except ARIA in this lesson.

There are several features the Details tab provides that we will try out.

1. Clicking on any of the icons for a given type of item will jump us to where the item is on the page. As an example, click on the Linked image missing alternative text error. This keeps us from having to search or guess to find what image WAVE is referring to.
2. Hovering over the icon in the sidebar (or on the page) adds a dashed outline around it. For this particular error, the outline makes it clear what image is causing the problem.
3. Clicking on the "i" icon for a given type of error, alert, or feature will take us to the Reference tab where we can get more information. WAVE will explain what it means, why it matters, how to fix it (or how to tell if it needs to be fixed), how WAVE checks for it, and any related standards or guidelines.
<!-- In this case, we can find that having an image without alternative text as a link makes an empty link. This is important because without link text, screen readers will not be able to tell users what will happen if they click the link. And so forth. -->
4. Another feature we may find useful is the ability to toggle various items on the page. In this case, perhaps we have made a note of the error and how we are going to fix it, but we want to finish testing the page before we start editing the page. We could then click the checkbox next to the error, and the icon will disappear from the page. We can click the checkbox again if we want to bring the icon back. It is worth noting that we must toggle all icons of a specific type at once. For example, there are two skipped heading level alerts, but there is only one checkbox to toggle them.

We will make use of all of these features as we continue through the lesson, so there will be plenty of opportunity for practice. There are also two other tabs we have not looked at yet, Structure and Contrast, that we will explore later.

To turn WAVE off, we can either click the extension icon again or refresh the page.

> ## Caution
>
> If you have embedded content in your website, keep in mind that WAVE (and other tools) may not be able to check that content, depending on how it is embedded. You will need to be extra careful in testing and ensuring the accessibility of embedded content.
{: .caution}

> ## Exercise: Suspicious alternative text
>
> For each of the following, would WAVE detect it as suspicous alternative text? Hint: The sample page has a suspicious alternative text alert. Use the algorithm described in the alert's reference information.
>
> 1. "Image of a butterfly"
> 2. "logo"
> 3. "Company logo"
> 4. "something"
> 5. "Monarch_Butterfly.png"
> 6. "To do: Add alt text"
>
> > ## Solution
> >
> > 1. Yes. WAVE looks for any alt text that begins with "graphic of", "bullet", or "image of".
> > 2. Yes. "logo" is one of the words WAVE looks for.
> > 3. No. WAVE only looks for alt text that is the word "logo", not that includes the word with other text.
> > 4. No. "something" is not one of the words WAVE looks for.
> > 5. Yes. WAVE checks for image file names.
> > 6. No. WAVE will not flag any of this text.
> {: .solution}
{: .challenge}

<!-- Could also have an easier challenge that asks how many of a given error or alert or something are on a page -->

## Accessibility Insights for Web

The other tool we will use is Accessibility Insights for Web. This name is a mouthful, so we can refer to it as Insights for simplicity.

1. As before, make sure you are using Google Chrome and have the [Accessibility Insights for Web extension](https://chrome.google.com/webstore/detail/accessibility-insights-fo/pbjjkligggfmakdaogkfomddhfmpjeni) installed.
2. Stay on or return to the sample page we used with WAVE.
3. Make sure WAVE has been turned off. We want to test the website, not WAVE.
4. Find and activate the extension. The icon is a heart with a magnifying glass. As with WAVE, the icon may be displayed at the top right of the browser, or we may have to find the extension using the Extensions dropdown menu.
5. A small menu will open up with three options. We want the one labeled Assessment. Note that the assessment interface will open in a new window. If you have previously used the extension, you may get a dialog box saying that an assessment is in progress. If so, click _Start new_.

While Insights can run some automated tests, WAVE provides a better interface, so there is no need to use the FastPass option. We can still run automated tests in the assessment tool, if desired. What we are interested in, however, is how the assessment tool assists with a number of manual tests.

On the left, there is a long list of categories for testing. If we click on one (Links), we can see additional subcategories. We can click on one of these subcategories (Link Purpose) to find a specific set of tests. The Link Purpose page is especially useful, because it provides a list of all links on the page, along with their accessible names. That is, if a link consists of an image with no visible text, the link text shown here will provide the image's alternative text (if applicable).

There are two interactive features we can make use of. To the left are a series of checkboxes. These are for the visual helper tool. Clicking the one at the top turns all of the visual helpers on. If we then go the page we are testing, we can see that each link has been given a bold red outline.

<!--To the right are a series of Pass or Fail buttons. We can use these to indicate if a link is accessible, or if it needs some kind of correction. Once we have marked every link that has an issue, we can click "Pass unmarked instances" to automatically mark the others. This can be useful if we want to refer directly to the assessment when we start editing the page, but there is an additional function it serves. Once we have done all the tests we want, we can click "Export result" at the top left. We have the option to add a message to the report, and then we can to export as HTML (or JSON, if you want). This downloads an HTML file that will open in the browser when clicked. We can then refer to the results in the future, or even send theme to someone else to review.-->

In this lesson, our main reason for using Accessibility Insights for Web is for the Link purpose section. WAVE can detect some link issues, but it does not help with manually checking each link, a process that would be quite painful without some sort of tool.

We can turn Insights off by X-ing out of the browser tab. When we open it next, it will have saved our most recent progress.

{% include links.md %}

