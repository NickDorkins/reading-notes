# EJS Partials
Source: https://medium.com/@henslejoseph/ejs-partials-f6f102cb7433

Partials come in handy when you want to reuse the same HTML across multiple views.

**When you bundle the code like this it allows you to only need to change information in one location instead of needing to track the info down on every page that uses the same information.**


You can save each task as a new `.ejs` file and call it to the page that you are working on.

Examples:
- `header.ejs`
- `footer.ejs`
- `navbar.ejs`
- `searchBox.ejs`
- etc.

In EJS, any JavaScript or non-HTML syntax you include in your templates is always surrounded by (strawberries) `<%` `%>` delimiters.

> You can change these delimiters if you would like, but that's for a later date.

> Delimiters -  a sequence of one or more characters for specifying the boundary between separate, independent regions in plain text, mathematical expressions or other data streams.

>Note: The `<%-` `%>` tags allow us to output the unescaped content onto the page (notice the `-`). This is important when using the include() statement since you don’t want EJS to escape your HTML characters like ‘<’, ‘>’, etc…

Writing Example:
```
<%- include('directory/file') %>

<%- include('partials/navbar') %>

<%- include('partials/footer') %>
```
> You do not need to put the `.ejs` after the file name.
---

# Intro to EJS - Partials - 7

John created the HTML line prior to creating the file, not sure if this is done for a reason.
