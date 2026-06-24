# Unit IV – Day 2 (2 Hours)
## CSS — Complete Guide for Pharmacy Students

---

## 🎯 Session Goals
By the end of this session, you will be able to:
- Explain what CSS is and why it's separated from HTML
- Use all three ways of applying CSS to a page
- Understand selectors, the box model, colours, typography, and layout properties
- Style tables, forms, and full page sections professionally
- Apply everything practically by styling the pharmacy pages you built in Day 1

---

## ⏱️ Session Plan (2 Hours)

| Time | Block | Topic |
|------|-------|-------|
| 0:00 – 0:05 | — | Session overview |
| 0:05 – 1:05 | **THEORY** | What CSS is → syntax → selectors → box model → colours/fonts → layout |
| 1:05 – 1:55 | **PRACTICAL** | Hands-on styling — restyle Day 1's profile page, drug monograph, form, and portal |
| 1:55 – 2:00 | — | Recap + Q&A |

> 💬 **How to use this document:** Just like Day 1, read all of Part A first. CSS has a LOT of small rules (specificity, the box model, units) that are easy to misuse if you jump straight to styling without understanding them. Part B reuses the exact HTML pages from Day 1 — so make sure those files are saved and ready before the practical begins.

---
---
---

# 🅰️ PART A — THEORY

---

# SECTION 1 — What is CSS and Why It Exists

## 1.1 Definition

> **CSS** stands for **Cascading Style Sheets**.
> - **Cascading** = rules can come from multiple places and "flow down," with clear rules deciding which one wins
> - **Style** = colours, fonts, spacing, layout — the visual appearance
> - **Sheets** = a separate document of style rules, applied to one or many HTML pages

> **HTML builds the structure. CSS decides how that structure looks.**

---

## 1.2 The Pharmacy Analogy, Continued

Recall from Day 1:

| Pharmacy | Web Development |
|----------|----------------|
| **Active ingredient** | **HTML** — structure |
| **Excipients / coating** | **CSS** — appearance |
| **Mechanism of action** | **JavaScript** — behaviour |

A tablet's active ingredient (HTML) is the same Paracetamol whether it's a plain white tablet or a film-coated, brand-coloured one. The **coating** (CSS) doesn't change what the drug does — it changes how it looks, how easy it is to swallow, how trustworthy it appears on the shelf. That is exactly the relationship between your HTML content and your CSS styling.

---

## 1.3 Why Keep CSS Separate from HTML?

Imagine writing the colour, font, and spacing instructions directly inside every single tag, on every single page, of a 50-page hospital website. If the hospital later decides to change its brand colour from navy to teal, you'd have to hunt through every page and change it everywhere — extremely error-prone.

CSS solves this with **one rule, applied everywhere**:

```css
h1 {
    color: navy;
}
```

Change `navy` to `teal` in **one file**, and every `<h1>` across the entire website updates instantly. This is the single biggest reason CSS exists as a separate technology.

---
---

# SECTION 2 — CSS Syntax

## 2.1 The Anatomy of a CSS Rule

```css
selector {
    property: value;
    property: value;
}
```

```css
p {
    color: black;
    font-size: 16px;
}
```

| Part | Meaning |
|------|---------|
| **Selector** (`p`) | WHICH HTML element(s) this rule applies to |
| **Property** (`color`) | WHAT aspect you are changing |
| **Value** (`black`) | The setting you're giving that property |
| **Declaration** | One `property: value;` pair |
| **Rule / Rule-set** | The selector + all its declarations together |

> ⚠️ Every declaration must end with a semicolon `;` — forgetting this is one of the most common CSS mistakes, and it can silently break the *next* declaration too.

---

## 2.2 The Three Ways to Apply CSS

### Method 1 — Inline CSS (on a single element)
```html
<p style="color: red; font-weight: bold;">High Alert Medication</p>
```
Written directly inside the `style` attribute of one tag. Quick, but **not reusable** — if 50 paragraphs need this style, you'd repeat it 50 times. Use only for one-off, rare cases.

