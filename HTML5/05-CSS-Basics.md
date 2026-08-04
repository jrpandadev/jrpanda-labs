| [⬅️ Links & Images](04-Links-Images.md) | [🏠 HTML5 Index](README.md) | [Tables ➔](06-Tables.md) |
---

# 📖 Module 5: CSS Basics

<details open>
<summary><b>📋 What You'll Learn</b></summary>

- Understand the **CSS rule structure** — selectors, properties, and values
- Style basic elements: `html`, `body`, headings, paragraphs, and links
- Master **CSS pseudo-classes**: `:hover`, `:visited`, `:active`, `:focus`
- Understand the **CSS cascade** and how styles are applied
- Learn **CSS specificity** basics and how conflicts are resolved
- Understand the **CSS Box Model**
- Practice with **3 interactive quiz questions**

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

## 📦 CSS Box Model

Every HTML element is rendered as a **box** with four layers:

```text
┌─────────────────────────────────────┐
│              MARGIN                 │
│  ┌───────────────────────────────┐  │
│  │           BORDER              │  │
│  │  ┌───────────────────────┐    │  │
│  │  │       PADDING         │    │  │
│  │  │  ┌─────────────────┐  │    │  │
│  │  │  │    CONTENT       │  │    │  │
│  │  │  └─────────────────┘  │    │  │
│  │  └───────────────────────┘    │  │
│  └───────────────────────────────┘  │
└─────────────────────────────────────┘
```

| Layer | What it Controls |
| :--- | :--- |
| **Content** | The actual text, image, or element |
| **Padding** | Space between content and border |
| **Border** | The visible edge of the element |
| **Margin** | Space between this element and its neighbors |

```css
div {
    width: 200px;
    padding: 20px;
    border: 2px solid black;
    margin: 10px;
}
/* Total width = 200 + 20*2 + 2*2 + 10*2 = 264px */
```

> [!TIP]
> Use `box-sizing: border-box;` to make `width` and `height` include padding and border. This makes sizing much more intuitive:
> ```css
> * {
>     box-sizing: border-box;
> }
> ```

---

## 🏆 CSS Specificity

When multiple rules target the same element, the browser uses **specificity** to decide which wins.

| Selector Type | Specificity | Example |
| :--- | :--- | :--- |
| Inline styles | `1-0-0-0` | `style="color: red;"` |
| ID selectors | `0-1-0-0` | `#header` |
| Class / pseudo-class | `0-0-1-0` | `.nav`, `:hover` |
| Element / pseudo-element | `0-0-0-1` | `p`, `::before` |

```text
Inline > ID > Class > Element
```

> [!WARNING]
> Avoid using `!important` to override styles. It breaks the natural cascade and makes debugging extremely difficult. Instead, use more specific selectors.

---

## CSS Cascade

The browser applies styles in this order:

```text
HTML Element → CSS Selector → Apply Matching Rules → Display Styled Element
```

When multiple rules match, the last one in the stylesheet wins (if specificity is equal).

---

## W3C Validator Analysis

> [!NOTE]
> Validate HTML using the **W3C Markup Validation Service**: [https://validator.w3.org/](https://validator.w3.org/)

### Validation Results

| Check | Status | Notes |
| :--- | :--- | :--- |
| `<section>` | ✅ Valid | Semantic grouping used correctly |
| `<nav>` | ✅ Valid | Proper semantic navigation |
| Internal Links | ✅ Valid | IDs match navigation links |
| External Link | ✅ Valid | MDN URL is correctly formed |
| Lists | ✅ Valid | `<ul>`, `<ol>`, and `<dl>` are used appropriately |
| CSS Selectors | ✅ Valid | Syntax is correct |
| Pseudo Classes | ✅ Valid | `:visited`, `:hover`, and `:active` are valid |
| `href="#"` | ⚠ Acceptable | Works for "Back to Top", but `#top` is more explicit |
| `<sec>` Element | ❌ Invalid | Not an HTML element — replace with `<section>` or `<div>` |
| Missing `<body>` Start Tag | ❌ Invalid | Add `<body>` immediately after `</head>` |

### Improvements

#### 1. Add the missing `<body>` tag

```html
<!-- ❌ Current -->
</head>
<section id="html">

<!-- ✅ Correct -->
</head>
<body>
<section id="html">
```

#### 2. Replace the invalid `<sec>` tag

Replace `<sec>` with `<section>`, `<div>`, or `<p>` as appropriate.

#### 3. Simplify duplicate CSS

```css
/* ❌ Current — three identical rules */
p { color: wheat; }
p { color: wheat; }
p { color: wheat; }

/* ✅ Better — one rule */
p { color: wheat; }
```

#### 4. Add `target="_blank"` with security

```html
<a href="https://developer.mozilla.org/en-US/" target="_blank" rel="noopener noreferrer">
    MDN
</a>
```

---

## 🧪 Self-Check Questions & Quizzes

### Question 1: Specificity ⭐⭐

Which rule wins when both target the same `<p>` element?

```css
p { color: red; }
.intro { color: blue; }
```

```html
<p class="intro">Hello</p>
```

<details>
<summary><b>💡 Click to Reveal Solution & Explanation</b></summary>

#### ✅ Solution
```text
blue
```

#### 🔍 Explanation
A **class selector** (`.intro`) has higher specificity (`0-0-1-0`) than an **element selector** (`p`) which has (`0-0-0-1`). So `color: blue` wins.
</details>

---

### Question 2: Box Model ⭐⭐

An element has `width: 200px`, `padding: 20px`, `border: 5px`, and `margin: 10px`. What is the total space it occupies horizontally?

<details>
<summary><b>💡 Click to Reveal Solution & Explanation</b></summary>

#### ✅ Solution
```text
270px
```

#### 🔍 Explanation
Total = width + left padding + right padding + left border + right border + left margin + right margin = 200 + 20 + 20 + 5 + 5 + 10 + 10 = **270px**.

With `box-sizing: border-box`, the width (200px) would include padding and border, so total space = 200 + 10 + 10 = 220px.
</details>

---

### Question 3: Pseudo-Class Order ⭐⭐⭐

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
| **Pseudo-classes** | `:hover`, `:visited`, `:active`, `:focus` — describe states |
| **Specificity** | Inline > ID > Class > Element — determines which rule wins |
| **Box Model** | Content + Padding + Border + Margin = total space |
| **`box-sizing: border-box`** | Makes width/height include padding and border |
| **Cascade** | Last rule wins when specificity is equal |
| **LoVe HAte** | Correct pseudo-class order: `:link`, `:visited`, `:hover`, `:active` |

---

| [⬅️ Links & Images](04-Links-Images.md) | [🏠 HTML5 Index](README.md) | [Tables ➔](06-Tables.md) |
