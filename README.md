# Frontend Mentor - Age calculator app solution

This is a solution to the [Age calculator app challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/age-calculator-app-dF9DFFpj-Q).

**Part of my 100-Day JavaScript Challenge - Day 3**

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View an age in years, months, and days after submitting a valid date through the form
- Receive validation errors if:
  - Any field is empty when the form is submitted
  - The day number is not between 1-31
  - The month number is not between 1-12
  - The year is in the future
  - The date is invalid e.g. 31/04/1991 (there are 30 days in April)
- View the optimal layout for the interface depending on their device's screen size
- See hover and focus states for all interactive elements on the page
- ✅ **BONUS COMPLETED**: See the age numbers animate to their final number when the form is submitted

### Screenshot

![Age Calculator with animated numbers](assets/images/screenshot.png)

### Links

- Solution URL: [GitHub Repository](https://github.com/Exc1D/age-calculator)
- Live Site URL: [Live Demo](https://exc1d.github.io/day-03-age-calculator/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Mobile-first workflow
- Vanilla JavaScript
- Date manipulation and validation
- CSS/JavaScript animations

### What I learned

This project taught me several key concepts:

**1. Working with JavaScript Date Objects:**

```js
// Calculating age with proper date handling
const today = new Date();
const birthDate = new Date(year, month - 1, day);
const ageInMilliseconds = today - birthDate;
```

**2. Complex Date Validation:**

- Checking for valid day/month combinations
- Handling leap years
- Preventing future dates
- Edge case validation (like April 31st)

**3. Number Counting Animation:**

```js
// Animating numbers from 0 to final value
function animateValue(element, start, end, duration) {
  let startTimestamp = null;
  const step = (timestamp) => {
    if (!startTimestamp) startTimestamp = timestamp;
    const progress = Math.min((timestamp - startTimestamp) / duration, 1);
    element.textContent = Math.floor(progress * (end - start) + start);
    if (progress < 1) {
      window.requestAnimationFrame(step);
    }
  };
  window.requestAnimationFrame(step);
}
```

**4. Form Validation Patterns:**

- Real-time error messaging
- Visual error states
- User-friendly feedback

**5. Frontend Mentor Challenge Workflow:**

- Working from design specifications
- Implementing bonus features
- Professional README documentation

### What I added beyond the challenge

- Custom purple color scheme
- Enhanced animation timing
- Additional validation feedback
- Smooth transitions on all interactions

### Challenges faced

**Date calculation complexity:**
The trickiest part was calculating exact age in years, months, and days when the current day is before the birthday in the month. This required careful logic to "borrow" from the previous month.

**Animation timing:**
Coordinating the number counting animation to feel smooth without being too fast or too slow required experimentation with `requestAnimationFrame` timing.

**Validation edge cases:**
Handling all possible invalid date combinations (leap years, different month lengths, future dates) required thorough testing.

### Continued development

Future enhancements I'd like to add:

- Show age in different formats (weeks, hours, minutes)
- Add "days until next birthday" feature
- Calculate age at specific future dates
- Add historical context ("You were born X days after Y event")
- Zodiac sign calculator
- Life expectancy statistics

## Author

- GitHub - [Exc1D](https://github.com/Exc1D)
- Frontend Mentor - [@Exc1D](https://www.frontendmentor.io/profile/Exc1D)
- LinkedIn - [David Laurence Aviado](https://www.linkedin.com/in/david-laurence-aviado-b1aaa8272/)

---

**Day 3 of my 100-Day JavaScript Challenge**

**For Joy, Hero, Aiah, and Aria** 💙🐕
