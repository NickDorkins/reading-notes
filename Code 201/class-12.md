## Read:12 Docs for the HTML `<canvas>` Element & Chart.js

### Article: EASILY CREATE STUNNING ANIMATED CHARTS WITH CHART.JS

Source: https://www.webdesignerdepot.com/2013/11/easily-create-stunning-animated-charts-with-chart-js/

**Charts are far better for displaying data visually than tables and easier to look at to convey data quickly, but they’re not always easy to create.**


You can create many types of charts and graphs using Chart.js

**Chart Styles**
* Line Chart
* Pie Chart
* Bar Chart

### Basic usage of canvas

Source: https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Basic_usage

The `<canvas>` element has only two attributes, width and height. These are both optional and can also be set using DOM properties. When no width and height attributes are specified, the canvas will initially be 300 pixels wide and 150 pixels high.

The `<canvas>` element makes it easy to define some fallback content, to be displayed in older browsers not supporting it, like versions of Internet Explorer earlier than version 9 or textual browsers.

Providing fallback content is very straightforward: just insert the alternate content inside the `<canvas>` element. Browsers that don't support `<canvas>` will ignore the container and render the fallback content inside it. Browsers that do support `<canvas>` will ignore the content inside the container, and just render the canvas normally.

`<canvas>` tag does require a closing tag, `</canvas>`.

The `<canvas>` element has a method called `getContext()`, used to obtain the rendering context and its drawing functions. `getContext()` takes one parameter, the type of context. For 2D graphics, you specify "2d" to get a `CanvasRenderingContext2D`.

### Drawing shapes with canvas

Source:https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes

**The Grid** Starts in the top left corner of the canvas. X-Axsis = Width, Y-Axsis = Height 

**Drawing rectangles**
- `fillRect(x, y, width, height)` - Draws a filled rectangle.
- `strokeRect(x, y, width, height)` - Draws a rectangular outline.
- `clearRect(x, y, width, height)` - Clears the specified rectangular area, making it fully transparent.

**Drawing paths**

*A path is a list of points, connected by segments of lines that can be of different shapes, curved or not, of different width and of different color. A path, or even a subpath, can be closed. To make shapes using paths, takes some extra steps:*

- `beginPath()` - Creates a new path. Once created, future drawing commands are directed into the path and used to build the path up.
- `Path methods` - Methods to set different paths for objects.
- `closePath()` - Adds a straight line to the path, going to the start of the current sub-path.
- `stroke()` - Draws the shape by stroking its outline.
- `fill()` - Draws a solid shape by filling the path's content area.

### Applying styles and colors

Source:https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Applying_styles_and_colors

- `fillStyle = color` - Sets the style used when filling shapes.
- `strokeStyle = color` - Sets the style for shapes' outlines.

Transparency

- `globalAlpha = transparencyValue` - Applies the specified transparency value to all future shapes drawn on the canvas. The value must be between 0.0 (**fully transparent**) to 1.0 (**fully opaque**). This value is 1.0 (**fully opaque**) by default.

Line styles

- `lineWidth = value` - Sets the width of lines drawn in the future.
- `lineCap = type` - Sets the appearance of the ends of lines.
- `lineJoin = type` - Sets the appearance of the "corners" where lines meet.
- `miterLimit = value` - Establishes a limit on the miter when two lines join at a sharp angle, to let you control how thick the junction becomes.
- `getLineDash()` - Returns the current line dash pattern array containing an even number of non-negative numbers.
- `setLineDash(segments)` - Sets the current line dash pattern.
- `lineDashOffset = value` - Specifies where to start a dash array on a line.

Gradient

- `createLinearGradient(x1, y1, x2, y2)` - Creates a linear gradient object with a starting point of (x1, y1) and an end point of (x2, y2).
- `createRadialGradient(x1, y1, r1, x2, y2, r2)` - Creates a radial gradient. The parameters represent two circles, one with its center at (x1, y1) and a radius of r1, and the other with its center at (x2, y2) with a radius of r2.


Patterns

- `createPattern(image, type)` - Creates and returns a new canvas pattern object. image is a CanvasImageSource (that is, an HTMLImageElement, another canvas, a `<video> `element, or the like. type is a string indicating how to use the image.


- `repeat` - Tiles the image in both vertical and horizontal directions.
- `repeat-x` - Tiles the image horizontally but not vertically.
- `repeat-y` - Tiles the image vertically but not horizontally.
- `no-repeat` - Doesn't tile the image. It's used only once.

Shadows

- `shadowOffsetX = float` - Indicates the horizontal distance the shadow should extend from the object. This value isn't affected by the transformation matrix. The default is 0.
- `shadowOffsetY = float` - Indicates the vertical distance the shadow should extend from the object. This value isn't affected by the transformation matrix. The default is 0.
- `shadowBlur = float` - Indicates the size of the blurring effect; this value doesn't correspond to a number of pixels and is not affected by the current transformation matrix. The default value is 0.
- `shadowColor = color` - A standard CSS color value indicating the color of the shadow effect; by default, it is fully-transparent black.

### Drawing text

Source: https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_text

Drawing Text

- `fillText(text, x, y [, maxWidth])` - Fills a given text at the given (x,y) position. Optionally with a maximum width to draw.
- `strokeText(text, x, y [, maxWidth])` - Strokes a given text at the given (x,y) position. Optionally with a maximum width to draw.

Styling Text

- `font = value` - The current text style being used when drawing text. This string uses the same syntax as the CSS font property. The default font is 10px sans-serif.
- `textAlign = value` - Text alignment setting. Possible values: start, end, left, right or center. The default value is start.
- `textBaseline = value` - Baseline alignment setting. Possible values: top, hanging, middle, alphabetic, ideographic, bottom. The default value is alphabetic.
- `direction = value` - Directionality. Possible values: ltr, rtl, inherit. The default value is inherit.






















### Resources:

Chart.js Plugin: https://www.chartjs.org/

Download Chart.js file: https://github.com/chartjs/Chart.js

Chart.js GitHub: https://github.com/chartjs/Chart.js/releases/tag/v2.9.3

JS**DELIVR**: https://www.jsdelivr.com/package/npm/chart.js

Chartjs: https://www.chartjs.org/docs/latest/getting-started/installation.html

