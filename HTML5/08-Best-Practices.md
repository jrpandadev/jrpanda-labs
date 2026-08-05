| [⬅️ Forms](07-Forms.md) | [🏠 HTML5 Index](README.md) | [Interview Questions ➔](09-Interview-Questions.md) |
---

# 📖 Module 8: Best Practices

<details open>
<summary><b>📋 What You'll Learn</b></summary>

- Apply **HTML5 best practices** for clean, maintainable, and professional code
- Master **accessibility (a11y)** techniques: ARIA, skip links, keyboard navigation
- Implement **SEO** best practices: meta tags, heading hierarchy, Open Graph
- Optimize **performance**: resource hints, image optimization, Core Web Vitals
- Understand **security** fundamentals: CSP, XSS prevention, HTTPS
- Follow the **Senior Developer Checklist** for production-ready HTML

</details>

---

## 📝 HTML Best Practices

### 1. Always Declare DOCTYPE

```html
<!DOCTYPE html>
```

Without it, browsers switch to **Quirks Mode** — causing inconsistent rendering.

---

### 2. Use Semantic Elements

```html
<!-- ❌ Non-semantic -->
<div id="header"></div>
<div id="content"></div>
<div id="footer"></div>

<!-- ✅ Semantic -->
<header></header>
<main></main>
<footer></footer>
```

Semantic elements improve accessibility, SEO, and maintainability.

---

### 3. Always Include `alt` on Images

```html
<!-- ✅ Descriptive -->
<img src="city.jpg" alt="Anime city skyline at sunset">

<!-- ❌ Useless -->
<img src="city.jpg" alt="image">

<!-- ✅ Decorative (intentionally empty) -->
<img src="decoration.svg" alt="">
```

> [!IMPORTANT]
> For purely decorative images, use `alt=""` (empty string) — not `alt="image"`. This tells screen readers to skip the image entirely.

---

### 4. One `<h1>` Per Page

Use a single `<h1>` for the primary topic. Follow the heading hierarchy without skipping levels.

```text
✅ Good:  h1 → h2 → h3 → h4
❌ Bad:   h1 → h4 (skipped h2, h3)
```

---

### 5. Always Specify `width` and `height` on Images

```html
<img src="photo.jpg" alt="..." width="800" height="600">
```

Prevents **Cumulative Layout Shift (CLS)** — one of the Core Web Vitals.

---

### 6. Use External CSS

```html
<link rel="stylesheet" href="styles.css">
```

Keep styles separate from markup. Enables caching, reuse, and easier maintenance.

---

### 7. Validate Your HTML

