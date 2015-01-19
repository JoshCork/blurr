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

