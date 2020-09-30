# Light & Dark Mode

![cover](cover.png)

The purpose of this project is to implement dark / light theme to a template website using plain JavaScript.

<br>

---

<br>

## Learning Outcome

<br>

1. Using CSS variables
2. `background: rgb(255 255 255 / 50%)` instead of `rgba(255, 255, 255, 0.5)`
3. Smooth scroll with `html { scroll-behavior: smooth };`
4. Creating a [toggle switch](https://www.w3schools.com/howto/howto_css_switch.asp)
5. Setting attributes on the root element (html) 
6. Using `document.documentElement` 
7. Saving theme in localStorage

<br>

---

## Process

<br>

### Creating the toggle switch

<br>

**index.html**

```html
<div class="theme-switch-wrapper">
  <!-- Text and icon -->
  <span id="toggle-icon">
  	<span class="toggle-text">Light Mode</span>
    <i class="fas fa-sun"></i>
  </span>
  <!-- Switcher -->
  <label class="theme-switch">
  	<input type="checkbox">
    <div class="slider round"></div>
  </label>
</div>
```

- The text *Light Mode* has to change to *Dark Mode* when in dark mode.
- The styling of the switch is done via `slider` and `round` classes.

<br>

**script.js**

Add event listener to the toggle switch. We use the change event.

```js
const toggleSwitch = document.querySelector('input[type="checkbox"]');

// Switch Theme Dynamically
//...


// Event Listener
toggleSwitch.addEventListener('change', switchTheme);
```

<br>

We create function that dynamically changes the theme

```js
// Switch Theme Dynamically
function switchTheme(event) {
  if (event.target.checked) {
    document.documentElement.setAttribute('data-theme', 'dark');
    localStorage.setItem('theme', 'dark');
    toggleDarkLightMode(DARK_THEME);
  } else {
    document.documentElement.setAttribute('data-theme', 'light');
    localStorage.setItem('theme', 'light');
    toggleDarkLightMode(LIGHT_THEME);
  }
}
```

We use property `target.checked` to check if the switch toggle has been checked (show dark mode) or not (light mode).

1. We set the `data-theme` attribute at the highest level of the html
2. `document.documentElement` returns the root element -in this case `<html>`

<br>

We still need to change te **icons**, the **text** of the theme and the **images**. We create a single function `toggleDarkLightMode(mode)` that given a parameter, it changes the icon, text and images according to the theme choice.

<br>

I use two constants to identify the themes: `DARK_THEME` and `LIGHT_THEME`.

There is a function `imageMode(mode)` that's in charge of changing the source of the images in the HTML document according to the chosen mode:

```js
function imageMode(color) {
  image1.src = `img/undraw_proud_coder_${color}.svg`;
  image2.src = `img/undraw_feeling_proud_${color}.svg`;
  image3.src = `img/undraw_conceptual_idea_${color}.svg`;
}
```

<br>

### LocalStorage

<br>

We use local storage to store the user theme preference so that when the user refreshes the page, the previous chosen theme remains. 

<br>

---

- Background from [hero patterns](https://www.heropatterns.com/)

- Illustrations from [Undraw](https://undraw.co/illustrations)

- Icons from [FontAwesome](https://fontawesome.com/)



