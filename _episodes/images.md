---
title: "Images"
teaching: 15
exercises: 10
questions:
- "How can I check the alternative text of images in my content?"
objectives:
- "Describe the difference between alternative text and the alt attribute."
- "Identify any images without an alt attribute."
- "Check the alt attributes for all images on a page."
keypoints:
- "Alternative text can be provided through an image's alt attribute, image caption, text on the page, or a link to a longer description."
- "Alternative text should not be provided using an image's title attribute (hover text)."
- "WAVE will identify any images that do not have an alt attribute."
- "WAVE will provide the value for all image alt attributes to assist with manual checking."
- "Appropriate alternative text depends on the type of the image, so it is useful to have a resource to refer to that describes the different types of images."
---

## Alternative Text

We will start with definitions for three important terms:

Alternative text
: Text that is associated with an image and conveys any important information it provides.

Alt attribute
: An attribute included with image elements that is often used to provide alternative text.
<!-- Any reasonable content management system will provide a way to set this. -->

Title text
: Text included with image or other elements that is displayed on the screen when the user hovers over the element with their mouse, also known as hover text.

While the alt attribute is the most common method for providing alternative text, it is not the only one. Two other relatively common methods are including alternative text in the page content adjacent to the image or using an image caption. These methods are preferable in situations where the alternative text may also benefit sighted users, such as by increasing their understanding of a complex image.

Note that title text is **not** an acceptable method for providing alternative text.

## Missing Alternative Text

Even if an image is purely decorative or its alternative text is provided on the page, the alt attribute must never be ignored. A null or empty alt attribute marks an image as decorative, while no alt attribute will typically causes accessibility issues. Some content management systems will automatically take care of this if alt text is not provided, while others may provide a checkbox for indicating when an image is decorative.

WAVE will help us check for missing alt attributes by creating errors. The most common error to look for is **Missing alternative text**. There are a few other potential errors, but these will include the phrase "missing alternative text" in the name (e.g. the **Linked image missing alternative text** error that we have already discussed).

We already made a note of the linked image on the sample page, but there are also a couple of non-interactive images that are missing alt text.

1. The first one has a suitable description in a caption directly below it. While it is good that alternative text is provided, the missing alt attribute is an accessibility issue: Screen readers will read out the filename of the image when they reach it. Providing a null or empty alt attribute would solve this.

2. The second image is a more serious accessibility issue, as it has no alt attribute or alternative text at all. Screen readers will indicate the existence of the image and read out the image filename, but no additional information will be provided.

We should also pay attention to any **Image with title** alerts from WAVE. The name of this alert is slightly misleading, as it is not provided for every image with a title attribute. For example, if we scroll down to the last image on the page and hover over it, we can see that it has a title. However, the only WAVE alert for the image is about the length of the alternative text.

When WAVE provides an **Image with title** alert, this means that the image has a title, but does not have an alt attribute or has an empty alt attribute. The sample page has one of these alerts. An additional WAVE feature tells us that this particular image has null or empty alt text. All information in the title will be lost, because screen readers will ignore the image entirely. We should always treat **Image with title** alerts as though they were **Missing alternative text** errors.

<!-- > ## Exercise: The Alt Attribute
>
> 1. What is the difference between an image Missing alternative text and an image that has a null or empty alt attribute?
> 2. When is it appropriate for an image to have missing alternative text?
>
> > ## Solution
> >
> > 1. A null or empty alt attribute tells assistive technology to ignore the image, because it is a decorative image. These images will not even be mentioned to screen reader users. Images with missing alternative text, however, are not coded as either decorative or meaningful. Screen readers will typically read the image filename.
> > 2. Never. All images should either be coded as decorative (null or empty alt text) or meaningful (alt text with the appropriate content).
> {: .solution}
{: .challenge} -->

## Other WAVE Image Alerts

WAVE will also provide us with a number of alerts for potentially problematic alt text.

**Suspicious alternative text** is similar to the alert for suspicious link text in that it may not find all "obvious" issues, but will still find many, if not most. The sample page has one of these alerts. We can examine it further, as the alt text is provided under the image in green-highlighted white text. In this case, the alt text is the name of the image, which is not descriptive.

