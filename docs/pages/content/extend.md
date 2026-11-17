---
title: Extend the library
order: 6
---

# Extend the library

## Additional standard images

For the standard pop-ups, the Graphics input is a type definition combo box that also accepts undefined inputs. Because it is a string, you can pass the **name** of any standard image you add, as long as you follow these rules:

1. Image dimensions are **height 264 px** and **width 420 px**. Leave whitespace around the image border so no part is cut off.
2. The image must be a PNG or JPEG file.
3. Modify `Pop-Up.lvlib:Popup.lvclass:Convert Enum to Image.vi` and add a new case.

> The original design opened the image from a file. Hardcoding the image data constant into the case structure is much faster.

If you think an image belongs in the standard library, add it to the [Issues](https://github.com/danielcoons/tsc-pop-up/issues) page.

## Additional pop-up type

Create a new class with `PopUp.lvclass` as the parent. The required override is `Display.vi`, a protected method, so it can't be called from VIs outside the class hierarchy. Create an accessor VI or constructor to launch the dialog.

Design the dialog's front panel to behave the way your application needs. This lets you reuse the class functionality to apply a theme, set up the message and pass the information into the `Display.vi` override.
