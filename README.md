# Frontend Mentor - Huddle landing page with alternating feature blocks solution

This is a solution to the [Huddle landing page with alternating feature blocks challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/huddle-landing-page-with-alternating-feature-blocks-5ca5f5981e82137ec91a5100). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

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


## Overview

### The challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size
- See hover states for all interactive elements on the page

### Screenshot

![](/images/Screenshot.png)


### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

### Built with

- Semantic HTML5 markup
- Flexbox
- SCSS 
- Desktop-first workflow
- BEM naming Methodology


### What I learned

This was a fairly straight forward challenge, i utilized the BEM naming Methodology in combination with scss as i found that it provided the best way to make my CSS styles modular and reusable. I also utilized a 4-1 scss architecture inspired by **Matthew Elsom** to keep all my scss files organized. Implementing such an architecture helped in the modularity and reusability of my styles as mentioned above. 

On of the code snippets that illustrate this modular and reuseable approach the best i believe is the mixin i created for my button styles:

```SCSS
@mixin button-base{
    color:$color-white;
    background:$main-btn-bg-color;
    font-weight: $font-weight-bold;
    display: inline-block;
    text-decoration:none;
    border-radius: 2em;
    padding: 0.75rem 4rem;
    text-align: center;
    transition: all 0.3s ease;
    box-shadow: 0 0.125rem 0.25rem rgb(0 0 0 / 8%);


    &:hover {
        background:lighten($main-btn-bg-color, 8%);
        transform: translateX(0rem) translateY(-0.3125rem);
    }

    &:active {
        background:lighten($main-btn-bg-color, 25%);
        transform: translateX(0rem) translateY(.125rem);
    } 
}
```

With this mixin i defined the base styles for my button with the active & hover states included . This base style is then altered based on specific button styles using BEM style class names:
```SCSS
.button--primary{
    @include button-base;
}

.button--secondary{
    @include button-base;
    background-color: $secondary-btn-bg-color;
    color: $secondary-btn-txt-color;

    @include respond-to(xs){
        padding: 0.75rem 1.5rem;
        width: 50%;
    }

    &:hover,&:active {
        background:lighten($secondary-btn-bg-color, 8%);
        color: $regent-gray;
    }
}
```

Another way i added to the modularity to this project was utilizing functional naming for my scss color variables. I first defined a color pallette with descriptive naming:

```SCSS
  // Descriptive naming
  $color-black:#000000;
  $color-white:#FFFFFF;
  $lily-white:#EBFBFF;
```


Then i used the descriptive named variables in new variables that described the  descriptively named color variables function in my style sheet:
```SCSS
  // Functional naming
  $border-color:$color-black;
  $header-bg-color:$lily-white;
  $main-btn-bg-color:$hot-pink;
```

This approach made my scss more readable, and reusable.


### Continued development

This project was good in practicing how to organize my scss efficiently. Although some organizational choices were a bot overkill for a simple landing page, it offered me the ability to practice this architectural concepts which i plan to use i larger projects going forward.


### Useful resources

- [Matthew Elsom's Blog](https://matthewelsom.com/blog/simple-scss-playbook.html) - This gave me a strong foundation for implementing the 4-1 scss architecture i utilise in the project. I really liked the approach and will use it going forward.

- [Sitepoint](hhttps://www.sitepoint.com/managing-responsive-breakpoints-sass/) - This is an amazing article which helped me understand how to use make scalable media queries with scss. I'd recommend it to anyone still trying to come to grips to how to efficiently implement scss mixins with media queries.


## Author

- Website - [KXLA 🤙](https://github.com/KXLAA)
- Frontend Mentor - [@KXLAA](https://www.frontendmentor.io/profile/KXLAA)
