# Unit IV – Day 1 (2 Hours)
## Web Technologies & HTML — Complete Guide for Pharmacy Students

---

## 🎯 Session Goals
By the end of this session, students will be able to:
- Explain how the web works and where HTML fits in
- Understand HTML document structure — DOCTYPE, head, body
- Use all heading, paragraph, text formatting, and list tags
- Build tables for drug and patient data
- Add images and hyperlinks to a webpage
- Create forms to collect patient information
- Use semantic HTML tags for better page organization
- Build a complete pharmacy-themed webpage combining all elements

---

## ⏱️ Session Plan (2 Hours)

| Time | Topic |
|------|-------|
| 0:00 – 0:05 | Session overview |
| 0:05 – 0:15 | How the web works |
| 0:15 – 0:30 | HTML structure + head tags |
| 0:30 – 0:50 | Text — headings, paragraphs, formatting tags |
| 0:50 – 1:05 | Lists — ordered, unordered, nested |
| 1:05 – 1:25 | Tables — full coverage |
| 1:25 – 1:35 | Images and hyperlinks |
| 1:35 – 1:50 | Forms — all input types |
| 1:50 – 1:58 | Semantic tags + full page project |
| 1:58 – 2:00 | Recap + Q&A |

---

---

# SECTION 1 — How the Web Works
## (0:05 – 0:15 | 10 minutes)

---

## 1.1 The Simple Analogy

Think of building a webpage like preparing a drug:

| Pharmacy | Web Development |
|----------|----------------|
| **Active ingredient** (what the drug does) | **HTML** (content and structure) |
| **Excipients / coating** (how it looks) | **CSS** (design and appearance) |
| **Mechanism of action** (how it behaves in the body) | **JavaScript** (behaviour and interactivity) |
| **Manufacturing process** (backend production) | **Python / Java / PHP** (server-side logic) |
| **Storage system** (where raw material is kept) | **Database** (where data is stored) |

> 💬 "Just like a tablet needs an active ingredient, excipients, and a manufacturing process — a website needs HTML, CSS, and a backend. Today we focus on the active ingredient — HTML."

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

Today's session = **HTML only** — the skeleton of every webpage.

---

---

# SECTION 2 — HTML Document Structure
## (0:15 – 0:30 | 15 minutes)

---

## 2.1 What is HTML?

> **HTML** stands for **HyperText Markup Language**.
> - **HyperText** = text that contains links to other pages
> - **Markup** = using special tags to label and define content
> - **Language** = a structured system of rules

HTML tells the browser: "This piece of text is a heading. This is a paragraph. This is a table. This is a link." The browser then displays each element accordingly.

HTML is **NOT** a programming language — it does not have logic, conditions, or loops. It is a **markup language** — it simply describes and labels content.

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
- `<p>` = opening paragraph tag
- The sentence = content
- `</p>` = closing paragraph tag
- The whole thing = a paragraph element

### Self-Closing Tags
Some tags do not have content and do not need a closing tag:
```html
<br>       <!-- Line break -->
<hr>       <!-- Horizontal line -->
<img src="drug.jpg">   <!-- Image -->
<input type="text">    <!-- Input field -->
```

---

## 2.3 HTML Attributes

Attributes give extra information to a tag. They always go inside the opening tag.

```
<tagname  attribute="value">  content  </tagname>
```

Examples:
```html
<a href="https://www.who.int">WHO Website</a>
        ↑
   href = attribute   "https://www.who.int" = value

<img src="medicine.jpg" alt="Medicine bottle" width="300">
      ↑                  ↑                     ↑
  source              alt text              width
```

---

## 2.4 The Full HTML Document Structure

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

### Breakdown — Line by Line

**`<!DOCTYPE html>`**
- Must be the very first line in every HTML file
- Tells the browser: "This is an HTML5 document"
- Without this, the browser may display the page incorrectly
- Think of it like the drug label saying "Tablet — For Oral Use" — it declares what kind of thing this is

**`<html lang="en">`**
- The root element — everything else lives inside this
- `lang="en"` tells the browser the page is in English (important for screen readers for visually impaired users)

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
- All the content your user actually sees and interacts with

**HTML Comments: `<!-- comment text -->`**
- Not visible on the webpage
- Used by the developer as notes
- Like writing notes in pencil on a prescription draft

---

---

# SECTION 3 — Headings and Paragraphs
## (0:30 – 0:50 | 20 minutes)

---

## 3.1 Heading Tags — `<h1>` to `<h6>`

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
| `<h3>` | Subsections within a section | "Book New Appointment", "View Past Appointments" |
| `<h4>` | Subsections within subsections | "Morning Slots", "Evening Slots" |
| `<h5>`, `<h6>` | Rarely used — very small subheadings | Fine print, footnotes |

> 💬 "Think of headings like a drug monograph structure. The drug name is `<h1>`. Major sections like Indications, Dosage, Side Effects are `<h2>`. Subsections within them are `<h3>`. You never skip levels — just like a monograph has a logical hierarchy."

---

## 3.2 Paragraph Tag — `<p>`

