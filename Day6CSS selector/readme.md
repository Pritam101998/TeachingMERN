# CSS Selector

.class
#id
p.class --> tag.classname or p#idname
p#id
.class1.class2
.class1 .class2 /div p
p

- div ,p
  div>p
  div+p
  p~ul
  a[attribute]
  a:hover
  tag:nth-child()

CSS has a wide range of selectors that allow you to target specific elements, attributes, or even combinations of elements for styling. Below is a comprehensive list of the most common CSS selectors along with explanations and examples:

1. Universal Selector (\*)
   The universal selector targets all elements on the page.

-

* {
  margin: 0;
  padding: 0;
  }
  This will remove margin and padding from all elements.

2. Type Selector (Element Selector)
   The type selector targets all instances of a specific HTML element.

- p {
  color: blue;
  }
  All <p> elements will have blue text.

3. Class Selector (.className)
   The class selector targets all elements that have a specific class.

- .myClass {
  font-size: 18px;
  }
  All elements with the class myClass will have a font size of 18px.

4. ID Selector (#id)
   The ID selector targets a single element with a specific ID.

- #header {
  background-color: gray;
  }
  The element with the ID header will have a gray background.

5. Descendant Selector (A B)
   This selects elements that are descendants of a specified element.

- .container p {
  color: green;
  }
  Only <p> elements that are inside .container will have green text.

6. Child Selector (A > B)
   This selects elements that are direct children of a specified element.

- .container > p {
  color: red;
  }
  Only direct <p> children of .container will have red text.

7. Adjacent Sibling Selector (A + B)
   This selects an element that is immediately next to a specified element.

- h1 + p {
  margin-top: 10px;
  }
  Only the first <p> that comes right after an <h1> will have a 10px top margin.

8. General Sibling Selector (A ~ B)
   This selects all siblings of a specified element.

- h1 ~ p {
  font-style: italic;
  }
  All <p> elements that are siblings of an <h1> will be italicized.

9. Attribute Selector ([attribute])
   This selects elements that have a specific attribute.

- input[type="text"] {
  border: 1px solid black;
  }
  All <input> elements with type="text" will have a black border.

10. Pseudo-Classes (:pseudo-class)
    Pseudo-classes target elements in specific states.

## :hover: Applies styles when an element is hovered over.

button:hover {
background-color: lightblue;
}
:nth-child(n): Targets the nth child of an element.

- ul li:nth-child(2) {
  font-weight: bold;
  }
  The second <li> child will be bold.

11. Pseudo-Elements (::pseudo-element)
    Pseudo-elements style specific parts of an element.

## ::before: Inserts content before the element.

h1::before {
content: "⭐ ";
}
Adds a star before every <h1>.

## ::after: Inserts content after the element.

p::after {
content: " Read more...";
}
Adds "Read more..." after every <p>.

12. Grouping Selector (A, B, C)
    This groups multiple selectors to apply the same styles to different elements.

- h1, h2, h3 {
  font-family: Arial, sans-serif;
  }
  All <h1>, <h2>, and <h3> elements will have the same font.

13. Not Selector (:not(selector))
    This selects all elements except the specified one.

- p:not(.special) {
  color: black;
  }
  All <p> elements except those with the class special will have black text.

14. Attribute Selector with Value ([attribute=value])
    This selects elements with a specific attribute and value.

- input[type="checkbox"] {
  width: 20px;
  height: 20px;
  }
  All checkboxes (<input type="checkbox">) will have the specified width and height.

15. Only Child Selector (:only-child)
    This selects elements that are the only child of their parent.

- p:only-child {
  color: blue;
  }
  The <p> element will have blue text only if it's the only child of its parent.

16. First Child Selector (:first-child)
    This selects the first child of a parent element.

- p:first-child {
  color: red;
  }
  Only the first <p> child of a parent will have red text.

17. Last Child Selector (:last-child)
    This selects the last child of a parent element.

- p:last-child {
  font-size: 20px;
  }
  Only the last <p> child of a parent will have a 20px font size.

18. First of Type Selector (:first-of-type)
    This selects the first element of its type within its parent.

- p:first-of-type {
  color: blue;
  }
  The first <p> element within its parent will have blue text.

19. Last of Type Selector (:last-of-type)
    This selects the last element of its type within its parent.

