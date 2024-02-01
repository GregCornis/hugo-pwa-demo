# Hugo PWA Demo

This is a simple demo  to illustrate how to turn a [Hugo Website](https://gohugo.io/) into a [Progressive Web App](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps).

This means that your website can be installed by you users, on the desktop (Chromium only) or their mobiles, and even be used offline. That's pretty powerful, especially for static websites built with Hugo!

## To reproduce

There are just a few steps to take:
 1. Add a `manifest.json` file to `/static`, which describes your PWA. [Here](https://developer.mozilla.org/en-US/docs/Web/Manifest) is a more thorough description of the file and its content.
 2. Add a link to the manifest in _all_ your HTML pages. The easiest is to add it to `layouts/partials/head-additions.html` as done here
 3. Add a [Service Worker](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API), which will handle the behavior of the app. Here, the worker is simply responsible for caching the pages, and serving them when the app is offline. Credits to [offline-first-sw](https://github.com/wildhaber/offline-first-sw/blob/master/sw.js)
 4. Register the worker. See the `<script>` in `head-additions.html`