### Method 2 — Internal CSS (inside the HTML file)
```html
<head>
    <style>
        p {
            color: navy;
            font-family: Arial, sans-serif;
        }
    </style>
</head>
```
Written inside a `<style>` tag in the `<head>`. Applies to the whole page, but only that one page — other pages don't benefit from it.

### Method 3 — External CSS (a separate `.css` file) — **The Professional Standard**
```html
<head>
    <link rel="stylesheet" href="style.css">
</head>
```

```css
/* style.css */
p {
    color: navy;
    font-family: Arial, sans-serif;
}
```
One `.css` file, linked from as many HTML pages as you like. This is how every real, professional website — including hospital and pharmacy portals — is built. **This is the method we will use for all practicals today.**

> 💬 "Think of External CSS like your hospital's official dress code policy document — one document, referenced by every department, instead of each department writing its own rules from scratch."

---
---

# SECTION 3 — Selectors

Selectors decide *which* HTML elements a rule targets. This is the single most important skill in CSS — get the selector wrong, and your style applies to the wrong thing (or nothing at all).

## 3.1 Element (Type) Selector

Targets every instance of a tag.

```css
p {
    line-height: 1.6;
}

h2 {
    color: #003366;
}
```

## 3.2 Class Selector — `.classname`

Targets every element carrying a specific `class` attribute. Written with a **dot**.

```html
<p class="warning">Do not exceed 4000mg per day.</p>
<p class="warning">Contraindicated in liver disease.</p>
```

```css
.warning {
    color: red;
    font-weight: bold;
}
```

Both paragraphs above turn red and bold — because both share `class="warning"`. This is CSS's most-used selector, because `class` is **reusable** across many elements.

## 3.3 ID Selector — `#idname`

Targets exactly one specific element, matched by its unique `id`. Written with a **hash**.

```html
<div id="patient-card-1">...</div>
```

```css
#patient-card-1 {
    border: 2px solid navy;
}
```

> 💬 Recall from Day 1: `id` must be unique on the page, so an ID selector should only ever match one element. If you find yourself wanting the same style on multiple elements, that's a sign you should be using a `class`, not an `id`.

## 3.4 Grouping Selectors

Apply the same rule to multiple selectors at once, separated by commas:

```css
h1, h2, h3 {
    font-family: 'Segoe UI', Arial, sans-serif;
    color: #003366;
}
```

## 3.5 Descendant Selector

Targets an element only when it's *inside* another specific element:

```css
/* Only <li> elements that are inside a <nav> get this style */
nav li {
    display: inline;
    margin-right: 15px;
}
```

## 3.6 Attribute Selector

Targets elements that have a specific attribute — including `data-*` attributes from Day 1!

```css
/* Targets any input with type="text" */
input[type="text"] {
    border: 1px solid #aaa;
}

/* Targets any element with a data-risk-level of "high" */
[data-risk-level="high"] {
    background-color: #ffe0e0;
}
```

> 💬 "Remember the patient table row with `data-risk-level="high"` from Day 1? This is exactly how you'd visually flag every high-risk patient row in red, automatically, using nothing but CSS."

## 3.7 Pseudo-classes — Styling Based on State

Pseudo-classes apply a style only in a particular *state* — without needing extra HTML or JavaScript.

```css
/* Style a link differently when the mouse hovers over it */
a:hover {
    color: orange;
    text-decoration: underline;
}

/* Style every even row of a table — great for readability in data tables */
tr:nth-child(even) {
    background-color: #f0f8ff;
}

/* Style an input field when it's currently focused/selected */
input:focus {
    border-color: navy;
    outline: none;
}

/* Style the very first paragraph inside a container */
p:first-child {
    font-weight: bold;
}
```

## 3.8 CSS Specificity — Which Rule Wins?

