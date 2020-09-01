# avif / webp support for css background images

> A fork of [vitaly-bobrov/webp-detect](https://github.com/vitaliy-bobrov/webp-detect) pure javascript (no jQuery) lightweight library that checks browser WebP format support and adds 'webp' class to html element if supported.
> What is WebP? - [Answer](https://developers.google.com/speed/webp/)

## what is it?
A small script that checks if a browser is able to display **webp** and/or **avif** images and adds css 
classes (`.webp`, `.avif`) to the `<html>` element.

**Webp** and **avif** detection is stored in the `sessionStorage` object, and only executed on the first session impression.
When the user updates his browser and become capable of webp and or avif your code will automatically enhance the user experience.


## setup
copy all contents of [avif-webp.min.js](./avif-webp.min.js) into an inline script in your page and this script 
will add `.webp` and or `.avif` to your `<html>` element.

put this inline script **before** any css contents (inline or `<link rel="stylesheet">`) to avoid css images flashing
when this script adds its css classes to the `<html>` element.

```html
<!doctype html>
<html lang="en">
  <head>
    …
    <script>!function(document){"use strict";var webpImage,…</script>
    <link rel="stylesheet" href="my-styles.css">
    …
  </head>
  …
</html>
```

## css usage
```css
.my-class {
  background-image: url('image.jpg');
}
.webp .my-class {
  background-image: url('image.webp');
}
.avif .my-class {
  background-image: url('image.avif');
}
/* retina support */
@media
    screen and (-webkit-min-device-pixel-ratio: 2),
    screen and (min-resolution: 192dpi),
    screen and (min-resolution: 2dppx) {
    .my-class {
      background-image: url('image@2x.jpg');
    }
    .webp .my-class {
      background-image: url('image@2x.webp');
    }
    .avif .my-class {
      background-image: url('image@2x.avif');
    }
}
```
