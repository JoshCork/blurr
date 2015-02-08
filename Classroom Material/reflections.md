
# Lesson 2 Material

## 2/8/2015 - Final CRP Project Notes

![Optimizing your portfolio page](https://www.evernote.com/shard/s2/sh/4012c8b5-a931-4d0a-a7e0-57c98d4a1b49/601224f1fce874fa297d42a8758ab356/deep/0/Classroom---Udacity.png "Final Project: Optimize your Portfolio Page")

Instructor Notes

You can find the portfolio GitHub repo [here](https://github.com/udacity/frontend-nanodegree-mobile-portfolio) and a live version of Cameron's portfolio [here](http://cameronwp.github.com/udportfolio).

Using GitHub

If you are not familiar with Git and GitHub, the GitHub help pages are a great place to start. In particular, check out the following guides: setup Git, fork a repo, hosting with GitHub Pages, and the references section to learn more.

Check out the [course materials page](https://www.udacity.com/wiki/ud884) for project tips, tricks and inspiration.

## 2/6/2015 - Optimizing the CRP

Example CRP Diagram:
![Example CRP Diagram](https://www.evernote.com/shard/s2/sh/9cee629b-008d-4417-b682-940b166f2126/a5925f74e06d5bf82b6634ad0887a684/deep/0/Classroom---Udacity.png "Example CRP Diagram")

## 2/5/2015 - Optimizing the CRP

Instructor Notes

To learn more about the preload scanner, check out "[How the Browser Pre-loader Makes Pages Load Faster](http://andydavies.me/blog/2013/10/22/how-the-browser-pre-loader-makes-pages-load-faster/)".

Instructor Notes

Review the [Critical Rendering Path performance patterns](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp#performance-patterns) on Web Fundamentals.

Instructor Notes

Learn more about [optimizing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path)
Review the [Critical Rendering Path performance patterns](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp#performance-patterns)
Check out the PageSpeed mobile analysis documentation on guidance for [how to deliver a page that can be rendered in one second or less](https://developers.google.com/speed/docs/insights/mobile). To learn more about TCP Slow Start, check out Ilya's [book, High Performance Browser Networking](http://hpbn.co/).

At the end of the course, you'll find a [tough bonus question](https://www.udacity.com/course/viewer#!/c-ud884/l-1469569174/e-1524418574/m-1524418575) on TCP slow start. Give it a shot if you want to learn the math behind calculating how long files will take to download with TCP slow start.

![Great overview screenshot on patterns](https://www.evernote.com/shard/s2/sh/83e37fb4-14b2-4534-a5c5-e01d2edf5c18/9bc675b97cd3d60edba40b192199a9d7/deep/0/Classroom---Udacity.png "Optimization Patterns")

The above table illustrates the savings provided by GZIP compression for a few of the most popular JavaScript libraries and CSS frameworks. The savings range from 60 to 88%, and note that the combination of minified files (identified by “.min” in their filenames), plus GZIP, offers an even larger win.
Apply content-specific optimizations first: CSS, JS, and HTML minifiers.
Apply GZIP to compress the minified output.
The best part is that enabling GZIP is one of the simplest and highest payoff optimizations to implement - sadly, many people still forget to implement it. Most web servers will compress content on your behalf, and you just need to verify that the server is correctly configured to compress all the content types that would benefit from GZIP compression.

TL;DR
GZIP performs best on text-based assets: CSS, JavaScript, HTML
All modern browsers support GZIP compression and will automatically request it
Your server needs to be configured to enable GZIP compression
Some CDNs require special care to ensure that GZIP is enabled

In short, as a first step in optimizing the efficiency of your assets, build an inventory of the different content types and consider what kinds of content-specific optimizations you can apply to reduce their size - doing so can yield significant savings! Then, once you’ve figured out what they are, automate these optimizations by adding them to your build and release processes - that’s the only way you can guarantee that the optimizations will stay in place.

Instructor Notes

Learn more about [resource minification](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer#minification-preprocessing--context-specific-optimizations)
Learn more about [text compression with GZip](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer#text-compression-with-gzip)
Learn more about [HTTP caching](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching)

When we talk about “optimizing the critical rendering path,” to a large degree we’re talking about understanding and optimizing the dependency graph between HTML, CSS, and JavaScript.

JavaScript can query and modify DOM and CSSOM.
JavaScript execution blocks on CSSOM.
JavaScript blocks DOM construction unless explicitly declared as async.

When declaring your stylesheet assets, pay close attention to the media type and queries, as they will have big performance impact on the critical rendering path!

"CSS is a render blocking resource, get it down to the client as soon and as quickly as possible to optimize the time to first render!"

However, what if we have some CSS styles that are only used under certain conditions, for example, when the page is being printed, or being projected onto a large monitor? It would be nice if we didn’t have to block rendering on these resources!
CSS “media types” and “media queries” allow us to address these use-cases:
<link href="style.css" rel="stylesheet">
<link href="print.css" rel="stylesheet" media="print">
<link href="other.css" rel="stylesheet" media="(min-width: 40em)">

# Lesson 1 Material

## 2/5/2015
The HTML specification dictates specific conditions for each and every event: when it should be fired, which conditions should be met, and so on. For our purposes, we’ll focus on a few key milestones related to the critical rendering path:
domInteractive marks when DOM is ready.
domContentLoaded typically marks when both the DOM and CSSOM are ready.
If there is no parser blocking JavaScript then documentContentLoaded will fire immediately after domInteractive.
domComplete marks when the page and all of its subresources are ready.

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

