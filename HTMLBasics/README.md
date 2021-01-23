# HTML Basics

> An overview of HTML basics

In this section we are going to go over all of the essential HTML elements to build web pages.

## Head Section

In the head section we have a couple of meta elements for giving information about this web page. The purpose of meta elements with these elements
we can give information about a webpage

```html
<head>
  <!-- this defines the character set used in the document -->
  <meta charset="UTF-8" />

  <!-- this meta element configures the viewport of the page -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <!-- this meta element is used to define keywords on the page -->
  <meta name="keywords" content="HTML, CSS" />

  <!-- this meta element provides the description for the website on search engines -->
  <meta name="description" content="This is the description for this website" />
</head>
```

## Text

### Headings

In html we have 6 headings h1-h6 Heading 1 represents the most important heading and heading 6 is it least important.

A common mistake that is made is that the heading are choosed based on their size so people just use a heading that is benefical to them. This is not how we are suppose to use headings. This is because the size can be changed with CSS.

Headings should be used to create a hierachy. Every web page should have _ONE AND ONLY ONE H1 ELEMENT_. This heading represents what this page is all about having multiple h1s can confuse search engines.
After we use h1 we should use h2 we should not skip.

### Displaying Text

We use the paragraph element to display some text. To emphasize we would use the em element. It represents stress emphasis of its contents. Whenever we want to emphasis something we wrap it in the em element.

Another similar element is strong. Represents strong importance, seriousness, or urgency for its contents this also helps with search engines. Where we use this really depends on the context of our content.

Now the italic and bold elements are deprecated elements that we use to use instead of strong and em. We don't use these elements anymore.

```html
<!-- most important h1 -->
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<!-- least important h6 -->
<h6>Heading 6</h6>

<!-- Em is used to emphasis content  -->
<p>I love to use <em>HTML</em>!</p>
<!-- strong is used to show strong importance for its contents -->
<p>I love to use <strong>HTML</strong>!</p>
```

## HyperLinks

To create links to other pages and sites we use the achor element <a>.
Every achor element needs a href: (hypertext reference) attributes.
In the href we can link to a relative or absolute url.

_Question_:
what is the difference between hyperlink and link?

_Answer_:
link is just the address, the url, the location of the target page. Hyperlink is the element the user can click on to navigate to the target page.

### Relative urls

A relative url starts from the current page. If the file was in a different folder this still counts as a relative url.

In short, relative urls start from the current page and then it goes somewhere else.

### Absolute urls

There are times we are going to be working in heavily nested
folders and to keep going a level up for our hyperlinks can be a little messy

This is where we can use absolute urls
so we start with a "/" this represents the root of the site

```html
<!-- linking another page on our website -->
<!-- example of a relative url -->
<a href="about.html">about me</a>

<!-- another example of relative url -->
<a href="company/company.html">company</a>

<!-- linking to a image -->
<!-- prompting the user to download it -->
<!-- when the link is clicked download will start -->
<a href="images/84683.jpg" download>Photo</a>

<!-- adding a fragment to the link -->
<a href="#section-css">CSS</a>

<!-- this opens a new tab to google  -->
<a href="https://www.google.com/" target="_blank">google</a>

<!-- this will open the deafult mail application and set the email in the to field -->
<a href="mailto:random@gmail.com">Email me</a>

<!-- this opens a new tab to google  -->
<a href="https://www.google.com/" target="_blank">google</a>

<!-- absolute url -->
<a href="/company/company.html"></a>
```
