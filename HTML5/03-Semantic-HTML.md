| [⬅️ Text Formatting](02-Text-Formatting.md) | [🏠 HTML5 Index](README.md) | [Links & Images ➔](04-Links-Images.md) |
---

# 📖 Module 3: Semantic HTML

<details open>
<summary><b>📋 What You'll Learn</b></summary>

- Understand **why semantic HTML matters** for accessibility, SEO, and maintainability
- Master **structural elements**: `<header>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`
- Use **interactive elements** like `<details>` and `<summary>` without JavaScript
- Work with **`<mark>`**, **`<time>`**, and **`aria-label`** for enhanced semantics
- Understand the difference between **`<div>`/`<span>`** and semantic alternatives
- Learn **Block vs Inline** element categories
- Practice with **4 interactive quiz questions**

</details>

---

## 🌐 What is Semantic HTML?

Semantic HTML means using HTML elements that describe **the meaning of the content**, not just how it looks.

Instead of writing:

```html
<div id="header"></div>
<div id="content"></div>
<div id="footer"></div>
```

you write:

```html
<header></header>
<main></main>
<footer></footer>
```

The browser, search engines, and screen readers understand what each part represents.

### Semantic vs Non-Semantic Elements

| Semantic Elements | Non-Semantic Elements |
| :--- | :--- |
| `<header>`, `<nav>`, `<main>` | `<div>`, `<span>` |
| Describe the **meaning** of content | Describe **nothing** about content |
| Improve accessibility & SEO | Used only for styling/layout hooks |
| Screen readers can navigate by landmark | Screen readers treat as generic containers |

> [!IMPORTANT]
> HTML5 introduced semantic elements specifically because the web was drowning in `<div>` soup. Every `<div>` you can replace with a semantic element is a win for accessibility and SEO.

---

## Why HTML5 Semantic Elements Were Introduced

Before HTML5, developers mostly used:

```html
<div id="header"></div>
<div id="content"></div>
<div id="footer"></div>
```

The browser had **no idea** what those sections represented.

HTML5 introduced semantic elements:

```text
header, nav, main, article, section, aside, footer
```

Now browsers, search engines, and assistive technologies understand the structure of a page.

---

## 📐 Semantic Page Layout

Your webpage should follow this structure:

```text
BODY
│
├── HEADER
│
├── NAV
│
├── MAIN
│     │
│     ├── SECTION
│     │      └── ARTICLE
│     │
│     ├── SECTION
│     └── SECTION
│
├── ASIDE
│
└── FOOTER
```

This is the recommended HTML5 page layout.

---

## 1. `<header>`

```html
<header>
    <h1>Welcome to My First Web Page</h1>
</header>
```

### Purpose

Represents introductory content.

Usually contains:

- Logo
- Website title
- Navigation
- Search bar

Think of it as the **cover page** of a book.

### Browser Meaning

Instead of seeing `"Just another div"`, the browser understands `"This is the page header."`

> [!NOTE]
> A page can have **multiple `<header>` elements** — one for the page and one inside each `<article>` or `<section>`. But typically the main page header is the one at the top of `<body>`.

---

## 2. `<main>`

```html
<main>
    <!-- Primary content goes here -->
</main>
```

### Purpose

Contains the **primary content** of the webpage.

Everything important belongs here.

Examples:

- Blog posts
- Articles
- Products
- Tutorials

### Important Rule

A webpage should contain **only one** `<main>` element.

```html
<!-- ❌ Wrong -->
<main></main>
<main></main>

<!-- ✅ Correct -->
<main>
    ...
</main>
```

> [!WARNING]
> `<main>` should **not** include content that repeats across pages (navigation, footer, sidebar). Those belong outside `<main>` or in their own semantic elements.

---

## 3. `<section>`

```html
<section id="html">
    <h2>Learning HTML</h2>
    <p>HTML is the foundation of the web.</p>
</section>
```

### Purpose

Represents a **thematically related group of content**.

Think of a webpage as a book — each chapter is similar to a `<section>`.