```html
<p>Paracetamol is a commonly used analgesic and antipyretic medication.
It is available over-the-counter and is considered safe when taken
at recommended doses.</p>

<p>Overdose of Paracetamol can cause severe liver damage. The maximum
adult dose is 4000 mg per day. Patients with liver disease should
consult a physician before use.</p>
```

- Each `<p>` tag creates a new paragraph with automatic spacing above and below
- Even if you press Enter many times inside the tag, the browser ignores extra whitespace

---

## 3.3 Text Formatting Tags

These tags change how text looks — bold, italic, underline, etc.

```html
<!-- Bold — for important warnings, drug names -->
<b>WARNING: Do not exceed 4000 mg per day.</b>
<strong>CONTRAINDICATED in severe liver disease.</strong>

<!-- Italic — for drug generic names, Latin terms, emphasis -->
<i>Paracetamol</i> is the INN (International Non-proprietary Name).
<em>Always check for drug interactions before dispensing.</em>

<!-- Underline — use sparingly; looks like a link -->
<u>Refer to Section 4 for paediatric dosing.</u>

<!-- Strikethrough — for discontinued drugs, removed information -->
<s>Old dose: 1000mg every 4 hours</s> (Updated: 500mg every 6 hours)
<del>Rofecoxib (Vioxx)</del> — Withdrawn from market due to cardiac risk

<!-- Superscript and Subscript — for chemical formulas and references -->
Chemical formula: C<sub>8</sub>H<sub>9</sub>NO<sub>2</sub>
Reference<sup>[1]</sup>

<!-- Highlighted text -->
<mark>High Alert Medication — Double Check Dose</mark>

<!-- Small text — for fine print, disclaimers -->
<small>This information is for educational purposes only. 
Always consult a licensed pharmacist.</small>
```

### Visual Result:

| Tag | Renders As | Use in Pharmacy |
|-----|-----------|----------------|
| `<b>` | **Bold** | Drug warnings, important dose info |
| `<strong>` | **Bold + semantic importance** | Critical contraindications |
| `<i>` | *Italic* | Drug generic names (INN), Latin terms |
| `<em>` | *Italic + emphasis* | Critical instructions |
| `<u>` | Underlined | References (use sparingly) |
| `<s>` or `<del>` | ~~Strikethrough~~ | Withdrawn drugs, outdated info |
| `<mark>` | Highlighted | High-alert medications |
| `<sup>` | Superscript (x²) | References, chemical notation |
| `<sub>` | Subscript (H₂O) | Chemical formulas |
| `<small>` | Smaller text | Disclaimers, fine print |

---

## 3.4 Line Break and Horizontal Rule

```html
<!-- Line break — moves to next line WITHOUT starting new paragraph -->
<p>
    Tablet: 500mg, 650mg<br>
    Syrup: 125mg/5mL, 250mg/5mL<br>
    Suppository: 80mg, 125mg, 325mg
</p>

<!-- Horizontal rule — draws a dividing line across the page -->
<h2>Indications</h2>
<p>Fever, mild to moderate pain.</p>
<hr>
<h2>Contraindications</h2>
<p>Severe hepatic impairment.</p>
```

> 💬 "`<br>` is like pressing Enter once in the middle of a paragraph. `<hr>` is like drawing a line between two sections in a prescription — separating diagnosis from treatment."

---

## 3.5 Preformatted Text — `<pre>`

Displays text exactly as written — preserving spaces and line breaks. Useful for displaying chemical structures, code, or formatted data.

```html
<pre>
    Molecular Weight : 151.163 g/mol
    Melting Point    : 169–170 °C
    Solubility       : 14 mg/mL in water
    pKa              : 9.38
</pre>
```

---

---

# SECTION 4 — Lists
## (0:50 – 1:05 | 15 minutes)

---

## 4.1 Unordered List — `<ul>` and `<li>`

Used when the order does NOT matter — bullet points.

```html
<h3>Indications of Paracetamol</h3>
<ul>
    <li>Mild to moderate pain (headache, toothache, backache)</li>
    <li>Fever (antipyretic)</li>
    <li>Post-operative pain management</li>
    <li>Arthritis pain relief</li>
    <li>Cold and flu symptoms</li>
</ul>
```

```html
<h3>Adverse Drug Reactions — Amoxicillin</h3>
<ul>
    <li>Diarrhoea</li>
    <li>Nausea and vomiting</li>
    <li>Skin rash</li>
    <li>Allergic reactions (rare — up to anaphylaxis)</li>
    <li>Oral candidiasis (thrush) with prolonged use</li>
</ul>
```

---

## 4.2 Ordered List — `<ol>` and `<li>`

Used when the order MATTERS — numbered steps.

```html
<h3>How to Administer an IM Injection — Step-by-Step</h3>
<ol>
    <li>Wash hands thoroughly with soap and water for 20 seconds</li>
    <li>Gather equipment: syringe, needle, drug vial, swab</li>
    <li>Draw the drug into the syringe — check dose again</li>
    <li>Clean the injection site with an alcohol swab</li>
    <li>Insert needle at 90° angle into the muscle</li>
    <li>Aspirate to confirm needle is not in a blood vessel</li>
    <li>Inject the drug slowly and steadily</li>
    <li>Withdraw needle and apply gentle pressure with swab</li>
    <li>Dispose of needle in sharps container immediately</li>
    <li>Document the administration in patient record</li>
</ol>
```

