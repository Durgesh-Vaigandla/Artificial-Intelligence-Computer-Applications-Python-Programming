****# Unit IV – Day 1 (2 Hours)
## Web Technologies & HTML — Complete Guide for Pharmacy Students

---

## 🎯 Session Goals
By the end of this session, you will be able to:
- Explain how the web works and where HTML fits in
- Understand the complete HTML document structure
- Know every major HTML element by name and purpose — text, lists, tables, media, links, forms, and semantic tags
- Understand global attributes and custom `data-*` attributes
- Apply all of this practically by building real pharmacy-themed web pages

---

## ⏱️ Session Plan (2 Hours)

| Time | Block | Topic |
|------|-------|-------|
| 0:00 – 0:05 | — | Session overview |
| 0:05 – 1:05 | **THEORY** | How the web works → full HTML element reference → attributes |
| 1:05 – 1:55 | **PRACTICAL** | Hands-on building — profile page, drug monograph, form, semantic layout |
| 1:55 – 2:00 | — | Recap + Q&A |

> 💬 **How to use this document:** Part A is the full theory — read and understand every tag before touching the keyboard. Part B is where you actually build pages using everything from Part A. Don't skip ahead to Part B without finishing Part A — in HTML, half-known tags lead to broken pages.

---
---
---

# 🅰️ PART A — THEORY

---

# SECTION 1 — How the Web Works

## 1.1 The Pharmacy Analogy

Think of building a webpage like preparing a drug:

| Pharmacy | Web Development |
|----------|----------------|
| **Active ingredient** (what the drug does) | **HTML** (content and structure) |
| **Excipients / coating** (how it looks) | **CSS** (design and appearance) |
| **Mechanism of action** (how it behaves in the body) | **JavaScript** (behaviour and interactivity) |
| **Manufacturing process** (backend production) | **Python / Java / PHP** (server-side logic) |
| **Storage system** (where raw material is kept) | **Database** (where data is stored) |

> 💬 "Just like a tablet needs an active ingredient, excipients, and a manufacturing process — a website needs HTML, CSS, and a backend. Today we focus on the active ingredient — HTML. CSS gets its own full session next."

---

## 1.2 What Happens When You Open a Website

```
You type: www.apollohospitals.com in your browser
                    ↓
Browser asks DNS server: "What is the IP address of Apollo's server?"
                    ↓
DNS replies: "It lives at 103.25.46.12"
                    ↓
Browser sends HTTP Request to Apollo's server:
"Please send me the homepage"
                    ↓
Apollo's server processes the request, fetches data from database
                    ↓
Server sends back an HTML file
                    ↓
Your browser reads the HTML and RENDERS (displays) the page
                    ↓
You see: Apollo Hospitals homepage
```

### Key Terms

| Term | Meaning | Pharmacy Analogy |
|------|---------|-----------------|
| **Browser** | Software that displays web pages (Chrome, Firefox) | The patient who receives the drug |
| **Server** | Computer that stores and sends web files | The manufacturing plant |
| **HTML file** | The document browser reads and displays | The drug product |
| **HTTP/HTTPS** | Protocol for sending data over the internet | The delivery route (oral, IV, etc.) |
| **URL** | The web address (Uniform Resource Locator) | The drug label / address |
| **DNS** | Directory that converts names to server addresses | The drug index/formulary |

---

## 1.3 The Three Layers of a Website

```
┌─────────────────────────────────────────────────────┐
│                   WHAT USER SEES                    │
├─────────────────────────────────────────────────────┤
│  HTML  →  STRUCTURE   (the skeleton)                │
│           Headings, paragraphs, tables, forms       │
├─────────────────────────────────────────────────────┤
│  CSS   →  STYLE       (the appearance)              │
│           Colours, fonts, spacing, layout           │
├─────────────────────────────────────────────────────┤
│  JS    →  BEHAVIOUR   (the interaction)             │
│           Buttons that do things, live calculations │
└─────────────────────────────────────────────────────┘
```

Today's theory = **HTML only** — the skeleton of every webpage.

---
---

# SECTION 2 — What is HTML and How It's Built

## 2.1 Definition

> **HTML** stands for **HyperText Markup Language**.
> - **HyperText** = text that contains links to other pages
> - **Markup** = using special tags to label and define content
> - **Language** = a structured system of rules

HTML tells the browser: "This piece of text is a heading. This is a paragraph. This is a table. This is a link." The browser then displays each element accordingly.

HTML is **NOT** a programming language — it has no logic, conditions, or loops. It is a **markup language** — it simply describes and labels content.

---

## 2.2 HTML Tags — The Basic Concept

Everything in HTML is written using **tags**.

```
<tagname>  content goes here  </tagname>
   ↑                               ↑
Opening tag                   Closing tag
```

- Opening tag: `<tagname>`
- Closing tag: `</tagname>` — notice the forward slash
- The content sits between the opening and closing tags
- Together: opening tag + content + closing tag = an **HTML element**

### Example
```html
<p>Paracetamol is an analgesic and antipyretic drug.</p>
```

### Void Elements (Self-Closing Tags)

