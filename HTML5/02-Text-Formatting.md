| [⬅️ Fundamentals](01-Fundamentals.md) | [🏠 HTML5 Index](README.md) | [Semantic HTML ➔](03-Semantic-HTML.md) |
---

# 📖 Module 2: Text Formatting & Structure

<details open>
<summary><b>📋 What You'll Learn</b></summary>

- Understand the **`<hr>`** thematic break and when to use it
- Master the **heading hierarchy** (`<h1>` – `<h6>`) and document outline
- Differentiate between **semantic** (`<em>`, `<strong>`) and **visual** (`<i>`, `<b>`) formatting
- Use **`<abbr>`**, **`<address>`**, and **`<br>`** correctly
- Work with **HTML character entities** and **non-breaking spaces**
- Understand **lists** — unordered, ordered, and description lists
- Use **Lorem Ipsum** for prototyping layouts
- Practice with **3 interactive quiz questions**

</details>

---

## 1. `<hr>` — Horizontal Rule

```html
<hr>
```

### Purpose

Creates a **thematic break** between sections of content.

It indicates that one topic has ended and another has begun.

Example:

```text
Introduction
────────────────────────────
Learning HTML
────────────────────────────
Daily Schedule
```

### Browser Rendering

```text
------------------------------
```

---

### Why use `<hr>` instead of drawing a line?

Because HTML is **semantic**.

The browser understands that:

> "A new section starts here."

Screen readers can also announce the separator.

### Common Uses

- Separate chapters
- Separate articles
- Divide content sections
- Improve readability

> [!NOTE]
> `<hr>` is a **void element** — it has no closing tag. Writing `<hr></hr>` or `<hr/>` is unnecessary in HTML5.

---

## 2. Heading Hierarchy

```html
<h2>I'm ready to learn HTML</h2>
<h3>My Daily Schedule</h3>
```

### Heading Levels

```text
h1
│
├── h2
│      ├── h3
│      │      ├── h4
│      │      │      ├── h5
│      │      │      │       └── h6
```

Each heading represents a level in the document outline.

Think of it like a book:

```text
Book Title       → h1
    Chapter      → h2
        Section  → h3
            Subsection → h4
```

### Best Practice

Never choose heading levels because of their size.

Use them according to the document structure.

Good:

```text
h1
 ├── h2
 │     └── h3
```

Bad:

```text
h1
h4  ← Skipped h2 and h3!
h2
```

> [!WARNING]
> Skipping heading levels (e.g., `<h1>` → `<h4>`) breaks the document outline and confuses screen readers. Search engines also use heading hierarchy for SEO ranking.

---

## 3. `<em>` — Emphasis

```html
<em>really need a getaway</em>
```

Browser Output: _really need a getaway_

### Purpose

Adds **emphasis** to text.

It usually appears in italics.

However,

> The meaning is more important than the appearance.

Screen readers pronounce emphasized text differently.

### Difference Between `<i>` and `<em>`

| `<i>` | `<em>` |
| :--- | :--- |
| Italic style only | Semantic emphasis |
| Visual formatting | Meaning + formatting |
| Not important | Important emphasis |

> [!TIP]
> Use `<em>` whenever the text has emphasis. Use `<i>` only for stylistic italics like foreign words, technical terms, or thought text — where no emphasis is intended.

---

## 4. `<strong>` — Strong Importance

```html
<strong>MDN</strong>
```

Browser Output: **MDN**

### Purpose

Indicates strong importance.

Screen readers give extra stress to the enclosed text.

### Difference Between `<b>` and `<strong>`

| `<b>` | `<strong>` |
| :--- | :--- |
| Bold only | Strong importance |
| Visual | Semantic |

> [!NOTE]
> `<b>` is appropriate for keywords in a summary, product names, or lead sentences where no special importance is conveyed. For everything else, prefer `<strong>`.

---

## 5. `<abbr>` — Abbreviation

```html
<abbr title="Balasore">BLS</abbr>
```

### Purpose

Defines an abbreviation or acronym.

Hovering over it displays the full meaning.

```text
BLS → Mouse Hover → Balasore
```

Another example:

```html
<abbr title="Mozilla Developer Network">
    <strong>MDN</strong>
</abbr>
```

Hovering over MDN shows: `Mozilla Developer Network`

### Why use `<abbr>`?

- Better accessibility
- Better SEO
- Improves readability
- Helps users understand abbreviations

> [!IMPORTANT]
> Always provide the `title` attribute on `<abbr>`. Without it, the element has no practical benefit — browsers won't show anything on hover.

