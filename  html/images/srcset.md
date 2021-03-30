### Responsive Images

#### Supporting High-density Screens

Terminology

- Physical resolution - the actual number of pixel in a device
- Logical resolution - how a device behave (CSS is based on logical resolution)
- Device Pixel Ratio (DPR) - Physical / Logical
- High Density Screen - a screen with DPR greater than 1

<br>

`srcset` attribute provides high quality version of an image for high-density screen.

```html
<body>
  <img
    src="images/programming.jpg"
    alt="A woman using a laptop while sitting on the floor"
    class="skills"
    srcset="
      images/programming.jpg    1x,
      images/programming@2x.jpg 2x,
      images/programming@3x.jpg 3x
    "
  />
</body>
```

#### Resolution Switching

Technique used to provide different images for various devices like laptops, tablets and mobile phones.

```html
<body>
  <img
    src="images/programming.jpg"
    alt="A woman using a laptop while sitting on the floor"
    class="skills"
    srcset="
      images/programming.jpg     400w,
      images/programming@2x.jpg  800w,
      images/programming@3x.jpg 1200w
    "
    sizes="
      (max-width: 500px) 100vw,
      (max-width: 700px) 50vw,
      33vw
    "
  />
</body>
```

<br>

#### Using Modern Image Format

We may use a combination of `<picture>` and `<source>` tags, and `webp` image file type.

```html
<body>
  <picture>
    <source type="image/webp" srcset="images/programming.webp" />
    <source type="image/jpg" srcset="images/programming.jpg" />
    <img
      src="images/programming.jpg"
      alt="A woman using a laptop while sitting on the floor"
    />
  </picture>
</body>
```

We still need to use the `<img>` tag to provide the `alt` text, and serves as a fallback in case the browser doesn't support the `<picture>` and `<source>` tags.

<br>

#### Art Direction

We may want to display a different version of an image on different image display sizes. A good example is when we have a landscape shot with a person in the middle, it may look good at widescreen devices like laptop but the image is shrunk down in mobile devices. To solve this, we may provide a small portrait version which zooms in the person.

```html
<body>
  <picture>
    <source
      media="(max-width: 799px)"
      srcset="images/programming-400w-close-portrait.jpg"
    />
    <source media="(min-width: 800px)" srcset="images/programming-800w.jpg" />
    <img
      src="images/programming-800w.jpg"
      alt="A woman using a laptop while sitting on the floor"
    />
  </picture>
</body>
```

- the `<source>` elements include a `media` attribute that contains media condition as with the `scrset` example.
- these conditions are tests that decide which image to display
- the first condition that returns true will be displayed
- we still need to provide the `<img>` element with `<src>` and `<alt>`, otherwise, no image will appear, and this also serves as a fallback if no media conditions return true or the browser does not support the `<picture>` element.
