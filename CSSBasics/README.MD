# CSS Basics

> An overview of CSS basics

Here we are going to cover essential CSS concept we need to understand.

## Seperation of Concerns

We want to have different modules for different concerns. HTML is for structuring the web page and css is to style them. So we want to have them doing there own thing.

there are 3 different ways to provide styles

- Embedded Stylesheets
- External Stylesheets
- Inline Styles

### Embedded stylesheets

This is including the styles in the html document. There are 2 problems with approach though.

1. The first problem is that they are not scalable so if we have multiple pages. It is likely that we want our styles to carry over with this approach, we'd have to copy all of the styles here and place them on every single webpages. This mean if we change one thing in one file we have to do it for every file.

2. The second problem is that it violates a very important principle in computer science called seperation of concerns.

### External stylesheets:

this allows use to write our styles in seperate files. This helps us organize our code, so we can take all of the rules we have and place them in a seperate file. We create a file called style/styles.css and place our rules there.

We have to link this file using the link element. This element has 2 attributes rel (relationship) this determines. The type of resource we are linking this document too. next is href which we are familiar, with here we can provide a relative or absolute url.

### Inline styles:

We can apply a style directly to a element. Every HTML element has a style attribute and this is where we can write one or more styles. Add more rules by seperating them with semi-colons.

Now inline styles are a little noisy and they violate the principle of seperation of concerns, so we should try to avoid using that.

### Overriding

This is the priority order from greatest to least.

Inline -> Embedded -> External

Inline will always show up above the others.

## Basic Selector

**Selector**:
A selector is an element we choose to select in css. It's called a selector because we are selecting a element to apply rules to in styles.css. We can also use id's as a selector, the same can be done with classes.

**Question**:
What is the difference between the id and class attributes?

**Ans**: you can not have the same id for multiple elements you can only have one element for one id. But you can have one class for multiple elements, id's have to be unqiue.

```css
/* body is what we call a selector this is how we select a element */
/* here we are selecting a element by its type which in this case is the body element */
body {
  margin: 10px;
}

/* here we are selecting an element by it's id */
#products {
}

/* selecting a element by their class */
.product {
}

/* selecting a element using attributes */
/* here we are checking for the existence of the target attribute */
/* if we wanted to target the value just add it to the selector */
a[target] {
}
```

## Relational Selectors

Relational selectors are those selectors which bear resemblence in relationship just like humans. These selectors constitute Descendant Selector, Direct Child Selector, Sibling Selector and Next Sibling Selector.

they help us write cleaner markup, but there are 2 problems with relational markup we need to know about.

1. They can be fragile.
   This is because they are dependant on the location of the elements in the dom so of the elements are
   moved things will break

2. They are not as fast as basic selectors
   We aren't going to be worried about this and the changes are not "noticable". we can't tell the difference.

   This is depenedant on how the browser renders these selector
   the browser reads this from right to left so it will get all of the
   paragraph elements first then it checks to see if that element comes after the section with the id

```css
/* here we are combining two different selectors */
/* we call this a relational selector */
/* this particular one is called a desecendant selector */
/* this will affect any paragraph in the products section */
#products p {
  color: orange;
}

/* if we wanted to style only the first paragraph element in the section we can do this */
#products > p {
  color: steelblue;
}

/* this is going to select the paragraph element that is directly after the section */
#products + p {
  color: goldenrod;
}

/* this will affect all of the paragraphs outside of the section */
#products ~ p {
  color: steelblue;
}
```

## Psuedo-Class Selectors

with Psuedo-Class Selectors we use :

A CSS pseudo-class is a keyword added to a selector that specifies a special state of the selected element(s).

For example, it can be used to:

- Style an element when a user mouses over it.
- Style visited and unvisited links differently.
- Style an element when it gets focus

Here are some of those selectors:

- first-child selector
- first-of-type selector
- last-of-type
- last-child selector
- nth-child selector

```css
/* this is a psuedo class selector */
article :first-child {
  font-size: 140%;
  font-style: italic;
}

/* this selector targets the first occurance of element types*/
article :first-of-type {
  font-size: 140%;
  font-style: italic;
}

/* this is going to get the first occurance of the element */
article p:first-of-type {
  font-size: 140%;
  font-style: italic;
}

/* this targets the last paragraph element */
article p:last-of-type {
  font-style: bold;
}

/* does the same as the one above  */
article p:last-child {
  font-style: bold;
}

/* we want to get the odd items in the list  */
/* this selector is like a function we can pass a value or agruement here to target certain elements */
ul li:nth-child(odd) {
  color: salmon;
}
```

## Psuedo-Element Selectors

With Psuedo-Element Selectors we use ::

A CSS pseudo-element is a keyword added to a selector that lets you style a specific part of the selected element(s).

For example, it can be used to:

- Style the first letter, or line, of an element.
- Insert content before, or after, the content of an element.

Here are some of those selectors:

- ::first-letter
- ::first-line
- ::selection
- ::before
- ::after

**Question**:
what is the difference between Psuedo-Element Selectors and Psuedo-Class Selectors?

**Ans**:
in a Psuedo-element we use it to style part of an element. e.g first letter. with Psuedo-classes we use them to style elements in a particular state. e.g hovered achor

```css
/* getting the first letter in the element */
p::first-letter {
  font-size: 140%;
  font-weight: bold;
}

/* first line in element  */
p::first-line {
  font-weight: bold;
}

/* when we select text by clicking and dragging */
/* this is only applied to paragraphs */
/* if we get rid of the p all the selected elements will be pink */
::selection {
  background-color: pink;
}

/* inserting content before this element */
/* convertig this element to a block element  */
p::before {
  content: "...";
  display: block;
}

/* inserts content after this element  */
p::after {
  content: "...";
}
```

## Selector Specificity

Specificity is the means by which browsers decide which CSS property values are the most relevant to an element and, therefore, will be applied. Specificity is based on the matching rules which are composed of different sorts of CSS selectors.

Specificity is a weight that is applied to a given CSS declaration, determined by the number of each selector type in the matching selector. When multiple declarations have equal specificity, the last declaration found in the CSS is applied to the element. Specificity only applies when the same element is targeted by multiple declarations. As per CSS rules, directly targeted elements will always take precedence over rules which an element inherits from its ancestor.

we have something called the specificity triangle, this is how it goes:

- ID selector
  this is because we can not have 2 elements with the same id
  the id selector is very specific.

- Class & Attribute selectors
  these selectors are less specific because we can have multiple elements with the same class or attributes.

- Element selectors  
  because we can have many elements of a given type.

**Question**:
What will happen if we have 2 selectors with equal specificity or weight.

**Ans**:
The rule that comes last.

**Question**:
how do we prevent the id selector from overriding the element selector?

Ans:
there are 2 ways to do this

    1. One solution is to use the important key word. We add it to the end of a property. when this key word is applied other rules are discarded.

    So we want to avoid using this using the important keyword is consider a bad practice because it can make your css messy and hard to maintain.

    2. The second solution would be to make a rule that has more weight to it than the one. this can be accomplished by adding more than one selector to a rule.

    Another way to overide is if the element is inside of a container we can target the container then the child element.