```text
Book
│
├── Chapter 1 → <section>
├── Chapter 2 → <section>
├── Chapter 3 → <section>
```

Benefits:

- Better accessibility
- Better SEO
- Cleaner document structure

> [!TIP]
> A good rule of thumb: if a group of content would have its own heading, it's a candidate for `<section>`.

---

## 4. `<article>`

```html
<article>
    <h2>How to Learn HTML</h2>
    <p>Start with the basics...</p>
</article>
```

Represents **self-contained content**.

Imagine a newspaper:

```text
Newspaper → Article 1, Article 2, Article 3
```

Each article can exist independently.

Examples:

- Blog posts
- News articles
- Forum posts
- Reviews

### `<section>` vs `<article>`

| `<section>` | `<article>` |
| :--- | :--- |
| Groups **related** content | Contains **independent** content |
| Needs context from the page | Makes sense on its own |
| "Chapter of a book" | "A newspaper clipping" |

---

## 5. `<aside>`

```html
<aside>
    <h3>Did you know?</h3>
    <p>HTML was created by Tim Berners-Lee in 1993.</p>
</aside>
```

Contains content **related** to the main content but not essential.

Examples:

- Advertisements
- Related Links
- Quick Tips
- Did You Know?
- Author Info

---

## 6. `<footer>`

```html
<footer>
    <p>&copy; 2026 My Website. All rights reserved.</p>
    <nav>
        <a href="/privacy">Privacy Policy</a>
        <a href="/terms">Terms of Service</a>
    </nav>
</footer>
```

### Purpose

Represents the **footer** of a page or section.

Usually contains:

- Copyright notice
- Contact information
- Social media links
- Navigation links
- Legal information

> [!NOTE]
> Like `<header>`, you can have multiple `<footer>` elements — one for the page and one inside each `<article>` or `<section>` (e.g., for author info at the bottom of a blog post).

---

## 7. `<nav>`

```html
<nav>
    <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#contact">Contact</a></li>
    </ul>
</nav>
```

Represents a navigation section.

Browsers and screen readers know: `"These links are for navigation."`

Structure:

```text
nav
│
└── ul
      │
      ├── li → a
      ├── li → a
      └── li → a
```

> [!TIP]
> Not every group of links is a `<nav>`. Reserve `<nav>` for **major** navigation blocks (primary menu, breadcrumbs, pagination). A list of links in a footer can just be a `<ul>`.

---

## 8. `id` Attribute

```html
<section id="Routine">
```

Every `id` must be **unique** — think of it like an Aadhaar number.

### Uses

- Internal navigation (fragment identifiers)
- CSS styling
- JavaScript selection

### Internal Page Navigation

```html
<a href="#Routine">Go to Routine</a>
```

Browser action:

```text
Click Link → Find id="Routine" → Scroll There
```

This is called a **fragment identifier**.

---

## 9. `<details>` & `<summary>`

```html
<details>
    <summary>Did you know?</summary>
    <p>HTML was created by Tim Berners-Lee in 1993.</p>
</details>
```

Creates an expandable area — **no JavaScript required**.

Initially:

```text
▶ Did you know?
```

After clicking:

```text
▼ Did you know?
  HTML was created by Tim Berners-Lee in 1993.
```

Structure:

```text
details → summary → Hidden Content
```

> [!NOTE]
> Use the `open` attribute on `<details>` to make it expanded by default:
> ```html
> <details open>
>     <summary>Always visible</summary>
>     <p>This content is shown by default.</p>
> </details>
> ```

---

## 10. `<mark>`

```html
<mark>Did you know?</mark>
```

Highlights text — appears with a highlighted background (usually yellow by default).

Use for:

- Search results
- Important words
- Notes
- Keywords

---

## 11. `<time>`

```html
<time datetime="2026-01-18">January 18, 2026</time>
```

Represents dates or times.

The browser displays `January 18, 2026` while machines read `2026-01-18`.

### Why Use `<time>`?

Search engines, calendars, screen readers, and AI systems can understand dates automatically.

### Different Formats

