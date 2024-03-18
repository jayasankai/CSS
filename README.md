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


links:
https://developer.mozilla.org/en-US/docs/Web/CSS/Reference
https://developer.mozilla.org/en-US/docs/Web/CSS
https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Combinators
https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity
