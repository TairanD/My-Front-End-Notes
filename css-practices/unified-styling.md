# Unified Styling of Icons Through Container-Level Settings
In the front end development, we can unify all styles of internal elements through set their container's styling, which
can be achieved because the child elements will inherit their parent's styles by default.
This method can make our code more concise, and easy to maintain. For example:

###Icon Fonts Collection
Suppose you have a collection of icons using an icon font like Font Awesome. You can place all icons within a `<div>` 
container and set the font-size property on that container to uniformly adjust the size of all icons without the need to 
individually adjust each icon's size.
```html
<div class="icon-container" style="font-size: 24px">
  <i class="fas fa-home"></i>
  <i class="fas fa-user"></i>
  <i class="fas fa-envelope"></i>
  <!-- More icons... -->
</div>
```
