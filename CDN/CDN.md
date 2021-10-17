# What is CDN?
- At its core, a **CDN** is a *network of servers linked together* with *the goal of delivering content* as *quickly, cheaply, reliably, and securely* as possible.

- **CDNs** store *a cached version of your website content* in *multiple geographical locations* around the world, which are known as **points of presence** (PoPs). *These PoPs* will *contain their own caching servers* and will be *responsible for delivering that content in the user’s location*.

# How it works:
- For most CDNs, *each request for content* will cause the *end user to be mapped to an optimally-located CDN server* and the *server will respond with the cached (pre-saved) version of the requested files*. *If it fails to locate the files*, it will *look for the content on the other servers in the CDN platform and send the response to the end user*.

- However, *when content is unavailable or stale*, the **CDN** will *act as a request proxy to the origin server* and *store the fetched content to serve future requests*.