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

