# Using Material Symbols in Web

## 1 - What's Material Symbols
Material Symbols are Google's **icons**, consolidating over 2,500 glyphs in a single font file with a wide range of design 
**variants**. Symbols are available in three styles and four adjustable variable font axes (fill, weight, grade, and optical size).

## 2 - How to Use them?

### 2.1 - Static Icon Font
Developers can access icon resources by including the following code into the html file. The below snippet includes a 
default configuration for each axis, with weight at 400, optical size at 48, grade at 0 and fill (also 0).
```html
<link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined" rel="stylesheet" />
```
Through [Google website](https://fonts.google.com/icons), we can get customized static icon font code using the 
[Fonts CSS API](https://developers.google.com/fonts/docs/css2#forming_api_urls) to configure different axes values. For
example, the following code represents a configuration for each axis, with weight at 200, optical size at 24, grade at
200 and fill (also 0):
```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@24,200,0,200" />
```
Then, we will use **code point** or **name** of the icon to tell the browser which one we want it to show:
```html
<!--thumb_up is the icon-->
<span class="material-symbols-outlined">thumb_up</span>

<!--e8dc is the code point of the same icon-->
<span class="material-symbols-outlined">e8dc</span>
```

### 2.2 - Variable Icon Font
If you're animating icons via CSS, or want finer control over icon features, use the Google Symbols variable font. Using 
ranges, in the format `number..number`, we can load the entire variable font. Example:
```html
<!-- loads the entire Variable Font -->
<link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200" rel="stylesheet" />

<!-- thin outlined icons -->
<div style="font-variation-settings: 'FILL' 0, 'wght' 100, 'GRAD' 0, 'opsz' 48;">
  <span class="material-symbols-outlined">search</span>
  <span class="material-symbols-outlined">home</span>
  <span class="material-symbols-outlined">settings</span>
  <span class="material-symbols-outlined">favorite</span>
</div>

<!-- thick filled icons -->
<div style="font-variation-settings: 'FILL' 1, 'wght' 700, 'GRAD' 0, 'opsz' 48;">
  <span class="material-symbols-outlined">search</span>
  <span class="material-symbols-outlined">home</span>
  <span class="material-symbols-outlined">settings</span>
  <span class="material-symbols-outlined">favorite</span>
</div>
```

Or even animate them!

```html
<!-- loads the entire Variable Font -->
<link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200" rel="stylesheet" />

<div class="pulse">
  <span class="material-symbols-outlined">search</span>
  <span class="material-symbols-outlined">home</span>
  <span class="material-symbols-outlined">settings</span>
  <span class="material-symbols-outlined">favorite</span>
</div>
```
```css
.pulse {
  animation: pulse 3s infinite;
}

@keyframes pulse {
  0% {
    font-variation-settings: 'wght' 100;
  }
  50% {
    font-variation-settings: 'wght' 700;
  }
  100% {
    font-variation-settings: 'wght' 100;
  }
}
```


##### For more detailed information, [visit](https://developers.google.com/fonts/docs/material_symbols#using_material_symbols).