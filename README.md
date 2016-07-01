# download.servo.org
------------------

Style and layout based on [servo.org](https://github.com/servo/servo.org) and
used under MPL, bootstrap.css (c) Twitter and used under MIT license.

Current way to deploy changes to the download landing page is to ask an
administrator to manually upload them.

Assistance in improving the download page's appearance, accessibility, and
instructions is greatly appreciated!

The [Servo Contributing
Guide](https://github.com/servo/servo/blob/master/CONTRIBUTING.md) applies to
this repo.

## Subresource Integrity Hash Updating

If you update any of the static resources (e.g. a css file), you need to
regenerate the [SRI](https://www.w3.org/TR/SRI/) hash for that resource:

```sh
$ # Let's say you modified css/style.css
$ cat css/style.css | openssl dgst -sha512 -binary | openssl base64 -A
```
Copy the output, prepend it with "sha512-", and replace the corresponding
value for the integrity attribute on the HTML tag including that resource.

You can check if this worked by trying to load the page in a browser and
looking for console messages. (Note that Servo doesn't support this quite yet!)