```html
<h3>Prescription Dispensing Procedure</h3>
<ol>
    <li>Receive prescription from patient</li>
    <li>Verify patient identity and prescription authenticity</li>
    <li>Enter prescription into Pharmacy Information System (PIS)</li>
    <li>Check drug-drug interactions and allergy history</li>
    <li>Pick the correct drug, strength, and quantity from stock</li>
    <li>Generate and affix prescription label</li>
    <li>Perform final check — right patient, right drug, right dose</li>
    <li>Counsel patient on dose, timing, storage, and side effects</li>
    <li>Record dispensing in system</li>
</ol>
```

---

## 4.3 Ordered List — Custom Numbering

```html
<!-- Roman numerals -->
<ol type="I">
    <li>Phase I Clinical Trial</li>
    <li>Phase II Clinical Trial</li>
    <li>Phase III Clinical Trial</li>
    <li>Phase IV Post-Marketing Surveillance</li>
</ol>

<!-- Alphabetical -->
<ol type="A">
    <li>Analgesics</li>
    <li>Antibiotics</li>
    <li>Antidiabetics</li>
    <li>Antihypertensives</li>
</ol>

<!-- Start from a specific number -->
<ol start="5">
    <li>Step 5: Label the drug</li>
    <li>Step 6: Counsel patient</li>
    <li>Step 7: Record dispensing</li>
</ol>
```

---

## 4.4 Nested Lists

Lists inside lists — for hierarchical information like drug classifications.

```html
<h3>Drug Classification — Analgesics</h3>
<ul>
    <li>Non-Opioid Analgesics
        <ul>
            <li>Paracetamol (Acetaminophen)</li>
            <li>NSAIDs
                <ul>
                    <li>Ibuprofen</li>
                    <li>Diclofenac</li>
                    <li>Naproxen</li>
                </ul>
            </li>
        </ul>
    </li>
    <li>Opioid Analgesics
        <ul>
            <li>Weak Opioids
                <ul>
                    <li>Codeine</li>
                    <li>Tramadol</li>
                </ul>
            </li>
            <li>Strong Opioids
                <ul>
                    <li>Morphine</li>
                    <li>Fentanyl</li>
                    <li>Oxycodone</li>
                </ul>
            </li>
        </ul>
    </li>
</ul>
```

---

## 4.5 Description List — `<dl>`, `<dt>`, `<dd>`

Used for term-definition pairs — perfect for drug monographs and glossaries.

```html
<h3>Pharmacokinetics of Paracetamol</h3>
<dl>
    <dt>Absorption</dt>
    <dd>Rapidly and almost completely absorbed from the GI tract.
        Peak plasma concentration reached in 30–60 minutes.</dd>

    <dt>Distribution</dt>
    <dd>Widely distributed throughout body tissues.
        Volume of distribution: 0.9 L/kg. Protein binding: 10–25%.</dd>

    <dt>Metabolism</dt>
    <dd>Primarily hepatic (90%). Metabolized by glucuronidation and 
        sulphation. A small fraction via CYP2E1 to toxic NAPQI metabolite.</dd>

    <dt>Excretion</dt>
    <dd>Renal. 90% excreted in urine as glucuronide and sulphate conjugates.
        Half-life: 2–3 hours in healthy adults.</dd>
</dl>
```

---

---

# SECTION 5 — Tables (Complete Coverage)
## (1:05 – 1:25 | 20 minutes)

---

## 5.1 Why Tables in Healthcare?

In pharmacy practice, tables are everywhere:
- Drug dose charts (dose by age/weight)
- Patient lab results over time
- Drug interaction matrices
- Comparison of drug formulations
- Prescription records
- Adverse drug reaction reports

HTML tables display this data clearly and professionally on a web page.

---

## 5.2 Basic Table Structure

```html
<table>
    <tr>                        <!-- tr = Table Row -->
        <th>Column 1</th>       <!-- th = Table Header (bold, centered) -->
        <th>Column 2</th>
    </tr>
    <tr>
        <td>Data 1</td>         <!-- td = Table Data cell -->
        <td>Data 2</td>
    </tr>
</table>
```

Think of it like building a spreadsheet row by row:
- `<table>` = the entire spreadsheet
- `<tr>` = one row
- `<th>` = a header cell (column heading — like "Drug Name", "Dose")
- `<td>` = a data cell (like "Paracetamol", "500 mg")

---

## 5.3 Drug Dose Chart Table

