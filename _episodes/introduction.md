---
title: "Introduction"
teaching: 0
exercises: 0
questions:
- "What is digital accessibility testing, and why should I do it?"
- "How can I use tools to make testing easier?"
objectives:
- "Explain the importance of digital accessibility."
- "Demonstrate how to use WAVE and Accessibility Insights for Web."
keypoints:
- "Digital accessibility involves making content accessible to users with a wide variety of disabilities and assistive technology."
- "Digital accessibility makes content better for people with disabilities _and_ people without."
- "Automated testing tools catch only a relatively small percentage of accessibility issues."
- "WAVE is an automated testing tool that provides some useful information for performing manual checks, as well."
- "Accessibility Insights for Web has an assessment tool that provides valuable assistance with manual tests."
---

<!-- Note: Instructors can skim or skip some of this depending on starting experience level of learners -->

## Digital Accessibility

<!-- This is general content. Perhaps much of this would be assumed and included as a prerequisite. If not, perhaps some method should be considered so that the content can be shared between multiple lessons, and only one thing has to be modified. -->

- Digital accessibility refers to whether or not a digital item, like a website or video, is accessible to people with disabilities.
- An accessible website means that, regardless of vision, hearing, motor control, etc:
    - People have the same overall experience using the website.
    - People are able to do all the same tasks.
    - Nobody has to jump through extra hoops or deal with unnecessary barriers.
- Part of a website's accessibility will depend on the assistive technology available to a given person. When creating digital content, we use reasonable assumptions. For example, we assume a blind person will have a screen reader that can perform a number of standard functions.
- Part of a website's accessibility depends on the website itself. For those of us creating websites or content for websites, that part is our responsibility.

### Elements of Accessibility

- How can I know what my website users will need?
- There are lots of things that can impact a person's ability to use a website. A few examples:
    - Someone may be blind or have low vision.
    - Someone may be deaf, hard of hearing, or in a very noisy environment.
    - Someone may be missing one or both of their arms.
    - Someone may have very shaky hands, making fine motor control impossible.
- And there are many assistive technologies that can help with different types of disability:
    - Provide examples that include more than just screen readers (e.g. refreshable braille displays, alternative input devices).
- Do I need to be familiar with all of this?
    - Only if you are going to become an accessibility expert.
    - Assistive tech relies on standards. There are standard ways to indicate when text is a heading, where a link goes, and what content an image contains. As long as we meet these standards, we don't need to worry about what specific devices may be used.
        - Example: If the website can traversed with solely the keyboard or solely the mouse, you know it will be accessible for any reasonable alternative input device.
    - It can be helpful to have passing familiarity with some of what is out there, however. This can make some standards easier to understand. For example, coding all the headings on a webpage (or document) properly may not seem very important, until you learn that screen readers will read out all the headings on a page and allow users to jump to any of these, imitating the ability of a sighted person to skim a page for the headings and only start reading when they find the one they want.

### Why it Matters

- Lots of people have disabilities. Do you really want to exclude all these people from using your content?
- There are also lots of people with temporary disabilities.
    - Have you ever been in a really noisy environment?
    - Have you ever broken an arm or leg?
    - Have you ever had your mouse or keyboard die unexpectedly, lost your glasses or contacts, or lost some other device you rely on to perform everyday tasks?
- There is no need to create inaccessible content. You don't have to weigh doing a thing vs. accessibility, as long as you make sure to do the thing accessibly.
- And of course, for many of us, it's the law. For example, universities can (and do) get sued for providing inaccessible content.

> ## Exercise
>
> TODO: Some kind of empathy-building exercise that drives home how important digital accessibility is.
> Could be some kind of card game with two different types of decks (one easier and one harder) and two sets of rules (one of which is more restrictive than the other). Would demonstrate how much better the second set of rules is, not just for people with the difficult decks, but also for people with the easier decks.
>
> In a pinch could maybe do the #nomouse challenge.
{: .challenge}

## Testing Content

- There are a lot of factors that go into whether or not a webpage is accessible.
- Testing allows us to find various barriers that we would not have noticed otherwise.
- Some things can be tested with the help of various tools. Others need to be checked manually, for example, by trying to use the keyboard to navigate a site and making sure we can get everywhere.
- We can't put all our trust in any automated tool. You may hear different estimates on what percent of errors automated tools can catch, but the important thing to remember is that it is only a percentage.
- For a website with multiple pages (which is most of them), there are some aspects of the site that are the same. Generally this includes things like the page navigation, the footer, and various formatting options. We will not focus on these at the moment.
- There is also all of the actual content of each page. The main content is what changes from page to page, and is what we are most concerned with, as content creators. We may also provide other content, like what goes in the page footer.
- There are a lot of principles involved with digital accessibility. Trying to go based on these can be very difficult, since you first have to figure out how they apply to various pieces of content.
- We will instead break things down by content type to create a more understandable workflow.

### Tools

- There are lots of different tools for automated or semi-automated testing. As with everything, some will be better quality than others.
- We will use WAVE and Accessibility Insights for Web. These aren't the only useful tools available, but they are good ones.
- WAVE is an automated tool, although it also provides some assistance in manual checks by making note of things like heading structure and image alt text.
- An automated tool is an important component in testing: There is no reason not to automate everything that can be automated. Like all automated tools, WAVE shares the limitation that there are many aspects of accessibility that simply cannot be automatically checked, but it saves us from having to manually check for a number of potential issues.
- Reasons to use WAVE:
    - It is well-known, so other people you come into contact with may already be familiar with it, which can be helpful.
    - It is produced by WebAIM, which is an incredible font of accessibility knowledge and a very respectable organization.
    - It provides a useful user interface and highlights structural elements and features in addition to errors and alerts.
    - It has very good documentation.
- Using WAVE
    - Have everyone navigate to the first sample page.
    - (This should happen before starting:) Doublecheck that everyone has installed the extension. (and the Accessibility Insights one, too)
    - Show where the extension is and have everyone turn on WAVE.
    - Note how it messes with the formatting of the sample page.
    - Look over the overview and the various tabs.
    - Jump to a particular issue.
    - Toggle an issue off and back on.
    - Get more information about an issue.
    - Note that we will go through these steps quite a few times as we continue, so they will get quite a bit of practice.
    - Turn off WAVE: Either click the extension again or refresh the page.
- Accessibility Insights for Web is a bit more than an automated tool. It has an automated component (Fast Pass), but it is the Assessment tool that we are interested in (WAVE is a better automated tester). The assessment tool does run through some automated tests, but it also lists a lot of manual tests and provides assistance in doing them.
- Our primary reason for using Accessibility Insights is that it lists various types of content, like links, allowing us to check through them quickly and efficiently. It also provides checkboxes so we can indicate which are good and which aren't, which saves us the trouble of having to write down the information elsewhere.
- Using Insights:
    - Make sure everyone is still on the first sample page.
    - Show where the extension is and have everyone turn it on.
    - Indicate the correction option to choose: Assessment.
    - Note how it opens in a separate page.
    - Look over the list of tests.
    - Note that some of these can be pretty confusing. I'm never quite sure what I'm doing in the sections about widgets, which is part of the reason I don't typically run through the whole thing, but rather only the specific sections I find most useful.
    - Note the links section and how it lists out all the links on the page very conveniently.
    - Note the landmarks section and have everyone turn on the visual helper before taking a look at the sample page.
    - Turn off Accessibility Insights: X out of it. The assessment will actually keep, so if you try running it on a different page it will ask if you want to keep the old one or start something new.

{% include links.md %}