Use the [W3C Validator](https://validator.w3.org/) to catch errors early.

---

### 8. Close All Tags Properly

```html
<!-- ❌ Missing closing tag -->
<p>Hello
<p>World

<!-- ✅ Correct -->
<p>Hello</p>
<p>World</p>
```

---

### 9. Use Lowercase Tag Names

```html
<!-- ❌ Uppercase -->
<DIV><P>Hello</P></DIV>

<!-- ✅ Lowercase -->
<div><p>Hello</p></div>
```

Lowercase is the HTML5 convention and improves readability.

---

### 10. Indent Your Code

Proper indentation makes code readable and maintainable.

```html
<ul>
    <li>
        <a href="#">Link</a>
    </li>
</ul>
```

---

### 11. Use Meaningful `id` and `class` Names

```html
<!-- ❌ Unclear -->
<div class="box1"></div>

<!-- ✅ Descriptive -->
<div class="product-card"></div>
```

---

### 12. Don't Use `<br>` for Spacing

```html
<!-- ❌ Bad -->
<br><br><br>

<!-- ✅ Use CSS -->
<div style="margin-top: 2rem;"></div>
```

---

### 13. Use `<label>` for Every Form Input

```html
<label for="email">Email</label>
<input id="email" type="email">
```

Improves accessibility and click target area.

---

### 14. Don't Put Block Elements Inside Inline Elements

```html
<!-- ❌ Invalid -->
<span><div>Content</div></span>

<!-- ✅ Valid -->
<div><span>Content</span></div>
```

---

### 15. Remove Unnecessary Empty Elements

```html
<!-- ❌ Useless -->
<div></div>
<span></span>

<!-- ✅ Only include if used for styling or scripting -->
```

---

## ♿ Accessibility (a11y)

Accessibility ensures your website works for **everyone**, including people with disabilities.

### Semantic Landmarks

Use semantic elements so assistive technologies can navigate by landmark:

```html
<header>   <!-- Banner landmark -->
<nav>      <!-- Navigation landmark -->
<main>     <!-- Main landmark -->
<aside>    <!-- Complementary landmark -->
<footer>   <!-- Content info landmark -->
```

### Skip Links

Allow keyboard users to skip navigation and jump to main content:

```html
<a href="#main-content" class="skip-link">Skip to main content</a>
<!-- ... navigation ... -->
<main id="main-content">
```

> [!NOTE]
> The CSS below uses advanced layout properties (`position`, `z-index`) which are outside the scope of HTML basics. You will learn these in a dedicated CSS course, but they are included here because Skip Links require CSS to visually hide and show the link.

```css
.skip-link {
    position: absolute;
    top: -40px;
    left: 0;
    background: #000;
    color: #fff;
    padding: 8px;
    z-index: 100;
}

.skip-link:focus {
    top: 0;
}
```

### Keyboard Navigation

- All interactive elements must be reachable via **Tab**
- All actions must be triggerable via **Enter** or **Space**
- Never remove `:focus` styles without providing a visible alternative

### ARIA Attributes

| Attribute | Purpose |
| :--- | :--- |
| `aria-label` | Provides an accessible name for elements without visible text |
| `aria-labelledby` | Points to a visible element that labels this element |
| `aria-describedby` | Points to a visible element that describes this element |
| `aria-hidden="true"` | Hides decorative elements from screen readers |
| `role` | Defines the element's role if no semantic HTML element fits |

> [!WARNING]
> The **first rule of ARIA** is: Don't use ARIA if a native HTML element does the same thing. For example, use `<button>` instead of `<div role="button">`.

### Focus Management

```css
/* ❌ Never do this */
*:focus {
    outline: none;
}

/* ✅ Custom focus styles */
*:focus-visible {
    outline: 2px solid #4A90D9;
    outline-offset: 2px;
}
```

---

## 🔍 SEO (Search Engine Optimization)

### Essential Meta Tags

```html
<head>
    <title>Page Title — Site Name</title>
    <meta name="description" content="50-160 char description">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="canonical" href="https://example.com/page">
</head>
```

### Open Graph (Social Sharing)

```html
<meta property="og:title" content="My Page Title">
<meta property="og:description" content="A brief description">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:url" content="https://example.com/page">
<meta property="og:type" content="website">
```

These tags control how your page appears when shared on social media (Facebook, LinkedIn, Twitter/X).

### Twitter Cards

```html
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="My Page Title">
<meta name="twitter:description" content="A brief description">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

### SEO Checklist

| Check | Status |
| :--- | :--- |
| Unique `<title>` per page | Required |
| Meta description (50-160 chars) | Required |
| Single `<h1>` per page | Required |
| Proper heading hierarchy | Required |
| `alt` text on all images | Required |
| Semantic HTML elements | Required |
| Canonical URL | Recommended |
| Open Graph tags | Recommended |
| Structured data (JSON-LD) | Advanced |

---

## ⚡ Performance

### Resource Hints

```html
<!-- Preconnect to CDNs -->
<link rel="preconnect" href="https://fonts.googleapis.com">

<!-- Preload critical resources -->
<link rel="preload" href="hero.jpg" as="image">

<!-- Prefetch next page resources -->
<link rel="prefetch" href="/about.html">
```

| Hint | Purpose |
| :--- | :--- |
| `preconnect` | Establishes early connection to external origins |
| `preload` | Downloads critical resources immediately |
| `prefetch` | Downloads resources for future navigation |
| `dns-prefetch` | Resolves DNS for external domains early |

### Image Optimization

```html
<!-- Use modern formats with fallback -->
<picture>
    <source type="image/avif" srcset="hero.avif">
    <source type="image/webp" srcset="hero.webp">
    <img src="hero.jpg" alt="Hero image" width="1200" height="600" loading="eager">
</picture>
```

### Core Web Vitals

| Metric | What it Measures | Target |
| :--- | :--- | :--- |
| **LCP** (Largest Contentful Paint) | How fast the main content loads | < 2.5s |
| **INP** (Interaction to Next Paint) | How responsive the page is | < 200ms |
| **CLS** (Cumulative Layout Shift) | How stable the layout is | < 0.1 |

> [!TIP]
> The fastest performance wins:
> - Specify `width` and `height` on all images (prevents CLS)
> - Use `loading="lazy"` on below-fold images (improves LCP)
> - Minimize render-blocking CSS/JS
> - Use `<link rel="preload">` for critical assets

---

## 🔒 Security

### Content Security Policy (CSP)

```html
<meta http-equiv="Content-Security-Policy"
      content="default-src 'self'; img-src *; script-src 'self'">
```

Restricts which resources the browser can load, preventing XSS attacks.

### XSS Prevention

- Always **sanitize user input** on the server
- Use `textContent` instead of `innerHTML` when setting text dynamically
- Never put user data directly into HTML without escaping
- Use CSP headers to restrict script sources

### HTTPS

- Always serve pages over HTTPS
- Use `<meta http-equiv="Content-Security-Policy" content="upgrade-insecure-requests">`
- Set `Strict-Transport-Security` header on the server

### Form Security

```html
<!-- Use POST for sensitive data -->
<form method="post" action="/login">
    <!-- Add CSRF token -->
    <input type="hidden" name="csrf_token" value="...">
</form>
```

> [!CAUTION]
> Never store passwords, API keys, or sensitive information in:
> - HTML comments
> - Hidden form fields (without encryption)
> - Local/session storage
> - URL parameters

---

## ✅ Senior Developer Checklist

```text
Before Deployment:
├── HTML
│   ├── ✅ DOCTYPE declared
│   ├── ✅ lang attribute set
│   ├── ✅ charset UTF-8
│   ├── ✅ viewport meta tag
│   ├── ✅ Single h1, proper heading hierarchy
│   ├── ✅ Semantic elements used throughout
│   ├── ✅ All images have alt text
│   ├── ✅ All images have width/height
│   └── ✅ W3C validation passes
│
├── Accessibility
│   ├── ✅ Skip link present
│   ├── ✅ All forms have labels
│   ├── ✅ Focus styles visible
│   ├── ✅ Keyboard navigable
│   └── ✅ ARIA used sparingly and correctly
│
├── SEO
│   ├── ✅ Unique title per page
│   ├── ✅ Meta description present
│   ├── ✅ Open Graph tags set
│   └── ✅ Canonical URL defined
│
├── Performance
│   ├── ✅ Critical images preloaded
│   ├── ✅ Below-fold images lazy loaded
│   ├── ✅ External CSS (no inline styles)
│   └── ✅ Modern image formats (WebP/AVIF)
│
└── Security
    ├── ✅ HTTPS enforced
    ├── ✅ CSP headers set
    ├── ✅ Server-side validation
    └── ✅ No sensitive data in HTML
```

---

## 🔑 Key Takeaways

| Concept | Key Point |
| :--- | :--- |
| **DOCTYPE** | Always declare — prevents Quirks Mode |
| **Semantic HTML** | Use `<header>`, `<main>`, `<footer>` — not `<div>` soup |
| **Accessibility** | Skip links, labels, focus styles, keyboard navigation |
| **SEO** | Unique `<title>`, meta description, heading hierarchy, Open Graph |
| **Performance** | Preload critical assets, lazy load images, specify dimensions |
| **Security** | CSP headers, XSS prevention, HTTPS, server-side validation |
| **Validation** | Use W3C Validator before every deployment |
| **Code Quality** | Indent properly, use lowercase, close all tags, meaningful names |

---

| [⬅️ Forms](07-Forms.md) | [🏠 HTML5 Index](README.md) | [Interview Questions ➔](09-Interview-Questions.md) |