```html
<!DOCTYPE html>
<html>
<head>
    <title>Paracetamol Dose Chart</title>
    <style>
        table {
            border-collapse: collapse;
            width: 80%;
            margin: 20px auto;
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
            background-color: #f0f8ff;   /* Alternate row shading */
        }
        tr:hover {
            background-color: #ffe0b2;   /* Highlight on hover */
        }
    </style>
</head>
<body>

<h2>Paracetamol — Dosage by Age Group</h2>

<table>
    <thead>
        <tr>
            <th>Age Group</th>
            <th>Weight Range (kg)</th>
            <th>Dose (mg)</th>
            <th>Frequency</th>
            <th>Max Daily Dose</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>0–3 months</td>
            <td>3–5 kg</td>
            <td>40 mg</td>
            <td>Every 8 hours</td>
            <td>120 mg/day</td>
        </tr>
        <tr>
            <td>3–12 months</td>
            <td>5–10 kg</td>
            <td>60–120 mg</td>
            <td>Every 6 hours</td>
            <td>480 mg/day</td>
        </tr>
        <tr>
            <td>1–5 years</td>
            <td>10–18 kg</td>
            <td>120–250 mg</td>
            <td>Every 6 hours</td>
            <td>1000 mg/day</td>
        </tr>
        <tr>
            <td>6–12 years</td>
            <td>18–40 kg</td>
            <td>250–500 mg</td>
            <td>Every 6–8 hours</td>
            <td>2000 mg/day</td>
        </tr>
        <tr>
            <td>Adults & >12 years</td>
            <td>&gt;40 kg</td>
            <td>500–1000 mg</td>
            <td>Every 4–6 hours</td>
            <td>4000 mg/day</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="5">
                <small>⚠️ Reduce dose in hepatic impairment. 
                Avoid in severe liver disease.</small>
            </td>
        </tr>
    </tfoot>
</table>

</body>
</html>
```

### Table Semantic Sections Explained

| Tag | Meaning | Pharmacy Analogy |
|-----|---------|-----------------|
| `<thead>` | Table header section | Column headings row in a dose chart |
| `<tbody>` | Table body — all data rows | The actual dose data |
| `<tfoot>` | Table footer | Footnotes and disclaimers at bottom of chart |

---

## 5.4 Spanning Cells — colspan and rowspan

Sometimes a cell needs to stretch across multiple columns or rows.

```html
<h3>Patient Lab Results — Morning & Evening Readings</h3>

<table border="1" cellpadding="10">
    <thead>
        <tr>
            <th rowspan="2">Date</th>        <!-- spans 2 rows down -->
            <th rowspan="2">Patient</th>
            <th colspan="2">Blood Glucose (mg/dL)</th>   <!-- spans 2 columns -->
            <th colspan="2">Blood Pressure (mmHg)</th>
        </tr>
        <tr>
            <!-- These headers sit under the colspan headings above -->
            <th>Morning</th>
            <th>Evening</th>
            <th>Morning</th>
            <th>Evening</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>15-Jun-2025</td>
            <td>Rahul Sharma</td>
            <td>118</td>
            <td>142</td>
            <td>128/82</td>
            <td>135/88</td>
        </tr>
        <tr>
            <td>16-Jun-2025</td>
            <td>Rahul Sharma</td>
            <td>112</td>
            <td>138</td>
            <td>125/80</td>
            <td>130/85</td>
        </tr>
    </tbody>
</table>
```

---

## 5.5 Drug Interaction Table

```html
<h3>Drug-Drug Interaction Matrix</h3>

<table border="1" cellpadding="10" style="text-align:center;">
    <thead>
        <tr>
            <th>Drug A \ Drug B</th>
            <th>Aspirin</th>
            <th>Warfarin</th>
            <th>Metformin</th>
            <th>Atorvastatin</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th>Aspirin</th>
            <td>—</td>
            <td style="background:#ffcccc;">⚠️ Major</td>
            <td style="background:#ffffcc;">Minor</td>
            <td style="background:#ffffcc;">Minor</td>
        </tr>
        <tr>
            <th>Warfarin</th>
            <td style="background:#ffcccc;">⚠️ Major</td>
            <td>—</td>
            <td style="background:#ccffcc;">None</td>
            <td style="background:#ffeecc;">Moderate</td>
        </tr>
        <tr>
            <th>Metformin</th>
            <td style="background:#ffffcc;">Minor</td>
            <td style="background:#ccffcc;">None</td>
            <td>—</td>
            <td style="background:#ccffcc;">None</td>
        </tr>
        <tr>
            <th>Atorvastatin</th>
            <td style="background:#ffffcc;">Minor</td>
            <td style="background:#ffeecc;">Moderate</td>
            <td style="background:#ccffcc;">None</td>
            <td>—</td>
        </tr>
    </tbody>
</table>
```

> 💬 "This is exactly how drug interaction databases display information. The colour coding — red for major, yellow for minor, green for none — is a visual safety cue. HTML tables with inline colours make this possible."

---

---

# SECTION 6 — Images and Hyperlinks
## (1:25 – 1:35 | 10 minutes)

---

## 6.1 Images — `<img>`

The `<img>` tag displays an image. It is a self-closing tag — no closing `</img>` needed.

```html
<!-- Basic image -->
<img src="paracetamol_tablet.jpg" alt="Paracetamol 500mg tablet">

<!-- Image with size specified -->
<img src="prescription.jpg" alt="Sample prescription" width="400" height="300">

<!-- Image from an internet URL -->
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b1/Paracetamol-from-xtal-3D-bs-17.png/240px-Paracetamol-from-xtal-3D-bs-17.png" 
     alt="Paracetamol molecular structure" 
     width="200">
```

### Important Attributes

