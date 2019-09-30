# Test Parcel Webmanifest Icons

This shows the result of a `site.webmanifest` file that is at the path `static/site.webmanifest` built with parcel@1.12.3. The file path in the "icons" value contains no path, but the image itself is placed in the root of th dist folder.

I am seeing that Mobile Safari tries to find the image relative to the manifest file's path at `static/` and it fails because the images actually get placed in the root directory of the build.

According to the examples ([Google Developers Web App Manifest](https://developers.google.com/web/fundamentals/web-app-manifest), [MDN Web Manifest](https://developer.mozilla.org/en-US/docs/Web/Manifest)) for the manifest of a PWA, the "icons" file paths should include the paths to files.

NOTE: this is at odds with how Chrome extension manifests should reference icons e.g., [MDN WebExtensions icons docs](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/manifest.json/icons) says, "It consists of key-value pairs of image size in px and image path relative to the root directory of the extension."

As a workaround, it appears I can either (1) move the `site.webmanifest` file to the root directory or (2) add a HACK into the build script to copy the icons files to the proper directory.
