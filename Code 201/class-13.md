## Read 13: Local Storage

Persistent local storage works best with native client applications; better than web apps.

Native storage provides all of the data that the user will need/want while using the application.

If your native client application needs local storage beyond key/value pairs, you can embed your own database, invent your own file format, or any number of other solutions.

### Cookies:

There are several downsides to using cookies for user data storage.

- Cookies are included with every HTTP request, thereby slowing down your web application by needlessly transmitting the same data over and over

- Cookies are included with every HTTP request, thereby sending data unencrypted over the internet (unless your entire web application is served over SSL)

- Cookies are limited to about 4 KB of data — enough to slow down your application (see above), but not enough to be terribly useful

**What a dev really wants is:**

- a lot of storage space
- on the client
- that persists beyond a page refresh
- isn’t transmitted to the server

**Page data storage started with Internet Explorer's userData and was 64KB of storage**

- In 2002, Adobe released Flash 6, soon known by the misleading name of "Flash Cookies". This would allow domains to store up to 100KB `(1MB)` of data each.

- By 2006, with the advent of ExternalInterface in Flash 8, accessing LSOs from JavaScript.

- Flash gives each domain 100 KB of storage per domain“for free.”

- In 2007, Google launched Gears,an open source browser plugin aimed at providing additional capabilities in browsers.

**What is HTML5 Storage?** 

It’s a way for web pages to store named key/value pairs locally, within the client web browser. 

HTML5 Storage is based on named key/value pairs. You store data based on a named key, then you can retrieve that data with the same key. The named key is a string. The data can be any type supported by JavaScript, including strings, Booleans, integers, or floats.

If you want to keep track programmatically of when the storage area changes, you can trap the storage event. The storage event is fired on the window object whenever setItem(), removeItem(), or clear() is called and actually changes something. For example, if you set an item to its existing value or call clear() when there are no named keys, the storage event will not fire, because nothing actually changed in the storage area.

The storage event is supported everywhere the localStorage object is supported, which includes Internet Explorer 8. IE 8 does not support the W3C standard addEventListener (although that will finally be added in IE 9). Therefore, to hook the storage event, you’ll need to check which event mechanism the browser supports.