| Attribute | Purpose | Example |
|-----------|---------|---------|
| `src` | Path to the image file (required) | `src="drug.jpg"` |
| `alt` | Alternative text if image fails to load (required for accessibility) | `alt="Paracetamol tablet"` |
| `width` | Width in pixels | `width="300"` |
| `height` | Height in pixels | `height="200"` |
| `title` | Tooltip text on hover | `title="Paracetamol 500mg"` |

> 💬 "`alt` text is critically important. For visually impaired patients using screen readers, the `alt` text is read aloud instead of showing the image. In healthcare websites, accessibility is not optional — it is an ethical responsibility."

### Image in a Healthcare Context

```html
<h2>Drug Monograph — Paracetamol</h2>

<img src="paracetamol_structure.png" 
     alt="Chemical structure of Paracetamol (C8H9NO2)" 
     width="250"
     title="Paracetamol — Molecular Weight 151.16 g/mol">

<p>
    <b>Paracetamol</b> (Acetaminophen) — Molecular formula: 
    C<sub>8</sub>H<sub>9</sub>NO<sub>2</sub>
</p>
```

---

## 6.2 Hyperlinks — `<a>`

The `<a>` (anchor) tag creates clickable links.

```html
<!-- Link to another webpage -->
<a href="https://www.who.int">WHO — World Health Organisation</a>

<!-- Link opens in a new tab (important for external sites) -->
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

### Pharmacy-Relevant Links

```html
<h3>Drug Reference Resources</h3>
<ul>
    <li><a href="https://pubmed.ncbi.nlm.nih.gov" target="_blank">PubMed — Biomedical Research Database</a></li>
    <li><a href="https://www.cdsco.gov.in" target="_blank">CDSCO — Central Drugs Standard Control Organisation</a></li>
    <li><a href="https://www.who.int/medicines" target="_blank">WHO Essential Medicines</a></li>
    <li><a href="https://www.mims.com" target="_blank">MIMS Drug Information</a></li>
    <li><a href="https://abdm.gov.in" target="_blank">ABHA — Ayushman Bharat Health Account</a></li>
</ul>
```

---

---

# SECTION 7 — Forms (All Input Types)
## (1:35 – 1:50 | 15 minutes)

---

## 7.1 Why Forms in Healthcare?

Forms are how patients and pharmacists interact with web-based systems:
- Patient registration forms
- Online prescription submissions
- Symptom questionnaires and health screening
- Appointment booking
- Drug adverse reaction reporting
- Feedback and rating systems

---

## 7.2 Basic Form Structure

```html
<form action="submit_prescription.php" method="POST">
    <!-- All form inputs go here -->
    <input type="submit" value="Submit">
</form>
```

| Attribute | Meaning |
|-----------|---------|
| `action` | Where the form data is sent when submitted (a server URL) |
| `method="GET"` | Data sent in the URL (for searches) |
| `method="POST"` | Data sent hidden in the request body (for sensitive data like patient info — always use POST for healthcare forms) |

---

## 7.3 All Input Types — with Pharmacy Examples

### Text Input
```html
<label for="patient_name">Patient Full Name:</label>
<input type="text" 
       id="patient_name" 
       name="patient_name" 
       placeholder="e.g. Rahul Sharma"
       maxlength="100"
       required>
```

### Number Input
```html
<label for="age">Age:</label>
<input type="number" id="age" name="age" min="0" max="120" required>

<label for="weight">Weight (kg):</label>
<input type="number" id="weight" name="weight" min="1" max="300" step="0.1">

<label for="glucose">Fasting Glucose (mg/dL):</label>
<input type="number" id="glucose" name="glucose" min="40" max="600">
```

### Email Input
```html
<label for="email">Email Address:</label>
<input type="email" id="email" name="email" 
       placeholder="patient@email.com">
```

### Phone Input
```html
<label for="phone">Mobile Number:</label>
<input type="tel" id="phone" name="phone" 
       placeholder="10-digit mobile number"
       pattern="[0-9]{10}">
```

### Date Input
```html
<label for="dob">Date of Birth:</label>
<input type="date" id="dob" name="dob">

<label for="prescription_date">Prescription Date:</label>
<input type="date" id="prescription_date" name="prescription_date">
```

### Password Input
```html
<label for="password">Create Password (for patient portal):</label>
<input type="password" id="password" name="password" minlength="8">
```

### Radio Buttons — Single Choice
```html
<p><b>Gender:</b></p>
<input type="radio" id="male" name="gender" value="male">
<label for="male">Male</label>

<input type="radio" id="female" name="gender" value="female">
<label for="female">Female</label>

<input type="radio" id="other" name="gender" value="other">
<label for="other">Other / Prefer not to say</label>
```

```html
<p><b>Blood Group:</b></p>
<input type="radio" name="blood_group" value="A+"> <label>A+</label>
<input type="radio" name="blood_group" value="A-"> <label>A−</label>
<input type="radio" name="blood_group" value="B+"> <label>B+</label>
<input type="radio" name="blood_group" value="B-"> <label>B−</label>
<input type="radio" name="blood_group" value="O+"> <label>O+</label>
<input type="radio" name="blood_group" value="O-"> <label>O−</label>
<input type="radio" name="blood_group" value="AB+"> <label>AB+</label>
<input type="radio" name="blood_group" value="AB-"> <label>AB−</label>
```

### Checkboxes — Multiple Choice
```html
<p><b>Known Allergies (check all that apply):</b></p>
<input type="checkbox" name="allergy" value="penicillin">
<label>Penicillin / Amoxicillin</label><br>

