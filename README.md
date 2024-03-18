# CSS Selectors
1. Elements
h1 {
    color: red;
}

2. Classes
.class-name {
    color: red;
}

4. ID
#element_id {
    color: red;
}

5. Attributes
[disabled] {
    color: red;
}

6. Universal
* {
    color: red;
}

# CSS inherit
#product-overview {
    color: inherit;
}

# CSS combinator
1. Adjacent Sibling : color the paragraph in RED in every &lt;p&gt; adjacent to &lt;h2&gt; tag.
h2 + p {
    color: red;
}

2. General Sibling: color the paragraph in RED in every &lt;p&gt; in same level of &lt;h2&gt; tag.
h2 ~ p {
    color: red;
}

3. Child : color the paragraph in RED in every child &lt;p&gt; of &lt;div&gt;
div &gt; p {
    color: red;
}

4. Descendent : color the paragraph in RED in every decendent &lt;p&gt; of &lt;div&gt;
div p {
    color: red;
}


# Usefull links:
https://developer.mozilla.org/en-US/docs/Web/CSS/Reference
https://developer.mozilla.org/en-US/docs/Web/CSS
https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Combinators
https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity


# display: block | inline | none

# display: none vs visibility: hidden
.box-1 {
    display: none;
}
 
.box-2 {
    display: inline-block;
}
Will render:
x
where x  has the class box-2 . The first element just isn't displayed. It's still part of the DOM though, you can still access it via JavaScript for example.

----
.box-1 {
    visibility: hidden;
}
 
.box-2 {
    display: inline-block;
}

Will render:
_x
where _  simply is an empty spot and x  has the class box-2. The element is only invisible, it's not removed from the document flow and of course also not from the DOM.

# Block-level elements 
are rendered as a block and hence take up all the available horizontal space. You can set margin-top and margin-bottom and two block-level elements will render in two different lines.

Some examples are: <div> , <section> , <article> , <nav>  but also <h1> , <h2>  etc and <p> .

# Inline elements 
on the other hand only take up the space they require to fit their content in. Hence two inline-elements will fit into the same line (as long as the combined content doesn't take up the entire space in which case a line break would be added).

They also use the box-model you learned about but margin-top  and margin-bottom  have no effect on the element. padding-top  and padding-bottom  also have a different effect. They don't push the adjacent content away but they will do so with the element border. You can read more about that behavior in the following article: https://hacks.mozilla.org/2015/03/understanding-inline-box-model/

Additionally, setting a width  or height  on an inline element also has no effect. The width and height is auto to take as much space as required by the content.

Logically, this makes sense since you don't want your inline elements to destroy your multi-line text-layout. If you want to do so or need both block-level and inline behavior, you can set display: inline-block  to merge behaviors.

Some example elements are: <a> , <span> , <img> 

