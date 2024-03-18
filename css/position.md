<body style="font-family: serif"></body>

# Position

## 1 - Normal Flow (Flow Layout)

Why do we need to understand the flow layout before we get into the `position` property in css? - Because `position` is
closely related to it, and it can escape from the normal flow.

After reading the official document, I consider flow layout as the default (or original) rule of how elements will be
arranged, a.k.a. our familiar **block-and-inline layout**.

## 2 - Position

The `position` property defines how an element is positioned in the webpage.

### 2.1 - Static

* A static element will be positioned following the normal flow of the document, and will be influenced with the changes
  of the flow of the document.
* The `top`, `right`, `bottom`, `left`, and `z-index` properties will be no effect.
* Will scroll as we scroll.

### 2.2 - Relative

* A relative element also follows the normal flow.
* However, it can relocate (offset in the doc) itself to based on the values of `top`, `right`, `bottom`, and `left`.
  Note that the **offset** of a relative element will NOT affect other elements in the flow.
* Will scroll as we scroll.

### 2.3 - Absolute

* An absolute element does _**NOT**_ locate according to the normal flow! Therefore, absolute element itself will **_NOT_** influence other 'normal' elements in
  the page. In another word, other 'normal' elements will ignore the absolute.
* An absolute element is positioned relative to its closest non-static positioned ancestor (if any), which can be determined by the
  values of `top`, `right`, `bottom`, and `left`.
* Will scroll as we scroll.

### 2.4 - Fixed

* An absolute element does NOT locate according to the normal flow! It will also influence other 'normal' elements in
  the page.
* The element is positioned relative to its initial containing block, which is the viewport in the case of visual media.
  Its final position is determined by the values of `top`, `right`, `bottom`, and `left`.
* Will NOT scroll as we scroll.

### 2.5 - Sticky
* A relative element also follows the normal flow.
* Continue...