<input type="checkbox" name="allergy" value="sulfa">
<label>Sulfa drugs</label><br>

<input type="checkbox" name="allergy" value="nsaid">
<label>NSAIDs (Ibuprofen, Aspirin)</label><br>

<input type="checkbox" name="allergy" value="latex">
<label>Latex</label><br>

<input type="checkbox" name="allergy" value="contrast">
<label>Contrast dye</label><br>

<input type="checkbox" name="allergy" value="none" checked>
<label>No known allergies</label>
```

```html
<p><b>Existing Medical Conditions:</b></p>
<input type="checkbox" name="condition" value="diabetes"> <label>Diabetes</label><br>
<input type="checkbox" name="condition" value="hypertension"> <label>Hypertension</label><br>
<input type="checkbox" name="condition" value="cardiac"> <label>Cardiac Disease</label><br>
<input type="checkbox" name="condition" value="renal"> <label>Kidney Disease</label><br>
<input type="checkbox" name="condition" value="hepatic"> <label>Liver Disease</label><br>
<input type="checkbox" name="condition" value="pregnancy"> <label>Pregnant / Planning pregnancy</label><br>
<input type="checkbox" name="condition" value="asthma"> <label>Asthma / COPD</label>
```

### Dropdown — Select
```html
<label for="state">State:</label>
<select id="state" name="state">
    <option value="">-- Select State --</option>
    <option value="AP">Andhra Pradesh</option>
    <option value="TG">Telangana</option>
    <option value="KA">Karnataka</option>
    <option value="TN">Tamil Nadu</option>
    <option value="MH">Maharashtra</option>
</select>
```

```html
<label for="frequency">Dosing Frequency:</label>
<select id="frequency" name="frequency">
    <option value="od">Once Daily (OD)</option>
    <option value="bd">Twice Daily (BD)</option>
    <option value="tds">Three Times Daily (TDS)</option>
    <option value="qid">Four Times Daily (QID)</option>
    <option value="sos">As Needed (SOS/PRN)</option>
    <option value="stat">Immediately (STAT)</option>
</select>
```

### Textarea — Multi-line Text
```html
<label for="current_meds">Current Medications (one per line):</label><br>
<textarea id="current_meds" name="current_meds" 
          rows="5" cols="50"
          placeholder="Example:
Metformin 500mg — Twice daily
Amlodipine 5mg — Once daily
Atorvastatin 10mg — At bedtime"></textarea>

<label for="symptoms">Describe your symptoms:</label><br>
<textarea id="symptoms" name="symptoms" rows="4" cols="50"
          placeholder="Please describe when symptoms started, how severe they are, and anything that makes them better or worse.">
</textarea>
```

### Range Slider — For Pain Scales
```html
<label for="pain">Pain Level (0 = No Pain, 10 = Worst Pain):</label>
<input type="range" id="pain" name="pain" min="0" max="10" value="5">
<span>Current: 5/10</span>
```

### File Upload
```html
<label for="prescription_img">Upload Prescription Image:</label>
<input type="file" id="prescription_img" name="prescription_img"
       accept=".jpg,.png,.pdf">
```

### Hidden Input
```html
<!-- Not visible to user — used to pass background data -->
<input type="hidden" name="form_version" value="2.1">
<input type="hidden" name="hospital_id" value="APL-HYD-001">
```

### Submit and Reset Buttons
```html
<input type="submit" value="Submit Patient Registration">
<input type="reset" value="Clear All Fields">