Some elements have no content, so they don't need a closing tag at all. These are called **void elements**:

```html
<br>      <!-- Line break -->
<hr>      <!-- Horizontal line -->
<img>     <!-- Image -->
<input>   <!-- Input field -->
<meta>    <!-- Metadata -->
<link>    <!-- External resource link -->
```

> 💬 You may sometimes see these written as `<br />` with a trailing slash — that's the older XHTML style. In modern HTML5, plain `<br>` is correct and preferred.

---

## 2.3 Attributes — Giving Tags Extra Information

Attributes go inside the opening tag and provide extra detail about an element. This applies to **every tag in HTML**, not just the ones shown below — so understand this concept thoroughly now.

```
<tagname  attribute="value">  content  </tagname>
```

```html
<a href="https://www.who.int">WHO Website</a>
        ↑
   href = attribute   "https://www.who.int" = value

<img src="medicine.jpg" alt="Medicine bottle" width="300">
      ↑                  ↑                     ↑
  source              alt text              width
```

### 2.3.1 Global Attributes (Work on Almost Any Tag)

| Attribute | Purpose | Example |
|-----------|---------|---------|
| `id` | A unique identifier for one specific element on the page | `<div id="patient-card-1">` |
| `class` | A reusable label — many elements can share the same class | `<p class="warning">` |
| `style` | Inline CSS styling directly on the element | `<p style="color:red;">` |
| `title` | Tooltip text shown on hover | `<span title="Generic name">` |
| `lang` | Language of the content | `<p lang="te">` (Telugu) |
| `hidden` | Hides the element from view entirely | `<p hidden>Internal note</p>` |
| `tabindex` | Controls keyboard "Tab" navigation order | `<input tabindex="1">` |
| `contenteditable` | Lets the user edit the content directly in the browser | `<div contenteditable="true">` |

> 💬 **`id` vs `class` — the most common beginner confusion:** `id` must be **unique** — only one element on the entire page can have `id="patient-card-1"`. `class` can be reused on **many** elements — every warning message on the page can share `class="warning"`. Think of `id` like a `PatientID` (unique to one person) and `class` like a `Category` (many patients can share "Diabetic").

### 2.3.2 Custom Data Attributes — `data-*`

HTML allows you to invent your **own** attributes for storing custom information on an element, as long as the attribute name starts with `data-`. These are invisible to the user but readable by CSS and JavaScript — extremely useful in healthcare dashboards for attaching hidden clinical data to visible elements.

```html
<div class="drug-card" 
     data-drug-id="D001" 
     data-requires-prescription="true" 
     data-max-dose="4000">
    Paracetamol 500mg
</div>
```

- `data-drug-id="D001"` — stores the drug's database ID directly on the HTML element
- `data-requires-prescription="true"` — a hidden flag a script could check before allowing "Add to Cart"
- `data-max-dose="4000"` — hidden safety data a script could use to validate a quantity field

> 💬 **Why this matters in pharmacy systems:** Imagine a drug-search results page. Each drug `<div>` on the page can carry hidden `data-*` attributes — drug ID, stock count, prescription requirement — so that when a pharmacist clicks "Dispense," a script instantly knows everything about that drug without needing to ask the server again. You will see this exact pattern in real pharmacy software interfaces.

```html
<!-- A patient row in a results table, carrying hidden data -->
<tr data-patient-id="P004" data-risk-level="high">
    <td>Anitha Reddy</td>
    <td>28</td>
    <td>Diabetic</td>
</tr>
```

---
---

# SECTION 3 — The HTML Document Structure

## 3.1 The Full Skeleton

Every HTML file must follow this structure:

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Drug information for pharmacy students">
    <meta name="author" content="Aavanto Pharmacy College">
    <title>Drug Information Page</title>
</head>

<body>

    <!-- All visible content goes here -->
    <h1>Welcome to the Pharmacy Portal</h1>
    <p>Your complete drug reference guide.</p>

</body>

