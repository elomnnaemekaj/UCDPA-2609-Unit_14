# Unit 14 – Student Hands-On Lab

## Accessibility in Practice: ARIA, Keyboard Navigation & Screen Readers

---

## Purpose of this lab

In this lab, you will:

- Practise accessibility as a **quality check**, not a theory exercise
- Test a website using:
  - Keyboard-only navigation
  - Screen reader tools

- Fix accessibility issues using:
  - Semantic HTML
  - CSS focus styles
  - ARIA attributes (only when necessary)

- Learn when **not** to use ARIA

The focus is on **finding and fixing real accessibility problems**.

---

## What you will work on

You will work on a **fully functional but accessibility-incomplete website** that:

- Loads correctly
- Looks visually fine
- Contains common accessibility issues

Your task is to **audit and improve accessibility**, not add features or redesign the UI.

---

## Prerequisites

Before starting, make sure you have:

- Completed Unit 12
- VS Code installed
- A web browser (Chrome or Firefox recommended)
- Basic HTML and CSS knowledge
- Understanding of semantic elements

---

## Part 0 — Project Setup

### Goal

Create a shared baseline project.

---

### Steps

1. Create a new directory:

   ```bash
   mkdir unit14-accessibility
   ```

2. Move into the directory:

   ```bash
   cd unit14-accessibility
   ```

3. Open the folder in VS Code:

   ```bash
   code .
   ```

4. Create the following structure:

   ```
   index.html
   css/style.css
   ```

5. If needed, create the CSS folder:

   ```bash
   mkdir css
   touch css/style.css
   ```

---

### Checkpoint

- All files exist
- No extra CSS or HTML has been added yet

---

## Part 1 — Baseline Page with Accessibility Issues

### Goal

Create a page that works visually but contains accessibility problems.

---

### Steps

1. Open `index.html`.
2. Add the following content:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Accessibility Practice</title>
    <link rel="stylesheet" href="css/style.css" />
  </head>
  <body>
    <div class="header">
      <div class="logo">My Site</div>
      <div class="nav">
        <span>Home</span>
        <span>About</span>
        <span>Contact</span>
      </div>
    </div>

    <div class="main">
      <div class="card">
        <h2>Welcome</h2>
        <p>This page needs accessibility improvements.</p>
        <div class="button">Learn more</div>
      </div>
    </div>

    <div class="footer">
      <p>Footer text</p>
    </div>
  </body>
</html>
```

3. Save and open the page in the browser.

---

### Observation Task (No Fixes Yet)

Without changing any code, identify:

- Non-semantic elements used for structure
- Clickable items that are not interactive elements
- Missing landmarks
- Potential keyboard navigation issues

---

### Checkpoint

- You can list multiple accessibility problems
- No fixes have been applied yet

---

## Part 2 — Keyboard Navigation Testing

### Goal

Experience the site using **keyboard only**.

---

### Steps

1. Click anywhere in the browser window.

2. Use the `Tab` key to navigate.

3. Observe:
   - Which elements receive focus
   - Which elements are skipped
   - Whether the focus order makes sense

4. Attempt to:
   - Navigate the menu
   - Activate the button

---

### Checkpoint

Confirm that:

- Navigation items cannot be focused
- The button is not reachable
- Keyboard navigation is incomplete

---

## Part 3 — Fixing Issues with Semantic HTML

### Goal

Fix accessibility problems using **correct HTML elements**.

---

### Steps

1. Replace layout containers:
   - Replace header container with `<header>`
   - Replace navigation container with `<nav>`

2. Replace navigation items:

```html
<nav>
  <a href="#">Home</a>
  <a href="#">About</a>
  <a href="#">Contact</a>
</nav>
```

3. Replace the button:

```html
<button>Learn more</button>
```

4. Replace the main content wrapper with `<main>`.
5. Replace the footer wrapper with `<footer>`.

---

### Re-test Keyboard Navigation

1. Use `Tab` again.
2. Confirm:
   - All interactive elements receive focus
   - Focus order matches visual order
   - Buttons can be activated

---

### Checkpoint

- Keyboard navigation now works end-to-end
- No ARIA has been used yet

---

## Part 4 — Focus Visibility with CSS

### Goal

Ensure keyboard focus is clearly visible.

---

### Steps

1. Open `css/style.css`.
2. Add:

```css
a:focus,
button:focus {
  outline: 3px solid #ff9800;
  outline-offset: 2px;
}
```

3. Navigate the page using the keyboard.

---

### Checkpoint

- Focus is always visible
- Focus does not rely on colour alone

---

## Part 5 — Screen Reader Awareness

### Goal

Understand how screen readers interpret structure.

---

### Steps

1. Enable a screen reader:
   - macOS: VoiceOver
   - Windows: Narrator

2. Navigate using:
   - Headings
   - Landmarks

3. Observe:
   - How content is announced
   - Whether structure is logical

---

### Checkpoint

Confirm the presence of:

- One `<header>`
- One `<main>`
- One `<nav>`
- One `<footer>`
- Clear heading order

---

## Part 6 — Using ARIA (Only When Necessary)

### Goal

Apply ARIA **carefully and correctly**.

---

### Rules

- Use semantic HTML first
- ARIA does not replace correct elements
- Incorrect ARIA can reduce accessibility

---

### Example — Navigation Label

Add only if needed:

```html
<nav aria-label="Main navigation"></nav>
```

Re-test with the screen reader.

---

### Example — Custom Control (Avoid If Possible)

```html
<div role="button" tabindex="0">Custom Action</div>
```

Prefer `<button>` whenever possible.

---

### Checkpoint

- ARIA is minimal
- Semantics do most of the work

---

## Part 7 — Independent Accessibility Audit

### Goal

Apply accessibility testing and fixes independently.

---

### Task

Audit the page and:

- Identify at least **three** accessibility issues
- Fix them using:
  - Semantic HTML
  - CSS focus styles
  - ARIA only where required

---

### Constraints

- No JavaScript
- No frameworks
- No visual redesign

---

### Checkpoint

- Issues are fixed deliberately
- You can explain why each fix improves accessibility

---

## Final Review

Confirm that:

- The site is fully keyboard navigable
- Focus indicators are visible
- Screen reader structure makes sense
- Semantic HTML is used correctly
- ARIA is used sparingly and intentionally

---

## End of Unit 14 Hands-On Lab

You should now be able to:

- Test accessibility using real tools
- Identify common accessibility problems
- Fix issues using correct HTML and CSS
- Decide when ARIA is appropriate

You are now ready to apply accessibility checks confidently in **assessments and real-world projects**.