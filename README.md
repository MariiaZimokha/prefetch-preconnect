# prefetch-preconnect

## Prefetch:

Prefetch is a low priority resource hint that allows the browser to **fetch resources in the background** that might be needed later, and **store them in the browser’s cache**. Once a page has finished loading it begins downloading additional resources and if a user then clicks on a prefetched link, it will load the content instantly. There are three different types of prefetching, link, DNS, and prerendering 


#### Link prefetching:

Link prefetching allows the browser to **fetch resources, store them in cache**, assuming that the user will request them. The browser looks for prefetch in the HTML or the HTTP header Link such as:

* **HTML**: `<link rel="prefetch" href="/uploads/images/pic.png">`
* **HTTP Header**: `Link: </uploads/images/pic.png>; rel=prefetch`

You need to be careful not to prefetch files too soon, or you can slow down the page.

In expample we want to prefetch image
`<link rel="prefetch" href="https://picsum.photos/id/870/500/500">`
Which means browser will download it as soon as possible and you can see it in the picture:

![prefetch](/assets/prefetch.png?raw=true)

#### DNS prefetching:

DNS prefetching allows the browser to **perform DNS lookups on a page in the background**.

DNS prefetching can be added to a specific URL by adding the rel="dns-prefetch" tag to the link attribute.

It will look like:

![dns-prefetch](/assets/dns-prefetch.png?raw=true)

## Preconnect:

Preconnect allows the browser to **setup early connections before an HTTP request is actually sent to the server**. This includes DNS lookups, TLS negotiations, TCP handshakes. This in turn eliminates roundtrip latency and saves time for users.


*“Preconnect is an important tool in your optimization toolbox… it can eliminate many costly roundtrips from your request path - in some cases reducing the request latency by hundreds and even thousands of milliseconds. - [Ilya Grigorik](https://www.igvita.com/2015/08/17/eliminating-roundtrips-with-preconnect/)”*
