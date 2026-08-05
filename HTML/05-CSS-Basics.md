| [⬅️ Links & Images](04-Links-Images.md) | [🏠 HTML5 Index](README.md) | [Tables ➔](06-Tables.md) |
---

# 📖 Module 5: CSS Basics

<details open>
<summary><b>📋 What You'll Learn</b></summary>

- Understand the **CSS rule structure** — selectors, properties, and values
- Style basic elements: `html`, `body`, headings, paragraphs, and links
- Master **CSS pseudo-classes**: `:hover`, `:visited`, `:active`, `:focus`
- Practice with **1 interactive quiz question**

</details>

---

## 🎨 What is CSS?

CSS stands for **Cascading Style Sheets**.

It controls how HTML elements **look** — colors, fonts, spacing, layout, and animations.

```text
HTML  → What the content IS (structure)
CSS   → How the content LOOKS (presentation)
```

> [!IMPORTANT]
> CSS should always be kept **separate** from HTML. This separation of concerns makes code easier to maintain, reuse, and debug.

---

## Three Ways to Add CSS

| Method | Syntax | Use Case |
| :--- | :--- | :--- |
| **Inline** | `style="color: red;"` on the element | Quick one-off overrides (avoid in production) |
| **Internal** | `<style>` block in `<head>` | Single-page styles |
| **External** | `<link rel="stylesheet" href="main.css">` | ✅ Best practice — reusable across pages |

> [!TIP]
> Always prefer **external CSS**. It allows browsers to cache the stylesheet, improving load times on subsequent page visits.

---

## CSS Rule Structure

```css
selector {
    property: value;
}
```

Example:

```css
body {
    background-color: #333;
    color: beige;
}
```

```text
Selector → { Property : Value }
```

---

## Element Selectors

### `html`

```css
html {
    font-size: 24px;
}
```

Sets the default font size for the document. Every element inherits it unless overridden.

### `body`

```css
body {
    background-color: #333;
    color: beige;
}
```

Background: Dark Gray | Text: Beige

### Headings

```css
h1, h2, h3 {
    color: whitesmoke;
}
```

Each heading is given the same color using a **group selector** (comma-separated).

### Paragraphs

```css
p {
    color: wheat;
}
```

Every paragraph becomes wheat-colored.

> [!WARNING]
> Avoid duplicating the same CSS rule multiple times. If you have three identical `p { color: wheat; }` rules, keep only one. Duplicate rules add file size without benefit.

### Anchors

```css
a {
    color: aliceblue;
}
```

Default hyperlink color.

---

## Class Selector

### The `class` Attribute

```html
<p class="highlight">This paragraph is highlighted.</p>
<p class="highlight">So is this one.</p>
```

```css
.highlight {
    background-color: yellow;
    font-weight: bold;
}
```

- Classes can be **reused** on multiple elements
- An element can have **multiple classes**: `class="card featured"`
- CSS class selectors start with a **dot** (`.`)

```html
<!-- Multiple classes -->
<div class="card featured large"></div>
```

> [!TIP]
> Use class names that describe **what an element is**, not what it looks like. `class="product-card"` is better than `class="red-box"` — if you change the color later, the name still makes sense.

---

## ID Selector

### The `id` Attribute

```html
<section id="about">About Us</section>
```

```css
#about {
    background-color: #1a1a2e;
    color: white;
}
```

- IDs must be **unique** — only one element per page can have a given ID
- CSS ID selectors start with a **hash** (`#`)
- IDs are also used for in-page navigation: `<a href="#about">`

### Class vs ID

| `class` | `id` |
| :--- | :--- |
| Reusable on many elements | Unique — one element only |
| `.classname` in CSS | `#idname` in CSS |
| Lower specificity | Higher specificity |
| For styling groups | For unique elements + anchors |

### Combining ID and Class

You can (and often will) combine both an `id` and a `class` on the same HTML element:

```html
<p id="intro" class="highlight bold">This paragraph has both an ID and multiple classes.</p>
```
- The `id` provides a unique hook for JavaScript or anchor links.
- The `class` applies reusable styling.

> [!WARNING]
> Avoid using IDs purely for styling — their high specificity makes overriding them painful. Prefer classes for CSS and reserve IDs for JavaScript hooks and anchor links.

---

## CSS Pseudo-Classes

Pseudo-classes describe an element's **state**.

### `:visited`

```css
a:visited {
    color: aqua;
}
```

Applied after the user has visited the link.

```text
Before Click → AliceBlue
After Click  → Aqua
```

### `:hover`

```css
a:hover {
    color: coral;
}
```

Runs when the mouse moves over the link. Useful for buttons, menus, and navigation.

### `:active`

```css
a:active {
    color: red;
}
```

Applied while the mouse button is pressed. Very short duration.

### `:focus`

```css
a:focus {
    outline: 2px solid blue;
}
```

Applied when the element receives keyboard focus (Tab key).

> [!IMPORTANT]
> Never remove `:focus` styles without providing a visible alternative. Keyboard users rely on focus indicators to navigate the page.

### Pseudo-Class Execution Order

```text
Normal → Hover → Active → Visited
```

> [!NOTE]
> The correct order for link pseudo-classes is **L**o**V**e **HA**te: `:link`, `:visited`, `:hover`, `:active`. Writing them in the wrong order can cause some states to be overridden.

---

## 🧪 Self-Check Questions & Quizzes

### Question 1: Pseudo-Class Order ⭐⭐⭐

Why does writing `:hover` before `:visited` in your CSS cause problems?

<details>
<summary><b>💡 Click to Reveal Solution & Explanation</b></summary>

#### ✅ Solution
Because `:visited` has the same specificity as `:hover` and appears later in the cascade, so it **overrides** the hover styles for visited links.

#### 🔍 Explanation
CSS rules with equal specificity are resolved by **source order** — the last one wins. The correct order is `:link`, `:visited`, `:hover`, `:active` (LoVe HAte mnemonic). This ensures hover effects still work on visited links.
</details>

---

## 🔑 Key Takeaways

| Concept | Key Point |
| :--- | :--- |
| **CSS** | Controls presentation — keep it separate from HTML |
| **External CSS** | Best practice — cacheable, reusable across pages |
| **Selectors** | Target elements by name, class, ID, or state |
| **Class (`.name`)** | Reusable — apply to multiple elements |
| **ID (`#name`)** | Unique — one per page; higher specificity |
| **Pseudo-classes** | `:hover`, `:visited`, `:active`, `:focus` — describe states |
| **LoVe HAte** | Correct pseudo-class order: `:link`, `:visited`, `:hover`, `:active` |

---

| [⬅️ Links & Images](04-Links-Images.md) | [🏠 HTML5 Index](README.md) | [Tables ➔](06-Tables.md) |
