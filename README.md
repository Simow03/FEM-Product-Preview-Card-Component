# Frontend Mentor - Product preview card component solution

This is a solution to the [Product preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/product-preview-card-component-GO7UmttRfa). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover and focus states for interactive elements

### Screenshot

![Screenshot for the project](./images/Screenshot%202023-03-24%20014133.png)

### Links

- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

### Built with

- HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Some CSS resets
- Mobile-first workflow
- Media-Queries

### What I learned

This project brought a lot of interesting challenges, which really helped me to push off my limits and look further for more css tips and tricks that I used in this project.

Starting off with the picture shown in the product card, it was actually two different versions, one for mobile and one for desktop.
The point was to change the images when switching between mobile and desktop and actually u can do it without alot of processing ..

like this :

```html
<picture class="product-img">
        <source srcset="./images/image-product-desktop.jpg" media="(min-width: 700px)">
        <img src="./images/image-product-mobile.jpg" alt="Gabrielle-Chanel-perfume">
</picture>
```
So the ```<picture>``` tag contains the two versions of the picture itself, and the attribute ```media="()"``` in the ```<source>``` working actually like a media query whitch tells the picture to switch to the version that in "srcset" when it hits the width of 700px; Otherwise it will show the picture in the ```<img>``` tag.

Another useful thing is the "screen-reader only" concept, basically it's an additional feature that allows people using the screen reader to have a bigger understanding of what is going on the actual page. 

In this project, I used it to differentiate between the prices with the following method :

```html
<p class="product-current-price">
        <span class="sr-only">current price</span>
        $149.99
</p>
```

```css
.sr-only:not(:focus):not(:active) {
    clip: rect(0 0 0 0);
    clip-path: inset(50%);
    height: 1px;
    overflow: hidden;
    position: absolute;
    white-space: nowrap;
    width: 1px;
}
```
What this does is the ```<span>```  is still readable for the screen reader but it's not shown on the screen. So that you can keep up between the look and the utility.

This is a very interesting topic, can be so useful in much bigger sites(There is a link in [Useful resources](#useful-resources) part for a more detailed blog about the hidden content!)

### Continued development

After this project I'm really interested in the screen-reader feature and I will still be looking for more in depth details.
Also I will focus more on the grid methods to make layouts, because it seems somehow more consistent than flexboxes. 
And always "No matter how much you learned, there is always more .." and that's why we love to code ! 

### Useful resources

- [Josh-Comeau's Costum Css Reset](https://www.joshwcomeau.com/css/custom-css-reset/) - Some on point Css resets that makes life easier!.
- [Inclusively Hidden](https://www.scottohara.me/blog/2017/04/14/inclusively-hidden.html) - this blog helps me to get a wider vision about the screen-reader only topic.

## Author

- Frontend Mentor - [@Simow03](https://www.frontendmentor.io/profile/Simow03)
- Twitter - [@mx7staali](https://twitter.com/mx7staali)

## Acknowledgments

This is just a quick thanks to [@ecemgo](https://www.frontendmentor.io/profile/ecemgo) for showing me the trick of the ```min-height: 100vh;``` which helps to center and makes the page a lot easier to compare in frontend mentor mode.