If two rules target the same element with conflicting values, CSS needs a way to decide which one applies. This is called **specificity**, and it follows a clear order, from weakest to strongest:

```
Element selector  <  Class selector  <  ID selector  <  Inline style  <  !important
   (p, h1)           (.warning)         (#header)      (style="...")   (avoid this)
```

```css
p { color: black; }          /* weakest */
.warning { color: red; }     /* stronger — wins over plain p */
#critical { color: orange; } /* even stronger — wins over .warning */
```

```html
<p id="critical" class="warning">This text will be ORANGE — the ID selector wins.</p>
```

> 💬 **Practical tip:** When your CSS doesn't seem to be working, 90% of the time it's a specificity conflict — another rule elsewhere is "winning." Avoid `!important` as a quick fix; it's a strong tool that creates more confusion later. Instead, write more specific selectors deliberately.

---
---

# SECTION 4 — The CSS Box Model

## 4.1 Every Element is a Box

This is the single most important concept for layout in CSS. **Every HTML element — a paragraph, a div, an image, a button — is treated by the browser as a rectangular box**, made of four layers:

```
┌───────────────────────────────────────────┐
│                 MARGIN                    │  ← space OUTSIDE the box, pushes other elements away
│   ┌───────────────────────────────────┐   │
│   │              BORDER                │   │  ← the visible edge/outline of the box
│   │   ┌───────────────────────────┐   │   │
│   │   │          PADDING           │   │   │  ← space INSIDE the box, between border and content
│   │   │   ┌───────────────────┐   │   │   │
│   │   │   │      CONTENT       │   │   │   │  ← the actual text/image/element itself
│   │   │   └───────────────────┘   │   │   │
│   │   └───────────────────────────┘   │   │
│   └───────────────────────────────────┘   │
└───────────────────────────────────────────┘
```

```css
.drug-card {
    width: 300px;
    padding: 15px;          /* space inside, around the content */
    border: 2px solid #003366;
    margin: 20px;            /* space outside, pushing neighbours away */
}
```

> 💬 **Pharmacy analogy:** Think of a blister pack. The **tablet** is the content. The **foil pocket molded around it** is the padding. The **printed edge of the blister card** is the border. The **gap between this blister card and the next one in the box** is the margin.

## 4.2 Box Model Shorthand

```css
/* All four sides the same */
padding: 10px;

/* top/bottom, then left/right */
padding: 10px 20px;

/* top, right, bottom, left — clockwise from top */
padding: 10px 15px 10px 15px;
margin: 10px 15px 10px 15px;
```

## 4.3 `box-sizing` — A Crucial Setting

By default, `width` only refers to the content area — padding and border get ADDED on top, making the box bigger than you expect.

```css
/* Without this, a "300px wide" box with 20px padding and a 2px border
   actually renders at 300+20+20+2+2 = 344px wide! */
* {
    box-sizing: border-box;
}
```

Setting `box-sizing: border-box` on everything makes `width` include padding and border — so a 300px box stays exactly 300px, however much padding you add. **This is considered standard professional practice — include this rule at the top of every stylesheet you write.**

---
---

# SECTION 5 — Colours, Typography, and Backgrounds

## 5.1 Specifying Colours

```css
h1 {
    color: navy;                    /* named colour */
}
h2 {
    color: #003366;                 /* hex code — most common in professional work */
}
p {
    color: rgb(51, 51, 51);         /* red, green, blue values, 0-255 each */
}
.alert {
    color: rgba(255, 0, 0, 0.7);    /* rgb + alpha (transparency), 0 = invisible, 1 = solid */
}
```

> 💬 Hex codes are the most common in real projects. `#003366` is a deep navy — you'll recognise this exact colour from the Aavanto brand work and the patient registration form built in Day 1.

## 5.2 Background Colour and Images

```css
body {
    background-color: #f5f9ff;
}

.alert-box {
    background-color: #ffe0e0;
    background-image: url('warning-icon.png');
    background-repeat: no-repeat;
    background-position: right center;
}
```

