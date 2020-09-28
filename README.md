# Light & Dark Mode

%PICTURE%

%Description%

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

<br>

**style.css**

```css

```

<br>

**script.js**

<br>

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
  } else {
    document.documentElement.setAttribute('data-theme', 'light');
  }
  
}
```

We use property `target.checked` to check if the switch toggle has been checked (show dark mode) or not (light mode).

1. We set the `data-theme` attribute at the highest level of the html
2. `document.documentElement` returns the...

<br>

---

Background from [hero patterns](https://www.heropatterns.com/)

Illustrations from [Undraw](https://undraw.co/illustrations)

Icons from [FontAwesome](https://fontawesome.com/)



