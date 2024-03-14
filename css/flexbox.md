<body style="font-family: serif"></body>

# The flexible box layout module - Flexbox

## 1 - Why Flexbox

Responsive websites that can adopt various sizes and devices are always the goal of front-end developer. Flexbox offers
such a flexible layout for us to creat adaptive webpages.

## 2 - Container and Items

They are two important concepts in the flexbox.

### 2.1 - The flex container

A flex container refers to the element applying the flex layout. We can define an element as a flex container by
add `display: flex` style.

*Note: flexbox will NOT influence normal flow! This flexibility makes it a powerful tool to create responsive web pages.

### 2.2 - The flex item

Flex items are the child elements of a flex container. They can be arranged in various flexible ways, according to the
property of their container.

## 3 - The Two Axes of Flexbox

Flexbox requires us arrange items based on two axes of the flex container - the main axes, and the cross axes. The main
axis is the primary direction of the Flex container, while the cross axis is perpendicular to the main axis.

### 3.1 - The main axes

We can use `flex-direction` property to define the main axes. It has four value:

- `flex-direction: row` (**default** if the `flex-direction` is not declared in the container)
- `flex-direction: row-reverse`
- `flex-direction: column`
- `flex-direction: column-reverse`

Items will be set horizontally (right-to-left) when we choose `row` and `row-reverse`.

While items will be set vertically (bottom-to-top) when we choose `column` and `column-reverse`.

### 3.2 - The cross axes

The cross axes is confirmed automatically (perpendicular to the main axis) after we define the `flex-direction`
property.

### Note*

It is important to understand the concepts above as they determine the direction by which we arrange our items.

## 4 - Flex Container Properties

We control the layout of flexbox by using properties. Let's firstly look at the container properties.

### 4.1 - justify-content

`justify-content` is a property set to the flex container, which is used to define how we can align items on the main
axis, and determines how extra space is distributed between and around flex items in the container. Following optional
values are common-used for us to choose:

- `start`: Items are packed towards the **start** of the main axis.
- `center`: Items are **centered** along the main axis.
- `space-evenly`: Items are **evenly** distributed along the main axis with the first item at the beginning, the last
  item at the end.
- `space-evenly`: Items are **evenly** distributed along the main axis with equal space around them.

### 4.2 - align-items

Similar to the function of `justify-content`, `align-items` is also used to align items, but on the cross axis. It also
has similar values to `justify-content`:

- `start`: Items are packed towards the **start** of the cross axis.
- `center`: Items are **centered** along the cross axis.
- `space-evenly`: Items are **evenly** distributed along the cross axis with the first item at the beginning, the last
  item at the end.
- `space-evenly`: Items are **evenly** distributed along the cross axis with equal space around them.

## 5 - Flex Item Properties

Properties `flex-grow`, `flex-shrink`, and `flex-basis` define the behaviors of items in terms of available space. 
### 5.1 - flex-grow
This property defines the growth factor of a flex item when there is available space along the main axis. The default value is 0, meaning the item won't grow.
### 5.2 - flex-shrink
This property defines the shrink factor of a flex item when there is limited space along the main axis. The default value is 1, meaning the item can shrink.
### 5.3 - flex-basis
This property defines the initial size of a flex item along the main axis before remaining space is distributed. It can be set to a fixed length, percentage, or the keyword auto.

### 5.3 - flex
Yet, the shorthand value for the `flex` property is more frequently used. The flex shorthand allows you to set the three values in this order — `flex-grow`, `flex-shrink`, `flex-basis`.
