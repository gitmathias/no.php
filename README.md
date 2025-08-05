# Simple Reverse Proxy in PHP

Forked from https://github.com/michaelfranzl/no.php

Thanks or the head-start!

## Updated to support

Authorization headers: Add a rewrite rule to enable.

```
        # Point all traffic to reverse proxy
        RewriteEngine On
        RewriteRule .* - [E=HTTP_AUTHORIZATION:%{HTTP:Authorization}]
        RewriteRule . no.php [L]
```

CORS support: Pass through CORS headers to target

etc.

# Installation

1. Create a virtual host - use `public` as the document root
1. Point all traffic to the base script using ModRewrite
1. Configure the environment (see source code)
1. Use SSL - self-signed or otherwise if you own your proxied domain

# Customize

This one little script can be modified depending on your needs...

 - Push certain routes to different hosts
 - Only proxy certain routes
 - Change headers for certain routes
 - etc.

