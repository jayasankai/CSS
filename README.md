# CSS: Cascading Style Sheets

## CSS Selectors
1. Elements
```css
h1 {
    color: red;
}
```

2. Classes
```css
.class-name {
    color: red;
}
```

4. ID
```css
#element_id {
    color: red;
}
```

5. Attributes
```css
[disabled] {
    color: red;
}
```

6. Universal
```css
* {
    color: red;
}
```

7. Class selector : Select by class name
> [!NOTE]
> Select all items having same class name. More reusable

Ex01: by class specified</br>
```html
<nav>
    <a href="#intro" class="active">Intro</a>
    <a href="#outro" class="active">Outro</a>
</nav>
```
```css
a.active {
    color: #521751;
}
```

Ex02: parent_class and child class </br>
```css
.plan--highlighted .plan__price {
    color: #0e4f1f;
}
```

8. ID selector: Select by ID
> [!NOTE]
> Select item with specific id. Not recomended as IDs have other usages

```html
<nav>
    <a href="#intro" id="link_1">Intro</a>
    <a href="#outro" id="link_2">Outro</a>
</nav>
```
```css
a#link_1 {
    color: #521751;
}
```

9. Selecting the opposite by Pseudo class :not()
> [!NOTE]
> Some browers may not support this features </br>
> https://developer.mozilla.org/en-US/docs/Web/CSS/:not
> https://caniuse.com/

```css
a.active {
    color: #521751;
}

a:not(.active) {
    color: blue;
}
```

## CSS inherit
```css
#product-overview {
    color: inherit;
}
```

## CSS combinator
1. Adjacent Sibling : color the paragraph in RED in every &lt;p&gt; adjacent to &lt;h2&gt; tag.
```css
h2 + p {
    color: red;
}
```

2. General Sibling: color the paragraph in RED in every &lt;p&gt; in same level of &lt;h2&gt; tag.
```css
h2 ~ p {
    color: red;
}
```

3. Child : color the paragraph in RED in every child &lt;p&gt; of &lt;div&gt;
```css
div &gt; p {
    color: red;
}
```

4. Descendent : color the paragraph in RED in every decendent &lt;p&gt; of &lt;div&gt;
```css
div p {
    color: red;
}
```

## Usefull links:
https://developer.mozilla.org/en-US/docs/Web/CSS/Reference</br>
https://developer.mozilla.org/en-US/docs/Web/CSS</br>
https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Combinators</br>
https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity</br>

## display: block | inline | none
### Block-level elements 
are rendered as a block and hence take up all the available horizontal space. You can set margin-top and margin-bottom and two block-level elements will render in two different lines.

Some examples are: &lt;div&gt; , &lt;section&gt; , &lt;article&gt; , &lt;nav&gt;  but also &lt;h1&gt; , &lt;h2&gt;  etc and &lt;p&gt;.

