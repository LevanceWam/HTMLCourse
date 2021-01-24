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
* this is a psuedo class selector */ article :first-child {
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