| Format | Example | Meaning |
| :--- | :--- | :--- |
| Date | `datetime="2026-01-18"` | January 18, 2026 |
| Time | `datetime="08:00"` | 8:00 AM |
| Duration | `datetime="PT17H"` | 17 Hours |
| Duration | `datetime="P7D"` | 7 Days |
| Combined | `datetime="PT2H30M"` | 2 Hours 30 Minutes |

### ISO-8601 Duration Format

| Letter | Meaning |
| :--- | :--- |
| `P` | Period (starts the duration) |
| `T` | Time separator |
| `H` | Hours |
| `D` | Days |
| `M` | Minutes (after T) or Months (before T) |
| `S` | Seconds |

---

## 12. `aria-label`

```html
<nav aria-label="primary-navigation">
```

ARIA stands for **Accessible Rich Internet Applications**.

### Purpose

Adds information for screen readers without changing the visual appearance.

```text
Visual users see:    Navigation
Screen reader says:  "Primary Navigation Landmark"
```

> [!TIP]
> Use `aria-label` when there's no visible text that describes the element's purpose. If there's already a visible heading, use `aria-labelledby` instead to avoid duplication.

---

## 13. `<div>` — Generic Block Container

```html
<div>
```

Has **no semantic meaning**.

Think of it as a box. Use it **only** when no semantic HTML element is appropriate.

---

## 14. `<span>` — Generic Inline Container

```html
<span>
```

Has **no semantic meaning** — it's the inline equivalent of `<div>`.

```html
<p>Hello <span style="color: red;">World</span></p>
```

Only "World" can be styled independently without creating a new block.

### `<div>` vs `<span>`

| `<div>` | `<span>` |
| :--- | :--- |
| Block-level | Inline |
| Starts on a new line | Stays in the flow of text |
| Takes full width | Takes only needed width |

---

## 15. `<dialog>` — Native Modal Dialog

```html
<dialog id="myDialog">
    <p>This is a dialog box.</p>
    <button onclick="document.getElementById('myDialog').close()">Close</button>
</dialog>

<button onclick="document.getElementById('myDialog').showModal()">Open Dialog</button>
```

### Purpose

Creates a native **modal or non-modal dialog box** — no JavaScript libraries needed.

| Method | Behaviour |
| :--- | :--- |
| `.show()` | Opens as a non-modal (background still interactive) |
| `.showModal()` | Opens as a true modal (background blocked) |
| `.close()` | Closes the dialog |

### `open` Attribute

```html
<dialog open>
    <p>This dialog is open by default.</p>
</dialog>
```

> [!TIP]
> `<dialog>` has built-in accessibility features: it traps keyboard focus inside the modal, supports the `Escape` key to close, and correctly manages ARIA `role="dialog"` automatically.

---

## 📚 Block vs Inline Elements

Elements in HTML generally fall into two layout categories: **Block** and **Inline**.

| Block-level Elements | Inline-level Elements |
| :--- | :--- |
| `<div>` | `<span>` |
| `<p>` | `<a>` |
| `<h1>`–`<h6>` | `<img>` |
| `<section>` | `<strong>` |
| `<article>` | `<em>` |
| `<table>` | `<input>` |
| `<ul>`, `<ol>` | `<br>` |
| `<header>`, `<footer>` | `<abbr>` |

### Key Differences

- **Block Elements**: Start on a new line and take up the full width available.
- **Inline Elements**: Do not start on a new line and only take up as much width as necessary.

> [!WARNING]
> In HTML5, the block/inline distinction is technically replaced by **content categories** (flow content, phrasing content, etc.), but the block/inline mental model remains useful for understanding CSS layout behavior.

---

## 🌐 Accessibility Benefits

Semantic elements improve:

- Screen readers
- Keyboard navigation
- Search engine understanding
- SEO
- AI interpretation
- Maintainability

### Browser Landmark Navigation

```text
Header → Main → Navigation → Article → Aside → Footer
```

Assistive technologies allow users to jump directly between these landmarks.

---

## W3C Validator Analysis

### ✅ Correct