## 5.3 Typography (Text Styling)

```css
body {
    font-family: 'Segoe UI', Arial, sans-serif;   /* fallback list — browser tries each in order */
    font-size: 16px;
    line-height: 1.6;          /* space between lines — improves readability */
}

h1 {
    font-weight: bold;
    font-size: 32px;
    text-align: center;
}

.drug-name {
    font-style: italic;        /* for generic drug names, as covered in HTML's <i> tag */
}

.warning-label {
    text-transform: uppercase;  /* WARNING TEXT IN CAPS */
    letter-spacing: 1px;
}

a {
    text-decoration: none;      /* removes the default underline from links */
}
```

| Property | Purpose |
|----------|---------|
| `font-family` | Which typeface to use (with fallbacks) |
| `font-size` | Text size |
| `font-weight` | Boldness (`normal`, `bold`, or `100`–`900`) |
| `font-style` | `normal` or `italic` |
| `line-height` | Vertical spacing between lines of text |
| `text-align` | `left`, `right`, `center`, `justify` |
| `text-decoration` | `underline`, `none`, `line-through` |
| `text-transform` | `uppercase`, `lowercase`, `capitalize` |

---
---

# SECTION 6 — Layout: Display, Flexbox, and Positioning

## 6.1 The `display` Property

Every element has a default display behaviour:

| Value | Behaviour | Examples |
|-------|-----------|----------|
| `block` | Takes the full available width, starts on a new line | `<div>`, `<p>`, `<h1>` |
| `inline` | Takes only as much width as its content needs, stays in line with text | `<span>`, `<a>`, `<b>` |
| `inline-block` | Like inline, but allows width/height/padding to be set | Useful for nav items |
| `none` | Completely hides the element (removed from layout) | Hiding a form field conditionally |

```css
.drug-card {
    display: inline-block;
    width: 200px;
    margin: 10px;
}
```

## 6.2 Flexbox — Modern Layout Made Simple

Flexbox is the modern standard way to align and distribute elements inside a container — horizontally or vertically — without complicated maths.

```css
.dashboard {
    display: flex;
    justify-content: space-between;   /* spreads children apart horizontally */
    align-items: center;               /* centers children vertically */
    gap: 20px;                         /* space between each child */
}
```

```html
<div class="dashboard">
    <div class="stat-card">Total Patients: 240</div>
    <div class="stat-card">High Risk: 12</div>
    <div class="stat-card">Today's Prescriptions: 38</div>
</div>
```

This single `display: flex` rule arranges all three stat cards neatly in a row, evenly spaced — something that took complicated workarounds before Flexbox existed.

| Flexbox Property | Goes On | Purpose |
|-------------------|---------|---------|
| `display: flex` | The container | Switches on flexbox layout for its children |
| `justify-content` | The container | Horizontal spacing/alignment (`center`, `space-between`, `space-around`) |
| `align-items` | The container | Vertical alignment (`center`, `flex-start`, `flex-end`) |
| `flex-direction` | The container | `row` (default) or `column` |
| `gap` | The container | Space between each child element |

## 6.3 Positioning

```css
.badge {
    position: relative;
    top: -5px;     /* shifts up slightly from its normal position */
}

.alert-banner {
    position: fixed;     /* stays in place even when the page scrolls */
    top: 0;
    width: 100%;
    background-color: red;
    color: white;
}
```

| Value | Behaviour |
|-------|-----------|
| `static` | Default — normal flow of the page |
| `relative` | Shifted relative to its own normal position |
| `fixed` | Locked relative to the browser window — stays during scroll |
| `absolute` | Positioned relative to its nearest positioned ancestor |

---
---

# SECTION 7 — Styling Tables and Forms

## 7.1 Styling Tables — Connecting to Day 1

