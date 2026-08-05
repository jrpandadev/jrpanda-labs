| [⬅️ Best Practices](08-Best-Practices.md) | [🏠 HTML5 Index](README.md) |
---

# 📖 Module 9: Interview Questions

<details open>
<summary><b>📋 What You'll Learn</b></summary>

- Test your knowledge with **40+ HTML interview questions** across all topics
- Practice with **collapsible answers** — try to answer before revealing
- Questions are organized by topic and rated by difficulty ⭐ – ⭐⭐⭐
- Covers: Fundamentals, Text, Semantic HTML, Links, Images, CSS, Tables, and Forms

</details>

---

## 📌 Fundamentals ⭐

<details>
<summary><b>1. What is the purpose of <code>&lt;!DOCTYPE html&gt;</code>?</b></summary>

It tells the browser to render the document using the **HTML5 standard**. Without it, browsers may switch to Quirks Mode, causing inconsistent rendering across browsers.
</details>

---

<details>
<summary><b>2. What is the difference between <code>&lt;head&gt;</code> and <code>&lt;body&gt;</code>?</b></summary>

- `<head>` contains **metadata and resources** (title, CSS links, meta tags, scripts).
- `<body>` contains the **visible content** shown to users.
</details>

---

<details>
<summary><b>3. Why is <code>lang="en"</code> important?</b></summary>

It improves **accessibility** (screen readers pronounce words correctly), **translation accuracy**, and **search engine understanding**.
</details>

---

<details>
<summary><b>4. What does <code>charset="UTF-8"</code> do?</b></summary>

It specifies the **character encoding**, allowing text from many languages and symbols (including emojis) to display correctly. Without it, characters may render as `�`.
</details>

---

<details>
<summary><b>5. What is the DOM?</b></summary>

The **Document Object Model (DOM)** is the tree-like representation of an HTML document that browsers create, allowing JavaScript to read and modify the page dynamically. The DOM may differ from the source code — browsers can fix errors and insert missing elements.
</details>

---

<details>
<summary><b>6. What is a favicon?</b></summary>

A favicon is the small icon displayed in the **browser tab**, bookmarks, and other browser UI elements to identify a website.
</details>

---

## ✏️ Text Formatting ⭐

<details>
<summary><b>7. What is the difference between <code>&lt;em&gt;</code> and <code>&lt;i&gt;</code>?</b></summary>

`<em>` adds **semantic emphasis** and is announced differently by screen readers. `<i>` is primarily a **visual italic style** with no semantic meaning — used for foreign words or technical terms.
</details>

---

<details>
<summary><b>8. What is the difference between <code>&lt;strong&gt;</code> and <code>&lt;b&gt;</code>?</b></summary>

`<strong>` indicates **strong importance** (semantic), whereas `<b>` simply makes text **bold** without adding meaning.
</details>

---

<details>
<summary><b>9. Why do we use the <code>&lt;abbr&gt;</code> tag?</b></summary>

To mark abbreviations or acronyms and provide their full form using the `title` attribute, improving **accessibility and usability**. Example: `<abbr title="Cascading Style Sheets">CSS</abbr>`.
</details>

---

<details>
<summary><b>10. When should you use <code>&lt;address&gt;</code>?</b></summary>

For **contact information** related to the page, article, organization, or author. Do not use it for arbitrary postal addresses — use a regular `<p>` for those.
</details>

---

<details>
<summary><b>11. Why are HTML entities needed?</b></summary>

Because characters such as `<`, `>`, and `&` have **special meanings** in HTML. Entities like `&lt;`, `&gt;`, and `&amp;` allow them to be displayed as text instead of being interpreted as markup.
</details>

---

<details>
<summary><b>12. What is the purpose of HTML comments?</b></summary>

To leave **notes, reminders, or explanations** for developers without affecting the rendered webpage. Note: comments are **visible in the page source** — never put sensitive data in them.
</details>

---

## 🏗️ Semantic HTML ⭐⭐

<details>
<summary><b>13. What is the purpose of the <code>&lt;main&gt;</code> element?</b></summary>

It identifies the **primary content** of the page and should appear **only once** per document. Content that repeats across pages (nav, footer) should be outside `<main>`.
</details>

---

<details>
<summary><b>14. What is the difference between <code>&lt;section&gt;</code> and <code>&lt;article&gt;</code>?</b></summary>

A `<section>` groups **related content** that needs the page's context. An `<article>` represents **self-contained content** that could be distributed or reused independently (blog post, news article).
</details>

---

<details>
<summary><b>15. Why use <code>&lt;aside&gt;</code>?</b></summary>

To present **supplementary information** related to the main content, such as tips, advertisements, or related links.
</details>

---

<details>
<summary><b>16. What do <code>&lt;details&gt;</code> and <code>&lt;summary&gt;</code> provide?</b></summary>

