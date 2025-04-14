[![npm](https://img.shields.io/npm/v/chaos-sass)](https://www.npmjs.com/package/chaos-sass) [![license](https://img.shields.io/npm/l/chaos-sass)](https://github.com/ChaosWebDev/chaos-scss/blob/main/LICENSE) [![issues](https://img.shields.io/github/issues/chaoswebdev/chaos-scss)](https://github.com/ChaosWebDev/chaos-scss/issues)

# Chaos-SCSS

> Taking the chaos out of styling!

---

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Features](#features)
- [Classes](#classes)
- [Variables](#variables)
- [Forms](#forms)
- [Contributing](#contributing)
- [License](#license)

---

## Installation

### Option 1: Clone the Repository

```bash
# clone the repository
git clone https://github.com/chaoswebdev/chaos-scss.git

# navigate to the project directory
cd chaos-scss

# install dependencies
npm install
```

### Option 2: Install from NPM

```bash
npm i chaos-scss
```

Then import it in your SCSS file:

```scss
@use "chaos-sass" as *;
```

---

## Usage

Including this library will automatically set the following:

```scss
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
```

Import the main entry point of your SCSS file:

```scss
@use "chaos-sass" as *;
```

---

## Configuration

You can overwrite variables (see [Classes](#classes) or [Variables](#variables) or [Themes](#themes)) to adjust utilities and theme styles.

---

## Features

- 🔧 Modular architecture (base, components, layout, themes, utilities)
- 🎨 CSS custom property support with light/dark themes
- ⚙️ SCSS map-based utilities
- 🧩 Simple, consistent utility class generation
- 🤝 Built to integrate easily with custom or existing stylesheets
- 🪶 Lightweight and framework-agnostic

---

## Classes

Chaos-SCSS generates a number of utility classes using SCSS maps and mixins. These classes can be used directly or `@extend`ed in your custom styles.

### Typography

- `.font-[name]` — sets font family
- `.text-[weight]` — font weight (e.g. `text-bold`)
- `.text-[style]` — font style (e.g. `text-italic`)
- `.text-[decoration]` — text decoration
- `.text-[transform]` — text transform (e.g. `text-uppercase`)
- `.text-[alignment]` — text alignment
- `.text-[size]` — font size
- `.leading-[size]` — line height
- `.tracking-[size]` — letter spacing

### Layout & Flexbox

- `.row`, `.column` — flex containers
- `.flex-row`, `.flex-column` — alias classes
- `.align-[start|center|end|stretch]`
- `.justify-[start|center|end|between|around|evenly]`
- `.gap-[sm|md|lg|xl]`

### Cursor

- `.cursor-pointer`
- `.clickable`

### Positioning & Overflow

- `.relative`, `.absolute`, `.fixed`, `.sticky`
- `.z-[level]` — z-index classes
- `.overflow-[auto|hidden|scroll|visible]`
- `.whitespace-[nowrap|normal|pre]`

> All utility classes are generated from SCSS maps, and you can extend or customize them by modifying the maps in your config.

---

## Variables

> All variables can be overridden in your configuration

```scss
--fontSize, --bodyBG, --bodyFG, --navBG, --navFG, --navHoverBG, --navHoverFG, --borderColor, --important, --alert, --good
```

---

## Forms

If you want to use the chaos-scss `<form>` styling, add the class `cs` to it: `<form class='cs'>`

```html
<form>
  <fieldset>
    <legend>Legend</legend>

    <label for="x">X</label>
    <input type="text" name="x" id="x" />
    ...
  </fieldset>
</form>
```

`.col-2` or `.full-width` spreads a full row inside the fieldset in case you want a custom row outside of the fieldset's 2-column grid.

---

## Themes

Themes can be set in your opening `<html>` tag.

The default theme is applied to `<html>` (light theme).
To enable dark mode, use: `<html data-theme="dark">`

You can set a javascript toggle script as:

```js
document.documentElement.setAttribute("data-theme", "dark");
// or
document.documentElement.setAttribute("data-theme", "light");
```

It will also try and use your browser's default:

```scss
@media (prefers-color-scheme: dark) {
  :root {
    @include apply-theme($dark-theme);
  }
}
```

---

## Contributing

1. Fork the repository
1. Create a new branch: `git checkout -b feature/your-feature`
1. Commit your changes `git commit -am 'Add your feature'`
1. Push to the branch `git push origin feature/your-feature`
1. Create a new Pull Request

---

## License

Chaos-SCSS is open-source software licensed under the [MIT License](LICENSE).