</html>
```

### Line-by-Line Breakdown

**`<!DOCTYPE html>`**
- Must be the very first line in every HTML file
- Tells the browser: "This is an HTML5 document"
- Without this, the browser may display the page incorrectly
- Think of it like the drug label saying "Tablet — For Oral Use" — it declares what kind of thing this is

**`<html lang="en">`**
- The root element — everything else lives inside this
- `lang="en"` tells the browser the page is in English (important for screen readers used by visually impaired patients)

**`<head>` section**
- Contains information ABOUT the page — not visible on screen
- Like the package insert of a drug — important information, not the drug itself

**`<meta charset="UTF-8">`**
- Tells the browser which character encoding to use
- UTF-8 supports all languages including Telugu, Hindi, and symbols like °C, mg/dL, ®

**`<meta name="viewport">`**
- Makes the page responsive — looks good on mobile phones too
- Essential since most patients access health portals on their phones

**`<title>`**
- The text that appears in the browser tab
- Also what Google shows as the page heading in search results

**`<body>` section**
- Everything visible on the page goes here

**HTML Comments: `<!-- comment text -->`**
- Not visible on the webpage; notes for the developer only

---

## 3.2 Other `<head>` Elements You Should Know

| Tag | Purpose |
|-----|---------|
| `<link>` | Connects an external CSS file: `<link rel="stylesheet" href="style.css">` |
| `<script>` | Connects/embeds JavaScript |
| `<style>` | Embeds CSS directly inside the HTML file |
| `<base>` | Sets a default base URL for all relative links on the page |

We will use `<link>` heavily in the next session when we cover CSS.

---
---

# SECTION 4 — Text Content Elements

## 4.1 Heading Tags — `<h1>` to `<h6>`

HTML has six levels of headings — from the largest (`<h1>`) to the smallest (`<h6>`).

```html
<h1>Drug Information Portal</h1>
<h2>Paracetamol (Acetaminophen)</h2>
<h3>Mechanism of Action</h3>
<h4>Dosage by Age Group</h4>
<h5>Paediatric Dosing</h5>
<h6>Neonatal Dosing — Consult Physician</h6>
```

### When to Use Which Heading

| Tag | Use For | Example |
|-----|---------|---------|
| `<h1>` | Page title — use ONLY ONCE per page | "Apollo Hospital Patient Portal" |
| `<h2>` | Major sections of the page | "Appointments", "Lab Results", "Prescriptions" |
| `<h3>` | Subsections within a section | "Book New Appointment" |
| `<h4>` | Subsections within subsections | "Morning Slots", "Evening Slots" |
| `<h5>`, `<h6>` | Rarely used — very small subheadings | Fine print, footnotes |

> 💬 "Think of headings like a drug monograph structure. The drug name is `<h1>`. Major sections like Indications, Dosage, Side Effects are `<h2>`. Subsections within them are `<h3>`. You never skip levels."

---

## 4.2 Paragraph Tag — `<p>`

```html
<p>Paracetamol is a commonly used analgesic and antipyretic medication.
It is available over-the-counter and is considered safe when taken
at recommended doses.</p>
```

Each `<p>` tag creates a new paragraph with automatic spacing above and below. Extra Enter presses inside the tag are ignored by the browser.

---

## 4.3 Text Formatting Tags

```html
<!-- Bold — for important warnings, drug names -->
<b>WARNING: Do not exceed 4000 mg per day.</b>
<strong>CONTRAINDICATED in severe liver disease.</strong>

<!-- Italic — for drug generic names, Latin terms, emphasis -->
<i>Paracetamol</i> is the INN (International Non-proprietary Name).
<em>Always check for drug interactions before dispensing.</em>

<!-- Underline -->
<u>Refer to Section 4 for paediatric dosing.</u>

<!-- Strikethrough — for discontinued drugs, removed information -->
<s>Old dose: 1000mg every 4 hours</s> (Updated: 500mg every 6 hours)
<del>Rofecoxib (Vioxx)</del> — Withdrawn from market due to cardiac risk

<!-- ins — marks newly inserted/updated text (often paired with del) -->
<p>Dose updated: <del>500mg</del> <ins>650mg</ins> twice daily</p>

<!-- Superscript and Subscript — chemical formulas and references -->
Chemical formula: C<sub>8</sub>H<sub>9</sub>NO<sub>2</sub>
Reference<sup>[1]</sup>

<!-- Highlighted text -->
<mark>High Alert Medication — Double Check Dose</mark>

<!-- Small text — disclaimers, fine print -->
<small>This information is for educational purposes only.</small>

<!-- Abbreviation — shows full meaning on hover -->
<abbr title="Nil By Mouth">NBM</abbr> status confirmed before surgery.
<abbr title="Twice a Day">BD</abbr> dosing schedule.

<!-- Citation — naming a source, book, or reference work -->
Refer to <cite>Indian Pharmacopoeia, 2022</cite> for the full monograph.

<!-- Code — for displaying code, drug codes, or system identifiers -->
Batch code format: <code>PCM-2025-B047</code>

<!-- Keyboard input — represents a key the user should press -->
Press <kbd>Ctrl</kbd> + <kbd>F</kbd> to search the drug database.

<!-- Blockquote — a longer quoted passage, e.g. from a clinical guideline -->
<blockquote>
    "Paracetamol remains the first-line analgesic of choice in patients
    with normal hepatic function, given its favourable safety profile."
</blockquote>

<!-- Address — contact information for a person/organisation -->
<address>
    City Hospital Pharmacy<br>
    MG Road, Tirupati, Andhra Pradesh<br>
    Phone: 0877-XXXXXXX
</address>

