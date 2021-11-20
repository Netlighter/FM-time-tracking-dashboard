# Frontend Mentor - Time tracking dashboard solution

This is a solution to the [Time tracking dashboard challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/time-tracking-dashboard-UIQ7167Jw). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

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

- View the optimal layout for the site depending on their device's screen size
- See hover states for all interactive elements on the page
- Switch between viewing Daily, Weekly, and Monthly stats

### Screenshot

![](https://i.imgur.com/lTlsOiQ.png)

### Links

- Solution URL: [Frontend Mentor](https://www.frontendmentor.io/solutions/time-tracking-dashboard-based-on-flex-and-grid-CXqQmfR4p)
- Live Site URL: [Vercel](https://fm-time-tracking-dashboard-6hfc8h7wc-bruhdev.vercel.app/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow

### What I learned

I learned how to dynamically generate page code based on json data.

To see how you can add code snippets, see below:

```js
_createMarkup() {
    const { title, timeframes } = this.data;

    const id = title.toLowerCase().replace(/ /g, '-');
    const { current, previous } = timeframes[this.view.toLowerCase()];

    this.container.insertAdjacentHTML(
        'beforeend',
        `
    <div class="dashboard__item dashboard__item--${id}">
        <article class="tracking_card">
            <header class="tracking_card__header">
                <h4 class="tracking_card__title">${title}</h4>
                <img class="tracking_card__menu" src="images/icon-ellipsis.svg" alt="menu">
            </header>
            <div class="tracking_card__body">
                <div class="tracking_card__time">
                    ${current}hrs
                </div>
                <div class="tracking_card__prev-period">
                    Last ${DashboardItem.PERIODS[this.view]} - ${previous}hrs
                </div>
            </div>
        </article>
    </div>
    `
    );

    this.time = this.container.querySelector(`.dashboard__item--${id} .tracking_card__time`);
    this.prev = this.container.querySelector(`.dashboard__item--${id} .tracking_card__prev-period`);
}
```

### Continued development

I want to focus on the ability to dynamically change page layout through scripts

### Useful resources

- [BEM methodology resource](https://ru.bem.info/methodology/html/) - This helped me understand what BEM is and why it's cool.

## Author

- Website - [Netlighter](https://github.com/Netlighter)
- Frontend Mentor - [@Netlighter](https://www.frontendmentor.io/profile/Netlighter)


## Acknowledgments

Thanks to an experienced instructor, Michael Nepomnyashchiy, for helping with the basics and explaining the principles of layout.

