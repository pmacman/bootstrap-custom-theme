# Bootstrap Custom Theme (Multi-Version)

## ℹ️ Overview

A customizable, versioned Bootstrap theme system built with **Sass / Less** and **Webpack**, designed to support **multiple major Bootstrap versions** from a shared design foundation.

This project intentionally demonstrates:

- Large-scale CSS architecture
- Cross-version theming strategies
- Framework customization without forking source code
- Build tooling for style systems

## 💡 Why This Project Exists

Before component-driven UI frameworks became dominant, many teams relied on **Bootstrap-based design systems** that needed to:

- Support multiple applications
- Span several Bootstrap major versions
- Maintain consistent branding over time
- Allow controlled customization without breaking upstream updates

While Bootstrap is less fashionable today, the **theming and architectural concepts remain relevant** for design systems, legacy system maintenance, and enterprise frontend work.

## 📦 Features

- Separate folders for each Bootstrap version (`bootstrap3`, `bootstrap4`, `bootstrap5`)
- Shared Sass files for cross-version styling
- Version-specific overrides where breaking changes require them
- Compiled assets output to versioned `dist/` folders
- Fully responsive design

> ⚠️ Bootstrap 3 uses **Less** instead of Sass and therefore does not share the root styles due to breaking differences.

## 🚀 Running the Demo

Open the `index.html` file located in:

```
bootstrap{version}/dist/
```

Resize the browser or use mobile emulation to view responsive behavior.

## 🛠 Usage Options

### Option 1: Use the Prebuilt Theme

Copy the following folders from `bootstrap{version}/dist` into your project:

- `css`
- `fonts`
- `images`

> The `css` and `fonts` folders must remain at the same directory level.

Include styles in this order:

```html
<link rel="stylesheet" href="bootstrap-custom-base.min.css" />
<link rel="stylesheet" href="bootstrap-custom.min.css" />
```

Include scripts in this order (version-dependent):

- jquery (optional for Bootstrap 5+)
- popper (required for tooltips/popovers)
- bootstrap

### Option 2: Build and Customize

#### 1. Clone the repository

```bash
git clone <repo-url>
```

#### 2. Install dependencies

```bash
cd bootstrap5
npm install
```

Repeat for other versions as needed.

#### 3. Start the dev server

```bash
npm start
```

The page will automatically reload as you modify styles.

## 🛠 Customization Approach

- Shared styles live in `src/scss`
- Version-specific overrides live inside each Bootstrap folder
- Component-level partials such as `_buttons.scss` and `_typography.scss`
- Imported via `bootstrap-custom.scss`

The base theme imports Bootstrap directly:

```scss
@import "node_modules/bootstrap/scss/bootstrap";
```

You may selectively import Bootstrap components to reduce bundle size.

## ⚙️ Production Builds

Build a single version:

```bash
npm run build
```

Build all versions:

```bash
npm run build:all
```

Compiled assets are written to `bootstrap{version}/dist`.

## 📌 Notes

- This project reflects **pre-component-era frontend architecture**
- Focuses on **styling systems**, not application logic
- Useful for understanding legacy Bootstrap theming and CSS scalability

## 📄 License

MIT
