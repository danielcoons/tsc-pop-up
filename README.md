# tsc-pop-up
Find the VIP here: [![Image](https://www.vipm.io/package/tsc_lib_tsc_pop_up/badge.svg?metric=installs)](https://www.vipm.io/package/tsc_lib_tsc_pop_up/) [![Image](https://www.vipm.io/package/tsc_lib_tsc_pop_up/badge.svg?metric=stars)](https://www.vipm.io/package/tsc_lib_tsc_pop_up/)

The TSC pop-up library gives LabVIEW developers the ability to create customized, beautiful pop-up dialogs to users to give instructions, warnings, or to get their attention!

`Standard`  image pop-ups provide a consistent size and set of selected images

`PNG` image pop-ups allow for developer to define a custom image to load while running and give the ability to customize placement of image and size of message text box

`Plain` simple dialog for one, two, or three button message with a defined **Title**

See Example VIs for usage of a few of the different types of pop ups.

#### ! Double Click the Pop-Up for it to go Semi-Transparent !

## Pop-Up Types:
In general, each included pop-up library type has the following options:
- One Button - dialog box with a single button option  
<img src="./assets/images/one-button.png" alt = "One Button" width="180"/>
- Two Button - dialog with choices of `Y` or `N` option  
<img src="./assets/images/two-button.png" alt = "Two Button" width="180"/>
- Timeout - display message for defined time  
<img src="./assets/images/timeout.png" alt = "Timeout" width="180"/>
- Timeout One Button - display message until alloted time or toggle of single button  
<img src="./assets/images/timeout-one.png" alt = "Timeout - One Button" width="180"/>
- Timeout Two Button - display message until alloted time or choice of `Y` or `N` option (`N` is selected as default if time elapsed)  
<img src="./assets/images/timeout-two.png" alt = "Timeout - Two Button" width="180"/>
- Input (DBL) - input DBL value  
<img src="./assets/images/dbl-input.png" alt = "DBL Input" width="180"/>
- Input (I32)  - input an I32 value  
<img src="./assets/images/i32-input.png" alt = "I32 Input" width="180"/>
- Input (String) - input a String value  
<img src="./assets/images/str-input.png" alt = "String Input" width="180"/>

>  Note: the typical toggle action is RETURN will trigger the single or Y button and ESC will toggle the N button

## Formatting Text
The message text can be formatted with the following HTML-style tags:

`<b>bold</b>` = **bold**  
`<i>italic</i>`  = *itallic*  
`<strong>Strong</strong>`  = **strong**  
`<del>strike</del>`  = <del>strike</del>  
`<em>emphasis</em>` = *emphasis*  
`<ins>underline</ins>` = <ins>underline</ins>  
`<font rgb(0, 0, 255)><b>blue</b></font> other text` = <font color = 'blue'><b>blue</b></font> other text  
`<font rgb(0, 255, 0)>green</font>` = <font color = 'green'>green</font>  
`<font rgb(255, 0, 0)>red</font>` = <font color = 'red'>red</font> 

> Note: And tags can be nested as well, but internal tag must be closed **before** closing the outer tag.

## Theme
The pop-up library allows you to define a theme for the coloration of the pop ups in an application. Open the theme definer by going to:

    Tools->TSC->Theme Definer UI...

Edit and save the theme for use in LabVIEW with **download button** or `Ctrl+S`. For the application, the data is saved in a flattened XML file using a LabVIEW class.
<img src="./assets/images/Theme Definer.png" alt = "Theme Definer UI" /> 

Choose the color scheme and see a live preview with the standard `hourglass` image applied for reference on how the theme will appear when applied. Once completed, save the theme (*.style) file for use in your development. This theme can be loaded in program `initialization` by calling `Theme.lvclass:Load Theme.vi`.

## Additional Standard Images

For the standard pop-ups, the Graphics input is a type definition combo box but it allows for undefined inputs. Because it is a string, the **name** of the standard image that has been added can be defined as an input to any of the standard types as long as the following rules are adhered to:

1. Image Dimensions are `Height = 264px` and `Width = 420px` with a recommendation for whitespace around the image border so that no portion is cut off.

2. The image must be a `PNG` or `JPEG` file.

3. Modify the VI `Pop-Up.lvlib:Popup.lvclass:Convert Enum to Image.vi` and add a new case.  
  
   
>   Note: In original design, this VI would open from the file, but it is a much faster process to keep it standardized and hardcode the constant for the `image data` into the case structure

As long as these rules are followed, developers can extend the standard library of pop-up images. If any images should be considered for addition to the library as a standard selection, add them to the [Issues](https://github.com/danielcoons/tsc-pop-up/issues) page.  

## Additional Pop-Up Type

To create an additional pop-up type, create a new class and choose PopUp.lvclass as the parent. The required override method is called `Display.vi` - it is a protected method meaning that it cannot be called from within a VI outside of the class hierarchy. This means that an accessor VI or constructor of some sort must be created to launch the dialog. 

The front panel of the dialog should be designed to mimic how the desired behavior should be for the application. Setting up a pop-up in this manner allows the developer to use any functionality built into the class to apply a theme, set up the message, and pass the information into the `Display.vi` override. 