<body style="font-family: serif"></body>

# Personal Questions

This file records my questions during my development experience.

## 1 - Proxy Problem in React

When I use `fetch` to fetch data from an url. When the url is `http://student@csi420-01-vm7.ucd.ie`,
error  `Failed to execute 'fetch' on 'Window': Request cannot be constructed from a URL that includes credentials: http://student@csi420-01-vm7.ucd.ie/all_questions`
will pop out. To fix this problem, I have to add `"proxy": "http://student@csi420-01-vm7.ucd.ie"` to my package.json
file to config proxy.

Yet, when I accessed url `https://catfact.ninja/fact`, the above configuration is unnecessary.

### 1.1 - My thoughts about this error

Firstly, http protocol has less security compared to https protocol*. Therefore, browsers are stricter to http url.

*HTTP:It is an insecure protocol as data is transmitted in plain text without encryption. This means that sensitive
information (such as usernames, passwords, etc.) can be intercepted and eavesdropped during transmission.
*HTTPS: HTTPS builds on HTTP by adding a Secure Sockets Layer (SSL)/Transport Layer Security (TLS) to encrypt data,
ensuring the security of data during transmission. Therefore, HTTPS provides higher security, especially for websites
that handle sensitive user information.