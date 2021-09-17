---
title: "Content for Testing"
teaching: 0
exercises: 0
questions:
- "Key question"
- "Key question 2"
objectives:
- "First learning objective."
- "Second learning objective."
- "Third learning objective."
keypoints:
- "First key point."
- "Second key point."
- "Third key point."
---

The purpose of this page is to provide all the types of content so that everything can easily be tested using one page (for the most part).

## Standard Markdown

Characters: I l 1. 0 O o.

Ordered list:

1. Item 1
2. Item 2
3. Item 3

Nested ordered list:

1. Item 1
    1. Item 1.1
    2. Item 1.2
2. Item 2
3. Item 3
    1. Item 3.1
    2. Item 3.2
        1. Item 3.2.1
        2. Item 3.2.2
    3. Item 3.3
4. Item 4

Unordered list:

- Item 1
- Item 2
- Item 3

Nested unordered list:

- Item 1
    - Item 1.1
    - Item 1.2
- Item 2
- Item 3
    - Item 3.1
    - Item 3.2
        - Item 3.2.1
        - Item 3.2.2
    - Item.3.3
- Item 4

Horizontal Rule:

---

Link: [my link](libraries.ou.edu)

Inline code: `some inline code`

Table:

| Category | Item | 
|--------- | ---- |
| Food     | Sandwich |
| Drink    | Tea | 
| Food     | Apple |
<!--{: .table-bordered}-->

Image: ![Pancake Rocks, New Zealand](../fig/pancake-rocks-nz.jpg)

Normal blockquote:

> ### Blockquote
>
> Content.
>
> 1. Blockquote list item 1
> 2. Blockquote list item 2

## Code Chunks

Standard (source) code chunk:

```
pwd
I l 1
0 O o
```
{: .source}

Output:

```
some output
```
{: .output}

Error:

```
Oh no! Something went horribly wrong.
```
{: .error}

Languages:

<pre class="highlight">
    <code>
        <span>The following classes reference the first item in the CSS file with that color. For example, "Operator" is also used for various numbers, but "Operator" came first.</span>
        <span class="c">Comment</span> <!-- Duplicates: ch, cm, cpf, c1, cs -->
        <span class="k">Keyword</span> <!-- Duplicates: kc, kd, kn, kp, kr, nb, nt, sx, bp -->
        <span class="o">Operator</span> <!-- Duplicates: m, mb, mf, mh, mi, mo, il -->
        <span class="cp">Comment.Preproc</span>
        <span class="gd">Generic.Deleted</span>
        <span class="gr">Generic.Error</span>
        <span class="gh">Generic.Heading</span> <!-- Duplicates: gp -->
        <span class="gi">Generic.Inserted</span>
        <span class="go">Generic.Output</span>
        <span class="gs">Generic.Strong</span>
        <span class="gu">Generic.Subheading</span>
        <span class="gt">Generic.Traceback</span>
        <span class="kt">Keyword.Type</span>
        <span class="s">Literal.String</span> <!-- Duplicates: sa, sb, sc, dl, sd, s2, sh, s1 -->
        <span class="na">Name.Attribute</span>
        <span class="nc">Name.Class</span> <!-- Duplicates: nf, nn, fm -->
        <span class="no">Name.Constant</span>
        <span class="nd">Name.Decorator</span> <!-- Duplicates: ow -->
        <span class="ni">Name.Entity</span>
        <span class="ne">Name.Exception</span>
        <span class="nl">Name.Label</span>
        <span class="nv">Name.Variable</span> <!-- Duplicates: ss, vc, vg, vi, vm -->
        <span class="w">Text.Whitespace</span>
        <span class="se">Literal.String.Escape</span>
        <span class="si">Literal.String.Interpol</span> <!-- Duplicates: sr -->
    </code>
</pre>

## Special Blockquotes

> ## Callout
>
> A standard callout.
{: .callout}

> ## Caution
>
> Not referenced in handbook.
{: .caution}

> ## Challenge
>
> A challenge. Have the user try to do a thing, then provide the solution so they can check their work.
>
> > ## Solution
> >
> > The solution to the challenge.
> >
> > Did you get it right?
> {: .solution}
{: .challenge}

> ## Checklist
>
> Not referenced in handbook.
>
> An ordered list?
>
> 1. Item 1
> 2. Item 2
> 3. Item 3
>
> Or a gh-flavored markdown task list?
>
> - [ ] Item 1
> - [x] Item 2
> - [ ] Item 3
{: .checklist}

> ## Discussion
>
> A dicussion prompt.
{: .discussion}

> ## Testimonial
>
> Not referenced in handbook.
{: .testimonial}

## Other

Keyboard: <kbd>Ctrl</kbd>

---

{% include links.md %}

