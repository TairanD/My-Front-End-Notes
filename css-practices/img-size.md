# How to adjust image size?

---
- Directly specify the height and width of the image, which will cause the image **out of shape**.
  - use `object-fit` to further modify
---
- Set the container of the `<img>` tag `overflow: hidden` if you do not care about the **completeness** of the image.
---
- Set the image as your container `<div>`'s `background-image`
  - use `background-size` & `background-position` to further modify
---
- Use percentage to set the height or width of the image, and set the other one as `auto`. 
  - In this way, the height/width of the 
  image will adjust automatically based on changes to its width/height, preserving the original proportions.
  - But may **not** fill the container
---
- Use percentage to set the height or width of the image, and without set the other one as `auto`. 
  - This means that the height of the image will not adjust automatically to maintain the original aspect ratio, but will
instead adjust based on changes to the parent element's width. This may result in distortion of the image as the aspect ratio is not preserved.