<!-- Time — machine-readable dates/times -->
Prescription issued on <time datetime="2025-06-15">15th June 2025</time>.
```

### Quick Reference Table

| Tag | Renders As | Use in Pharmacy |
|-----|-----------|----------------|
| `<b>` | **Bold** | Drug warnings, important dose info |
| `<strong>` | **Bold + semantic importance** | Critical contraindications |
| `<i>` | *Italic* | Drug generic names (INN), Latin terms |
| `<em>` | *Italic + emphasis* | Critical instructions |
| `<u>` | Underlined | References (use sparingly) |
| `<s>` / `<del>` | ~~Strikethrough~~ | Withdrawn drugs, outdated info |
| `<ins>` | <u>Underlined (inserted)</u> | Updated dosage values |
| `<mark>` | Highlighted | High-alert medications |
| `<sup>` / `<sub>` | x² / H₂O | References, chemical notation |
| `<small>` | Smaller text | Disclaimers, fine print |
| `<abbr>` | Dotted underline + tooltip | Medical abbreviations (NBM, BD, STAT) |
| `<cite>` | *Italic* | Naming a guideline, pharmacopoeia, journal |
| `<code>` | Monospace font | Batch codes, drug IDs, system codes |
| `<kbd>` | Boxed monospace | Keyboard shortcuts in a software guide |
| `<blockquote>` | Indented block | Quoted clinical guidelines |
| `<address>` | Italic block | Pharmacy/hospital contact details |
| `<time>` | Normal text + hidden machine-readable date | Prescription dates, expiry dates |

---

## 4.4 Line Break and Horizontal Rule

```html
<p>
    Tablet: 500mg, 650mg<br>
    Syrup: 125mg/5mL, 250mg/5mL<br>
    Suppository: 80mg, 125mg, 325mg
</p>

<h2>Indications</h2>
<p>Fever, mild to moderate pain.</p>
<hr>
<h2>Contraindications</h2>
<p>Severe hepatic impairment.</p>
```

> 💬 "`<br>` is like pressing Enter once in the middle of a paragraph. `<hr>` is like drawing a line between two sections in a prescription."

---

## 4.5 Preformatted Text — `<pre>`

```html
<pre>
    Molecular Weight : 151.163 g/mol
    Melting Point    : 169–170 °C
    Solubility       : 14 mg/mL in water
    pKa              : 9.38
</pre>
```

Displays text exactly as written — preserving spaces and line breaks. Useful for chemical structures, code, or aligned data.

---
---

# SECTION 5 — Lists

## 5.1 Unordered List — `<ul>` and `<li>`

Used when the order does NOT matter — bullet points.

```html
<h3>Indications of Paracetamol</h3>
<ul>
    <li>Mild to moderate pain (headache, toothache, backache)</li>
    <li>Fever (antipyretic)</li>
    <li>Post-operative pain management</li>
</ul>
```

---

## 5.2 Ordered List — `<ol>` and `<li>`

Used when the order MATTERS — numbered steps.

```html
<h3>Prescription Dispensing Procedure</h3>
<ol>
    <li>Receive prescription from patient</li>
    <li>Verify patient identity and prescription authenticity</li>
    <li>Enter prescription into Pharmacy Information System (PIS)</li>
    <li>Check drug-drug interactions and allergy history</li>
    <li>Dispense, label, and counsel the patient</li>
</ol>
```

### Custom Numbering

```html
<!-- Roman numerals -->
<ol type="I">
    <li>Phase I Clinical Trial</li>
    <li>Phase II Clinical Trial</li>
</ol>

<!-- Start from a specific number -->
<ol start="5">
    <li>Step 5: Label the drug</li>
    <li>Step 6: Counsel patient</li>
</ol>
```

---

## 5.3 Nested Lists

```html
<h3>Drug Classification — Analgesics</h3>
<ul>
    <li>Non-Opioid Analgesics
        <ul>
            <li>Paracetamol</li>
            <li>NSAIDs
                <ul>
                    <li>Ibuprofen</li>
                    <li>Diclofenac</li>
                </ul>
            </li>
        </ul>
    </li>
    <li>Opioid Analgesics
        <ul>
            <li>Tramadol</li>
            <li>Morphine</li>
        </ul>
    </li>
</ul>
```

---

## 5.4 Description List — `<dl>`, `<dt>`, `<dd>`

Used for term-definition pairs — perfect for drug monographs and glossaries.

```html
<h3>Pharmacokinetics of Paracetamol</h3>
<dl>
    <dt>Absorption</dt>
    <dd>Rapidly and almost completely absorbed from the GI tract.</dd>

    <dt>Metabolism</dt>
    <dd>Primarily hepatic, via glucuronidation and sulphation.</dd>

    <dt>Excretion</dt>
    <dd>Renal. Half-life: 2–3 hours in healthy adults.</dd>
</dl>
```

---
---

# SECTION 6 — Tables

## 6.1 Why Tables in Healthcare?

In pharmacy practice, tables display: drug dose charts, patient lab results, drug interaction matrices, formulation comparisons, prescription records, and ADR reports.

## 6.2 Basic Table Structure

```html
<table>
    <tr>                        <!-- tr = Table Row -->
        <th>Column 1</th>       <!-- th = Table Header -->
        <th>Column 2</th>
    </tr>
    <tr>
        <td>Data 1</td>         <!-- td = Table Data cell -->
        <td>Data 2</td>
    </tr>
