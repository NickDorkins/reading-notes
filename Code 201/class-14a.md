## Article: CSS Transformations
 
Source: https://learn.shayhowe.com/advanced-html-css/css-transforms/
 
`transform` property comes in both 2D and 3D settings.
 
`transform` does not work on all browsers and users wanting to get the most out of the element should look at the nightly version of Google Chrome.
Google Chrome (Nightly Version) : https://tools.google.com/dlpage/chromesxs/
 
**The value specifies the transform type followed by a specific amount inside parentheses.**
 
Example:
```
div {
  -webkit-transform: scale(1.5);
     -moz-transform: scale(1.5);
       -o-transform: scale(1.5);
          transform: scale(1.5);
}
 
```
 
The `transform` property includes multiple vendor prefix declarations to gain the best support across multiple browsers. The final `transform` property prefix is blank to cover any browsers that fully support `transform`.
 
### 2D Transforms
 
Elements may be distorted, or transformed, on both a two-dimensional plane or a three-dimensional plane. Two-dimensional transforms work on the x and y axes, known as horizontal and vertical axes. Three-dimensional transforms work on both the x and y axes, as well as the z axis. These three-dimensional transforms help define not only the length and width of an element, but also the depth. We’ll start by discussing how to transform elements on a two-dimensional plane, and then work our way into three-dimensional transforms.
 
Transform Properties:
 
- Rotate: provides the ability to rotate an element from 0 to 360 degrees.
- Scale: allows you to change the appeared size of an element. (Two input values x and y values)
- Skew: used to distort elements on the horizontal axis, vertical axis, or both.
                - skewX - value distorts an element on the horizontal axis
                - skewY - value distorts an element on the vertical axis
                - To distort an element on both axes the skew value is used, declaring the x axis value first, followed by a comma, and then the y axis value.
**Using multiple transform declarations will not work, as each declaration will overwrite the one above it.**
 
The default transform origin is the dead center of an element, both 50% horizontally and 50% vertically. To change this default origin position the transform-origin property may be used.
- The transform-origin property can accept one or two values
- When only one value is specified, that value is used for both the horizontal and vertical axes.
- 0 0 = top left, 100 100 = bottom right (20px 50px would set the origin to 20 pixels across and 50 pixels down the element)
 
 
## Transitions & Animations
 
Source: https://learn.shayhowe.com/advanced-html-css/transitions-animations/
 
**For a transition to take place, an element must have a change in state, and different styles must be identified for each state. The easiest way for determining styles for different states is by using the `:hover`, `:focus`, `:active`, and `:target` pseudo-classes.**
 
There are four transition related properties in total, including:
- `transition-property`
- `transition-duration`
- `transition-timing-function`
- `transition-delay`
 
Example
```
.box {
  background: #2db34a;
  transition-property: background;
  transition-duration: 1s;
  transition-timing-function: linear;
}
.box:hover {
  background: #ff7b29;
}
 
```
Explanation: The box will change its background color over the course of 1 second in a linear fashion.
 
### Vendor Prefixes
 
The code above, is not vendor prefixed. This is intentionally un-prefixed in the interest of keeping the code snippet small and comprehensible.
**For the best support across all browsers, use vendor prefixes.**
 
For reference, the prefixed version of the code above would look like the following.
 
```
.box {
    background: #2db34a;
    -webkit-transition-property: background;
       -moz-transition-property: background;
         -o-transition-property: background;
            transition-property: background;
    -webkit-transition-duration: 1s;
       -moz-transition-duration: 1s;
         -o-transition-duration: 1s;
            transition-duration: 1s;
    -webkit-transition-timing-function: linear;
       -moz-transition-timing-function: linear;
         -o-transition-timing-function: linear;
            transition-timing-function: linear;
}
.box:hover {
  background: #ff7b29;
}
```
 
- **Transitional Property** -  determines exactly what properties will be altered in conjunction with the other transitional properties. By default, all of the properties within an element’s different states will be altered upon change. However, only the properties identified within the transition-property value will be affected by any transitions.
 
