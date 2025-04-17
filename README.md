# quik-css
A modern utility-first CSS framework for rapid web development.

## Why Choose Quik CSS?

### Advantages Over Tailwind CSS

1. **Simpler Learning Curve**
   - More intuitive class naming system
   - Less cognitive load with straightforward utility classes
   - No need to learn complex configuration

2. **Built-in Dark Mode**
   - Native dark mode support without additional configuration
   - Automatic theme switching with localStorage persistence
   - Consistent dark mode styling across all components

3. **Lighter Weight**
   - Smaller bundle size
   - No build process required
   - Can be used directly in HTML without compilation

4. **Better Default Styling**
   - More polished default component styles
   - Consistent design language out of the box
   - Less need for custom styling

### Advantages Over Bootstrap

1. **Modern Utility-First Approach**
   - More flexible than Bootstrap's component-based approach
   - Easier to customize without fighting framework styles
   - Better for creating unique designs

2. **No JavaScript Dependencies**
   - Pure CSS framework
   - No jQuery dependency
   - Faster performance

3. **Simpler Customization**
   - Easy to override with CSS variables
   - No need to modify SASS/LESS files
   - More straightforward theming system

4. **Better Mobile-First Design**
   - More intuitive responsive classes
   - Better control over mobile layouts
   - Simpler breakpoint system

5. **Cleaner Code**
   - No unnecessary wrapper divs
   - Less markup required
   - More semantic HTML structure

## Installation

```bash
npm install quik-css
```

## Usage

### 1. Basic Setup

Add the CSS file to your HTML:

```html
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" href="node_modules/quik-css/css/styles.css">
</head>
<body>
    <!-- Your content -->
</body>
</html>
```

Or import it in your CSS file:

```css
@import 'quik-css/css/styles.css';
```

### 2. Layout Examples

#### Container
```html
<div class="container">
    <!-- Content with max-width and centered -->
</div>
```

#### Flexbox
```html
<div class="flex">
    <div>Item 1</div>
    <div>Item 2</div>
</div>

<!-- Flex with space between -->
<div class="flex space-between">
    <div>Left</div>
    <div>Right</div>
</div>

<!-- Flex column -->
<div class="flex-col">
    <div>Top</div>
    <div>Bottom</div>
</div>
```

#### Grid
```html
<div class="grid" style="grid-template-columns: repeat(3, 1fr);">
    <div>Grid Item 1</div>
    <div>Grid Item 2</div>
    <div>Grid Item 3</div>
</div>
```

### 3. Typography

```html
<h1 class="main-heading">Main Heading</h1>
<h2 class="medium-heading">Medium Heading</h2>
<p class="normal-font">Normal text</p>
<p class="tiny-font">Small text</p>
<p class="big-font">Large text</p>

<!-- Font weights -->
<p class="fw-thin">Thin weight</p>
<p class="fw-normal">Normal weight</p>
<p class="fw-thick">Thick weight</p>
```

### 4. Spacing

```html
<!-- Margin -->
<div class="m-4">Margin all sides</div>
<div class="mt-4">Margin top</div>
<div class="mb-4">Margin bottom</div>
<div class="ml-4">Margin left</div>
<div class="mr-4">Margin right</div>

<!-- Padding -->
<div class="p-4">Padding all sides</div>
<div class="pt-4">Padding top</div>
<div class="pb-4">Padding bottom</div>
<div class="pl-4">Padding left</div>
<div class="pr-4">Padding right</div>
```

### 5. Colors

```html
<!-- Background colors -->
<div class="bg-white">White background</div>
<div class="bg-black">Black background</div>
<div class="bg-light-red">Light red background</div>
<div class="bg-deep-red">Deep red background</div>
<div class="bg-light-green">Light green background</div>
<div class="bg-deep-green">Deep green background</div>
<div class="bg-light-blue">Light blue background</div>
<div class="bg-deep-blue">Deep blue background</div>

<!-- Text colors -->
<p class="font-white">White text</p>
<p class="font-black">Black text</p>
<p class="font-red">Red text</p>
<p class="font-green">Green text</p>
<p class="font-blue">Blue text</p>
```

### 6. Components

#### Buttons
```html
<button class="btn btn-primary">Primary Button</button>
<button class="btn btn-secondary">Secondary Button</button>
<button class="btn" disabled>Disabled Button</button>
```

#### Cards
```html
<div class="card p-4">
    <h3 class="medium-heading">Card Title</h3>
    <p>Card content goes here</p>
</div>
```

#### Forms
```html
<form class="form-group">
    <div class="mb-2">
        <label class="form-label">Text Input</label>
        <input type="text" class="form-control" placeholder="Enter text">
    </div>
    
    <div class="mb-2">
        <label class="form-label">Textarea</label>
        <textarea class="form-control" placeholder="Enter message"></textarea>
    </div>
    
    <button type="submit" class="btn btn-primary">Submit</button>
</form>
```

#### Tables
```html
<table class="normal-table w-100p">
    <thead>
        <tr>
            <th>Header 1</th>
            <th>Header 2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Row 1, Cell 1</td>
            <td>Row 1, Cell 2</td>
        </tr>
    </tbody>
</table>
```

#### Alerts
```html
<div class="alert bg-light-red">Danger alert</div>
<div class="alert bg-light-green">Success alert</div>
<div class="alert bg-light-blue">Info alert</div>
```

### 7. Dark Mode

Add this to your HTML:
```html
<button id="darkModeToggle">Toggle Dark Mode</button>
```

And this JavaScript:
```javascript
const darkModeToggle = document.getElementById('darkModeToggle');
const html = document.documentElement;

function toggleDarkMode() {
    const isDark = html.getAttribute('data-theme') === 'dark';
    const newTheme = isDark ? 'light' : 'dark';
    html.setAttribute('data-theme', newTheme);
    localStorage.setItem('theme', newTheme);
}

darkModeToggle.addEventListener('click', toggleDarkMode);

// Check for saved theme preference
const savedTheme = localStorage.getItem('theme');
if (savedTheme) {
    html.setAttribute('data-theme', savedTheme);
}
```

### 8. Responsive Design

The framework includes responsive classes:
- `hide-mobile`: Hides element on mobile
- `hide-tablet`: Hides element on tablet
- `w-100p-mobile`: Full width on mobile
- `flex-mobile-col`: Column direction on mobile

Example:
```html
<div class="flex flex-mobile-col">
    <div class="w-20p w-100p-mobile">Sidebar</div>
    <div class="w-80p w-100p-mobile">Main Content</div>
</div>
```

## Customization

You can customize the framework by overriding CSS variables:

```css
:root {
    --primary-color: #your-color;
    --secondary-color: #your-color;
    --bg-color: #your-color;
    --text-color: #your-color;
    /* Add more customizations */
}
```

## License

MIT

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request. 