<!-- Or styled as buttons -->
<button type="submit">Submit Registration</button>
<button type="reset">Clear Form</button>
```

---

## 7.4 Complete Patient Registration Form

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Patient Registration — Hospital Pharmacy</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 30px; background: #f5f9ff; }
        h1 { color: #003366; }
        h3 { color: #005599; border-bottom: 1px solid #ccc; padding-bottom: 5px; }
        label { display: block; margin-top: 12px; font-weight: bold; color: #333; }
        input[type="text"], input[type="number"], input[type="email"],
        input[type="tel"], input[type="date"], select, textarea {
            width: 420px; padding: 8px; margin-top: 4px;
            border: 1px solid #aaa; border-radius: 4px; font-size: 14px;
        }
        .checkbox-group label { font-weight: normal; display: inline; margin-left: 5px; }
        .checkbox-group div { margin: 5px 0; }
        button[type="submit"] {
            margin-top: 20px; padding: 12px 40px;
            background-color: #003366; color: white;
            border: none; border-radius: 4px;
            font-size: 16px; cursor: pointer;
        }
        button[type="reset"] {
            margin-top: 20px; margin-left: 10px; padding: 12px 30px;
            background-color: #888; color: white;
            border: none; border-radius: 4px; cursor: pointer;
        }
    </style>
</head>
<body>

<h1>🏥 Hospital Pharmacy — Patient Registration</h1>
<p>Please fill all fields accurately. This information helps us ensure safe medication dispensing.</p>

<form action="#" method="POST">

    <!-- Section 1: Personal Details -->
    <h3>Section 1: Personal Details</h3>

    <label for="full_name">Full Name: *</label>
    <input type="text" id="full_name" name="full_name"
           placeholder="As per government ID" required>

    <label for="dob">Date of Birth: *</label>
    <input type="date" id="dob" name="dob" required>

    <label>Gender: *</label>
    <input type="radio" name="gender" value="male" required>
    <label style="display:inline; font-weight:normal;">Male</label> &nbsp;
    <input type="radio" name="gender" value="female">
    <label style="display:inline; font-weight:normal;">Female</label> &nbsp;
    <input type="radio" name="gender" value="other">
    <label style="display:inline; font-weight:normal;">Other</label>

    <label for="blood_group">Blood Group:</label>
    <select id="blood_group" name="blood_group">
        <option value="">-- Select --</option>
        <option>A+</option><option>A−</option>
        <option>B+</option><option>B−</option>
        <option>O+</option><option>O−</option>
        <option>AB+</option><option>AB−</option>
        <option>Unknown</option>
    </select>

    <label for="phone">Mobile Number: *</label>
    <input type="tel" id="phone" name="phone"
           placeholder="10-digit number" pattern="[0-9]{10}" required>

    <label for="email">Email Address:</label>
    <input type="email" id="email" name="email"
           placeholder="For lab reports and prescriptions">

    <!-- Section 2: Physical Parameters -->
    <h3>Section 2: Physical Parameters</h3>

    <label for="weight">Weight (kg):</label>
    <input type="number" id="weight" name="weight" min="1" max="300" step="0.1">

    <label for="height">Height (cm):</label>
    <input type="number" id="height" name="height" min="30" max="250">

    <!-- Section 3: Medical History -->
    <h3>Section 3: Medical History</h3>

    <label>Existing Medical Conditions:</label>
    <div class="checkbox-group">
        <div><input type="checkbox" name="condition" value="diabetes">
             <label>Type 2 Diabetes Mellitus</label></div>
        <div><input type="checkbox" name="condition" value="hypertension">
             <label>Hypertension (High BP)</label></div>
        <div><input type="checkbox" name="condition" value="cardiac">
             <label>Cardiac Disease (IHD, Heart Failure)</label></div>
        <div><input type="checkbox" name="condition" value="renal">
             <label>Chronic Kidney Disease (CKD)</label></div>
        <div><input type="checkbox" name="condition" value="hepatic">
             <label>Liver Disease (Hepatitis, Cirrhosis)</label></div>
        <div><input type="checkbox" name="condition" value="asthma">
             <label>Asthma / COPD</label></div>
        <div><input type="checkbox" name="condition" value="thyroid">
             <label>Thyroid Disorder</label></div>
    </div>

    <label>Known Drug Allergies:</label>
    <div class="checkbox-group">
        <div><input type="checkbox" name="allergy" value="penicillin">
             <label>Penicillin / Amoxicillin (Antibiotics)</label></div>
        <div><input type="checkbox" name="allergy" value="sulfa">
             <label>Sulfa Drugs (Cotrimoxazole)</label></div>
        <div><input type="checkbox" name="allergy" value="nsaid">
             <label>NSAIDs (Ibuprofen, Aspirin, Diclofenac)</label></div>
        <div><input type="checkbox" name="allergy" value="none" checked>
             <label>No Known Drug Allergies</label></div>
    </div>

    <label for="current_meds">Current Medications:</label>
    <textarea id="current_meds" name="current_meds" rows="4"
              placeholder="List all drugs you are currently taking, including OTC drugs and supplements"></textarea>

    <!-- Section 4: Submission -->
    <h3>Section 4: Declaration</h3>
    <input type="checkbox" name="declaration" required>
    <label style="display:inline; font-weight:normal;">
        I confirm that the information provided is accurate and complete.
    </label>

    <br>
    <button type="submit">✅ Register Patient</button>
    <button type="reset">🔄 Clear All Fields</button>

</form>

</body>
</html>
```

---

---

# SECTION 8 — Semantic HTML Tags
## (1:50 – 1:58 | 8 minutes)

---

## 8.1 What is Semantic HTML?

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

- **Accessibility** — Screen readers for visually impaired patients understand the page structure
- **Search Engines** — Google ranks healthcare information pages higher when structure is clear
- **Maintenance** — Developers reading the code know immediately what each section is
- **Regulations** — Healthcare websites increasingly must meet accessibility standards (WCAG)

---

