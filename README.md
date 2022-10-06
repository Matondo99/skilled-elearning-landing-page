# Frontend Mentor - Skilled e-learning landing page solution

This is a solution to the [Skilled e-learning landing page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/skilled-elearning-landing-page-S1ObDrZ8q). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
    - [Desktop View](#desktop-view)
    - [Tablet View](#tablet-view)
    - [Mobile View](#mobile-view)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Issue to fix](#issue-to-fix)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- [x] View the optimal layout depending on their device's screen size
- [x] See hover states for interactive elements

### Screenshot

#### Desktop View

![Desktop-Screenshot](./solution/Desktop-Screenshot.png)

___

#### Tablet View

![Tablet-Screenshot](./solution/Tablet-Screenshot.png)

___

#### Mobile View

![Mobile-Screenshot](./solution/Mobile-Screenshot.png)

### Links

- Solution URL: [Add solution URL here](https://github.com/Matondo99/skilled-elearning-landing-page)
- Live Site URL: [Add live site URL here]( https://matondo99.github.io/skilled-elearning-landing-page/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow

### What I learned

- Learned how to apply the `picture` element in a really complex use case. It seems to work until I set desktop site on a mobile screen, then it screws my design. Still lot to learn.

```html
<picture>
  <source media="(min-width: 800px)"
          type="image/webp"
          srcset="assets/image-hero-desktop.webp 1x,
                  assets/image-hero-desktop@2x.webp 2x">
  <source media="(min-width: 800px)"
          srcset="assets/image-hero-desktop.png 1x,
                  assets/image-hero-desktop@2x.png 2x">
  <source media="(min-width: 500px)"
          type="image/webp"
          srcset="assets/image-hero-tablet.webp 1x,
                  assets/image-hero-tablet@2x.webp 2x">
  <source media="(min-width: 500px)"
          srcset="assets/image-hero-tablet.png 1x,
                  assets/image-hero-tablet@2x.png 2x">
  <source type="image/webp"
          srcset="assets/image-hero-mobile.webp 1x,
                  assets/image-hero-mobile@2x.webp 2x">
  <img class="hero_img" src="assets/image-hero-mobile.png"
        alt="young lady pondering in front of her laptop while drinking a cup of coffee"
        srcset="assets/image-hero-mobile@2x.png 2x">
</picture>
```

- Instead of changing every single color links' colors for hover purposes, I just wrapped a pale veil over every button. The challenge was to apply pseudo-class to pseudo-element:

```css
.btn::before {
  content: "";
  width: 100%;
  height: 100%;
  border-radius: 100px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: rgba(255,255,255, .0);
  transition: background-color 300ms ease-out 100ms;
}

.btn:focus::before,
.btn:hover::before  {
  background-color: rgba(255,255,255, 0.42);
}
```

### Issue to fix

It was excruciatingly difficult to fit the hero image at the right place across all screen sizes with absolute position. As a result:

- header bottom padding is huge on landscape view;
- mobile hero image is displayed on mobile screen when desktop site is set.

### Useful resources

- [Responsive Images 101 by Jason Grigsby](https://cloudfour.com/thinks/responsive-images-101-definitions/) Published on March 16th, 2015 - This helped me to manage the plethora of possibilities inside the `picture` element between **art direction**, **screen resolution** and more. Lenghty article, but worth any second you invest in.

- [How to make a hover effect for pseudo elements?](https://stackoverflow.com/questions/8874326/how-to-make-a-hover-effect-for-pseudo-elements) - You can change the pseudo-element based on hover of the parent, **JSFiddle DEMO**.

## Author

- Frontend Mentor - [@Matondo99](https://www.frontendmentor.io/profile/Matondo99)