A **built-in, accessible disclosure widget** that lets users expand and collapse additional content **without JavaScript**. The browser handles the toggle behavior natively.
</details>

---

<details>
<summary><b>17. What is the purpose of the <code>&lt;time&gt;</code> element?</b></summary>

It provides a **machine-readable representation** of dates, times, or durations while displaying a human-friendly format. Search engines and calendars can parse the `datetime` attribute automatically.
</details>

---

<details>
<summary><b>18. What is <code>aria-label</code>?</b></summary>

An accessibility attribute that supplies an **accessible name** for an element, helping screen readers identify its purpose when there's no visible text.
</details>

---

<details>
<summary><b>19. What is the difference between <code>&lt;div&gt;</code> and <code>&lt;span&gt;</code>?</b></summary>

`<div>` is a generic **block-level** container (starts on a new line, takes full width). `<span>` is a generic **inline** container (stays in the text flow). Neither has semantic meaning — use only when no semantic element fits.
</details>

---

<details>
<summary><b>20. What is the purpose of the <code>&lt;nav&gt;</code> element?</b></summary>

It identifies a section containing **major navigation links**, helping browsers, search engines, and assistive technologies. Not every group of links is a `<nav>` — reserve it for primary navigation.
</details>

---

<details>
<summary><b>21. What is the difference between <code>&lt;ul&gt;</code>, <code>&lt;ol&gt;</code>, and <code>&lt;dl&gt;</code>?</b></summary>

- `<ul>`: **Unordered** (bulleted) list.
- `<ol>`: **Ordered** (numbered) list.
- `<dl>`: **Description** list for term-definition pairs.
</details>

---

<details>
<summary><b>22. What is a fragment identifier?</b></summary>

A fragment identifier is the part of a URL after `#` that links to an element with a **matching `id`** on the same page. Example: `#contact` scrolls to `<section id="contact">`.
</details>

---

<details>
<summary><b>23. What are CSS pseudo-classes?</b></summary>

Pseudo-classes define the **state** of an element, such as `:hover`, `:visited`, `:active`, and `:focus`.
</details>

---

<details>
<summary><b>24. Why should <code>id</code> values be unique?</b></summary>

Because each `id` identifies a **single element**, enabling reliable linking, styling, and JavaScript selection. Duplicate IDs cause unpredictable behavior.
</details>

---

## 🔗 Links & Images ⭐⭐

<details>
<summary><b>25. What does the <code>download</code> attribute do?</b></summary>

It instructs the browser to **download** the linked resource instead of opening it. Only works for **same-origin** URLs.
</details>

---

<details>
<summary><b>26. What is the purpose of <code>mailto:</code>?</b></summary>

It opens the user's **default email application** with a new message addressed to the specified email.
</details>

---

<details>
<summary><b>27. What is the purpose of <code>tel:</code>?</b></summary>

It creates a clickable phone number that opens the device's **dialer or calling application**.
</details>

---

<details>
<summary><b>28. Why is <code>target="_blank"</code> commonly used?</b></summary>

It opens the linked page in a **new browser tab**, allowing users to keep the current page open.
</details>

---

<details>
<summary><b>29. Why should <code>rel="noopener noreferrer"</code> be used with <code>target="_blank"</code>?</b></summary>

It prevents the newly opened page from accessing the original page via `window.opener`, improving **security and performance**.
</details>

---

<details>
<summary><b>30. What is the difference between relative, root-relative, and absolute URLs?</b></summary>

- **Relative URL:** Points to a resource relative to the current directory (e.g., `about.html`).
- **Root-relative URL:** Starts from the website's root (e.g., `/about`).
- **Absolute URL:** Includes the full web address (e.g., `https://google.com`).
</details>

---

<details>
<summary><b>31. Why is the <code>alt</code> attribute important?</b></summary>

It provides alternative text for **screen readers** and displays when an image cannot be loaded, making webpages more **accessible**. Use `alt=""` for decorative images.
</details>

---

<details>
<summary><b>32. What is the difference between <code>loading="eager"</code> and <code>loading="lazy"</code>?</b></summary>

- `eager` loads the image **immediately** (default).
- `lazy` **delays loading** until the image is near the viewport, improving page performance.

Never use `lazy` on above-the-fold images — it hurts LCP.
</details>

---

<details>
<summary><b>33. What is the purpose of <code>&lt;figure&gt;</code>?</b></summary>

It groups **self-contained content** (such as images, diagrams, or code) with an optional `<figcaption>`.
</details>

---

<details>
<summary><b>34. When should you use <code>&lt;pre&gt;&lt;code&gt;</code> instead of <code>&lt;code&gt;</code> alone?</b></summary>

When displaying **multi-line code** or preserving whitespace and indentation. `<pre>` preserves formatting; `<code>` alone is for inline code snippets.
</details>

---

<details>
<summary><b>35. Why is using many <code>&lt;br&gt;</code> tags considered bad practice?</b></summary>

