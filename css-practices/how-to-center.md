<body style="font-family: serif"></body>

# How to Center Elements?

## Approach 1: Using margin property
In CSS, `margin: auto;` will help us put one element in the horizontal center of a box. The left and right margin will be distributed to the left available space automatically and evenly in this way.

**Restrains**: 
- Only suitable for horizontal direction because in the vertical direction, the upper and lower margin can not be distributed to the left available space automatically like what we do in the horizontal direction.
- Only suitable for one single element.

**Advantage**:
- Less code, we only need to add one property to the target element.

## Approach 2: Using flexbox