</table>
```

## 6.3 Semantic Table Sections

```html
<table border="1" cellpadding="10">
    <caption>Paracetamol — Dosage by Age Group</caption>
    <thead>
        <tr>
            <th>Age Group</th>
            <th>Dose (mg)</th>
            <th>Frequency</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1–5 years</td>
            <td>120–250 mg</td>
            <td>Every 6 hours</td>
        </tr>
        <tr>
            <td>Adults</td>
            <td>500–1000 mg</td>
            <td>Every 4–6 hours</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="3"><small>⚠️ Reduce dose in hepatic impairment.</small></td>
        </tr>
    </tfoot>
</table>
```

| Tag | Meaning | Pharmacy Analogy |
|-----|---------|-----------------|
| `<caption>` | Table title, shown above the grid | The chart's heading, e.g., "Dose by Age" |
| `<thead>` | Header section | Column headings row |
| `<tbody>` | Body — all data rows | The actual dose data |
| `<tfoot>` | Footer | Footnotes at the bottom |

## 6.4 Spanning Cells — colspan and rowspan

```html
<table border="1" cellpadding="10">
    <tr>
        <th rowspan="2">Date</th>
        <th colspan="2">Blood Glucose (mg/dL)</th>
    </tr>
    <tr>
        <th>Morning</th>
        <th>Evening</th>
    </tr>
    <tr>
        <td>15-Jun-2025</td>
        <td>118</td>
        <td>142</td>
    </tr>
</table>
```

---
---

# SECTION 7 — Images and Media

## 7.1 Images — `<img>`

```html
<img src="paracetamol_tablet.jpg" alt="Paracetamol 500mg tablet" width="300" height="200" title="Paracetamol 500mg">
```

| Attribute | Purpose |
|-----------|---------|
| `src` | Path to the image file (required) |
| `alt` | Alternative text — read aloud by screen readers (required for accessibility) |
| `width` / `height` | Size in pixels |
| `title` | Tooltip text on hover |

> 💬 "`alt` text is critically important. For visually impaired patients using screen readers, the `alt` text is read aloud instead of showing the image. On healthcare websites, accessibility is not optional."

## 7.2 Figure and Caption — `<figure>`, `<figcaption>`

When an image needs a proper, semantically-linked caption (much better practice than a loose `<p>` under an image):

```html
<figure>
    <img src="paracetamol_structure.png" alt="Chemical structure of Paracetamol" width="250">
    <figcaption>Fig 1: Molecular structure of Paracetamol (C₈H₉NO₂)</figcaption>
</figure>
```

## 7.3 Audio — `<audio>`

Useful for accessibility — e.g., audio-recorded dosage instructions for low-literacy patients.

```html
<audio controls>
    <source src="dosage_instructions_telugu.mp3" type="audio/mpeg">
    Your browser does not support the audio element.
</audio>
```

## 7.4 Video — `<video>`

Useful for injection technique demonstrations or patient education videos.

```html
<video width="400" controls>
    <source src="inhaler_technique.mp4" type="video/mp4">
    Your browser does not support the video tag.
</video>
```

## 7.5 Embedding External Content — `<iframe>`

Used to embed another webpage inside your page — for example, embedding a Google Map to a pharmacy's location, or a YouTube health-education video.

```html
<iframe 
    width="400" height="250" 
    src="https://www.youtube.com/embed/example" 
    title="Correct inhaler usage demonstration"
    allowfullscreen>
</iframe>
```

---
---

# SECTION 8 — Hyperlinks

```html
<!-- Link to another webpage -->
<a href="https://www.who.int">WHO — World Health Organisation</a>

<!-- Link opens in a new tab -->
<a href="https://pubmed.ncbi.nlm.nih.gov" target="_blank">Search PubMed</a>

<!-- Link to another page in the same website -->
<a href="drug_interactions.html">View Drug Interaction Checker</a>

<!-- Link to a section on the same page (anchor link) -->
<a href="#contraindications">Jump to Contraindications</a>
...
<h2 id="contraindications">Contraindications</h2>

<!-- Email link -->
<a href="mailto:pharmacy@hospital.com">Email the Pharmacy Team</a>

<!-- Phone link — tappable on mobile -->
<a href="tel:+914023456789">Call Hospital Pharmacy: 040-2345-6789</a>
```

| Attribute | Purpose |
|-----------|---------|
| `href` | The destination URL (required) |
| `target="_blank"` | Opens link in a new browser tab |
| `download` | Forces the file to download rather than open in-browser |

---
---

# SECTION 9 — Forms

## 9.1 Why Forms in Healthcare?

Forms are how patients and pharmacists interact with web-based systems: registration, prescription submission, screening questionnaires, appointment booking, feedback.

## 9.2 Basic Form Structure

```html
<form action="submit_prescription.php" method="POST">
    <!-- All form inputs go here -->
    <input type="submit" value="Submit">
</form>
```

| Attribute | Meaning |
|-----------|---------|
| `action` | Where the form data is sent when submitted |
| `method="GET"` | Data sent in the URL (fine for non-sensitive searches) |
| `method="POST"` | Data sent hidden in the request body — **always use for patient data** |

## 9.3 All Input Types

```html
<!-- Text -->
<input type="text" name="patient_name" placeholder="e.g. Rahul Sharma" maxlength="100" required>

<!-- Number -->
<input type="number" name="age" min="0" max="120" required>
<input type="number" name="weight" min="1" max="300" step="0.1">

