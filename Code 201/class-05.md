## Duckett HTML book: Chapter 5: Images

- Include an image in your web pages using HTML
- Pick which image format to use
- Show an image at the right size
- Optimize an image for use on the web to make pages load faster


#### Stock images reference sites
- www.istockphoto.com
- www.gettyimages.com
- www.veer.com
- www.sxc.hu
- www.fotolia.com

**img** - required to add and image, empty tag(no closing tag)

**src** - tells browser where to find the image

**alt** - describes the photo in words incase the user cannot see it

**title** - provides additional information, usually displays text when user hovers over the image

**height** - specify height in number of pixels

**width** - specify width in number of pixels

**align** - where should the image be located(**left/right or top/middle/bottom**)

**figure** - wraps the image tags so the browser knows the figcaption goes with the image

**figcaption** - tells the user about the photo, displayed at the bottom under the photo

#### Where to place images in your code

1: before a paragraph the paragraph starts on a new line after the image.

2: InsIde the start of a paragraph the first row of text aligns with the bottom of the image.

3: In the mIddle of a paragraph the image is placed between the words of the paragraph that it appears in.

#### 3 rules for creating images

- Save images in the right format (**jpeg,gif,png**)

- Save images in the right size (incorrect sizing can distort the image)

- Use the correct resolution (72px or less)

#### online editors
- www.photoshop.com
- www.pixlr.com
- www.splashup.com
- www.ipiccy.com

### Summary:
- The <img> element is used to add images to a web page.

- You must always specify a src attribute to indicate the source of an image and an alt attribute to describe the content of an image.

- You should save images at the size you will be using them on the web page and in the appropriate format.

- Photographs are best saved as JPEGs; illustrations or logos that use flat colors are better saved as GIFs.


## Duckett HTML book Chapter 11: Color

**RGB values** - these express colors in terms of how much red, green and blue are used to make it up. Example: rgb(100,100,90)

**hex Codes** - these are six-digit codes that represent the amount of red, green and blue in a color, preceded by a pound or hash # sign. Example: #ee3e80

**Color names** - there are 147 predefined color names that are recognized by browsers. Example: DarkCyan

**Hue** - Hue is near to the colloquial idea of color. 

**Saturation** - refers to the amount of gray in a color

**Brightness** - refers to how much black is in a color.

**Lightness** - refers to how much white is in a color.

### Summary:

- Color not only brings your site to life, but also helps convey the mood and evokes reactions.

- There are three ways to specify colors in CSS: RGB values, hex codes, and color names.

- Color pickers can help you find the color you want.

- It is important to ensure that there is enough contrast between any text and the background color (otherwise people will not be able to read your content).

- CSS3 has introduced an extra value for RGB colors to indicate opacity. It is known as RGBA.

- CSS3 also allows you to specify colors as HSL values, with an optional opacity value. It is known as HSLA.

## Duckett HTML book Chapter 12: Text

**Typeface Terminology**

- **Serif** fonts have extra details on
the ends of the main strokes of
the letters. These details are
known as serif.

- **Sans-serif** fonts have straight ends to letters, and therefore have a much cleaner design.

**Monospace** -Every letter in a monospace (or fixed-width) font is the same width. (Non-monospace fonts have different widths)

**Weight** - The font weight not only adds emphasis but can also affect the amount of white space and contrast on a page.

**Style** - Italic fonts have a cursive aspect to some of the lettering. Oblique font styles take the normal style and put it on an angle.

**Stretch** - In condensed (or narrow) versions of the font, letters are thinner and closer together. In expanded versions they are thicker and further apart.

**@font-face** allows you to use a font, even if it is not installed on the computer of the person browsing, by allowing you to specify a path to a copy of the font, which will be downloaded if it is not on the user's machine.

**font-family** - specifies the name of the font. 

**src** - specifies the path to the font. I

**format** - specifies the format that the font is supplied in.

#### Font website referencce:

- www.fontsquirrel.com
- www.fontex.org
- www.openfontlibrary.org
- www.typekit.com
- www.kernest.com
- www.fontspring.com

### Summary:

- There are properties to control the choice of font, size, weight, style, and spacing.

- There is a limited choice of fonts that you can assume most people will have installed.

- If you want to use a wider range of typefaces there are several options, but you need to have the right license to use them.

- You can control the space between lines of text, individual letters, and words. Text can also be aligned to the left, right, center, or justified. It can also be indented.

- You can use pseudo-classes to change the style of an element when a user hovers over or clicks on text, or when they have visited a link.

