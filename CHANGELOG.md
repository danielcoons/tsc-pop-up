# Changelog - TSC Pop-Up
All notable changes to the TSC Pop-Up library will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]
- Future features to include

## [4.0.0] - 10.16.2025
### Added
- Released the tool as a public, open-source project
- Example VI and style output to show ability to theme the dialogs

### Changed
- Updated minimum compatible version to LabVIEW 2021

### Removed
- Moved the GIF and SVG pop-up types to their own repos because of a package dependency needed
- External package dependency for this version

## [3.6.0] - 10.22.2024
### Added
- Added a new data member access method to track the `Timeout` result; tracked as a Boolean and is written and read in all timeout pop up types

## [3.5.0] - 08.29.2024
### Added
- Added plain pop up types to the pop up library (title/message/and one, two, or three button choices)
- Added a function to temporarily define different font for a pop up to set justification/message size

## [3.4.0] - 08.14.2024
### Added
- Added ability to construct a theme from a material xml file

## [3.3.0] - 07.09.2024
### Added
- Added capability to support Custom Gifs
- Added capability to support Custom SVGs

## [3.2.0] - 04.11.2024
### Fixed
- Bottom image location was not correctly placing buttons

## [3.1.0] - 01.17.2024
### Added
- Users can now double click the pop up to make it semi-transparent

### Fixed
- Ignore clicks and double clicks in button or input regions

## [3.0.1] - 01.03.2024
### Added
- Added font name, size, bold, itallic to button text

### Fixed
- Fixed a few minor bugs in the Theme Designer 
    - Put in an image so that could be seen with the preview
    - Made the save work so that new or existing files could be used (was only letting save for existing previously)

## [3.0.0] - 12.29.2023
### Added
- Added a theme class that defines the theme for the pop-up
- Added a LabVIEW Tool to define a new theme style file with a preview

### Changed
- Changed all standard images and updated to be a combobox ring input so that users can extend images
- All standard and custom pop-ups updated to apply theme

### Removed
- Removed all unused functions

## [2.4.1] - 09.12.2023
### Fixed
- Fixed embedded tags in formatting 

        <b><i>bold and italic</i></b>

  will now correctly work to produce: ***bold and italic***

## [2.4.0] - 09.08.2023
### Added
- Ability to use custom formatting in messages for the text
- Feature was added to all pop up types and includes:
    
        <b> bold </b>
        <i> italic </i>
        <strong> bold - strong </strong>
        <em> italic - emphasis </em>
        <del> strikethrough </del>
        <ins> underline </ins>
        <font rgb(#,#,#)> RGB-based color of text </font>

## [2.3.0] - 04.26.2023
### Added
- Implemented the ability to close pop-ups early (most useful for timeouts of an unknown length)
  - This was incorporated by a new set of functions
  - New functions are a general close and then ability to set default values for DBL, I32, String, and a two button dialog

## [2.2.0] - 04.11.2022
### Changed
- LabVIEW 2021 SP1 upgrade
- Updated the style of each of the standard pop-ups; changed background color, updated the button style, change size input for dbl/i32 (and added decoration to cover the focus highlight box), and disabled all text boxes that display message
- Updated the style and input for the custom pop-ups; all updates applied to standard were also done for custom and also some of the padding and placement of buttons
- Separated compiled from source for all VIs in the project
- Updated VI Description documentation

## [2.1.2] - 07.02.2021
### Added
- Testing for the pop up types
- Library of common pop up functions

### Changed
- Post-build action for output ppl