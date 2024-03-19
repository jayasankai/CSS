# CSS Selectors
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

# CSS inherit
<pre>
#product-overview {
    color: inherit;
}
</pre>

# CSS combinator
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

# Usefull links:
https://developer.mozilla.org/en-US/docs/Web/CSS/Reference
https://developer.mozilla.org/en-US/docs/Web/CSS
https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Combinators
https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity

# display: block | inline | none
## Block-level elements 
are rendered as a block and hence take up all the available horizontal space. You can set margin-top and margin-bottom and two block-level elements will render in two different lines.

Some examples are: &lt;div&gt; , &lt;section&gt; , &lt;article&gt; , &lt;nav&gt;  but also &lt;h1&gt; , &lt;h2&gt;  etc and &lt;p&gt;.

## Inline elements 
on the other hand only take up the space they require to fit their content in. Hence two inline-elements will fit into the same line (as long as the combined content doesn't take up the entire space in which case a line break would be added).

They also use the box-model you learned about but margin-top  and margin-bottom  have no effect on the element. padding-top  and padding-bottom  also have a different effect. They don't push the adjacent content away but they will do so with the element border. You can read more about that behavior in the following article: https://hacks.mozilla.org/2015/03/understanding-inline-box-model/

Additionally, setting a width  or height  on an inline element also has no effect. The width and height is auto to take as much space as required by the content.

Logically, this makes sense since you don't want your inline elements to destroy your multi-line text-layout. If you want to do so or need both block-level and inline behavior, you can set display: inline-block  to merge behaviors.

Some example elements are: &lt;a&gt; , &lt;span&gt; , &lt;img&gt; 

## display: none vs visibility: hidden
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

----
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

# Pseudo classes and Pseudo elements
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

# Group rules
<pre>
.main-nav__item a:hover,
.main-nav__item a:active {
    color: white;
}
</pre>