```css
table {
    border-collapse: collapse;   /* removes double borders between cells */
    width: 100%;
}

th {
    background-color: #003366;
    color: white;
    padding: 12px;
    text-align: left;
}

td {
    border: 1px solid #cccccc;
    padding: 10px;
}

tr:nth-child(even) {
    background-color: #f0f8ff;   /* alternating row colour for readability */
}

tr:hover {
    background-color: #ffe0b2;   /* highlight row under the mouse */
}
```

## 7.2 Styling Forms — Connecting to Day 1

```css
label {
    display: block;
    margin-top: 12px;
    font-weight: bold;
    color: #333;
}

input[type="text"],
input[type="number"],
input[type="email"],
input[type="tel"],
input[type="date"],
select,
textarea {
    width: 100%;
    max-width: 420px;
    padding: 8px;
    margin-top: 4px;
    border: 1px solid #aaa;
    border-radius: 4px;
    font-size: 14px;
}

input:focus,
textarea:focus,
select:focus {
    border-color: #003366;
    outline: none;
}

button[type="submit"] {
    margin-top: 20px;
    padding: 12px 40px;
    background-color: #003366;
    color: white;
    border: none;
    border-radius: 4px;
    font-size: 16px;
    cursor: pointer;
}

button[type="submit"]:hover {
    background-color: #00509e;
}

button[type="reset"] {
    margin-top: 20px;
    margin-left: 10px;
    padding: 12px 30px;
    background-color: #888;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}
```

---
---

# SECTION 8 — Borders, Shadows, and Rounded Corners

```css
.drug-card {
    border: 1px solid #ccc;
    border-radius: 10px;                          /* rounded corners */
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);     /* soft drop shadow */
    padding: 16px;
}

.high-alert {
    border-left: 6px solid red;    /* a coloured accent strip — common for alerts */
    background-color: #fff5f5;
}
```

> 💬 "That coloured left-border accent style is exactly how real clinical dashboards visually flag a high-alert medication row or an urgent lab result — a quick glance tells the pharmacist something needs attention, before they even read the text."

---
---

# SECTION 9 — Responsive Design Basics

## 9.1 Why Responsiveness Matters

Recall from Day 1: most patients access health portals on their phones. A page that looks perfect on a laptop screen can be unusable on a small phone screen unless it's built to adapt.

## 9.2 Media Queries

A media query applies CSS rules **only** when the screen matches certain conditions — typically screen width.

```css
/* Default styles — apply to all screen sizes */
.dashboard {
    display: flex;
    gap: 20px;
}

/* Override for small screens (phones), width 600px or less */
@media (max-width: 600px) {
    .dashboard {
        flex-direction: column;   /* stack vertically instead of side-by-side */
    }

    body {
        font-size: 14px;          /* slightly smaller text on small screens */
    }
}
```

> 💬 "This is the same `dashboard` we built with Flexbox in Section 6 — on a laptop it shows three stat cards side by side; on a phone, this media query stacks them vertically so nothing gets squeezed and unreadable."

---
---
---

# 🅱️ PART B — PRACTICAL

> 💬 We will now restyle the exact HTML pages built in Day 1. Open those files again — `practice1.html`, your Student Profile page, the Drug Monograph page, the Diabetes Screening Form, and the Semantic Hospital Portal page. For each practical below, create **one external CSS file**, link it using `<link rel="stylesheet">`, and watch your plain HTML transform.

---

## PRACTICAL 1 — Your First External Stylesheet

**Goal:** Connect an external CSS file to an HTML page and confirm it works.

**Step 1:** In the same folder as `practice1.html`, create a new file named `style.css`.

**Step 2:** Add this single rule to `style.css`:
```css
body {
    background-color: #f0f8ff;
}

h1 {
    color: navy;
    text-align: center;
}
```

**Step 3:** Open `practice1.html` and add the link inside `<head>`:
```html
<head>
    <meta charset="UTF-8">
    <title>My First Pharmacy Page</title>
    <link rel="stylesheet" href="style.css">
</head>
```

