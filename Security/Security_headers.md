# Security headers

### [X-Powered-By](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)

This header exposes what kind server (eg.  express) is being used.

> *Remove this header so that attackers won't get the info about the server used hence minimizing the chance to get exploited by any security vulnerability.*

### [Referrer-Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy)

This header contains website information from where it gets redirected.

> *Apply referrer policy as per requirement to prevent exposing more information while redirecting*

### [X-Content-Type-Options](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Content-Type-Options)

Earlier browser used to upgrade the content type (sniffing) of the requested item based on the content received. In order to control the sniffing, this header comes into play.

> *Apply sniffing to `nosniff` so that browser won't upgrade the content type by prediction*

### [X-XSS-Protection](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-XSS-Protection)

This header is for legacy browsers only to prevent any XSS attack. However, modern browsers are efficient enough to prevent any XSS attack since inline scripts are blocked by default in modern browsers..

> *This header is not required if legacy browser support is not intended. Don't enable `unsafe-inline` in CSP header*

### [HTTP Strict Transport Security header (HSTS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Strict-Transport-Security)

This header upgrades HTTP request to HTTPS on first time and post that browser will by default stop any request that's not HTTPS.

If first-time also user needs to be prevented from accessing HTTP request, the website has to be registered at `hstspreload.org`.

> *Use it to have a request from secure protocall. We can have a custom redirection at our side of code to redirect based on protocall `x-forwarded-proto` of it's not https*