### Inline elements 
on the other hand only take up the space they require to fit their content in. Hence two inline-elements will fit into the same line (as long as the combined content doesn't take up the entire space in which case a line break would be added).

They also use the box-model you learned about but margin-top  and margin-bottom  have no effect on the element. padding-top  and padding-bottom  also have a different effect. They don't push the adjacent content away but they will do so with the element border. You can read more about that behavior in the following article: https://hacks.mozilla.org/2015/03/understanding-inline-box-model/

Additionally, setting a width  or height  on an inline element also has no effect. The width and height is auto to take as much space as required by the content.

Logically, this makes sense since you don't want your inline elements to destroy your multi-line text-layout. If you want to do so or need both block-level and inline behavior, you can set display: inline-block  to merge behaviors.

Some example elements are: &lt;a&gt; , &lt;span&gt; , &lt;img&gt; 

### display: none vs visibility: hidden
```css
.box-1 {
    display: none;
}
 
.box-2 {
    display: inline-block;
}
```
Will render: </br>
x
</br>
where x  has the class box-2 . The first element just isn't displayed. It's still part of the DOM though, you can still access it via JavaScript for example.

--
```css
.box-1 {
    visibility: hidden;
}
 
.box-2 {
    display: inline-block;
}
```
Will render:</br>
_x
</br>
where _  simply is an empty spot and x  has the class box-2. The element is only invisible, it's not removed from the document flow and of course also not from the DOM.

## Pseudo classes and Pseudo elements
Pseudo classes : defins a special state of an element
```css
.main-nav__item a:hover {
    color: white;
}
```

Pseudo elements: defines specific part of an element
```css
p::first-letter {
    color: red;
    font-size: 20px;
}
```

Select first item of list of divs
```css
.main-header div:first-of-type {
    /* display: none; */
    visibility: hidden;
}
```

## Group rules
```css
.main-nav__item a:hover,
.main-nav__item a:active {
    color: white;
}
```

## Changing a link to button
```css
.main-nav__item a {
    text-decoration: none;
    color: #0e4f1f;
    font-weight: bold;
    padding: 3px 0;
}

.main-nav__item--cta a{
    color: white;
    background: #ff1b68;
    padding: 8px 16px;
    border-radius: 8px;
}

.main-nav__item--cta a:hover,
.main-nav__item--cta a:active {
    color: #ff1b68;
    background: white;
    border-bottom: none
}
```

```html
<li class="main-nav__item main-nav__item--cta">
    <a href="start-hosting/index.html">Start Hosting</a>
</li>
```

## Image reference in CSS
```css
#product-overview {
    background: <b>url("freedom.jpg");</b>
    width: 100%;
    height: 528px;
    padding: 10px;
}
```

## Do not use <b>!important</b>
```css
.main-section {
    height: 800px;
    border: 1px solid #ccc !important;
    padding: 16px;
}
```

## Add a drop shadow to item
```css
box-shadow: 2px 2px 2px 2px rgba(0, 0, 0, .5);
```

> [!NOTE]
> box-shadow: x-axis, y-axis, blurriness, spread
> rgba: red, green, blue with alpha channel

## border-radius : Rounded conders to box
```css
box-shadow: 2px 2px 2px 2px rgba(0, 0, 0, .5);
border-radius: 8px;
```

## Remove list Style
```css
list-style: none;
```

## Improving action button
```css
.plan--button {
    background: #0e4f1f;
    color: white;
    font: inherit;
    border: 1.5px solid #0e4f1f;
    padding: 8px;
    border-radius: 8px;
    font-weight: bold;
    cursor: pointer;
}

.plan--button:hover,
.plan--button:active {
    background: white;
    color: #0e4f1f;
}
```

Remove outline of the button
```css
.plan--button:focus {
    outline: none;
}
```

## Adding a circled div : border-radius: 50% and margin: auto
```css
.key-feature__image {
    background-color: #ffcede;
    width: 128px;
    height: 128px;
    border: 2px solid #424242;
    border-radius: 50%;
    margin: auto;
}
```

## float and clear_both : not recomend to use often
> [!NOTE]
> Float will align an item to specified direction. However, that will mess the positioning of other elements.
> To fix that, you may need to add new empty DIV with class of clear_both.
> link : https://developer.mozilla.org/en-US/docs/Web/CSS/float 

```css
.middle_section {
    background: rgba(234, 252, 237, 0.95);
    float: right;
}
```
To fix:
```html
<section> content1 </section>
<section class="middle_section"> content2 </section>
<div class="clearfix"></div>
<section> content3 </section>
```
```css
.clearfix {
    clear: both;
}
```

## Navigation bar : Element position and moving around the 'view port'
```html
<div class="parent">
    <div class="child-1">Navigation Bar</div>
    <div class="child-2">Background Image</div>
    <div class="child-3">Features</div>
</div>
```
```css
.parent .child-1 {
    position: fixed;
    width: 100%;
    top: 0;
    left: 0;
    margin: 0;
    box-sizing: border-box;
}
```

## Positioning elements
There are five different position values:

1. static
2. relative
3. fixed
4. absolute
5. sticky - some browers not supoort

> [!NOTE]
> Elements are then positioned using the top, bottom, left, and right properties. However, these properties will not work unless the position property is set first. They also work differently depending on the position value.

### position-fixed and Z-Index to possition items relative to view port.
is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled. The top, right, bottom, and left properties are used to position the element.

A fixed element does not leave a gap in the page where it would normally have been located.

Notice the fixed element in the lower-right corner of the page.

```html
<body>
    <div class="background"></div>
    <header class="main-header">
        <div>Test</div>
    </header>
</body>
```
```css
.background {
    background: url("../images/plans-background.jpg");
    width: 100%;
    height: 100%;
    position: fixed;
    z-index: -1;
}
```

### position-relative:
The element is positioned according to the normal flow of the document, and then offset relative to itself based on the values of top, right, bottom, and left. </br>
The offset does not affect the position of any other elements; thus, the space given for the element in the page layout is the same as if position were static.

### position-absolute:
Elements that are relatively positioned remain in the normal flow of the document. </br>
In contrast, an element that is absolutely positioned is taken out of the flow; thus, other elements are positioned as if it did not exist. </br>
The absolutely positioned element is positioned relative to its nearest positioned ancestor (i.e., the nearest ancestor that is not static). </br>
If a positioned ancestor doesn't exist, it is positioned relative to the ICB (initial containing block), which is the containing block of the document's root element.

> [!NOTE]
> Absolute positioned elements are removed from the normal flow, and can overlap elements.

```html
<section class="package" id="plus">
    <h1 class="package__title">Our PLUS Plan</h1>
    <h2 class="package__badge">RECOMENDED</h2>
    <h2 class="package__subtitle">The most popular choice of our customers.</h2>
</section>
```

```css
.package {
    width: 80%;
    margin: 16px 0;
    border: 4px solid #0e4f1f;
    border-left: none;
    position: relative;
}
.package__badge {
    position: absolute;
    top: 0;
    right: 0;
    margin: 20px;
    font-size: 12px;
    color: white;
    background: #ff5454;
    padding: 8px;
}
```

### position-sticky:
Sticky positioning can be thought of as a hybrid of relative and fixed positioning when its nearest scrolling ancestor is the viewport. A stickily positioned element is treated as relatively positioned until it crosses a specified threshold, at which point it is treated as fixed until it reaches the boundary of its parent. For example:

```CSS
#one {
  position: sticky;
  top: 10px; <-- distance to view port from the element
}
```

The above CSS rule would position the element with id one relatively until the viewport was scrolled such that the element would be less than 10 pixels from the top. Beyond that threshold, the element would be fixed to 10 pixels from the top.

> [!NOTE]
> You must specify a threshold with at least one of top, right, bottom, or left for sticky positioning to behave as expected. Otherwise, it will be indistinguishable from relative positioning.

### Z index and Stacking
ref : https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_positioned_layout/Understanding_z-index/Stacking_context


## Image background and positioning
1. repeat image of 100px width
```css 
    /* background: url("freedom.jpg"); */
    background-image: url("freedom.jpg");
    background-size: 100px;
```
2. to keep the size (width) and no repeat
```css
    background-image: url("freedom.jpg");
    background-size: 100px;
    background-repeat: no-repeat;
```

3. to repeat in x axis or y axis
```css
    background-image: url("freedom.jpg");
    background-size: 100px;
    background-repeat: repeat-x;
```
```css
    background-image: url("freedom.jpg");
    background-size: 100px;
    background-repeat: repeat-y;
```

4. No repeat with corrrect width and height : image will not keep the default aspect ratio
```css
    background-image: url("freedom.jpg");
    background-size: 300px 100px;
    background-repeat: no-repeat;
```

5. No repeat with corrrect width and height in precentage value 
```css
    background-image: url("freedom.jpg");
    background-size: 50%;
    background-repeat: no-repeat;
```

6. No repeat with corrrect width and height in precentage value and auto : may not occupy the full container
```css
    background-image: url("freedom.jpg");
    background-size: auto 100%;
    background-repeat: no-repeat;
```

7. cover the container by image : may crop the image, resized image by auto wrt container
```css
    background-image: url("freedom.jpg");
    background-size: cover;
    background-repeat: no-repeat;
```

7. contains: make sure full image fit in to the container
```css
    background-image: url("freedom.jpg");
    background-size: contain;
    background-repeat: no-repeat;
```