**Redundant alternative text** and **A nearby image has the same alternative text** are both alerts that will almost always indicate problems ranging from mild to severe. As with all automated checks, they do have limitations.

There is an alert for **Long alternative text** on this page. Alt attributes should be relatively concise: If the necessary alternative text is too long, it should be provided using a different method. Unfortunately, WAVE does not show the alt text below the image for this alert. Two good options for investigating the issue further would be finding the alt text from the content management system or starting up a screen reader to hear how it identifies the image. Either of these methods will reveal that this alternative text includes copyright attribution: Source and copyright info never belong in the alt attribute.

## Manually Checking Images with WAVE

Once we have checked the errors and alerts, we can run through all the images to check for other issues. WAVE can help with this, but it is primarily a manual process, much like how we checked the page's heading structure.

First, as we did with headings, we want to turn off everything from WAVE that is not relevant to images. This means some of the errors, alerts, and features, as well as all contrast errors, structural elements, and ARIA. Once we have done this we can check out each relevant feature listed by WAVE.

1. The first image has the **Alternative text** feature. For every image that has this feature, the alt text will be added to the page in white text on a green background below the image. This image could be considered decorative, but some people prefer to have short alt text provided even for primarily decorative images.
2. The next two images have the **Linked image with alternative text** feature. This feature (and the Image button with alternative text feature) indicates a functional image. When checking the alt text WAVE shows us, we want to make sure the text describes the image function. Sometimes it may be appropriate to also describe the image, but this can get in the way and make the link text overly clunky, so it should be done only when necessary. The first of the two image links describes the image, which is not helpful. The second is a much better example, as it describes what the image links to (a webpage about saving the monarch butterfly).
3. Below those images is one we have made note of previously - a linked image with no alternative text - and all of the remaining images also have errors or alerts we have checked.
4. The rainbow image has a **Figure** feature. This means that assistive technology will identify the image and caption as a figure. When looking at images with captions, we do want to make sure we see this feature. It is possible to format text to look like an image caption, but screen reader users will not receive the benefit of that formatting.
5. The image with the title alert also has a **Null or empty alternative text** feature. When we see this feature, we want to make sure the image is purely decorative and that it would be preferable for blind and low vision screen reader users not to be informed of its existence at all.
6. Once we have verified there are no other images with empty or existing alternative text to check, we can move on.

Another thing we want to check for is if any images of text can be found on the page. Images of text should be avoided except when absolutely required.

Determining the appropriate alternative text for an image can be complicated. Therefore, as we check images, we will want to either already be familiar with the various aspects to consider or have a resource to consult with (or both). WAI provides an excellent [images tutorial](https://www.w3.org/WAI/tutorials/images/) that can be useful to look over before testing and to refer to while testing.

> ## Exercise: Testing Images
>
> For each of the images on the testing sample page, answer the following questions:
>
> 1. Does the image have any accessibility issues?
> 2. If there are issues, what should be done to make the image accessible?
>
> > ## Solution
> > 
> > 1. An image of text describing color contrast accessibility
> >     1. Yes: This is an image of text, which should be avoided. It also has null alt text, so the text from the image is not provided to assistive technology at all.
> >     2. The image should be replaced with actual text.
> > 2. A landscape image that is also a link
> >     1. Yes: The image has no alternative text, making it an empty link.
> >     2. The alt attribute should describe the link destination. For example, "Yellowstone National Park" would be appropriate alt text.
> > 3. An image of a sunset
> >     1. Yes: The image has no alt attribute.
> >     2. Either the image should be marked as decorative (with null or empty alt) or it should be given an alt attribute with a brief description.
> > 4. An image of the crescent sun
> >     1. No. This image has descriptive alt text.
> > 5. An image of the New Zealand coast and the Pancake Rocks
> >     1. Maybe: The image has redundant alternative text.
> >     2. Since there is text directly adjacent to the image describing it, the image could have a null or empty alt attribute so that screen reader users would not hear the same information twice.
> {: .solution}
{: .challenge}

{% include links.md %}

