# Positioning 
There are many ways to position an element in HTML-CSS. In this article I'm going to talk about positioning the elements using the *inline-block*, *float* and *position* properties.

## Inline Block
Inline block is a display property but it can be used align elements horizontally since it only takes the width of the content.

```
  <!-- HTML -->
  <header>..........</header>
  <aside>.........</aside><!--
  --><section>.........</section>
  <footer>............</footer>

  <!-- CSS -->
  header, aside, section, footer {
    background: green;
    padding: 50px;
    box-sizing: border-box;
  }
  section, aside {
    display: inline-block;
    margin: 32px 1.5%;
  }
  aside {
    width: 30%;
  }
  section {
    width: 63%;
  }
```
In this example the *aside* and *section* element are positioned on the same line horizontally to make a two column layout using the inline block and the box-sizing property of *border-box* to manage the paddings.
Normally, there is a small space between the elements positioned using *border-box* and can be removed using the comment tag as shown above.
## Float
The *Float* property can be used to make multiple columns by aligning the elements to the side. The float comes with three different values: `left, right, and none`. It was first introduced to wrap text around an image but later on was used by developers to create columns.
 Since the display property of the floated elements are changed and and are removed from the natural flow of the page, certain fixes were introduced . The widely and most effective used fix is called the *clear-fix* technique .
 ```

  <!-- HTML -->
  <header>..........</header>
  <div class="parent">
    <aside>.........</aside>
    <section>.........</section>
  </div>
  <footer>............</footer>

  <!-- CSS -->

  header, aside, section, footer {
    padding: 50px;
    background: green;
    box-sizing: border-box;
  }
  .parent {
    background-color: orange;
  }
  aside {
    float: left;
    width: 30%;
    margin: 32px 1.5%;
  }
  section {
    float: right;
    width: 63%;
    margin: 32px 1.5%;
  }
  .parent:before, .parent:after {
  content: "";
    display: table;
  }
  .parent:after {
    clear: both;
  }
```
In the above example, The *aside* and *section* elements are floated to the left and right side of the page respectively . In order to contain these floats, the clear-fix technique is applied to the parent element i.e the `div<class= "parent"`. With the parent targeted and
` .parent:before, .parent:after {
  content: "";
    display: table;
  }
  .parent:after {
    clear: both;
  }` applied, the floats are contained.
  ## Uniquely Positioning using the *position* property
  Elements can be positioned uniquely using the *position* properties like *static, relative, absolute* and *fixed* with the *box-offset* values of *top, right, bottom* and *left*. This property changes the display property to *inline-block*.
  ### Position: Static
  The static position is the default position of an element. it doesn't accept any box-offset properties
  ```
  div.static {  
position:  static;    
}
```
### Position: Relative
An element with  `position: relative;`  is positioned relative to its normal position.

Setting the box-offset properties of a relatively-positioned element will cause it to be adjusted away from its normal position. Other content will not be adjusted to fit into any gap left by the element.
```
div.relative {  
position:  relative;  
left:  30px;    
}
```
### Position: Absolute
An element with `position: absolute;` is positioned relative to the nearest positioned parent.
```div.absolute {  
position:  absolute;  
top:  80px;  
right:  0;  
width:  200px;  
height:  100px;  
border:  3px solid #73AD21;  
}
```
### Position: Fixed
An element with `position: fixed;` is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled. The nox-offset properties are used to position the element.
```
div.fixed {  
position:  fixed;  
bottom:  0;  
right:  0;  
width:  300px;  
border:  3px solid #73AD21;  
}
```