<!-- Email -->
<input type="email" name="email" placeholder="patient@email.com">

<!-- Telephone -->
<input type="tel" name="phone" pattern="[0-9]{10}">

<!-- Date -->
<input type="date" name="dob">

<!-- Password -->
<input type="password" name="password" minlength="8">

<!-- Radio (single choice) -->
<input type="radio" name="gender" value="male"> Male
<input type="radio" name="gender" value="female"> Female

<!-- Checkbox (multiple choice) -->
<input type="checkbox" name="allergy" value="penicillin"> Penicillin
<input type="checkbox" name="allergy" value="sulfa"> Sulfa drugs

<!-- Range slider -->
<input type="range" name="pain" min="0" max="10" value="5">

<!-- File upload -->
<input type="file" name="prescription_img" accept=".jpg,.png,.pdf">

<!-- Hidden field -->
<input type="hidden" name="hospital_id" value="APL-HYD-001">

<!-- Colour picker -->
<input type="color" name="highlight_colour">

<!-- Search box -->
<input type="search" name="drug_search" placeholder="Search drugs...">

<!-- Submit and Reset -->
<input type="submit" value="Submit">
<input type="reset" value="Clear">
```

## 9.4 Dropdown — `<select>`, `<option>`, and `<optgroup>`

```html
<select name="frequency">
    <option value="">-- Select Frequency --</option>
    <optgroup label="Standard Dosing">
        <option value="od">Once Daily (OD)</option>
        <option value="bd">Twice Daily (BD)</option>
        <option value="tds">Three Times Daily (TDS)</option>
    </optgroup>
    <optgroup label="As-Needed Dosing">
        <option value="sos">As Needed (SOS/PRN)</option>
        <option value="stat">Immediately (STAT)</option>
    </optgroup>
</select>
```

`<optgroup>` visually groups related options under a bold label inside the dropdown — useful when a list is long, e.g., grouping drugs by category in a search dropdown.

## 9.5 Suggestions While Typing — `<datalist>`

Gives the user autocomplete-style suggestions while still allowing free text entry (unlike `<select>`, which locks them to only the listed options).

```html
<label for="drug_input">Drug Name:</label>
<input type="text" id="drug_input" name="drug_input" list="drug_suggestions">

<datalist id="drug_suggestions">
    <option value="Paracetamol">
    <option value="Amoxicillin">
    <option value="Metformin">
    <option value="Atorvastatin">
</datalist>
```

## 9.6 Multi-line Text — `<textarea>`

```html
<textarea name="symptoms" rows="4" cols="50"
    placeholder="Describe when symptoms started and their severity"></textarea>
```

## 9.7 Grouping Related Fields — `<fieldset>` and `<legend>`

Visually and semantically groups related form fields inside a bordered box with a title — much cleaner than just using headings for sections of a long form.

```html
<fieldset>
    <legend>Medical History</legend>

    <input type="checkbox" name="condition" value="diabetes"> Diabetes<br>
    <input type="checkbox" name="condition" value="hypertension"> Hypertension<br>
    <input type="checkbox" name="condition" value="asthma"> Asthma
</fieldset>
```

## 9.8 Calculated Display Field — `<output>`

Displays the result of a calculation (typically driven by JavaScript) — for example, showing a live BMI result as the user types.

```html
<label for="weight">Weight (kg):</label>
<input type="number" id="weight" name="weight">

<label for="height">Height (m):</label>
<input type="number" id="height" name="height" step="0.01">

<p>Calculated BMI: <output id="bmi_result">--</output></p>
```

(The actual live calculation requires JavaScript, which is outside today's HTML-only scope — but knowing this tag exists matters, since you'll see it in real healthcare calculator widgets.)

## 9.9 Connecting Labels Properly — `<label>`

```html
<label for="patient_name">Patient Full Name:</label>
<input type="text" id="patient_name" name="patient_name">
```

The `for` attribute on `<label>` must exactly match the `id` of its input. This isn't just cosmetic — clicking the label text will then also focus/activate the input, and screen readers will correctly announce the label when the field is focused. **Always pair label and input this way.**

---
---

# SECTION 10 — Semantic HTML Tags

## 10.1 What is Semantic HTML?

> **Semantic HTML** uses tags that describe the **meaning and purpose** of content — not just how it looks.

**Non-semantic tags** — tell the browser nothing about what the content is:
```html
<div>  <span>  <!-- Just generic containers — no meaning -->
```

**Semantic tags** — clearly describe what the content represents:
```html
<header>   <nav>   <main>   <section>   <article>   <aside>   <footer>
```

### Why Semantic Tags Matter in Healthcare

- **Accessibility** — Screen readers understand the page structure
- **Search Engines** — Google ranks healthcare pages higher when structure is clear
- **Maintenance** — Developers immediately understand what each section is
- **Regulations** — Healthcare websites increasingly must meet accessibility standards (WCAG)

## 10.2 Key Semantic Tags — At a Glance

| Tag | Purpose |
|-----|---------|
| `<header>` | Top section — logo, site name, intro |
| `<nav>` | Navigation links |
| `<main>` | The primary content of the page (used once) |
| `<section>` | A thematic group of content |
| `<article>` | Self-contained content (could stand alone, e.g. one drug entry) |
| `<aside>` | Supplementary/sidebar content |
| `<footer>` | Bottom section — copyright, contact, disclaimers |
| `<details>` / `<summary>` | A collapsible, expandable content block |

## 10.3 Collapsible Content — `<details>` and `<summary>`

A genuinely useful semantic pair that's often missed: creates a native, no-JavaScript-needed expand/collapse box — perfect for FAQs or "show more side effects" sections.

```html
<details>
    <summary>⚠️ Click to view full list of side effects</summary>
    <ul>
        <li>Nausea</li>
        <li>Diarrhoea</li>
        <li>Skin rash</li>
        <li>Allergic reaction (rare)</li>
    </ul>