Because `<br>` is intended for **line breaks** (poems, addresses), not layout. Spacing and positioning should be handled with **CSS** (`margin`, `padding`).
</details>

---

## 📊 Tables ⭐⭐

<details>
<summary><b>36. What is the purpose of the <code>&lt;caption&gt;</code> element?</b></summary>

It provides a **descriptive title** for the table and improves accessibility — screen readers announce it before reading the table data.
</details>

---

<details>
<summary><b>37. What is the difference between <code>&lt;thead&gt;</code>, <code>&lt;tbody&gt;</code>, and <code>&lt;tfoot&gt;</code>?</b></summary>

- `<thead>` contains **column headers**.
- `<tbody>` contains the **main data**.
- `<tfoot>` contains **summary or footer** information.
</details>

---

<details>
<summary><b>38. What is the difference between <code>&lt;th&gt;</code> and <code>&lt;td&gt;</code>?</b></summary>

`<th>` defines **header cells** (bold, centered by default, used by screen readers). `<td>` defines regular **data cells**.
</details>

---

<details>
<summary><b>39. What does <code>scope="col"</code> and <code>scope="row"</code> do?</b></summary>

They associate header cells with their corresponding **columns or rows**, helping screen readers interpret the table correctly.
</details>

---

<details>
<summary><b>40. What is the difference between <code>rowspan</code> and <code>colspan</code>?</b></summary>

`rowspan` merges cells **vertically** across multiple rows. `colspan` merges cells **horizontally** across multiple columns.
</details>

---

<details>
<summary><b>41. Why use <code>border-collapse: collapse</code>?</b></summary>

It combines adjacent borders into a **single border**, producing a cleaner table appearance instead of double borders.
</details>

---

## 📝 Forms ⭐⭐⭐

<details>
<summary><b>42. What is the purpose of the <code>&lt;form&gt;</code> element?</b></summary>

It **collects user input** and sends data to a server using the `action` (where) and `method` (how) attributes.
</details>

---

<details>
<summary><b>43. Difference between GET and POST?</b></summary>

**GET** sends data through URL parameters (visible, limited size, bookmarkable). **POST** sends data inside the request body (hidden, larger size, more secure for sensitive data).
</details>

---

<details>
<summary><b>44. Why use <code>&lt;fieldset&gt;</code>?</b></summary>

To **group related form controls** and improve accessibility. Combined with `<legend>`, it provides a visible title for the group.
</details>

---

<details>
<summary><b>45. Difference between radio buttons and checkboxes?</b></summary>

**Radio** allows **one choice** from a group (buttons must share the same `name`). **Checkbox** allows **multiple choices** independently.
</details>

---

<details>
<summary><b>46. What does <code>required</code> do?</b></summary>

Prevents form submission until the field contains a value. This is **client-side validation** — always validate on the server too.
</details>

---

<details>
<summary><b>47. What is the purpose of <code>&lt;datalist&gt;</code>?</b></summary>

Provides **predefined suggestions** while users type, combining the flexibility of text input with the convenience of a dropdown.
</details>

---

<details>
<summary><b>48. Why is label association important?</b></summary>

It improves **accessibility** (screen readers announce what each input is for) and allows users to **click the label** to activate the input, increasing the click target area.
</details>

---

## 🔥 Advanced ⭐⭐⭐

<details>
<summary><b>49. What is the difference between <code>localStorage</code> and <code>sessionStorage</code>?</b></summary>

`localStorage` persists data **after the browser is closed**. `sessionStorage` is cleared when the **tab is closed**. Both store key-value pairs and are scoped per origin. Neither should store sensitive data (vulnerable to XSS).
</details>

---

<details>
<summary><b>50. What is Content Security Policy (CSP)?</b></summary>

CSP is a security mechanism that restricts which resources (scripts, images, styles) the browser can load. It prevents **XSS attacks** by whitelisting trusted sources.

```html
<meta http-equiv="Content-Security-Policy"
      content="default-src 'self'; script-src 'self'">
```
</details>

---

<details>
<summary><b>51. What are Core Web Vitals?</b></summary>

Google's metrics for page experience:
- **LCP** (Largest Contentful Paint): Main content load speed — target < 2.5s
- **INP** (Interaction to Next Paint): Responsiveness — target < 200ms
- **CLS** (Cumulative Layout Shift): Visual stability — target < 0.1
</details>

---

<details>
<summary><b>52. What is the <code>&lt;picture&gt;</code> element used for?</b></summary>

It serves **different images** based on screen size, resolution, or format support. The browser picks the first `<source>` that matches and falls back to the `<img>`. Used for art direction and serving modern formats (WebP/AVIF) with fallbacks.
</details>

---

| [⬅️ Best Practices](08-Best-Practices.md) | [🏠 HTML5 Index](README.md) |
