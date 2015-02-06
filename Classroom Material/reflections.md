
# Lesson 2 Material

## 2/5/2015 - 


# Lesson 1 Material

## 2/5/2015
Adding the async keyword to the script tag tells the browser that it should not block the DOM construction while it waits for the script to become available - this is a huge performance win!

## 1/31/2015 - Analyzing the entire crp in devtools
Instructor Notes

Here's a link to the [sample page](http://udacity-crp.herokuapp.com/cssom-inline.html) Ilya uses. For bonus points, review the [Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/) content on Google's Web Fundamentals.

## 1/21/2015

### setting the viewport
Always include: <meta name="viewport" content="width=device-width, initial-scale=1">

-  Use meta viewport tag to control the width and scaling of the browsers viewport.
-  Include width=device-width to match the screen's width in device independent pixels.
-  Include initial-scale=1 to establish a 1:1 relationship between CSS pixels and device independent pixels.
-  Ensure your page is accessible by not disabling user scaling.

### Good information: display:none vs. hidden

"As a brief aside, note that 'visibility: hidden' is different from 'display: none'. The former makes the element invisible, but the element is still occupies space in the layout (i.e. it's rendered as an empty box), whereas the latter (display: none) removes the element entirely from the render tree such that the element is invisible and is not part of layout."

### Instructor Notes
Learn more about [render-tree construction, layout, and paint](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-tree-construction)
Learn more about [layout viewport and the basics of responsive web design](https://developers.google.com/web/fundamentals/layouts/rwd-fundamentals/)

## 1/20/2015 

Instructor Notes
Check out the [demo page](http://udacity-crp.herokuapp.com/cssom.html) we're using in this example: compare the HTML to the resulting render tree and what you see on the screen. Neat, right?
You can learn more about [Render Tree construction](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-tree-construction) at Google's Web Fundamentals.

Instructor Notes
Check out the [demo page](http://udacity-crp.herokuapp.com/cssom.html) we're using in this example: compare the HTML to the resulting render tree and what you see on the screen. Neat, right?
You can learn more about [Render Tree construction](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-tree-construction) at Google's Web Fundamentals.

### Measure First --> then optimize as needed. 

Instructor Notes
Learn more about [saving and loading timeline recordings](https://developer.chrome.com/devtools/docs/timeline#saving-and-loading-recordings).
Download the [timeline trace](https://raw.githubusercontent.com/igrigorik/udacity-webperf/master/assets/cssom-timeline.json) used in this video.

Instructor's notes:
Why does the browser match CSS selectors from right to left? Check out this [great discussion on StackOverflow](http://stackoverflow.com/questions/5797014/why-do-browsers-match-css-selectors-from-right-to-left).

## 1/19/2015

Instructor Notes

Ilya: I know what you're thinking... "Wait a second, but the header is not the same for each user, because once you sign-in, you have the customized icon and navigation in top right corner!" ... right?

Well, this optimization still works! The Google search team has built an optimized service that is able to retrieve and build the customized header that includes the custom user information in mere milliseconds after the request first arrives at the server - as a result, they can flush the header back to the client even before they have parsed the search query. Alternatively, many sites use a static header and then use JavaScript to fill in the custom bits - this allows them to serve the same header regardless of user status.

In either case, the important part is that the server does not have wait to render the full response before returning it to the client. The sooner you can flush some data, the sooner the browser can start building the DOM, and discover and dispatch requests for other critical resources.

See [Flushing the Document Early](http://www.stevesouders.com/blog/2009/05/18/flushing-the-document-early/) to learn more.

Also, check out [Chunk Scatter](http://blog.cowchimp.com/chunk-scatter-http-chunked-response-analysis-tool/), a fantastic tool for visualizing chunked HTTP responses.

Links from Lesson 1 - the Critical Rendering Path
[What is the Document Object Model?](http://www.w3.org/TR/DOM-Level-2-Core/introduction.html)
[How the Document Object Model is constructed](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/constructing-the-object-model#document-object-model-dom)
[The HTML5 Specification](http://www.w3.org/TR/html5/)

"We used curl using Terminal on a Mac to download the HTML. If you're a Windows user and would like to try [curl](http://www.cyberciti.biz/faq/mac-os-x-terminal-download-file/), check out this [StackOverflow discussion](http://superuser.com/questions/344927/powershell-equivalent-of-curl)."