</details>
```

By default, this displays only the `<summary>` line; clicking it reveals the hidden list — entirely built into the browser, no scripting required.

## 10.4 `<div>` and `<span>` — Generic Containers

When no semantic tag fits, use these:

```html
<!-- div = block-level container (full width, starts new line) -->
<div class="drug-card" data-drug-id="D004">
    <h3>Atorvastatin 10mg</h3>
    <p>Category: Statin | Requires Prescription: Yes</p>
</div>

<!-- span = inline container (sits within text, no new line) -->
<p>
    The patient was prescribed 
    <span style="color:red; font-weight:bold;">Warfarin 5mg</span> 
    — a high-alert medication requiring INR monitoring.
</p>
```

---
---
---

# 🅱️ PART B — PRACTICAL

> 💬 Now that every tag has been explained, it's time to actually build. Open VS Code (or Notepad), create a new file, and save it with a `.html` extension **before** typing anything — that way your editor highlights the syntax correctly as you go.

---

## PRACTICAL 1 — Full Document Skeleton

**Goal:** Type out a correct, complete HTML skeleton from memory, without copy-pasting.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Pharmacy Page</title>
</head>
<body>

    <h1>Welcome to the Pharmacy Portal</h1>

</body>
</html>
```

Save as `practice1.html`, then double-click the file to open it in your browser. Confirm the heading and browser tab title both display correctly.

---

## PRACTICAL 2 — Student Profile Page

**Goal:** Combine headings, paragraphs, a table, and a list.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Student Profile</title>
</head>
<body>

    <h1>Student Profile</h1>

    <p><b>Name:</b> Priya Sharma</p>
    <p><b>Roll Number:</b> 2024PHARM042</p>
    <p><b>Course:</b> B.Pharm — 2nd Year</p>

    <h2>Academic Details</h2>
    <table border="1" cellpadding="8">
        <tr><th>Field</th><th>Details</th></tr>
        <tr><td>Specialization</td><td>Pharmaceutical Sciences</td></tr>
        <tr><td>CGPA</td><td>8.4 / 10</td></tr>
    </table>

    <h2>Subjects This Semester</h2>
    <ul>
        <li>Pharmacology II</li>
        <li>Pharmaceutical Chemistry</li>
        <li>AI & Computer Applications in Pharmacy</li>
    </ul>

</body>
</html>
```

**Now extend it yourself:** Add a `<figure>` with a placeholder image and a `<figcaption>`, and one hyperlink to your college's website opening in a new tab.

---

## PRACTICAL 3 — Drug Monograph Page

**Goal:** Use text formatting, description lists, abbreviations, and a `<details>` block together.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Drug Monograph — Paracetamol</title>
</head>
<body>

    <h1>Paracetamol <small>(Acetaminophen)</small></h1>
    <p><i>INN:</i> Paracetamol | <abbr title="International Non-proprietary Name">INN</abbr> Class: Analgesic/Antipyretic</p>

    <h2>Indications</h2>
    <ul>
        <li>Mild to moderate pain</li>
        <li>Fever</li>
    </ul>

    <h2>Pharmacokinetics</h2>
    <dl>
        <dt>Absorption</dt>
        <dd>Rapid, peak plasma concentration in 30–60 minutes.</dd>
        <dt>Half-life</dt>
        <dd>2–3 hours in healthy adults.</dd>
    </dl>

    <h2>Dosage Chart</h2>
    <table border="1" cellpadding="8">
        <thead>
            <tr><th>Age Group</th><th>Dose</th><th>Frequency</th></tr>
        </thead>
        <tbody>
            <tr><td>Adults</td><td>500–1000mg</td><td>Every 4–6 hrs</td></tr>
        </tbody>
    </table>

    <details>
        <summary>⚠️ Click to view full side-effect list</summary>
        <ul>
            <li>Nausea</li>
            <li>Liver damage (in overdose)</li>
            <li>Skin rash (rare)</li>
        </ul>
    </details>

    <p><strong>Maximum Adult Dose: 4000mg/day.</strong></p>

</body>
</html>
```

**Now extend it yourself:** Add a `<blockquote>` citing a clinical guideline, and wrap the chemical formula using `<sub>`.

---

## PRACTICAL 4 — Diabetes Screening Form