- `<header>`, `<main>`, `<article>`, `<aside>`, `<footer>`
- `<details>`, `<summary>`
- `<mark>`, `<time>`
- `aria-label`

All are valid HTML5 elements.

### ⚠ Improvements

#### 1. Remove excessive `<br>` elements for spacing

Using many `<br>` tags for spacing is not valid layout practice. Use CSS instead:

```css
.section-spacing {
    margin-top: 500px;
}
```

#### 2. Wrap multi-line code in `<pre><code>`

```html
<!-- ❌ Wrong -->
<code>
    ...
</code>

<!-- ✅ Correct -->
<pre>
<code>
    ...
</code>
</pre>
```

#### 3. Remove empty elements

```html
<div></div>
<span></span>
```

These are valid HTML, but they have no purpose unless used for styling or scripting. Remove them if they are placeholders.

---

## 🧪 Self-Check Questions & Quizzes

### Question 1: Section vs Article ⭐

What is the difference between `<section>` and `<article>`?

<details>
<summary><b>💡 Click to Reveal Solution & Explanation</b></summary>

#### ✅ Solution
`<section>` groups **related content** that needs the page's context. `<article>` contains **self-contained content** that makes sense on its own.

#### 🔍 Explanation
A blog post is an `<article>` because it can be syndicated independently. The "Related Posts" sidebar on that same page is a `<section>` because it only makes sense in the context of the current page.
</details>

---

### Question 2: How Many `<main>` Elements? ⭐

How many `<main>` elements should a webpage have?

<details>
<summary><b>💡 Click to Reveal Solution & Explanation</b></summary>

#### ✅ Solution
```text
One
```

#### 🔍 Explanation
The HTML spec requires only **one visible `<main>`** per page. It should contain the dominant content that is unique to that page. Navigation, footers, and sidebars should be outside `<main>`.
</details>

---

### Question 3: ARIA Label ⭐⭐

When should you use `aria-label` on an element?

<details>
<summary><b>💡 Click to Reveal Solution & Explanation</b></summary>

#### ✅ Solution
When the element has no visible text that describes its purpose to screen reader users.

#### 🔍 Explanation
If a `<nav>` contains only links without a visible heading, `aria-label="Primary Navigation"` tells screen readers what the navigation is for. If a visible `<h2>` already labels the section, use `aria-labelledby` to reference it instead.
</details>

---

### Question 4: details Without JavaScript ⭐⭐⭐

How does `<details>` create an interactive toggle without JavaScript?

<details>
<summary><b>💡 Click to Reveal Solution & Explanation</b></summary>

#### ✅ Solution
The browser has **built-in behavior** for `<details>` that toggles the visibility of its content when the `<summary>` is clicked.

#### 🔍 Explanation
This is a native HTML5 widget. The browser handles the open/close state internally using the `open` attribute. You can detect state changes in JavaScript using the `toggle` event, but the core functionality requires no scripting.
</details>

---

## 🔑 Key Takeaways

| Concept | Key Point |
| :--- | :--- |
| **Semantic HTML** | Uses elements that describe meaning, not just appearance |
| **`<header>`** | Introductory content — logo, title, nav |
| **`<main>`** | Primary page content — only one per page |
| **`<section>`** | Groups related content with a common theme |
| **`<article>`** | Self-contained, independently distributable content |
| **`<aside>`** | Supplementary content — tips, ads, related links |
| **`<footer>`** | Closing content — copyright, legal, social links |
| **`<nav>`** | Major navigation blocks |
| **`<details>/<summary>`** | Native toggle widget — no JavaScript needed |
| **`<time>`** | Machine-readable dates and durations (ISO-8601) |
| **`<div>`/`<span>`** | Generic containers — use only when no semantic element fits |
| **`<dialog>`** | Native modal dialog — use `.showModal()` for accessible modals |
| **Block vs Inline** | Block = new line + full width; Inline = stays in text flow |

---

| [⬅️ Text Formatting](02-Text-Formatting.md) | [🏠 HTML5 Index](README.md) | [Links & Images ➔](04-Links-Images.md) |
