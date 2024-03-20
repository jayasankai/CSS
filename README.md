# CSS: Cascading Style Sheets

## CSS Selectors
1. Elements
<pre>
h1 {
    color: red;
}
</pre>

2. Classes
<pre>
.class-name {
    color: red;
}
</pre>

4. ID
<pre>
#element_id {
    color: red;
}
</pre>

5. Attributes
<pre>
[disabled] {
    color: red;
}
</pre>

6. Universal
<pre>
* {
    color: red;
}
</pre>

7. Class selector : Select by class name
Note: Select all items having same class name. More reusable</br>
Ex01: by class specified</br>
<pre>
--html
&lt;nav&gt;
    &lt;a href="#intro" class="active"&gt;Intro&lt;/a&gt;
    &lt;a href="#outro" class="active"&gt;Outro&lt;/a&gt;
&lt;/nav&gt;

--css
a.active {
    color: #521751;
}
</pre>

Ex02: parent_class and child class </br>
<pre>
.plan--highlighted .plan__price {
    color: #0e4f1f;
}
</pre>

8. ID selector: Select by ID
Note: Select item with specific id. Not recomended as IDs have other usages
<pre>
--html
&lt;nav&gt;
    &lt;a href="#intro" id="link_1"&gt;Intro&lt;/a&gt;
    &lt;a href="#outro" id="link_2"&gt;Outro&lt;/a&gt;
&lt;/nav&gt;

--css
a#link_1 {
    color: #521751;
}
</pre>

9. Selecting the opposite by Pseudo class :not()
Note: Some browers may not support this features
https://developer.mozilla.org/en-US/docs/Web/CSS/:not</br>
https://caniuse.com/</br>
<pre>
a.active {
    color: #521751;
}

a:not(.active) {
    color: blue;
}
</pre>

## CSS inherit
<pre>
#product-overview {
    color: inherit;
}
</pre>

## CSS combinator
1. Adjacent Sibling : color the paragraph in RED in every &lt;p&gt; adjacent to &lt;h2&gt; tag.
<pre>
h2 + p {
    color: red;
}
</pre>

2. General Sibling: color the paragraph in RED in every &lt;p&gt; in same level of &lt;h2&gt; tag.
<pre>
h2 ~ p {
    color: red;
}
</pre>

3. Child : color the paragraph in RED in every child &lt;p&gt; of &lt;div&gt;
<pre>
div &gt; p {
    color: red;
}
</pre>

4. Descendent : color the paragraph in RED in every decendent &lt;p&gt; of &lt;div&gt;
<pre>
div p {
    color: red;
}
</pre>

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
<pre>
.box-1 {
    display: none;
}
 
.box-2 {
    display: inline-block;
}
</pre>
Will render: </br>
x
</br>
where x  has the class box-2 . The first element just isn't displayed. It's still part of the DOM though, you can still access it via JavaScript for example.

--
<pre>
.box-1 {
    visibility: hidden;
}
 
.box-2 {
    display: inline-block;
}
</pre>
Will render:</br>
_x
</br>
where _  simply is an empty spot and x  has the class box-2. The element is only invisible, it's not removed from the document flow and of course also not from the DOM.

## Pseudo classes and Pseudo elements
Pseudo classes : defins a special state of an element
<pre>
.main-nav__item a:hover {
    color: white;
}
</pre>

Pseudo elements: defines specific part of an element
<pre>
p::first-letter {
    color: red;
    font-size: 20px;
}
</pre>

Select first item of list of divs
<pre>
.main-header div:first-of-type {
    /* display: none; */
    visibility: hidden;
}
</pre>

## Group rules
<pre>
.main-nav__item a:hover,
.main-nav__item a:active {
    color: white;
}
</pre>

## Changing a link to button
<pre>
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

--html
&lt;li class="main-nav__item main-nav__item--cta"&gt;
    &lt;a href="start-hosting/index.html"&gt;Start Hosting&lt;/a&gt;
&lt;/li&gt;
</pre>

## Image reference in CSS
<pre>
#product-overview {
    background: <b>url("freedom.jpg");</b>
    width: 100%;
    height: 528px;
    padding: 10px;
}
</pre>

## Do not use <b>!important</b>
<pre>
.main-section {
    height: 800px;
    border: 1px solid #ccc !important;
    padding: 16px;
}
</pre>

## Add a drop shadow to item
--css
<pre>
box-shadow: 2px 2px 2px 2px rgba(0, 0, 0, .5);
</pre>

Note: </br>
    box-shadow: x-axis, y-axis, blurriness, spread </br>
    rgba: red, green, blue with alpha channel</br>

## border-radius : Rounded conders to box
<pre>
box-shadow: 2px 2px 2px 2px rgba(0, 0, 0, .5);
border-radius: 8px;
</pre>

## Remove list Style
<pre>
list-style: none;
</pre>

## Improving action button
<pre>
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
</pre>

Remove outline of the button
<pre>
.plan--button:focus {
    outline: none;
}
</pre>

## Adding a circled div : border-radius: 50% and margin: auto
<pre>
.key-feature__image {
    background-color: #ffcede;
    width: 128px;
    height: 128px;
    border: 2px solid #424242;
    border-radius: 50%;
    margin: auto;
}
</pre>

## float and clear_both
Float will align an item to specified direction. However, that will mess the positioning of other elements.</br>
To fix that, you may need to add new empty DIV with class of clear_both.
<pre>
.middle_section {
    background: rgba(234, 252, 237, 0.95);
    float: right;
}
</pre>
To fix:
<pre>
--html
<pre>
&lt;section&gt; content1 &lt;/section&gt;
&lt;section class="middle_section"&gt; content2 &lt;/section&gt;
&lt;div class="clearfix"&gt;&lt;/div&gt;
&lt;section&gt; content3 &lt;/section&gt;
</pre>
<pre>
.clearfix {
    clear: both;
}
</pre>

## 