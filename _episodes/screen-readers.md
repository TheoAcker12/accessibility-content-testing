---
title: "Screen Readers"
teaching: 10
exercises: 0
questions:
- "How can a screen reader help with testing content?"
objectives:
- "List some of the issues that screen readers can identify."
keypoints:
- "Screen readers are extremely valuable testing tools."
- "Having the computer read text aloud (typically while you look away) can help with testing for content or structure that relies on formatting."
- "You do not have to be proficient to get valuable information from a screen reader."
- "Screen readers do more than read the screen."
- "Screen readers interact with semantic elements like headings and lists in important ways."
---

## Using Screen Readers for Testing

In talking about formatting, there were several types of issues that cannot be easily tested with tools like WAVE or Insights. The best way to test for these (and certain other) issues is with a screen reader.

Screen readers are specialized software that provide the content of the page in a structured audio format. They can help us test for formatting used to convey meaning or structure, for potential typos, and for a wide variety of other issues. While they should not be relied on as the sole means of testing (not all disabled users are blind or low vision), screen readers are a valuable tool for testing.

Screen readers may sound like complicated and intimidating tools, so it is important to know: You do not have to be proficient in using a screen reader to get major benefits from it. It is generally enough for this kind of testing to know how to turn the screen reader on and off and how to have it read through content on a page.

Because different operating systems work with different screen reader software, it is not realistic to try teaching how to use them here. Fortunately, there are plenty of instructional materials for getting started. [Screen Reader Resources](https://guides.ou.edu/accessibility-reference/resources#s-lg-box-wrapper-31204987)

<!-- Link needs to be included here so that people can find what screen reader is built-in with their operating system and instructional materials for using it. -->

We will go through a quick demo, however, so you get a sense of how screen readers can be used and why they are so important. It will also help demonstrate the importance of some of the issues we are testing for. This demo will use VoiceOver, which is the built-in screen reader for Apple devices. Because VoiceOver works best with Safari, we will use that instead of Chrome.

<!--
Demo goes here: The only text that makes sense to provide with this is a transcript, I think.

Idea for reflection/discussion: After the demo, consider the following questions, then discuss your thoughts with a partner.
- Did the screen reader announce various parts of the page the way you would have expected? If not, what was different?
-->

> ## Screen Reader Demo
>
> ### Start
>
> - Start the screen reader: <kbd>Cmd</kbd> + <kbd>F5</kbd>
> - Can pause (and resume) the voice with <kbd>Ctrl</kbd>
> - Multiple ways to go straight to the main content of the page. Screen reader users often navigate using headings, so I will demonstrate that.
>
> ### Rotor
>
> - I can open the VoiceOver rotor: <kbd>Ctrl</kbd> + <kbd>Option</kbd> + <kbd>U</kbd> (other screen readers will have similar functions)
> - Navigate between lists using left and right arrow keys.
> - Note the links menu. This is one of the reasons it is important for link text to make sense out of context.
>   - There is a "click here" link that is meaningless to us.
>   - There is a link that is a URL, and the screen reader starts reading it letter by letter.
> - Headings menu is what we want. Provides an outline of the page content the way a sighted user might visually scan a page for headings.
> - Navigate up and down with arrow keys
> - Press <kbd>Return</kbd> to pick heading level one.
>
> ### Content
>
> - Can navigate through content on the page with <kbd>Ctrl</kbd> + <kbd>Option</kbd> (called the VoiceOver keys) and left/right arrow keys
> - Can jump around using the mouse
> - Can hear how screen reader identifies meaningful elements, like headings
> - Lists: screen reader gives a lot of information
> - We do not get the same amount of info when the list is pure text.
>
> ### Done
>
> - Turn VoiceOver off with same command as on.
> - There is a lot more people can do with a screen reader, but hopefully this has demonstrated how much you can learn about a page with only a few basic commands.
> - Keep in mind: There is variation between screen readers. Remember our theme of "Trust, but verify." Testing with a screen reader is good, but we also want to use other tests to ensure our content is accessible.
{: .discussion}

{% include links.md %}