**Step 4:** Save both files, then refresh `practice1.html` in your browser. Confirm the background is now light blue and the heading is centered and navy.

---

## PRACTICAL 2 — Style the Student Profile Page

**Goal:** Apply the box model, table styling, and typography to Day 1's Student Profile page.

Create `profile_style.css`:

```css
* {
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', Arial, sans-serif;
    background-color: #f5f9ff;
    margin: 40px;
    color: #222;
}

h1 {
    color: #003366;
    border-bottom: 3px solid #003366;
    padding-bottom: 8px;
}

h2 {
    color: #005599;
    margin-top: 30px;
}

table {
    border-collapse: collapse;
    width: 60%;
    margin-top: 10px;
}

th {
    background-color: #003366;
    color: white;
    padding: 10px;
    text-align: left;
}

td {
    border: 1px solid #ccc;
    padding: 10px;
}

ul li {
    margin-bottom: 6px;
}
```

Link it inside your Student Profile HTML's `<head>`:
```html
<link rel="stylesheet" href="profile_style.css">
```

**Now extend it yourself:** Add a `tr:nth-child(even)` rule for alternating table row colours, and give the page's `<ul>` a `background-color` and `padding` so it looks like a card.

---

## PRACTICAL 3 — Style the Drug Monograph Page

**Goal:** Use class selectors, the box model, and `border-left` accents to style clinical content meaningfully.

First, go back to your Day 1 Drug Monograph HTML and add a class to the warning paragraph:
```html
<p class="max-dose-warning"><strong>Maximum Adult Dose: 4000mg/day.</strong></p>
```

Create `monograph_style.css`:

```css
body {
    font-family: Georgia, serif;
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
    line-height: 1.6;
}

h1 {
    color: #003366;
}

h1 small {
    color: #777;
    font-size: 18px;
}

dl dt {
    font-weight: bold;
    color: #005599;
    margin-top: 10px;
}

dl dd {
    margin-left: 20px;
}

table {
    border-collapse: collapse;
    width: 100%;
    margin: 15px 0;
}

th, td {
    border: 1px solid #ccc;
    padding: 8px;
}

th {
    background-color: #eef4fb;
}

details {
    background-color: #fffbe6;
    border: 1px solid #e6d88a;
    border-radius: 6px;
    padding: 10px 15px;
    margin: 15px 0;
}

summary {
    font-weight: bold;
    cursor: pointer;
}

.max-dose-warning {
    border-left: 6px solid red;
    background-color: #fff5f5;
    padding: 10px 15px;
    margin-top: 20px;
}
```

**Now extend it yourself:** Add a `.indication-list` class to the indications `<ul>` and style it with a green `border-left` accent (since indications are reassuring information, not a warning).

---

## PRACTICAL 4 — Style the Diabetes Screening Form

**Goal:** Apply form-specific selectors, focus states, and Flexbox to lay out the buttons.

Create `form_style.css`:

```css
* {
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f5f9ff;
    margin: 30px;
}

h1 {
    color: #003366;
}

fieldset {
    border: 1px solid #aac;
    border-radius: 8px;
    padding: 15px 20px;
    margin-bottom: 15px;
}

legend {
    font-weight: bold;
    color: #003366;
    padding: 0 5px;
}

label {
    display: block;
    margin-top: 10px;
    font-weight: bold;
}

input[type="text"],
input[type="number"] {
    width: 100%;
    max-width: 350px;
    padding: 8px;
    margin-top: 4px;
    border: 1px solid #aaa;
    border-radius: 4px;
}

input:focus {
    border-color: #003366;
    outline: none;
}

textarea {
    width: 100%;
    max-width: 350px;
    padding: 8px;
    border: 1px solid #aaa;
    border-radius: 4px;
}

.button-row {
    display: flex;
    gap: 10px;
    margin-top: 20px;
}

button[type="submit"] {
    padding: 12px 30px;
    background-color: #003366;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

button[type="submit"]:hover {
    background-color: #00509e;
}

button[type="reset"] {
    padding: 12px 30px;
    background-color: #888;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}
```