**Goal:** Build a complete form using `<fieldset>`, `<datalist>`, radio buttons, checkboxes, and a dropdown with `<optgroup>`.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Diabetes Screening Form</title>
</head>
<body>

<h1>Diabetes Risk Screening</h1>

<form action="#" method="POST">

    <fieldset>
        <legend>Personal Details</legend>

        <label for="name">Full Name:</label><br>
        <input type="text" id="name" name="name" required><br><br>

        <label for="age">Age:</label><br>
        <input type="number" id="age" name="age" min="1" max="120" required>
    </fieldset>

    <br>

    <fieldset>
        <legend>Risk Factors</legend>

        <p>Family history of diabetes?</p>
        <input type="radio" name="family_history" value="yes"> Yes
        <input type="radio" name="family_history" value="no"> No

        <p>Symptoms (check all that apply):</p>
        <input type="checkbox" name="symptom" value="thirst"> Excess thirst<br>
        <input type="checkbox" name="symptom" value="urination"> Frequent urination<br>
        <input type="checkbox" name="symptom" value="fatigue"> Fatigue<br>
        <input type="checkbox" name="symptom" value="vision"> Blurred vision
    </fieldset>

    <br>

    <label for="glucose">Fasting Glucose (mg/dL), if known:</label><br>
    <input type="number" id="glucose" name="glucose" min="40" max="600"><br><br>

    <label for="notes">Additional Notes:</label><br>
    <textarea id="notes" name="notes" rows="4" cols="40"></textarea><br><br>

    <button type="submit">Submit Screening</button>
    <button type="reset">Clear Form</button>

</form>

</body>
</html>
```

**Now extend it yourself:** Add a `<select>` with `<optgroup>` for "BMI Category" grouped under "Underweight/Normal" and "Overweight/Obese," and a `<datalist>` for a free-text "Current Medication" field with 4 common drug suggestions.

---

## PRACTICAL 5 — Full Semantic Hospital Pharmacy Page

**Goal:** Combine everything — `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>` — into one complete, realistic page.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>City Hospital — Drug Information Portal</title>
</head>
<body>

    <header>
        <h1>🏥 City Hospital — Drug Information Portal</h1>
        <p>Your trusted pharmaceutical reference</p>
    </header>

    <nav>
        <a href="#">Home</a> |
        <a href="#">Drug Search</a> |
        <a href="#">Contact Pharmacy</a>
    </nav>

    <main>
        <section>
            <h2>Drug of the Week — Metformin</h2>

            <article data-drug-id="D003">
                <h3>Overview</h3>
                <p>Metformin hydrochloride is the first-line treatment for
                Type 2 Diabetes Mellitus.</p>
            </article>

            <article data-drug-id="D003">
                <h3>⚠️ Safety Alert</h3>
                <p>Withhold in patients with eGFR &lt; 30 mL/min — risk of
                lactic acidosis.</p>
            </article>
        </section>
    </main>

    <aside>
        <h3>Quick Reference</h3>
        <ul>
            <li>Normal Fasting Glucose: 70–100 mg/dL</li>
            <li>Diabetic: ≥126 mg/dL</li>
        </ul>
    </aside>

    <footer>
        <hr>
        <p>© 2025 City Hospital, Hyderabad.</p>
        <p><small>For reference only. Always consult a licensed pharmacist.</small></p>
    </footer>

</body>
</html>
```

**Now extend it yourself:** Add a second `<section>` for "Patient Self-Help Resources" containing an embedded `<video>` or `<iframe>`, and give the `<aside>` a `data-section="quick-reference"` attribute.

---

## 🧠 Complete Session Key Takeaways

1. **HTML = structure** of every web page; it labels and organises content for the browser
2. **Every HTML file** must have `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>` — no exceptions
3. **Global attributes** (`id`, `class`, `style`, `title`) work on virtually any tag; `id` is unique, `class` is reusable
4. **`data-*` attributes** let you attach hidden custom data to elements — used heavily in real pharmacy/hospital dashboards
5. **Headings, text formatting, lists, tables** structure and label content meaningfully
6. **Media tags** (`<img>`, `<figure>`, `<audio>`, `<video>`, `<iframe>`) bring in visuals and external content
7. **Forms** collect patient data — always `method="POST"`; `<fieldset>`/`<legend>` group related fields; `<datalist>` and `<optgroup>` improve usability
8. **`<details>`/`<summary>`** gives you a no-JavaScript collapsible section — genuinely useful for FAQs and side-effect lists
9. **Semantic tags** (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`) make pages accessible and professional
10. Theory comes first because in HTML, a single missing closing tag or misunderstood attribute breaks the whole page — understanding before building avoids hours of frustrated debugging

---

## ❓ Q&A Discussion

- "Why must we use `method="POST"` and not `method="GET"` for a patient registration form?"
- "What is the practical difference between using `id` and using `class` on an HTML element?"
- "Give an example of when you'd use a `data-*` attribute on a drug card in a pharmacy web app."
- "Why does `<details>`/`<summary>` not need any JavaScript to work, while `<output>` typically does?"