- p:last-of-type {
  color: green;
  }
  The last <p> element within its parent will have green text.

20. Nth of Type Selector (:nth-of-type(n))
    This selects the nth element of its type within its parent.

- li:nth-of-type(3) {
  color: purple;
  }
  The third <li> element within its parent will have purple text.

21. Empty Selector (:empty)
    This selects elements with no children.

- div:empty {
  display: none;
  }
  All empty <div> elements will be hidden.

22. Disabled Selector (:disabled)
    This selects elements that are disabled.

- input:disabled {
  background-color: gray;
  }
  All disabled <input> elements will have a gray background.

23. Checked Selector (:checked)
    This selects elements that are checked (like checkboxes or radio buttons).

- input:checked {
  border: 2px solid green;
  }
  All checked checkboxes or radio buttons will have a green border.

24. Hover Selector (:hover)
    This selects elements when the user hovers over them.

- a:hover {
  color: red;
  }
  All links (<a>) will turn red when hovered over.

25. Focus Selector (:focus)
    This selects elements when they are focused (like when you click into an input field).

- input:focus {
  border: 2px solid blue;
  }
  When an input field is focused, its border will turn blue.

# CSS Specificity

CSS Specificity determines which styles are applied to an element when there are conflicting CSS rules. Specificity is essentially a weight that is applied to a given CSS declaration, and the browser uses this weight to determine which rule to apply.

Specificity Hierarchy
Inline styles: Styles directly applied to an element via the style attribute.
ID selectors: Styles applied using #id.
Class selectors, attribute selectors, and pseudo-classes: Styles applied using .class, [attribute=value], or :hover, :focus, etc.
Type selectors (element selectors) and pseudo-elements: Styles applied using div, p, ::before, ::after, etc.
Universal selector (\*), combinators (+, >, ~), and negation pseudo-class (:not()): These have the lowest specificity.
Specificity Calculation
Each CSS selector has a specificity score, which is calculated by counting the occurrences of different types of selectors. This can be thought of as a four-part value (A, B, C, D):

A: Inline styles (1 if present, 0 otherwise)
B: Number of ID selectors (#id)
C: Number of class selectors (.class), attribute selectors ([type="text"]), and pseudo-classes (:hover, :nth-child)
D: Number of type selectors (div, h1) and pseudo-elements (::before, ::after)
Example:
Let's look at some examples of selectors and their specificity scores:

#header – (0, 1, 0, 0)

B: 1 ID selector.
.content p – (0, 0, 1, 1)

C: 1 class selector (.content)
D: 1 type selector (p).
ul li:first-child – (0, 0, 1, 2)

C: 1 pseudo-class (:first-child).
D: 2 type selectors (ul, li).
#header .nav a:hover – (0, 1, 2, 1)

B: 1 ID selector (#header).
C: 2 class selectors (.nav, :hover).
D: 1 type selector (a).
div > .item – (0, 0, 1, 1)

C: 1 class selector (.item).
D: 1 type selector (div).
How Specificity Works:
When multiple CSS rules target the same element, the rule with the highest specificity will be applied. For example:

html
Copy code

<div id="header" class="title">Hello World</div>
If we have the following styles:

- #header {
  color: red;
  }

.title {
color: green;
}

div {
color: blue;
}
The element will be styled with red text because the #header selector has the highest specificity.

#header – Specificity: (0, 1, 0, 0)
.title – Specificity: (0, 0, 1, 0)
div – Specificity: (0, 0, 0, 1)
Since the ID selector has higher specificity, its styles will take precedence.

Important Notes:
Inline styles have the highest specificity and will always override other styles except for !important rules.

html
Copy code

<div style="color: blue;">This is blue.</div>
!important will override all other styles, regardless of specificity. However, use of !important should be minimal as it can make debugging and maintenance difficult.

- .title {
  color: red !important;
  }
  In this case, even if an ID selector or inline style tries to override the color property, the !important rule will take precedence.

 <!-- 
 1. git remote add origin https://github.com/Pritam101998/TeachingMERN.git
 2. git remote set-url origin https://github.com/Pritam101998/TeachingMERN.git
 3. git add .
 4. git commit -m "add one folder"
 5. git push origin main --force
 https://github.com/Pritam101998/TeachingMERN.git -->
