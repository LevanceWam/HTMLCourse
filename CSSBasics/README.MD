# CSS Basics

> An overview of CSS basics

Here we are going to cover essential CSS concept we need to understand.

## Seperation of Concerns

We want to have different modules for different concerns. HTML is for structuring the web page and css is to style them. So we want to have them doing there own thing.

there are 3 different ways to provide styles

- Embedded Stylesheets
- External Stylesheets
- Inline Styles

## Embedded stylesheets

This is including the styles in the html document. There are 2 problems with approach though.

1. The first problem is that they are not scalable so if we have multiple pages. It is likely that we want our styles to carry over with this approach, we'd have to copy all of the styles here and place them on every single webpages. This mean if we change one thing in one file we have to do it for every file.

2. The second problem is that it violates a very important principle in computer science called seperation of concerns.

## External stylesheets:

this allows use to write our styles in seperate files. This helps us organize our code, so we can take all of the rules we have and place them in a seperate file. We create a file called style/styles.css and place our rules there.

We have to link this file using the link element. This element has 2 attributes rel (relationship) this determines. The type of resource we are linking this document too. next is href which we are familiar, with here we can provide a relative or absolute url.

## Inline styles:

We can apply a style directly to a element. Every HTML element has a style attribute and this is where we can write one or more styles. Add more rules by seperating them with semi-colons.

Now inline styles are a little noisy and they violate the principle of seperation of concerns, so we should try to avoid using that.

### Overriding

This is the priority order from greatest to least.

Inline -> Embedded -> External

Inline will always show up above the others.
