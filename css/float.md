# float

## 1 - What's float
float is a CSS property. It is used to be positioned to the left or right side of its container instead of sticking to 
its default position within the document flow. This alteration in positioning changes how surrounding content behaves.

For example, if you float an image to the left, text or other elements following it will wrap around its right side. 
Similarly, if you float an element to the right, content will flow around its left side.

In essence, float enables elements to be taken out of the normal flow of the document and placed to one side of their 
containing block, influencing how nearby content is displayed. This property has been historically used for creating 
layouts where content wraps around specific elements, such as images or sidebars.

## 2 - Characteristics
- **Floated elements are taken out of the normal document flow. Other elements will ignore floated elements and flow around them.**
- Floated elements will align themselves to the left or right of their containing block, depending on the specified float value.

## 3 - Clearing Floats: Using Clearfix
When floating elements, it's essential to ensure that subsequent content doesn't wrap around them unexpectedly. 
You can clear floats using the clear property.
```css
.clearfix::after {
    content: "";
    display: table;
    clear: both;
}
```
This is a common technique to ensure that an element (like a container) wraps around floated elements properly. 
Apply the clearfix class to the **parent element containing floated children**.