---

## 6. `<address>` — Contact Information

```html
<address>
    State Bank of India<br>
    Main Road<br>
    Balasore<br>
    Odisha<br>
    756001
</address>
```

### Purpose

Represents contact information.

Typical contents:

- Address
- Email
- Phone Number
- Website
- Author Contact

Browsers usually render it in italics.

### Semantic Meaning

The browser understands: `"This is contact information."` instead of `"This is just another paragraph."`

> [!WARNING]
> `<address>` should only contain contact information for the nearest `<article>` ancestor or the `<body>`. Do **not** use it for arbitrary postal addresses in page content — use a regular `<p>` for those.

---

## 7. `<br>` — Line Break

```html
<br>
```

Forces text onto the next line.

Without `<br>`:

```text
Morning Afternoon Night
```

With `<br>`:

```text
Morning
Afternoon
Night
```

### When to Use

- Addresses
- Poems
- Songs
- Short formatted text

> [!WARNING]
> Avoid using `<br>` to create spacing between paragraphs. Use separate block elements and CSS for layout. Multiple `<br>` tags in a row is a code smell.

---

## 8. `&nbsp;` — Non-Breaking Space

```html
&nbsp;
```

HTML normally collapses multiple spaces into one.

Example:

```text
Hello     World  →  Browser renders:  Hello World
```

`&nbsp;` creates a space that the browser keeps.

```html
Hello&nbsp;&nbsp;&nbsp;World
```

Output: `Hello   World`

> [!TIP]
> Modern HTML prefers CSS (e.g., `margin` or `padding`) for spacing rather than repeated `&nbsp;`. The `&nbsp;` entity is best used for preventing line breaks between two words (e.g., `10&nbsp;km`).

---

## 9. HTML Character Entities

Some characters are reserved in HTML. Instead of writing them directly, HTML uses entities.

| Entity | Output | Name |
| :--- | :--- | :--- |
| `&lt;` | < | Less Than |
| `&gt;` | > | Greater Than |
| `&amp;` | & | Ampersand |
| `&copy;` | © | Copyright |
| `&quot;` | " | Double Quote |
| `&apos;` | ' | Apostrophe |

### Why Character Entities Exist

Imagine writing:

```html
<p>5 < 10</p>
```

The browser may think `< 10` starts a tag.

Correct:

```html
<p>5 &lt; 10</p>
```

> [!NOTE]
> Inside HTML attributes, always escape `"` as `&quot;` and `&` as `&amp;`. In normal text content, only `<` and `&` strictly need escaping.

---

## 10. HTML Comments

```html
<!-- TODO: Add a list of things I want to learn -->
```

### Purpose

Comments are ignored by the browser.

They are only for developers.

Uses:

- Notes
- TODOs
- Reminders
- Temporary explanations

> [!WARNING]
> Comments are **visible in the page source** (View Source / DevTools). Never put passwords, API keys, or sensitive information in HTML comments.

---

## Accessibility Notes

✅ `<em>` provides meaningful emphasis.

✅ `<strong>` indicates importance.

✅ `<abbr>` supplies the expanded form of abbreviations.

✅ `<address>` identifies contact information.

These semantic elements improve accessibility for screen readers and assistive technologies.

---

## W3C Validator Analysis

