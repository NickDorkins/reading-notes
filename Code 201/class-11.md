## Duckett HTML Chapter 16: Images (pp.406-427)

**Controlling the size and alignment of your images using CSS keeps rules that affect the presentation of your page in the CSS and out of the HTML markup.**

**Controlling Sizes of Images in CSS**

You can control the size of an image using the width and height properties in CSS, just like you can for any other box.

Specifying image sizes helps pages to load more smoothly because the HTML and CSS code will often load before the images, and telling the browser how much space to leave for an image allows it to render the rest of the page without waiting for the image to download.

It's a common practice to use images that are all the same size and scale them using CSS.

Use class or ID tags to locate and scale your images.

### Aligning Images Using CSS

The `float` property is added to the class that was created to represent the size of the image 

New classes are created with names such as `align-left` or `align-right` to align the images to the left or right of the page. These class names are used in addition to classes that indicate the size of the image.

Use margins to ensure that the text and images are not touching, this makes the page more readable by the user.

### Centering Images Using CSS

On the containing element, you can use the text-align property with a value of center.

On the image itself, you can use the use the margin property and set the values of the left and right margins to auto.

### Background Images

The `background-image` property allows you to place an image behind any HTML element. This could be the entire page or just part of the page. By default, a background image will repeat to fill the entire box.

The path to the image follows the letters url, and it is put inside parentheses and quotes.

### Repeating Images

* `repeat` - The background image is repeated both horizontally and vertically (the default way it is shown if the `background-repeat` property isn't used).
* `repeat-x` - The image is repeated horizontally only.
* `repeat-y` - The image is repeated vertically only.
* `no-repeat` - The image is only shown once.
* `fixed` - The background image stays in the same position on the page.
* `scroll` - The background image moves up and down as the user scrolls up and down the page.

`background-position` usually has a pair of values. The first represents the horizontal position and the second represents the vertical.

* `left top`
* `left center` 
* `left bottom`
* `center top`
* `center center` 
* `center bottom` 
* `right top` 
* `right center` 
* `right bottom`

**If you only specify one value, the second value will default to center.**

Properties of Background

* `background-color`
* `background-image`
* `background-repeat`
* `background-attachment`
* `background-position`

### Image Rollover and Sprites

Using CSS, it is possible to create a link or button that changes to a second style when a user moves their mouse over it (known as a `rollover`) and a third style when they click on it.

When a single image is used for several different parts of an interface, it is known as a `sprite`. You can add the logo and other interface elements, as well as buttons to the image.

- High Contrast -  A high contrast background image makes the text difficult to read. (Dark text on Dark image)

- Low Contrast - A low contrast background image makes the text easier to read.

- screen – A screen added to a high contrast image makes the text easier to read.

You can specify the dimensions of images using CSS. This is very helpful when you use the same sized images on several pages of your site.

Images can be aligned both horizontally and vertically using CSS.

You can use a background image behind the box created by any element on a page.

Background images can appear just once or be repeated across the background of the box.

You can create image rollover effects by moving the background position of an image.

To reduce the number of images your browser has to load, you can create image sprites.

## Duckett HTML Chapter 19: Practical Information (476-492)

- S.E.O. - Search Enging Optimization
- Analytics -Understand how people are using your site; post launch

### S.E.O.:

- `Page title` - The page title appears at the top of the browser window or on the tab of a browser. It is specified in the `<title>` element which lives inside the `<head>` element.

- `URL` / `Web Address` - The name of the file is part of the URL. Where possible, use keywords in the file name.

- `headings` - If the keywords are in a heading `<hn>` element then a search engine will know that this page is all about that subject and give it greater weight than other text.

- `text` - Where possible, it helps to repeat the keywords in the main body of the text at least 2-3 times. Do not, however, over-use these terms, because the text must be easy for a human to read.

- `link text` - Use keywords in the text that create links between pages (rather than using generic expressions such as "click here").

- `image alt text` - Search engines rely on you providing accurate descriptions of images in the alt text. This will also help your images show up in the results of image-based searches.

- `Page descriptions` - The description also lives inside the `<head>` element and is specified using a `<meta>` tag. It should be a sentence that describes the content of the page. (These are not shown in the browser window but they may be displayed in the results pages of search engines.)

### How to Identify Keywords and Phrases:

1. Brainstorm
2. Organize
3. Research
4. Compare
5. Refine
6. Map

### Analytics

1. Signing Up - The Google Analytics service relies on you signing up for an account at: www.google.com/analytics The site will give you a piece of tracking code which you need to put on every page of your site.

2. How it Works - Every time someone loads a page of your site, the tracking code sends data to the Google servers where it is stored. Google then provides a web- based interface that allows you to see how visitors use your site.

3. The Tracking Code - A tracking code is provided by Google Analytics for each website you are tracking. It should appear just before the closing `</head>` tag. The code does not alter the appearance of your web pages.

### Analytical Data Collected

- Visits
- Unique Visits
- Page Views
- Pages Per Visit
- Average Time on Site
- Date Selector
- Export

### User Views

- Pages
- Landing Pages
- Top Exit Pages
- Bounce Rate
  - Clicked a link to another site
  - Clicked on an advertisement
  - Entered a new URL
  - Used the "back" button
  - Closed the browser

### Visiting From

- Referrers
- Direct
- Search Terms
- Advanced Features

Search engine optimization helps visitors find your sites when using search engines.

Analytics tools such as Google Analytics allow you to see how many people visit your site, how they find it, and what they do when they get there.

To put your site on the web, you will need to obtain a domain name and web hosting.

FTP programs allow you to transfer files from your local computer to your web server.

Many companies provide platforms for blogging, email newsletters, e-commerce and other popular website tools (to save you writing them from scratch).

## MDN AV Article

The `<video>` and `<audio>` elements allow us to embed video and audio into web pages.

Part of the HTML5 spec, the HTMLMediaElement API provides features to allow you to control video and audio players programmatically — for example `HTMLMediaElement.play()`, `HTMLMediaElement.pause()`, etc. This interface is available to both `<audio>` and `<video>` elements, as the features you'll want to implement are nearly identical.

- The whole player is wrapped in a `<div>` element, so it can all be styled as one unit if needed.

- The `<video>` element contains two `<source>` elements so that different formats can be loaded depending on the browser viewing the site.


## Duckett HTML Chapter 9: Flash Video and Audio (201-206)

**Flash is a very popular technology used to add animations, video, and audio to websites.**

You can add video and audio to your site, using either the new HTML5 `<video>` and `<audio>` elements or a hosted service (such as YouTube or SoundCloud).

Whether you are creating an animation or a media player in Flash, the files you put on your website are referred to as Flash movies.

If you want to create your own Flash movie, you need to purchase the Flash authoring environment from Adobe.

There are several third party companies that offer Flash animation tools without purchasing them.

JAVAScript libraries are written to create animated effects





