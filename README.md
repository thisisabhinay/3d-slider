# CSS-Only 3D Slider

This project demonstrates a pure CSS implementation of a 3D slider, showcasing the power of modern CSS techniques for creating engaging, interactive user interfaces without JavaScript.

## Table of Contents

1. [Overview](#overview)
2. [File Structure](#file-structure)
3. [How It Works](#how-it-works)
4. [Key CSS Techniques](#key-css-techniques)
5. [Responsive Design](#responsive-design)
6. [Browser Compatibility](#browser-compatibility)
7. [Customization](#customization)

## Overview

The 3D slider creates an impressive rotating carousel effect using only HTML and CSS. It features:

- A circular arrangement of images in 3D space
- Automatic rotation animation
- Responsive design that adapts to different screen sizes
- Custom typography and layout

## File Structure

```
├── index.html
├── css/
│   ├── base.css
│   └── slider.css
├── images/
│   ├── dragon_1.jpg
│   ├── dragon_2.jpg
│   └── ...
└── fonts/
    ├── ICARubrikBold.woff
    ├── Poppins-Regular.woff
    └── Poppins-Bold.woff
```

- `index.html`: Main HTML structure
- `base.css`: General styling and background setup
- `slider.css`: 3D slider specific styles and animations

## How It Works

1. **HTML Structure**: The slider is created using nested `<div>` elements. Each image is contained within an `.item` div inside the main `.slider` container.

2. **3D Space**: The `.slider` container establishes a 3D space using CSS `transform-style` and `perspective` properties.

3. **Item Positioning**: Each `.item` is positioned in a circular arrangement using CSS `transform` with `rotateY()` and `translateZ()`.

4. **Animation**: The entire slider rotates using a CSS `@keyframes` animation, creating the carousel effect.

## Key CSS Techniques

### 3D Space Setup

```css
.banner .slider {
  transform-style: preserve-3d;
  transform: perspective(62.5rem);
}
```

This creates a 3D space for child elements.

### Item Positioning

```css
.banner .slider .item {
  transform: rotateY(calc((var(--position) - 1) * (360 / var(--quantity)) * 1deg))
             translateZ(34.38rem);
}
```

This positions each item in a circular arrangement. The `--position` and `--quantity` CSS variables allow for dynamic positioning.

### Rotation Animation

```css
@keyframes autoRun {
  from { transform: perspective(62.5rem) rotateX(-12deg) rotateY(0deg); }
  to { transform: perspective(62.5rem) rotateX(-12deg) rotateY(360deg); }
}
```

This animation rotates the entire slider, creating the carousel effect.

## Responsive Design

The slider adapts to different screen sizes using media queries:

- On screens smaller than 1024px, the slider size and positioning are adjusted.
- On screens smaller than 768px, further size reductions are applied.

This ensures the slider looks good on devices ranging from desktop to mobile.

## Browser Compatibility

This slider uses modern CSS properties and should work well in recent versions of major browsers. However, some features may not be supported in older browsers. Consider using autoprefixers or fallbacks for maximum compatibility.

## Customization

To customize the slider:

1. Adjust the number of items by changing the `--quantity` variable in the HTML.
2. Modify the rotation speed by changing the animation duration in `.banner .slider`.
3. Alter the size and positioning of items by adjusting the `width`, `height`, and `translateZ` values.
4. Change the background and styling in `base.css` and `slider.css`.

Feel free to experiment with different images, colors, and layouts to make the slider fit your project's needs!

---

This project demonstrates the capabilities of modern CSS for creating complex, interactive UI elements without relying on JavaScript. It's a great starting point for learning about 3D transforms and animations in CSS.