> [!NOTE]
> Validate your HTML using the **W3C Markup Validation Service**: [https://validator.w3.org/](https://validator.w3.org/)

### Validation Review

| Check | Status | Notes |
| :--- | :--- | :--- |
| `<hr>` usage | ✅ Valid | Correct thematic breaks |
| Heading hierarchy | ✅ Valid | `h1 → h2 → h3` is properly nested |
| `<em>` | ✅ Valid | Semantic emphasis used correctly |
| `<strong>` | ✅ Valid | Strong importance used correctly |
| `<abbr>` | ✅ Valid | Includes the required `title` attribute |
| `<address>` | ✅ Valid | Appropriate use for contact information |
| `<br>` | ✅ Valid | Acceptable for address and formatted schedule |
| HTML comments | ✅ Valid | Ignored by browsers |
| Character entities | ✅ Valid | Properly escaped |
| `&nbsp;` | ⚠ Improvement | Works correctly, but CSS is preferred for layout and spacing |

---

## 📝 Lists

### Unordered List — `<ul>`

```html
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
```

Creates a bulleted list.

```text
• HTML
• CSS
• JavaScript
```

Structure:

```text
ul
│
├── li
├── li
└── li
```

---

### List Item — `<li>`

```html
<li>
```

Represents one item inside a list.

Can contain:

- Paragraphs
- Images
- Links
- Headings
- Other lists (nested lists)

---

### Ordered List — `<ol>`

```html
<ol>
    <li>Wake up</li>
    <li>Code</li>
    <li>Sleep</li>
</ol>
```

Creates numbered items: `1. 2. 3.`

Perfect for:

- Recipes
- Tutorials
- Steps
- Algorithms

---

### Description List — `<dl>`

```html
<dl>
    <dt>Paris</dt>
    <dd>It's a beautiful city.</dd>
    <dt>Tokyo</dt>
    <dd>The capital of Japan.</dd>
</dl>
```

Unlike `<ul>` or `<ol>`, description lists contain **term → definition** pairs.

- `<dt>` — Description **Term**
- `<dd>` — Description **Definition**

```text
dl
│
├── dt → Paris
├── dd → It's a beautiful city.
├── dt → Tokyo
└── dd → The capital of Japan.
```

Perfect for:

- Dictionaries
- FAQs
- Glossaries
- Product descriptions

---

## 📝 Lorem Ipsum

Lorem Ipsum is standard placeholder (dummy) text used in web design and development to demonstrate the visual form of a document without relying on meaningful content.

### Purpose

- Fills in text areas during the layout and design phase.
- Helps designers and developers test typography and formatting.

### Example

```html
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
</p>
```

> [!TIP]
> Many text editors (like VS Code) have built-in shortcuts to generate dummy text. Simply type `lorem` and press `Tab` or `Enter`.

---

## 🧪 Self-Check Questions & Quizzes

### Question 1: Semantic vs Visual ⭐

What is the difference between `<em>` and `<i>`?

<details>
<summary><b>💡 Click to Reveal Solution & Explanation</b></summary>

#### ✅ Solution
`<em>` adds **semantic emphasis** — screen readers announce it differently. `<i>` is purely **visual** (italic) with no added meaning.

#### 🔍 Explanation
Both render as italic text, but `<em>` tells the browser and assistive technologies that the content is emphasized. `<i>` is used for stylistic purposes only (e.g., foreign words, technical terms).
</details>

---

### Question 2: Character Entities ⭐⭐

Why would `<p>5 < 10</p>` cause problems in a browser?

<details>
<summary><b>💡 Click to Reveal Solution & Explanation</b></summary>

#### ✅ Solution
The browser interprets `<` as the start of an HTML tag, potentially breaking the markup.

#### 🔍 Explanation
The `<` character is reserved in HTML. The browser sees `< 10` and tries to parse it as a tag name. The correct way is to use the entity `&lt;`:
```html
<p>5 &lt; 10</p>
```
</details>

---

### Question 3: List Types ⭐⭐

When would you use a `<dl>` instead of a `<ul>` or `<ol>`?

<details>
<summary><b>💡 Click to Reveal Solution & Explanation</b></summary>

#### ✅ Solution
When you need to display **term-definition pairs** such as glossaries, FAQs, or metadata.

#### 🔍 Explanation
- `<ul>` is for unordered collections (e.g., a list of skills).
- `<ol>` is for ordered sequences (e.g., steps in a recipe).
- `<dl>` is for term-definition pairs where each item has a label and a description (e.g., a dictionary or FAQ).
</details>

---

## 🔑 Key Takeaways

| Concept | Key Point |
| :--- | :--- |
| **`<hr>`** | Semantic thematic break — not just a visual line |
| **Headings** | `<h1>`–`<h6>` define document outline — never skip levels |
| **`<em>` vs `<i>`** | `<em>` = emphasis (semantic), `<i>` = italic (visual only) |
| **`<strong>` vs `<b>`** | `<strong>` = importance (semantic), `<b>` = bold (visual only) |
| **`<abbr>`** | Marks abbreviations — always include the `title` attribute |
| **`<address>`** | For contact information only — not arbitrary addresses |
| **`<br>`** | Line break for poems/addresses — not for layout spacing |
| **Entities** | Use `&lt;`, `&gt;`, `&amp;` for reserved characters |
| **Comments** | Developer notes — invisible to users but visible in source |
| **Lists** | `<ul>` (bullets), `<ol>` (numbers), `<dl>` (term-definition) |

---

| [⬅️ Fundamentals](01-Fundamentals.md) | [🏠 HTML5 Index](README.md) | [Semantic HTML ➔](03-Semantic-HTML.md) |
