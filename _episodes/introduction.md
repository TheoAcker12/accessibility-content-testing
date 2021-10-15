---
title: "Introduction"
teaching: 10
exercises: 0
questions:
- "Why is it important to test content for digital accessibility?"
- "How can I test my content?"
objectives:
- "Explain the importance of digital accessibility."
- "List various methods for testing."
- "Describe additional strategies to use beyond testing."
keypoints:
- "You do not have to be an expert to create accessible content."
- "Digital accessibility makes content better for people with disabilities and people without."
- "Automated testing tools catch only a relatively small percentage of accessibility issues."
---

<!--
Key points:
- People with disabilities have diverse situations and experiences.
- It can be useful to have a broad understanding of types of disabilities and assistive technology in order to better understand the importance of various accessibility principles.
- You do not have to be an expert to create accessible content.
- Digital accessibility makes content better for people with disabilities and people without.
-->
## Digital Accessibility

Digital accessibility determines how well people with disabilities can use digital content, like websites. But what does it mean for a website to be accessible?

An accessible website means that, regardless of vision, hearing, motor control, cognitive ability, or other disability status:

- People have the same overall experience using the website.
- People are able to do all the same tasks.
- Nobody has to jump through extra hoops or deal with unnecessary barriers.

There are many ways that websites could create barriers for people with disabilities, especially since there is much diversity when it comes to disabilities people may have, their experiences with disabilities, and the assistive technology they use to interact with computers and content. While there is no need to know everything, it is useful to have some general knowledge of types of disabilities and assistive technology to better understand how creating content in certain ways will impact the people who use it.

Here are a few examples of some users who benefit from and may rely on digital accessibility:

- A blind or low-vision person who uses a screen reader to tell them what is on the page.
- A deaf or hard-of-hearing person who needs captions or transcripts for videos and podcasts, since they cannot hear the audio.
- A person without hands who interacts with their computer using an alternative input device, perhaps operating by their feet or their mouth.

There is a lot to know about disabilities, assistive technologies, and how accessibility principles apply to content on the web. Fortunately, you do not have to be expert to create accessible content. Even when we do not create perfectly accessible content, every piece of progress we make has real and lasting benefits.

### Why it Matters

There are many reasons to pursue digital accessibility:

- Many people have disabilities, and we certainly do not want to exclude them from using our content!
- Nobody, with or without disabilities, ever said: "Wow, this content is so clear, readable, and easy to use. I hate it."
- People without a given disability may find themselves in a situation that mimics that disability to some extent. For example, someone who can hear perfectly may need captions to listen to audio content in a particularly loud environment.
- Abilities change as we age. Someone who is perfectly happy reading tiny text now may not be so happy to do so in twenty or thirty more years.
- And of course, for many of us, digital accessibility is the law. Universities and other organizations can (and do) get sued for providing inaccessible content.

> ## Exercise
>
> TODO: Some kind of empathy-building exercise that drives home how important digital accessibility is.
> Could be some kind of card game with two different types of decks (one easier and one harder) and two sets of rules (one of which is more restrictive than the other). Would demonstrate how much better the second set of rules is, not just for people with the difficult decks, but also for people with the easier decks.
>
> In a pinch could maybe do the #nomouse challenge.
{: .challenge}

<!--
This is a brief introduction to what accessibility testing entails.

Key points:
- Keeping accessibility in mind when creating content will make testing and fixing content much easier.
- Provide contact information and do not be afraid to ask for feedback from your website visitors.
- Automated testing tools catch only a relatively small percentage of accessibility issues.
-->
## Testing Content

While testing is essential, it should not be the first or last step in ensuring our content is accessible. First, we should keep accessibility in mind when we choose content management systems (if we are given the opportunity) and as we create content. It is much easier to create content that is accessible from the beginning than to correct inaccessible content.

We also need some plan for how to deal with errors that we do not manage to catch during testing. While we hope to catch everything, there are never any guarantees. A good strategy is to provide contact information in an easy to find location and ask users to let us know how we are doing. Most users will appreciate our efforts and will be happy to let us know when they encounter some accessibility issue that we missed.

That being said, we certainly cannot ignore testing! So, what does testing look like? There is a lot that goes into whether or not a webpage is accessible, which means that there is not one test that will catch everything. Depending on the type of issue, one or more of the following methods may be required to test for it:

<!-- Cite deque? https://www.deque.com/blog/automated-testing-study-identifies-57-percent-of-digital-accessibility-issues/ -->
- Using an automated tool to find errors. This is the most convenient method, but cannot be relied on. Estimates vary of the percentage of errors such tools can catch, but we know that the percentage is nowhere near 100%.
- Using an automated tool to find potential errors that require manual checks
- Using a tool to highlight or otherwise examine various elements on the page to more easily check them manually.
- Navigating the page with only a keyboard or with a screen reader.
- Manually examing the content. We want to avoid this as much as possible.

There are several ways to go about testing. For our purposes, we will group the major issues and how to test for them based on content type. As you become more comfortable with testing, you may decide to rearrange the order of tests you perform to find a workflow that works best for you, but this will get you started.

As for what content we need to test, as content creators we can typically categorize the content or elements of a webpage as either features of the content management system or features of the content itself.

Features of the content management system are automatically applied across pages. These might include the page navigation, the header and footer, and various formatting options, such as how links are formatted.

Features of the content, on the other hand, includes everything that we specifically create or modify. For the most part, this will mean the content we create for each page (text, links, images, etc.) and formatting changes we apply to specific items that override the default formatting, though it would also include content we provide for repetitive elements like a footer or sidebar.

This lesson will focus specifically on our content. Features of the content management system will be covered in a separate lesson, as the system requires different considerations in testing.

<!--
Possible exercise: Provide a list of accessibility issues and either ask if learners think the issue can be found with an automated tool or ask what method of testing learners think would be required.
- Low color contrast
- Menu options that cannot be reached with the keyboard
- Image missing alternative text
- Broken link
-->

> ## Challenge: Automated Tools
>
> For the following issues, is the most likely cause the content management system (CMS) or the content? If you are not sure, it is perfectly fine to guess.
>
> 1. Low color contrast
> 2. Menu options that cannot be reached with the keyboard
> 3. An image missing alternative text
> 4. Non-heading text that is formatted by using a heading
>
> > ## Solution
> >
> > 1. Either. If the colors in question were modified from their default values, then the issue is the content. Otherwise the issue is the CMS.
> > 2. CMS. Content management systems handle site navigation.
> > 3. Content. Most images will be added by content creators, who are responsible for providing the appropriate alternative text.
> > 4. Either. Content management systems typically provide formatting options or content types for creating headings that the content creator is responsible for applying, but a CMS may use headings inappropriately when creating navigational elements, subtitles, and other content.
> {: .solution}
{: .challenge}

{% include links.md %}

