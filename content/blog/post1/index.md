---
title: Blog Post with Inline Images
subtitle: "Blog post subtitle :zap:"
summary: These are my personal dotfiles for the i3 window manager.
date: 2024-08-24
cardimage: photo1_card.jpeg
featureimage: photo1.jpeg
caption: Image caption
authors:
  - Christian: author.jpeg
---
Use the shortcode "figArray" to add images to your blog post. Add your images to a subfolder. Call the figArray shortcode using the following syntax:

```
{{</* figArray subfolder="<subfoldername>" figCaption="Some caption" numCols=2 */>}}
```
Both "figCaption" and "numCols" are optional. The shortcode will try to guess the best number of columns to use for the array of figures if "numCols" is not passed.
You will need one subfolder containing images per call to the shortcode. The image files need to be one of the following types: png, jpg, jpeg or webp.

{{< figArray subfolder="images" figCaption="A nice figure caption :wave:" >}}
These dotfiles come with Catppuccin & Nordic theme.