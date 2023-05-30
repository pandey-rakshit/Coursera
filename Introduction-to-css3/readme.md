# Introduction to CSS3 by University of Michigan

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
