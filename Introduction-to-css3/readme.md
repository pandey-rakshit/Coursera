# Introduction to CSS3 by University of Michigan

<details>
<summary>📖 Table of Content</summary>

<p>

- [`Box Model`](#box-model)

- [`Border`](#border)

- [`Margin and Padding`](#margin-and-padding)

- [`Additive Height and width`](#additive-height-and-width)

- [`Centering an Element`](#centering-an-element)

- [`Box Sizing`](#box-sizing)

- [`Measurement`](#measurements)

- [`Links`](#links)

- [`Buttons`](#buttons)

- [`Selectors`](#selectors)

- [`Classes vs ids`](#classes-vs-ids)

- [`Transitions`](#transitions)

- [`Transform`](#transform)

- [`z-index`](#z-index)
</p>

</details>

## Box Model

- Box Model is a general concept of CSS which helps in size and place you element.

- Every thing that we see in HTML is a box.

- `Height` and `Width` are just the `content` itself of `inline` elements, Hence we can not change it.

- `Elements` that are `not inline` can take `Height` and `width` properties.

```css
* {
  box-sizing: border-box;
}
```

## Border

- Any box or element can have border.

- border property specifies `style`, `width` and `color`.

- border property `style` is `MUST`

```css
div {
  border: solid 1px #90ab3f;
}
```

- `color` and `width` are default to `black`, `1 px`

- Border `style` - `none`, `dotted`, `dashed`, `solid`, `double`, `groove`, `ridge`, `inset`, `outset`, `hidden`

![`border-style`](./docs/images/border-style.png)

## Margin and Padding

- Margin is aditional space outside your border - between you and neighbour

```css
div {
  margin: 15px;
}
```

- padding is simmilar to margin just the difference is its between element and its border.

```css
div {
  padding: 15px;
}
```

- Neither takes a color( transparent )

- can also be defined in 1 - 4 values like border.

  ![`maring-padding`](./docs/images/margin-padding.png)

## Additive Height and width

> - ActualWidth = margin + border + padding + width
> - ActualHeight = margin + border + padding + height

```css
div {
  width: 100px;
  height: 50px;
  padding: 10px;
  margin: 5px;
  border: 1px solid black;
}

/* 

TotalWidth = margin-left + border-left + padding-left  + width + padding-right + border-right + margin-right

TotalWidth = 5 + 1 + 10 + 100 + 10 + 1 + 5 => 132 

TotalHeight = margin-top + border-top + padding-top + heigth + padding-bottom + border-bottom + margin-bottom

TotalHeight = 5 + 1 + 10 + 50 + 10 + 1 + 5 => 82

*/
```

## Centering an Element

- To Horizontally center an element use - `{ margin: 0 auto; }`

- The element must be `{ display: block }`

- The element must not be float

- The element must not have a fixed or absolute position

- The element must have a width that is not auto - if the width is auto, the element will expand to fill the container

## box-sizing

- box-sizing takes some of the `math` out

- options:
  - content-box: default additive
  - border-box: width takes content, padding, and border into consideration

## Measurements

- Absolute - set to a specific size - px, mm, cm, pt ...

- Fluid - sets size relative to surrounding elelments
  - %, vh, vw
  - em (for font): 1 em is current size, .75 is 75% of the current size.
  - rem (for font): 1 rem is current size of root element.

## links

```css
/* example dummy A (link) */

a {
  display: block;
  font-weight: bold;
  color: #fff;
  background-color: #0006cc;
  width: 200px;
  text-align: center;
  padding: 4px;
  text-decoration: none;
}
```

- links help the browser to understand and map the pages around the internet.

- Be semantic, ex - if you want a button use the `<button>` element instead.

### states

- a:link - a normal, unvisited link

- a:visited - has been visited

- a:hover - activated by mouse

- a:focus - activated with the keyboard

- a:active - is being clicked

### Precedence of Rule

- a:hover Must come after a:link and a:visited

- a:active Must come after a:hover

## Buttons

```html
<button>Submit</button>
```

## Selectors

- help in styling speicific object or element

- id - selects a single element (`#id`)

- class - selects a group of elements (`.class`)

- tag - selects a specific element (<`tag`>)
- descendant - selects all the descendant elements (`nav a`) - all of anchor links inside nav tag
- sibling - selects all the sibling elements
- child - selects all direct descendant - (`nav > a`) - all of the anchor links whose first or immediate parent is nav.
- adjacent - selects all the adjacent elements (`h1 + ol`) where h1 and ol are adjacent element
- attribute - select the element that have the given attribute - `a[href="info.html"]`

```css
/* Operators can be used to find attributes values you are looking for */

a[href^="https://umich"]
{
  /* ^: match the beginning  exactly */
}

img[src$=".png"] {
  /* $: match the end exactly */
}

a[href*="umich"] {
  /* *: wildcard */
}
```

- combinator - selects all the sibling elements
- universal - selects all the elements (`*`)

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

- pseudo-class - selects all the elements
- pseudo-element - selects all the elements
- :not - selects all the elements
- :first-child - selects the first child element
- :last-child - selects the last child element
- :only-child - selects the only child element
- :empty - selects the element if it has no child element
- :root - selects the root element
- :nth-child - selects the nth child element
- :nth-last-child - selects the nth last child element

## Classes vs ids

- id - unique - can be used only once.
- classes can be used multiple times.

## Transitions

- Animation

- When element transition from one state to another, you can alter their appearance

  - if you hover over the link, change the color.
  - if an image comes into focus, change the size

  ```css
  Element {
    /* 
  
  transition-property: 
  what is it you want to change ? (size, color, position, etc...)
  
   transition-duration: 
   how long the transition will last ? (in milliseconds)
  
  transition-timing:
  how the transition will be paced ? (ease, linear, etc...)
  
  transition-delay:
  when the transition will start ? (in milliseconds)  
  
  */
  }
  ```

- Define the element
- choose the element for transition
- Define the new values
  - you must combine this step with a pseudo-class

```css
div {
  color: #000000;
  background: #2db34a;
  line-height: 200px;
  text-align: center;
  width: 250px;
  height: 200px;
  border-radius: 6px;
  transition-property: background, border-radius, color, width;
  transition-duration: 0.5s;
  transition-timing-function: linear;
  transition-delay: 0.5s;
}

div:hover {
  background: #011b3f;
  width: 350px;
  border-radius: 30%;
}

div:active {
  color: #000000;
  width: 150px;
  background: #2db34a;
}
```

## Transform

2D Transition options

- translate

```css
/* transform: translate(x, y) */
.box {
  transform: translate(100px, 100px);
}

/* 
  - move x pixels to the left/right and y pixel up/down
*/
```

- rotate

```css
/* tranform: rotate(angle(degree)) */

.box {
  transform: rotate(45deg);
}

/* 

- Rotate/spin the element a certain number of degree

*/
```

- scale

```css
/* transform: scale(x, y) */

.box {
  transform: scale(1.5, 1.5);
}

/* 

- change the width and height of the element

*/
```

- skew

```css
/* transfrom: skew(x-angle, y-angle) */

.box {
  transform: skew(30deg, 45deg);
}

/* 

- Rotate the element a certain number of degree along the x and y axis

*/
```

- matrix

```css
/* transform: matrix(a, b, c, d, e, f) 

matrix(scaleX(), skewY(), skewX(), scaleY(), translateX(), translateY())

*/

.box {
  transform: matrix(1.5, 0, 0, 1.5, 0, 0);
}

/* 

- combines all the 2D transform methods into one

*/
```

## Position

- The four position properties are:

  - Static - default value

  ```css
  /* 
  
  - Place in the next available position
  - not affected by the top, bottom, left, and right properties
  
  */
  ```

  - Relative

  ```css
  /* 
  
  - Positioned "relative to itself"
  - Takes the static position, but add offset
  - The new positioning does not affect any other element. It is possible to move an element and leave a big hole where it would have been.
  - Relative positioned elements are often used as container blocks for other elements
  - Relative positioned elements are usually used to align images
  
  */
  ```

  - Absolute

  ```css
  /* 
  
  - Element is removed from the document flow and positioned relative to its nearest ancestor(or the root)
  - Other elements behave as if element doesnot exist
  - can end up on top of another element
  
  */
  ```

  - Fixed

  ```css
  /* 
  
  - Positioned relative to the browser window
  - will not move, even if the window is scrolled 
      - IE7 and IE8 support the fixed value only if a !DOCTYPE is specified
  - Think of popup boxes that won't go away !!
  - Or a navigation bar that is always visible on the top
  
  */
  ```

- Position are modified by the properties: top, right, bottom, left

- Position is a combination of top, right, bottom, left, z-index, transform, opacity, visibility

## z-index

- Multiple elements may be placed in the same position.

- z-index is a numeric value, positive or negative that dictates stacking order.