It is important to note, not all properties may be transitioned, only properties that have an identifiable halfway point.
Colors, font sizes, and the alike may be transitioned from one value to another as they have recognizable values in-between one another.
The display property, for example, may not be transitioned as it does not have any midpoint.
 
A handful of the more popular transitional properties include the following:
 
- `background-color`
- `background-position`
- `border-color`
- `border-width`
- `border-spacing`
- `bottom`
- `clip`
- `color`
- `crop`
- `font-size`
- `font-weight`
- `height`
- `left`
- `letter-spacing`
- `line-height`
- `margin`
- `max-height`
- `max-width`
- `min-height`
- `min-width`
- `opacity`
- `outline-color`
- `outline-offset`
- `outline-width`
- `padding`
- `right`
- `text-indent`
- `text-shadow`
- `top`
- `vertical-align`
- `visibility`
- `width`
- `word-spacing`
- `z-index`
 
- **Transition Duration** - The duration in which a transition takes place
                - can be set using general timing values, including seconds (s) and milliseconds (ms)
                - These timing values may also come in fractional measurements, .2s for example.
 
- **Transition Timing** -  used to set the speed in which a transition will move.
                                                -  keyword values for the transition-timing-function property include `linear`, `ease-in`, `ease-out`, and `ease-in-out`.
 
                - `linear` - identifies a transition moving in a constant speed from one state to another
                - `ease-in` - identifies a transition that starts slowly and speeds up throughout the transition
                - `ease-out` - identifies a transition that starts quickly and slows down throughout the transition
                - `ease-in-out` - identifies a transition that starts slowly, speeds up in the middle, then slows down again before ending
 
Each timing function has a cubic-bezier curve behind it, which can be specifically set using the cubic-bezier(x1, y1, x2, y2) value. Additional values include step-start, step-stop, and a uniquely identified steps(number_of_steps, direction) value.
Cubic-bezier curve reference information source: http://www.roblaplaca.com/examples/bezierBuilder/
 
- **Transition Delay** -  sets a time value, seconds or milliseconds, that determines how long a transition should be stalled before executing
 
- **Transition** - Shorthand property - set every transition value in the order of transition-property, transition-duration, transition-timing-function, and lastly transition-delay. Do not use commas with these values unless you are identifying numerous transitions.
                                - To set numerous transitions at once, set each individual group of transition values, then use a comma to separate each additional group of transition values
 
 
### Animations
 
**To set multiple points at which an element should undergo a transition, use the @keyframes rule.**
 
- `@keyframes` - includes the animation name, any animation breakpoints, and the properties intended to be animated.
- `animation-name` - property is used with the animation name, identified from the @keyframes rule, as the property value - declaration is applied to the element in which the animation is to be applied to
- `animation-duration` - property and value so that the browser knows how long an animation should take to complete
 
**Once you have declared the animation-name property on an element, animations behave similarly to transitions. They include a duration, timing function, and delay if desired. To start, animations need a duration declared using the animation-duration property. As with transitions, the duration may be set in seconds or milliseconds.**
 
- `animation-iteration-count` - have an animation repeat itself numerous times -  property include either an `integer` or the `infinite` keyword - may limit the number of times an animation runs both forwards and backwards. The count starts at 1 running an animation forwards from 0% to 100%, then adds 1 running an animation backwards from 100% to 0%. Combining for a total of 2 iterations. The alternate value also inverses any timing functions when playing in reverse. If an animation uses the ease-in value going from 0% to 100%, it then uses the ease-out value going from 100% to 0%.
- `animation-direction` - declare the direction an animation completes
- `normal` - plays an animation as intended from beginning to end
- `reverse` - play the animation exactly opposite as identified within the @keyframes rule, thus starting at 100% and working backwards to 0%
- `alternate` -  play an animation forwards then backwards. Within the keyframes that includes running forward from 0% to 100% and then backwards from 100% to 0%
- `alternate-reverse` -  combines both the alternate and reverse values, running an animation backwards then forwards. The `alternate-reverse` value starts at 100% running to 0% and then back to 100% again.
 
 
 
