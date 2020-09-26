# RESPONSIVE WEB DESIGN and FLOATS

## Shay Howe’s intro to RWD
Source: http://learn.shayhowe.com/advanced-html-css/responsive-web-design/

**Responsive web design is the practice of building a website suitable to work on every device and every screen size, no matter how large or small, mobile or desktop. Responsive web design is focused around providing an intuitive and gratifying experience for everyone. Desktop computer and cell phone users alike all benefit from responsive websites.**

### Responsive vs. Adaptive vs. Mobile
- **Responsive** - react quickly and positively to any change
- **Adaptive** - easily modified for a new purpose or situation, such as change
- **Mobile** - generally means to build a separate website commonly on a new domain solely for mobile users

### Relative Viewport Lengths
- `vw` - Viewports width
- `vh` - Viewports height
- `vmin` - Minimum of the viewport’s height and width
- `vmax` - Maximum of the viewport’s height and width

**Flexible Grid** - Take all of the fixed units of length and turn them into relative units


### **Media Queries**
*Styles based on true/false conditions*

**Key Features**
1. Initializing Media Queries - `@media` , `@import`
2. Logical Operators in Media Queries
    -Omitting a Media Type
3. Media Features in Media Queries
4. Height & Width Media Features
    -Using Minimum & Maximum Prefixes
5. Orientation Media Feature
6. Aspect Ratio Media Features
    - Pixel Ratio Media Features
7. Resolution Media Feature
8. Media Query Browser Support

### Mobile First - styles targeted at smaller viewports as the default styles for a website
### Viewport
- Viewport Height & Width
- Viewport Scale
- Viewport Resolution
- Combining Viewport Values

### Flexible Media
- Flexible Embedded Media

## All About Floats
Source: https://css-tricks.com/all-about-floats/

**What is “Float”?** - `Float` is a CSS positioning property.
  - Images may be set into the page such that text wraps around them as needed. This is commonly and appropriately called “text wrap”
- Floated elements remain a part of the flow of the web page.
- Absolutely positioned page elements are removed from the flow of the webpage, like when the text box in the print layout was told to ignore the page wrap
- Absolutely positioned page elements will not affect the position of other elements and other elements will not affect them
- Position values - `Left`,`Right`,`Inherit`,`none`
- Clear Values - `Left`,`Right`,`Both`,`none` (`inherit` - usable but not supported by Internet explorer)


### Techniques for Clearing Floats
- Empty Div Method
- Overflow Method
- Easy Clearing Method 

## Don’t Overthink It Grids
Source: https://css-tricks.com/dont-overthink-it-grids/

- **Context** - A block level element is as wide as the parent it’s inside
- **Columns** 
- **Clearing Context** 
- **Gutters** 
- **Outside Gutters**
- **Sass**
- **Modules**


## CSS Floats Explained By Riding An Escalator 
Source: https://www.freecodecamp.org/news/css-floats-explained-by-riding-an-escalator-57fa55232333/

**Floats create alternate flow**

- **Floats**: Left and Right
- **Clear Property**

## SMACSS Official Documentation
Source: http://smacss.com/

SMACSS is more style guide than rigid framework. There is no library you have to download or install. There is no git repository for you to clone. SMACSS is a way to examine your design process and as a way to fit those rigid frameworks into a flexible thought process. It is an attempt to document a consistent approach to site development when using CSS. And really, who isn’t building a site with CSS these days?!



