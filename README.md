# webpageperformancebestpractices

## Urls
- https://getbootstrap.com/docs/4.0/examples/
- https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript
## Ngnix

https://www.techrepublic.com/article/how-to-configure-gzip-compression-with-nginx/
```
gzip on;
gzip_vary on;
gzip_min_length 10240;
gzip_proxied expired no-cache no-store private auth;
gzip_types text/plain text/css text/xml text/javascript application/x-javascript application/xml;
gzip_disable "MSIE [1-6]\.";
```

Here's an explanation for the configuration, line by line:

- gzip on; enables gzip compression

-gzip_vary on:tells proxies to cache both gzipped and regular versions of a resource
- gzip_min_length 1024; informs NGINX to not compress anything smaller than the defined size
- gzip_proxied ; compress data even for clients that are connecting via proxies (here we're enabling compression if: a response header includes the "expired", "no-cache", "no-store", "private", and "Authorization" parameters)
- gzip_types enables the types of files that can be compressed
- gzip_disable "MSIE [1-6]\.";  disable compression for Internet Explorer versions 1-6
## Async Javascript

By default all JavaScript is parser blocking. Because the browser does not know what the script is planning to do on the page, it assumes the worst case scenario and blocks the parser. A signal to the browser that the script does not need to be executed at the exact point where it's referenced allows the browser to continue to construct the DOM and let the script execute when it is ready; for example, after the file is fetched from cache or a remote server.

To achieve this, we mark our script as async:
```
    <script src="app.js" async></script>
```
