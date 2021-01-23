# HTML Basics

> An overview of HTML basics

In this section we are going to go over all of the essential HTML elements to build web pages.

## Concepts and Principles

**DRY principle**:
DRY -> Don't Repeat Yourself.

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

  <!-- The title for the page -->
  <title>Providing CSS</title>

  <!-- external stylesheet -->
  <link rel="stylesheet" href="style.css" />
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

**Question**:
what is the difference between hyperlink and link?

**Answer**:
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

## List

In html we have 3 types of list elements:

- ul: unordered list
- ol: ordered list
- dl: description list

### ul

The type we use the most is ul, this is used to showcase a list of items where the order does not matter.

a common application for this element is for implementing a navigation menu.Quite often navigation menus are implemented using unordered list.

### ol

In contrast to a ul we have ol where the order of the items do matter. A real world example of this would be a recipe site.

### dl

we use a dl for implementing a glossary or displaying meta data. We can have a term and details about that term.

```html
<ul>
  <!-- list item -->
  <li>About me</li>
  <li>courses</li>
</ul>

<ol>
  <li>Preheat the oven</li>
  <li>Place items on crust</li>
  <li>put pizza in the oven</li>
</ol>

<dl>
  <!-- description term -->
  <dt>HTML</dt>
  <!-- description detail to desrcibe the term -->
  <dd>Hypertext Markup Language</dd>
</dl>
```

## Tables

To make tables we use the table element. In the past we useto use this for laying out pages. This is considered bad practice because we have better ways of doing this now.

### Rows

To define a row we use the tr element
in this element we can have one or more cells which can be:

- data cells
- header cells

Header cells are labels that describes what each column represents. All the other cells are known as data cells
because they contain data.

**Question**:
What is the difference between header and data cells in terms of styling?

**Ans**:
The text is bold for the header and the text is align in the center. Where as the td is text align to the left.

```html
<table>
  <thead>
    <tr>
      <!-- setting the span of the column -->
      <th colspan="2">expenses</th>
    </tr>

    <tr>
      <!-- table header cell -->
      <th>catergory</th>
      <th>amount</th>
    </tr>
  </thead>

  <tbody>
    <!-- the table row -->
    <tr>
      <!-- table data cell -->
      <td>marketing</td>
      <td>$100</td>
    </tr>
  </tbody>

  <tfoot>
    <th>total</th>
    <th>300</th>
  </tfoot>
</table>
```

## Containers

Quite often we need to group a bunch of elements for styling purposes. Containers are used a lot in web development especially for this purpose.

In html we have a few container elements, the most commonly used one is div element (division). This element does not have any visual appearance. Even if we give it child elements it will still show nothing

A div is something we call a block-level element. Block level elements always start on a new line and fill up the entire availiable space. CSS can easily change their width.

Another generic container element called span. which is often used to style text, the span element is a like a div but it is not a block-level element div. A span element is a inline element so it is not going to take up the entire width of the page.

```html
<div class="product">
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Sint omnis hic aliquam dignissimos consequatur
            ipsum iure quas, quis ducimus, sit culpa error necessitatibus enim? Porro corporis illo eum animi inventore?
        </p>
        <a href="#">link</a>
    </div>

    <p>
        <span> class="highlight">Lorem,<span> ipsum dolor sit amet consectetur adipisicing elit. Quae architecto
                explicabo dignissimos recusandae quiavitae, animi debitis optio quos alias.
    </p>
```

## SemanticElements

HTML5 introduced a couple of elements that are more descriptive or more meaningful. They are called Semantic Elements.

Some of the semantic elements:

- article
- figure
- mark
- time

Where ever possible we should use these new Elements. Instead of the generic containers because this helps search engines better understand our pages and what they contain.

### Article element

In html5 we have a element called article that is used to represent articles or post. We can use this element to make the markup more meaningful to search engines.

Now the article does not need to be a blog post or newspaper article
it can be: "An independent, self-contained content".

### Figure

The figure element is just a contianer for figuares. It does not have any visual characteristics. Figures can optionally have a caption it can be above or below the figure this is done with the figcaption element.

```html
<!-- using the article element to make the markup more meaningful to search engines  -->
<article class="article">
  <h1>heading</h1>
  <p>
    published <time datetime="2021-01-01 17:00">January 1, 2021 03:00pm</time>
  </p>

  <!-- highlights text -->
  <p>
    <mark>Lorem</mark> ipsum dolor sit amet consectetur, adipisicing elit.
    Debitis, cum.
  </p>

  <!-- a contianer similar to div but with meaning  -->
  <figure>
    <img src="" alt="" />
    <!-- figure caption -->
    <figcaption>my coffee this morning</figcaption>
  </figure>
</article>
```
