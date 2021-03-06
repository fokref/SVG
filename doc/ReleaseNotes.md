# SVG.NET Release Notes
The release versions are NuGet releases.

## Unreleased (master)

### Changes
* removed support for .NET 3.5
* upgraded the used Fizzler libary to 1.2.0 (supports Netstandard 1.0 and 2.0)

### Enhancements
* check that there is a `moveto` command at the beginning of a path (see [PR #616](https://github.com/vvvv/SVG/pull/616))
* add support for `<a>` element (see [#626](https://github.com/vvvv/SVG/issues/626) and [PR #628](https://github.com/vvvv/SVG/pull/628)))
* added ColorConverter from dotnet runtime codebase to make Netstandard 2.0 target more complete (see [PR #630](https://github.com/vvvv/SVG/pull/630))

### Fixes
* fixed nested svg tags not rendered properly (see [#622](https://github.com/vvvv/SVG/issues/622))
* added handling of invalid property in parser (see [#632](https://github.com/vvvv/SVG/issues/632))
* fixed CoordinateParser handling of invalid state (see [PR #640](https://github.com/vvvv/SVG/pull/640))

## [Version 3.0.84](https://www.nuget.org/packages/Svg/3.0.84)

_**Note:**_
* this is the last release version that still supports .NET version 3.5
* the support for .NET Standard introduced in this version is preliminary and incomplete
* a compatibility warning from the Fizzler library is shown during build;
  this can be safely ignored and will be gone in the next version
 
### Enhancements
* added preliminary support for .NET Standard 2.0 (see [#346](https://github.com/vvvv/SVG/issues/346));
  Drawing2D is not fully supported
* added support for href namespace (see [PR #579](https://github.com/vvvv/SVG/pull/579)) 
* support non-standard mime types for embedded images (see [#578](https://github.com/vvvv/SVG/issues/578))

### Infrastructure
* the Fizzler library is now included via NuGet instead of copying the sources
* added Gitter chat room for SVG.NET

### Documentation
* moved documentation to GitHub pages
* added auto-generated API documentation

### Fixes
* fixed scaling of embedded images (see [#592](https://github.com/vvvv/SVG/issues/592))
* fixed issue for stroke dasharray with odd number of values (see [PR #584](https://github.com/vvvv/SVG/pull/584)) 
* fixed parsing of some color attributes (see [PR #580](https://github.com/vvvv/SVG/pull/580)) 
* fixed behavior of 'Inherit' value for several attributes (see [#541](https://github.com/vvvv/SVG/issues/541))


## [Version 3.0.49](https://www.nuget.org/packages/Svg/3.0.49)

**Note:** this is the first version that supports .NET Core alongside .NET.
To build it yourself, you need at least Visual Studio 2017 due to the added multi-platform support.

### Enhancements
* added support for .NET Core 2.2 (see PR [#448](https://github.com/vvvv/SVG/pull/448))
* handle missing gdi+ library on MacOs or Linux by a descriptive exception (see [#501](https://github.com/vvvv/SVG/issues/501))
* allow ID start with a number (see [#138](https://github.com/vvvv/SVG/issues/138))
* added support for embedded SVG in data URIs (see [#71](https://github.com/vvvv/SVG/issues/71)
  and [#220](https://github.com/vvvv/SVG/issues/220))
* support `auto-start-reverse` value for marker orientation (see PR [#458](https://github.com/vvvv/SVG/pull/458)) 
* added support for the SvgScript tag (see [PR #558](https://github.com/vvvv/SVG/pull/558)) 

### Infrastructure
* use NUnit instead of MSTest for unit tests (see [#420](https://github.com/vvvv/SVG/issues/420))
* added automatic git versioning
* xml documentation is included in the nuget package

### Documentation
* added "Getting Started" Wiki page

### Fixes

* added check for invalid bounds (see [#554](https://github.com/vvvv/SVG/issues/554))
* added support for "Grey" color (see [PR #551](https://github.com/vvvv/SVG/pull/551)) 
* updated core compat package to resolve font issues on Mac (see [#548](https://github.com/vvvv/SVG/issues/548))
* fixed parsing of white spaces in color matrix (see [PR #540](https://github.com/vvvv/SVG/pull/540))
* fixed zero matrix transformation issues (see [PR #537](https://github.com/vvvv/SVG/pull/537))
* avoid adding a null system font (see [#528](https://github.com/vvvv/SVG/issues/528))
* fixed missing text drawing (see [#84](https://github.com/vvvv/SVG/issues/84))
* fixed y2 default value for SvgLinearGradientServer (see [PR #530](https://github.com/vvvv/SVG/pull/530))
* fixed incorrect parsing of some float values for non-English cultures
  (see [PR #525](https://github.com/vvvv/SVG/pull/525) and [#526](https://github.com/vvvv/SVG/pull/526))
* fixed pattern drawing (see [#280](https://github.com/vvvv/SVG/issues/280))
* prevent crash on reading entities (see [#518](https://github.com/vvvv/SVG/issues/518))
* fixed saving of attributes with default value (see [PR #520](https://github.com/vvvv/SVG/pull/520))
* fixed determination of OS type (see [PR #517](https://github.com/vvvv/SVG/pull/517))
* fixed writing of custom style attributes (see [#507](https://github.com/vvvv/SVG/issues/507))
* handle overlapping caps by joining the lines (see [#508](https://github.com/vvvv/SVG/issues/508))
* correctly handle style attributes in top level svg element (see [#391](https://github.com/vvvv/SVG/issues/391))
* fixed incorrect rendering if stroke-dasharray value is none (see [PR #504](https://github.com/vvvv/SVG/pull/504))
* prevent exception for zero bounds and opacity not one (see [#479](https://github.com/vvvv/SVG/issues/479))
* make sure mask elements are written back to svg (see [#271](https://github.com/vvvv/SVG/issues/271))
* fixed incorrect clip region (see [#363](https://github.com/vvvv/SVG/issues/363))
* fixed overflow error on 1 character text with tspan (see [#488](https://github.com/vvvv/SVG/issues/488))
* fixed crash with unsupported pseudo classes (see [#315](https://github.com/vvvv/SVG/issues/315))
* fixes wrong text position in some scenarios (see PR [#475](https://github.com/vvvv/SVG/pull/475))
* fixed handling of spaces for `xml:space="default"` (see PR [#471](https://github.com/vvvv/SVG/pull/471))
* fixed crash if more than font have the same name (see [#452](https://github.com/vvvv/SVG/issues/452))
* fixed rendering bug for text on path using very large font
  (see PR [#468](https://github.com/vvvv/SVG/pull/468))
* avoid exception in nested SVGs without size (see [#460](https://github.com/vvvv/SVG/issues/460))
* fixed default input values for filter primitives
* fixed parsing of float values in color matrixes and colors on non-English systems
* fixed xlink:href value format (see PR [#455](https://github.com/vvvv/SVG/pull/455))
* support various formats of URL string (see PR [#454](https://github.com/vvvv/SVG/pull/454))
* fixed stack overflow crash on images with relative size 
  (see [#436](https://github.com/vvvv/SVG/issues/436))

## [Version 2.4.3](https://www.nuget.org/packages/Svg/2.4.3)
### Fixes
* fixed boundary drawing with corner and stroke (see PR [#444](https://github.com/vvvv/SVG/pull/444))
* fixed rendering with fill opacity 0 (see [#437](https://github.com/vvvv/SVG/issues/437))
* fixed opacity attribute (see PR [#433](https://github.com/vvvv/SVG/pull/433))
* fixed bounds calculation with stroke (see PR [#433](https://github.com/vvvv/SVG/pull/433))

## [Version 2.4.2](https://www.nuget.org/packages/Svg/2.4.2)
### Enhancements
* added font manager to allow user-defined font handling 
  (see PR [#414](https://github.com/vvvv/SVG/pull/414)) 

### Fixes
* fixed handling of invalid hex color and whitespace after hex color (see [#399](https://github.com/vvvv/SVG/issues/399))
* fixed default font size (caused text not to be displayed, see [#419](https://github.com/vvvv/SVG/issues/419))
* fixed writing of RGBA colors (see [#129](https://github.com/vvvv/SVG/issues/129))
* fixed writing of custom styles (see [#129](https://github.com/vvvv/SVG/issues/129))
* fixed handling of default values for radial gradients (see [#397](https://github.com/vvvv/SVG/issues/397))
* allow empty value for style property (see [#318](https://github.com/vvvv/SVG/issues/318))
* added handling of referenced viewBox scaling in "use" elements 
* handle special case where path consists of a single move command 
  (see [#223](https://github.com/vvvv/SVG/issues/223))
* correctly write fill-rule, clip-rule and named color attributes as lower case
  (see [#272](https://github.com/vvvv/SVG/issues/272))
* several fixes for markers:
  * added support for marker attributes in groups
  * partly fixed marker appearance (stroke and fill color, scaling, deafult orientation)
  * apply transformations in the marker drawing element (see [#215](https://github.com/vvvv/SVG/issues/215))
  * correctly show mid markers for paths with Bezier curves
  * handle markers on paths with successive equal points

## [Version 2.4.1](https://www.nuget.org/packages/Svg/2.4.1)
### Changes
* `ExCSS` lives now in the `Svg` namespace to avoid namespace collusions 
  (see [#408](https://github.com/vvvv/SVG/issues/408))

### Fixes
* fixed handling of url IDs enclosed in apostrophes (see [#345](https://github.com/vvvv/SVG/issues/345)) 
* fixed calculation of percentage values (PR [#410](https://github.com/vvvv/SVG/pull/410))
* regression: missing scaling if rendering into a bitmap with defined size 
  (see [#405](https://github.com/vvvv/SVG/issues/405))
* consider transformation for all svg element bounds (see [#331](https://github.com/vvvv/SVG/issues/331))
* prevent crash if `use` element has no reference (see [#323](https://github.com/vvvv/SVG/issues/323))
* fixed handling of `fill=currentColor` (see [#398](https://github.com/vvvv/SVG/issues/398))

## [Version 2.4.0](https://www.nuget.org/packages/Svg/2.4.0)

### Enhancements
  * added basic support for CSS text-transform 
  * added optional size parameter to `SvgDocument.Draw()`
  * allow relative paths for image URLs
  * improved path drawing performance
  * added XML Header to conform according to SVG spec ([PR #269](https://github.com/vvvv/SVG/pull/269))
  * added support for removing Byte Order Mark (BOM) ([PR #269](https://github.com/vvvv/SVG/pull/269))

### Infrastructure
  * added copy of license
  * added automatic unit test execution after check-in in AppVeyor

### Fixes
  * fixed display of rounded caps for dashed lines using dasharray (see [#191](https://github.com/vvvv/SVG/issues/191))
  * fixed calculation of percentage units in 'y' (see [#329](https://github.com/vvvv/SVG/issues/329))
  * fixed calculation of percentage units in `stroke-width` (see [#338](https://github.com/vvvv/SVG/issues/338))
  * fixed display of `dasharray` with odd number (see [#58](https://github.com/vvvv/SVG/issues/58))
  * fixed font alignment for "middle" and "end" (see [#385](https://github.com/vvvv/SVG/issues/385))
  * fixed handling of `stroke-dashoffset` (see [#388](https://github.com/vvvv/SVG/issues/388))
  * fixed font shorthand parsing
  * fixed case insensitive enum parsing
  * ignore cycles in `use` elements to prevent crash
  * fixes bounds calculation for `use` elements
  * corrected DPI calculation to fix text positioning for printing 
  * ignore `textLength` attribute if X attribute is list
  * fixed drawing of SvgFont objects
  * fixed adjustment if `lengthAdjust='spacingAndGlyphs'` (see [#373](https://github.com/vvvv/SVG/issues/373))
  * fixed SvgAttribute reflection for .Net core
  * fixed default value for `preserveAspectRatio` attribute 
  * fixed path parsing mistaking 'E' as a command instead of an exponent
  * fixed image opacity
  * fixed usage of `ms colortranslator` class
  * fixed inproper use of UTF8Encoding
  * fixed runtime error after accessing added `SvgText` element (see [#332](https://github.com/vvvv/SVG/issues/332)) 
  * fixed rendering error due to invalid `ColorBlend` position
  * fixed inheriting `text-anchor` and `baseline-shift` attributes
  * prevent crashes on zero length segments or paths
  * fixed handling of nested SVGs (see [#244](https://github.com/vvvv/SVG/issues/244))
  * fixed crash in `use` elements with transformation (see [#64](https://github.com/vvvv/SVG/issues/64)) 
  * fixed overflow handling for view boxes (see [#279](https://github.com/vvvv/SVG/issues/279))
  * bounds in path based elements did not consider transformations (see [#281](https://github.com/vvvv/SVG/issues/281))
