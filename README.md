# Frontend Mentor - Fylo data storage component solution

This is a solution to the [Fylo Data Storage Component Challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/fylo-data-storage-component-1dZPRbV5n).

## Table of contents

- [Overview](#overview)
  - [The Challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I Learned](#what-i-learned)
  - [Useful Resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### The Challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size.

### Screenshots

- Desktop View

![Desktop-View](/screenshots/desktop-view.png)

- Mobile View

![Mobile-View](/screenshots/mobile-view.png)

### Links

- Solution URL: [Fylo Data Storage Component](https://flyo-data-storage-component.netlify.app/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- CSS variables
- CSS flexbox
- Mobile-first workflow

### What I learned

Working out my way through this project taught me many things such as how CSS variables can be used effeciently, how media queries can be used to effectively change background images depending upon screen size, how positions work in CSS, how units such as rem, em and % work, the most newest of all is the progress bar styling and then comes the stylish tooltip design in the desktop view.

Below are some example codes of the things I learned during this project:

- #### Media Queries

  - Suppose we have 2 background images each respectively for mobile size (375px) and desktop size (1440px). Let us name the background for mobile be "mobile-bg.svg" and for desktop let it be "desktop-bg.svg", the code below shows how can we effeciently change backgrounds on changing screen sizes.

  ```css
  body {
    /* setting up consistent background properties */
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
  }
  /* mobile */
  @media screen and (max-width: 400px) {
    body {
    background-image: url("/mobile-bg.svg");
    }
  }
  /* mobile ends */

  /* desktop */
  @media screen and (min-width: 1025px) {
    body {
      background-image: url("/desktop-bg.svg");
    }
  }
  /* desktop ends */
  ```

- #### CSS Variables

  - Suppose we have 2 or more than 2 variables having same values, instead of repeating the values for each variable we can assign a variable to another variable.

  ```css
  :root {
    --variable1: value;
    --variable2: var(--variable1);
  }
  ```

- #### Progress Bar Styling

  - This was the most confusing part of the project, as mozilla doesn't support much of the features that other browsers support, but with few experiments and modifications I was successfully able to style the progress bar according to the project. Below is the exact code I used to style my progress bar.

  ```css
  /* progress tag styling */
  /* general styling */
  progress[value] {
    appearance: none; /* reset the default appearance */
    border: none; /* removing default borders */
    height: 15px;
    width: 100%;
    margin-top: 20px;
    margin-bottom: 5px;
    background-color: var(
      --progressBarBG
    ); /* --progressBarBG: hsl(229, 57%, 11%) */
    border-radius: 10px;
  }
  /* general styling ends */

  /* bar value styling */
  progress[value]::-moz-progress-bar {
    border-radius: 10px;
    background-image: var(
      --progressBarCol
    ); /* --progressBarCol: linear-gradient(90deg ,hsl(6, 100%, 80%), hsl(335, 100%, 65%));*/
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
  }
  /* bar value styling ends */
  /* progress tag styling ends */
  ```

- #### Stylish Tooltip Design

  - Below I add the code that helped me in designing a stylish tooltip for the left data container when viewed in a desktop view

  ```css
  /* callout styling */
  div.left-data-container:after {
    content: "";
    position: absolute;
    height: 0;
    width: 0;
    left: 79%;
    border-bottom: 40px solid var(--leftDataContainerBG); /* --leftDataContainerBG: hsl(0,  100%, 100%); */
    border-right: 40px solid transparent;
    transform: rotate(180deg);
  }
  /* callout styling ends */
  ```

### Useful resources

- [Web.dev](https://web.dev/optimize-css-background-images-with-media-queries/) - This article by [Demian Renzulli](https://web.dev/authors/demianrenzulli/) helped me with the media query usage especially when background images are concerned. I really liked this and will use it going forward.

- [CSS Tricks](https://css-tricks.com/html5-progress-element/) - This is an amazing article by [Pankaj Parashar](https://css-tricks.com/author/pankajparashar/) which helped me finally understand the styling of progress bar. I'd recommend it to anyone new to this concept.

- [Coding Artist](https://www.youtube.com/watch?v=tTNxykEAPpA) - This youtube video familiarised me with the concept of the callout or tooltip design.

- [Codepen](https://codepen.io/depthdev/pen/wiIsv) - This codepen by [Adam](https://codepen.io/depthdev) helped in styling the callout for my left data container.

## Author

- Name: Vikramaditya Pratap Singh
- Frontend Mentor - [@d02ev](https://www.frontendmentor.io/profile/d02ev)

## Acknowledgments

- [freeCodeCamp](https://freecodecamp.org/) - For providing such a great and awesome platform to teach coding for free. They are the reason I am into web development.

- [Frontend Mentor](https://frontendmentor.io/) - For providing such great and free projects which can also be used in portfolios, resume etc.

- [CSS Tricks](https://css-tricks.com/) - For such a great platform with such talented and experienced developers sharing their idea and tricks from all around the world.

- [CODEPEN](https://codepen.io/) - For such a great place where artists showoff their skills and talents, clearing tricky concepts for beginners.