## 8.2 Key Semantic Tags

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>City Hospital — Drug Information Portal</title>
</head>
<body>

    <!-- HEADER — site logo, hospital name, top navigation -->
    <header>
        <h1>🏥 City Hospital — Drug Information Portal</h1>
        <p>Your trusted pharmaceutical reference</p>
    </header>

    <!-- NAV — main navigation links -->
    <nav>
        <a href="index.html">Home</a> |
        <a href="drug_search.html">Drug Search</a> |
        <a href="interactions.html">Interaction Checker</a> |
        <a href="patient_register.html">Patient Registration</a> |
        <a href="contact.html">Contact Pharmacy</a>
    </nav>

    <!-- MAIN — the primary content of the page -->
    <main>

        <!-- SECTION — a thematic group of content -->
        <section>
            <h2>Drug of the Week — Metformin</h2>

            <!-- ARTICLE — self-contained content (could be shared independently) -->
            <article>
                <h3>Overview</h3>
                <p>Metformin hydrochloride is the first-line pharmacological 
                treatment for Type 2 Diabetes Mellitus. It belongs to the 
                biguanide class of antidiabetics.</p>
            </article>

            <article>
                <h3>Dosage and Administration</h3>
                <p>Initial dose: 500mg twice daily with meals.
                Titrate gradually. Maximum dose: 2000–2500mg/day.</p>
            </article>
        </section>

        <section>
            <h2>Drug Safety Alerts</h2>
            <article>
                <h3>⚠️ Metformin — Lactic Acidosis Risk</h3>
                <p>Withhold Metformin in patients with eGFR &lt; 30 mL/min.
                Risk of lactic acidosis in renal impairment.</p>
            </article>
        </section>

    </main>

    <!-- ASIDE — supplementary content, sidebar information -->
    <aside>
        <h3>Quick Reference</h3>
        <ul>
            <li>Normal Fasting Glucose: 70–100 mg/dL</li>
            <li>Pre-diabetic: 100–125 mg/dL</li>
            <li>Diabetic: ≥126 mg/dL</li>
        </ul>

        <h3>Emergency Contacts</h3>
        <p>Pharmacy Helpline: <a href="tel:040-2345-6789">040-2345-6789</a></p>
        <p>Poison Control: <a href="tel:1800-116-117">1800-116-117</a></p>
    </aside>

    <!-- FOOTER — bottom of page: copyright, links, contact -->
    <footer>
        <hr>
        <p>© 2025 City Hospital, Hyderabad. All rights reserved.</p>
        <p>
            <a href="privacy.html">Privacy Policy</a> |
            <a href="disclaimer.html">Medical Disclaimer</a> |
            <a href="contact.html">Contact Us</a>
        </p>
        <p><small>Information on this portal is for reference only. 
        Always consult a licensed pharmacist or physician.</small></p>
    </footer>

</body>
</html>
```

---

## 8.3 `<div>` and `<span>` — Generic Containers

When no semantic tag fits, use these:

```html
<!-- div = block-level container (takes full width, starts new line) -->
<div class="drug-card">
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

## 🧠 Complete Session Key Takeaways

1. **HTML = structure** of every web page — it labels and organises all content
2. **Every HTML file** must have `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>` — no exceptions
3. **Headings `<h1>`–`<h6>`** create hierarchy — like a drug monograph structure; use `<h1>` only once
4. **Text formatting** — `<b>`, `<strong>` for warnings; `<i>` for generic names; `<mark>` for high-alert drugs
5. **Lists**: `<ul>` for drug side effects (order doesn't matter); `<ol>` for procedures (order matters); `<dl>` for pharmacokinetics definitions
6. **Tables** — `<thead>`, `<tbody>`, `<tfoot>` for clean structure; `colspan` and `rowspan` for complex data like lab result charts
7. **Images** — always include `alt` text; critical for patient accessibility on healthcare sites
8. **Hyperlinks** — `target="_blank"` for external drug databases; `href="tel:"` for clickable phone numbers
9. **Forms** — use `POST` method for all patient data; radio for single choice (blood group); checkboxes for multiple (allergies, conditions)
10. **Semantic tags** — `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>` make healthcare portals accessible and professional

---

## 💻 Practice Exercises

**Exercise 1 — Student Profile Page:**
Create a complete HTML page for yourself as a pharmacy student. Include: your name as `<h1>`, a profile summary paragraph, a table with your course details (name, year, college, roll number), an ordered list of your current subjects, and links to 3 pharmacy reference websites.

**Exercise 2 — Drug Monograph Page:**
Choose any one drug (Metformin, Amoxicillin, or Atorvastatin). Build an HTML page with: drug name as heading, sections using `<h2>` for Indications / Dosage / Side Effects / Contraindications / Storage. Use `<ul>` for side effects, `<ol>` for dosing steps, `<dl>` for pharmacokinetics, and a dose-by-age `<table>`. Add bold for warnings and italic for the generic name.

**Exercise 3 — Diabetes Screening Form:**
Create a patient screening form for Type 2 Diabetes risk assessment with: text fields (name, age), radio buttons (family history: Yes/No), checkboxes (symptoms: excess thirst, frequent urination, fatigue, blurred vision, slow wound healing), a dropdown for BMI category, a number input for fasting glucose, a textarea for additional notes, and submit/reset buttons.

**Exercise 4 — Hospital Pharmacy Portal:**
Build a complete page using semantic tags (`<header>`, `<nav>`, `<main>`, `<section>`, `<aside>`, `<footer>`) for a fictional hospital pharmacy. The `<aside>` should show normal lab value ranges. The `<main>` should show two drug articles. The `<footer>` should have a medical disclaimer and poison control number.

---

## ❓ Q&A Discussion

- "Why must we use `method="POST"` and not `method="GET"` for a patient registration form?"
- "What is the difference between `<b>` and `<strong>` — they both make text bold, so why do two tags exist?"
- "If a visually impaired patient is using a screen reader on a hospital website, which HTML feature helps them the most — and what happens if developers skip it?"
