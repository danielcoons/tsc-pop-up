# README - TSC Pop-Up
Below are instructions to follow on how to extend the TSC Pop-Up library.

## Additional Standard Images

For the standard pop-ups, the Graphics input is a type definition combo box but it allows for undefined inputs. Because it is a string, the **name** of the standard image that has been added can be defined as an input to any of the standard types as long as the following rules are adhered to:

1. Image Dimensions are `Height = 264px` and `Width = 420px` with a recommendation for whitespace around the image border so that no portion is cut off.

2. The image must be a `PNG` file.

3. The image is stored in the `Graphics` folder.

As long as these rules are followed, developers can extend the standard library of pop-up images. If any images should be considered for addition to the library as a standard selection, email: <daniel.coons@tsc.com>. 

## Additional Pop-Up Type

To create an additional pop-up type, create a new class and choose PopUp.lvclass as the parent. The required override method is called `Display.vi` - it is a protected method meaning that it cannot be called from within a VI outside of the class hierarchy. This means that an accessor VI or constructor of some sort must be created to launch the dialog. 

The front panel of the dialog should be designed to mimic how the desired behavior should be for the application. Setting up a pop-up in this manner allows the developer to use any functionality built into the class to apply a theme, set up the message, and pass the information into the `Display.vi` override. 

## Using with an Executable

Using standard pop-ups with an executable have a setup expectation. They are expected to be included in the `data` folder of the EXE. This is defined in the `Convert Enum to Image.vi` function. This takes the name of the image and loads it as a PNG file to be displayed. Therefore, if the developer changes the output directory for these standard graphics, the standard pop-up images will not be found correctly. 

If additional standard images are created by the developer for a project, they should also get located in this folder for the executable output.