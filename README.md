# caddr.org browser extension

This browser extension adds an additional layer of security to caddr.org. 

When this extension is installed, even in the event that caddr.org gets compromised, an attacker would remain unable to manipulate the responses of the server to execute arbitrary JavaScript. 

## how it works

The extension uses the `declarativeNetRequest` API to modify the response headers of pages loaded from caddr.org. It sets the `Content-Security-Policy` header to a value that allows only scripts with the predefined hash to run and enforces the use of `'strict-dynamic'``. Any other script, even if it's injected maliciously by an attacker who has managed to compromise, will be blocked from executing.

