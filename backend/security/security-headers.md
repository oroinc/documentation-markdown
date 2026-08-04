<a id="backend-security-bundle-security-headers"></a>

# HTTP Security Response Headers

HTTP security headers help protect websites and their users from online threats and vulnerabilities. Web servers send these headers with HTTP responses to instruct browsers on how to handle certain aspects of the web page.

## NelmioSecurityBundle

The <a href="https://github.com/nelmio/NelmioSecurityBundle" target="_blank">NelmioSecurityBundle</a> provides additional security features for your Symfony application.
This bundle lets you define the following security headers:

* Content-Security-Policy (CSP) - Defines a set of rules that control which resources (e.g., scripts, stylesheets, images) a web page is allowed to load.
* Strict-Transport-Security (HSTS) - Enforces the use of secure, encrypted connections (HTTPS) by instructing the browser to interact with the website only over secure connections.
* X-Frame-Options - Controls whether a browser should be allowed to render a page in a frame or iframe. This helps prevent clickjacking attacks.
* X-Content-Type-Options - Prevents browsers from interpreting files as a different MIME type than declared by the server. This helps mitigate attacks that rely on tricking the browser into misinterpreting content.
* X-XSS-Protection - Enables or disables the browser’s built-in XSS protection mechanism.
* Referrer-Policy - Specifies how much information about the referring URL should be included in the HTTP Referer header when navigating from one page to another.

## OroSecurityBundle

In addition to the wide range of security headers supported by the NelmioSecurityBundle, OroSecurityBundle lets you set the <a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Permissions-Policy" target="_blank">Permissions-Policy</a> header.

*config/config.yml*
```yaml
 oro_security:
     permissions_policy:
         enable: true
         directives:
             accelerometer: deny
             autoplay: allow_self
             fullscreen: allow_all
             geolocation:
                 - allow_self
                 - 'http://trusted-domain.ltd'
```

<!-- Frontend -->
