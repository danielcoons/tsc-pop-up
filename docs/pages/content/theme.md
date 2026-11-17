---
title: Theme
order: 5
---

# Theme

Define a **theme** for the coloration of the pop-ups in your application. Open the theme definer from the LabVIEW Tools menu:

> Tools → TSC → Theme Definer UI...

Choose the color scheme and see a live preview with the standard hourglass image. When you are done, save the theme (`*.style` file) with the **download** button or `Ctrl+S`. The data is saved as a flattened XML file using a LabVIEW class.

![Theme Definer UI](/assets/pop-up/images/Theme%20Definer.png)

Load the theme at application initialization by calling `Theme.lvclass:Load Theme.vi`.