> 💬 To use the `.button-row` Flexbox class, wrap your two buttons in a `<div class="button-row">...</div>` in the HTML.

**Now extend it yourself:** Add a `@media (max-width: 500px)` rule that makes the `fieldset` padding smaller and stacks the buttons vertically (`flex-direction: column`) on small screens.

---

## PRACTICAL 5 — Style the Full Semantic Hospital Portal

**Goal:** Bring everything together — Flexbox navigation, card-styled articles, a sticky header, and a responsive layout.

Create `portal_style.css`:

```css
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Segoe UI', Arial, sans-serif;
    color: #222;
    line-height: 1.6;
}

header {
    background-color: #003366;
    color: white;
    padding: 20px;
    text-align: center;
}

nav {
    background-color: #00509e;
    display: flex;
    justify-content: center;
    gap: 25px;
    padding: 12px;
}

nav a {
    color: white;
    text-decoration: none;
    font-weight: bold;
}

nav a:hover {
    text-decoration: underline;
}

main {
    max-width: 900px;
    margin: 20px auto;
    padding: 0 20px;
}

section h2 {
    color: #003366;
    border-bottom: 2px solid #003366;
    padding-bottom: 5px;
}

article {
    background-color: #f5f9ff;
    border: 1px solid #d0dff0;
    border-radius: 8px;
    padding: 15px 20px;
    margin: 15px 0;
}

article h3 {
    color: #005599;
}

aside {
    max-width: 900px;
    margin: 20px auto;
    padding: 15px 20px;
    background-color: #fffbe6;
    border: 1px solid #e6d88a;
    border-radius: 8px;
}

footer {
    background-color: #003366;
    color: white;
    text-align: center;
    padding: 20px;
    margin-top: 30px;
}

footer a {
    color: #cfe3ff;
}

/* Responsive: stack navigation links on small screens */
@media (max-width: 500px) {
    nav {
        flex-direction: column;
        align-items: center;
    }
}
```

**Now extend it yourself:** Give each `article` a `data-drug-id` attribute selector rule (recall this from Day 1!) so that any article matching `[data-drug-id="D003"]` gets a small `border-left: 4px solid #005599` accent — connecting the HTML `data-*` attribute concept directly to a CSS attribute selector.

---

## 🧠 Complete Session Key Takeaways

1. **CSS controls appearance; HTML controls structure** — keeping them separate makes large sites maintainable
2. **External CSS** (`<link rel="stylesheet">`) is the professional standard — one file, linked from many pages
3. **Selectors** — element (`p`), class (`.warning`, reusable), ID (`#header`, unique) — choosing the right one matters
4. **Specificity** decides which rule wins in a conflict: element < class < ID < inline < `!important`
5. **The box model** — every element is content + padding + border + margin; `box-sizing: border-box` is essential
6. **Typography and colour properties** (`font-family`, `color`, `background-color`) define visual identity
7. **Flexbox** (`display: flex`, `justify-content`, `align-items`, `gap`) is the modern standard for laying out elements
8. **Pseudo-classes** (`:hover`, `:focus`, `:nth-child`) style based on state, without JavaScript
9. **Attribute selectors** (`[data-risk-level="high"]`) connect directly to the `data-*` attributes from Day 1
10. **Media queries** (`@media`) make pages responsive — essential since most patients use mobile devices

---

## ❓ Q&A Discussion

- "Why would a hospital prefer one external CSS file over writing inline styles on every single page?"
- "If a paragraph has both a class selector setting `color: red` and an ID selector setting `color: blue`, which colour wins, and why?"
- "What's the practical difference between `padding` and `margin` — use the blister pack analogy to explain it in your own words."
- "Why does a healthcare portal need a `@media` query at all — what actually breaks without one?"
