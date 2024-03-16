<body style="font-family: serif"></body>

# HTTP Credentials Issue

## 1 - Problem Context
Developing the react front-end for my final project in college (UCD final project). I need to fetch data from provided url `http://student@csi420-01-vm7.ucd.ie`


## 2 - Problem Statement
When I use `fetch` to fetch data from an url. When the url is `http://student@csi420-01-vm7.ucd.ie`,
error  `Failed to execute 'fetch' on 'Window': Request cannot be constructed from a URL that includes credentials: http://student@csi420-01-vm7.ucd.ie/all_questions`
will pop out. To fix this problem, I have to add `"proxy": "http://student@csi420-01-vm7.ucd.ie"` to my package.json
file to config proxy.

Yet, when I accessed url `https://catfact.ninja/fact`, the above configuration is unnecessary.

## 3 - Answer

Firstly, http protocol has less security compared to https protocol.

*   HTTP:It is an insecure protocol as data is transmitted in plain text without encryption. This means that sensitive
information (such as usernames, passwords, etc.) can be intercepted and eavesdropped during transmission.

*   HTTPS: HTTPS builds on HTTP by adding a Secure Sockets Layer (SSL)/Transport Layer Security (TLS) to encrypt data,
ensuring the security of data during transmission. Therefore, HTTPS provides higher security, especially for websites
that handle sensitive user information.

 Therefore, browsers are stricter to http url. They restrict `http://student@csi420-01-vm7.ucd.ie` to prevent exposing
 sensitive information (maybe since they mistakenly interpret `@` as an attempt at basic authentication).

Solution:
- Use HTTPS
  - yet, this way needs to apply to an **SSL Certificate**.
- Avoid Including Credentials in the URL
  - since the url is provided and determined by UCD, I cannot use this approach.
- Use a Proxy: using a proxy can be a workaround. However, it's essential to be cautious when handling credentials and 
consider the security implications (this approach did not solve security problem).
  - Adding `"proxy": "http://student@csi420-01-vm7.ucd.ie"` to package.json. Is such way hide sensitive contents
  in request?