## 8 SIMPLE CSS3 TRANSITIONS THAT WILL WOW YOUR USERS
Source: https://www.webdesignerdepot.com/2014/05/8-simple-css3-transitions-that-will-wow-your-users
 
1. Fade in - Fade in effects are coded in two steps: first, you set the initial state; next, you set the change
2. Change color - set the div’s class to “color” and specify the color wanted in CSS
3. Grow & Shrink - Set div’s class to “grow” and then add this code to style block:
```.grow:hover
{
        -webkit-transform: scale(1.3);
        -ms-transform: scale(1.3);
        transform: scale(1.3);
}
```
- **Shrinking an element is as simple as growing it.**
- **To enlarge an element specify a value greater than 1, to shrink it, specify a value less than 1:**
```
.shrink:hover
{
        -webkit-transform: scale(0.8);
        -ms-transform: scale(0.8);
        transform: scale(0.8);
}
```
 
4. Rotate elements - CSS transforms have a number of different uses, and one of the best is transforming the rotation of an element.
                - Give div the class “rotate” and add the following to CSS:
```
.rotate:hover
{
        -webkit-transform: rotateZ(-30deg);
        -ms-transform: rotateZ(-30deg);
        transform: rotateZ(-30deg);
}
```
 
5. Square to circle - Give your div the class “circle” and add this CSS to your styles:
```
.circle:hover
{
        border-radius:50%;
}
```
 
6. 3D shadow - This effect is achieved by adding a box shadow, and then moving the element on the x axis using the transform and translate properties so that it appears to grow out of the screen.
                - Give your div the class “threed” and then add the following code to your CSS:
```
.threed:hover
{
        box-shadow:
                1px 1px #53a7ea,
                2px 2px #53a7ea,
                3px 3px #53a7ea;
        -webkit-transform: translateX(-3px);
        transform: translateX(-3px);
}
```
 
7. Swing - Not all elements use the transition property. We can also create highly complex animations using `@keyframes`, animation and animation-iteration.
 
**`@keyframes` Example:**
 
```
@-webkit-keyframes swing
{
    15%
    {
        -webkit-transform: translateX(5px);
        transform: translateX(5px);
    }
    30%
    {
        -webkit-transform: translateX(-5px);
       transform: translateX(-5px);
    }
    50%
    {
        -webkit-transform: translateX(3px);
        transform: translateX(3px);
    }
    65%
    {
        -webkit-transform: translateX(-3px);
        transform: translateX(-3px);
    }
    80%
    {
        -webkit-transform: translateX(2px);
        transform: translateX(2px);
    }
    100%
    {
        -webkit-transform: translateX(0);
        transform: translateX(0);
    }
}
@keyframes swing
{
    15%
    {
        -webkit-transform: translateX(5px);
        transform: translateX(5px);
    }
    30%
    {
        -webkit-transform: translateX(-5px);
        transform: translateX(-5px);
    }
    50%
    {
        -webkit-transform: translateX(3px);
        transform: translateX(3px);
    }
    65%
    {
        -webkit-transform: translateX(-3px);
        transform: translateX(-3px);
    }
    80%
    {
        -webkit-transform: translateX(2px);
        transform: translateX(2px);
    }
    100%
    {
        -webkit-transform: translateX(0);
        transform: translateX(0);
    }
}
```
 
**`.swing:hover` Example:**
 
```
.swing:hover
{
        -webkit-animation: swing 1s ease;
        animation: swing 1s ease;
        -webkit-animation-iteration-count: 1;
        animation-iteration-count: 1;
}
```
 
8. Inset border - a button with no background and a heavy border
                - Give your div the class “border” and add the following CSS to your styles:
```
.border:hover
{
        box-shadow: inset 0 0 0 25px #53a7ea;
}
```
 
 
6 buttons animated Source: https://codepen.io/retyui/pen/ByoaXV
 
CSS3 Animations: Keyframes Source: https://codepen.io/akshaychauhan/pen/oAfae
 
404 Animation Source: https://codepen.io/kieranfivestars/pen/MYdQxX
 
Pure CSS Bounce Animation Source: https://codepen.io/dp_lewis/pen/gCfBv