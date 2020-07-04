# webpageperformancebestpractices

## Urls
- https://getbootstrap.com/docs/4.0/examples/
- https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript

## Async Javascript

By default all JavaScript is parser blocking. Because the browser does not know what the script is planning to do on the page, it assumes the worst case scenario and blocks the parser. A signal to the browser that the script does not need to be executed at the exact point where it's referenced allows the browser to continue to construct the DOM and let the script execute when it is ready; for example, after the file is fetched from cache or a remote server.

To achieve this, we mark our script as async:

    <script src="app.js" async></script>
