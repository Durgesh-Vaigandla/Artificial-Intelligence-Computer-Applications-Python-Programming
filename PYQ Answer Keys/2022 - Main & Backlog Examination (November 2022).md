# B.Pharmacy II Semester (PCI) — Computer Applications in Pharmacy
# 2022 — Main & Backlog Examination (November 2022)
## Answer Key

---

> **Instructions reflected in this key:** PART–A — **10 Marks each** (Q2 and Q3 are split into two 5-mark sub-parts). PART–B — **5 Marks each**.

---

# PART – A  (10 Marks Each)

---

## Q1. Define number system. Explain the conversion process from binary to octal and binary to hexadecimal. [10 Marks]

### 1. Definition (2 Marks)
A **number system** is a systematic method of representing numbers using a defined set of symbols (digits) and positional rules. Computers operate internally using **Binary** (base-2); **Octal** (base-8) and **Hexadecimal** (base-16) are used as compact, human-friendly groupings of binary digits.

### 2. Binary to Octal Conversion (4 Marks)

**Method:** Group the binary digits into sets of **3**, starting from the right. Convert each group to its octal digit using the reference table below.

**Reference Table:**

| Binary (3-bit) | Octal |
|----------------|-------|
| 000 | 0 |
| 001 | 1 |
| 010 | 2 |
| 011 | 3 |
| 100 | 4 |
| 101 | 5 |
| 110 | 6 |
| 111 | 7 |

**Worked Example 1:** Convert `101110` (binary) to octal.
```
101110 → grouped in 3s: 101 | 110
101 = 5
110 = 6
∴ 101110 (binary) = 56 (octal)
```

**Worked Example 2:** Convert `011111010` (binary) to octal.
```
011111010 → grouped in 3s: 011 | 111 | 010
011 = 3
111 = 7
010 = 2
∴ 011111010 (binary) = 372 (octal)
```

### 3. Binary to Hexadecimal Conversion (4 Marks)

**Method:** Group the binary digits into sets of **4**, starting from the right. Convert each group to its hex digit.

**Reference Table:**

| Binary (4-bit) | Hex |
|----------------|-----|
| 0000–0111 | 0–7 |
| 1000 | 8 |
| 1001 | 9 |
| 1010 | A |
| 1011 | B |
| 1100 | C |
| 1101 | D |
| 1110 | E |
| 1111 | F |

**Worked Example 1:** Convert `11110010` (binary) to hexadecimal.
```
11110010 → grouped in 4s: 1111 | 0010
1111 = F
0010 = 2
∴ 11110010 (binary) = F2 (hexadecimal)
```

**Worked Example 2:** Convert `101111001010` (binary) to hexadecimal.
```
101111001010 → grouped in 4s: 1011 | 1100 | 1010
1011 = B
1100 = C
1010 = A
∴ 101111001010 (binary) = BCA (hexadecimal)
```

### 4. Conclusion (Implicit — included in worked examples above)
These groupings work because 8 = 2³ and 16 = 2⁴, allowing exact, lossless conversion between binary and its octal/hex shorthand without arithmetic calculation — only direct digit-group lookup.

---

## Q2. *(i) Write a note on LIMS (Laboratory Information Management Systems). (ii) How Barcode Labels will work?* [10 Marks Total — 5 Marks Each]

### (i) LIMS (Laboratory Information Management Systems) [5 Marks]

**Definition:** A **LIMS** is software that manages, tracks, and automates laboratory workflow — from sample registration to final result reporting — ensuring accuracy, traceability, and regulatory compliance.

**Core Functions:**

| Function | Description |
|----------|-------------|
| Sample Tracking | Unique barcode/ID assigned to every sample |
| Workflow Management | Routes samples to correct test department |
| Data Capture | Receives results directly from analysers |
| Quality Control | Tracks instrument calibration/QC checks |
| Reporting | Auto-generates formatted result reports |

**Workflow:**
```
Sample registered with barcode → routed to department
        → analyser generates result → validated → report sent to EHR
```

**Advantages:** Eliminates transcription errors, prevents sample mix-ups, provides audit trail for inspections.

---

### (ii) How Barcode Labels Work [5 Marks]

**Definition:** A **barcode** is a machine-readable representation of data, typically encoding a series of numbers/letters as a pattern of parallel lines (1D) or a grid pattern (2D, e.g., QR code), scanned optically to instantly retrieve associated information.

**How It Works — Step by Step:**

```
1. Drug/Sample/Patient assigned a unique barcode at registration
2. Barcode printed onto a label and attached to the item
3. At point of use (dispensing, sample testing), staff scan the barcode
4. Scanner reads the pattern, converts it into the encoded number/ID
5. System looks up that ID in the database
6. Full record (drug name, batch, patient details) instantly displayed
```

**Applications in Pharmacy:**
1. Verifying correct drug is dispensed (matches prescription)
2. Tracking drug batches for recall management
3. Confirming patient identity before administering medication (patient wristband barcode)
4. Tracking lab samples through testing workflow (LIMS)

**Advantages:** Drastically reduces manual entry errors, speeds up verification, provides traceability.

---

## Q3. *(i) What is bioinformatics? Explain its applications. (ii) Explain any 5 HTML tags with examples.* [10 Marks Total — 5 Marks Each]

### (i) Bioinformatics and Its Applications [5 Marks]

**Definition:** **Bioinformatics** is an interdisciplinary field combining biology, computer science, and statistics to collect, store, analyze, and interpret biological data such as genomic and protein sequences.

**Applications:**

| Application | Description |
|-------------|--------------|
| **Drug Target Identification** | Analyzing genomic data to find disease-related proteins |
| **Protein Structure Prediction** | Tools like AlphaFold predict 3D protein shapes |
| **Sequence Alignment** | Comparing DNA/protein sequences to find similarities |
| **Personalized Medicine** | Using genetic data to tailor drug therapy to the individual |
| **Drug Repurposing** | Identifying existing drugs effective against new disease targets |

**Importance:** Bioinformatics accelerates and reduces the cost of pharmaceutical research, allowing computational screening before expensive lab testing.

---

### (ii) Any 5 HTML Tags with Examples [5 Marks]

| # | Tag | Description | Example |
|---|-----|--------------|---------|
| 1 | `<h1>` | Defines the main heading of a page | `<h1>Drug Information</h1>` |
| 2 | `<p>` | Defines a paragraph | `<p>Paracetamol relieves fever.</p>` |
| 3 | `<table>` | Creates a table (with `<tr>`, `<td>`) | `<table><tr><td>Data</td></tr></table>` |
| 4 | `<a>` | Creates a hyperlink | `<a href="who.int">WHO</a>` |
| 5 | `<form>` | Creates an interactive input form | `<form><input type="text"></form>` |

**Combined Example:**
```html
<h1>Paracetamol</h1>
<p>An analgesic and antipyretic drug.</p>
<a href="https://who.int">More info</a>
```

---
---

# PART – B  (5 Marks Each)

---

## Q4. Explain the concept of One's complement and Two's complements. [5 Marks]

**Definition:** **One's and Two's complement** are methods used by computers to represent negative binary numbers, enabling subtraction to be performed using addition circuitry.

**One's Complement:** Obtained by inverting every bit (changing 0→1 and 1→0) of the binary number.

**Worked Example:** Find the One's Complement of `1010`.
```
Original:        1010
Invert each bit:  0101
∴ One's Complement of 1010 = 0101
```

**Two's Complement:** Obtained by taking the One's Complement, then adding 1 to the result.

**Worked Example:** Find the Two's Complement of `1010`.
```
Original:           1010
One's Complement:    0101
Add 1:             + 0001
                   ------
Two's Complement:    0110
```

**Importance:** Two's Complement is the standard method computers use internally to represent negative numbers and perform subtraction via addition, simplifying processor circuit design.

---

## Q5. Write different types of Cascading Style Sheets with examples. [5 Marks]

**Definition:** **CSS (Cascading Style Sheets)** is used to control the visual presentation of HTML elements. There are three types based on where the CSS is written.

| Type | Description | Example |
|------|--------------|---------|
| **Inline CSS** | Written directly inside an HTML tag's `style` attribute | `<p style="color:red;">Warning</p>` |
| **Internal CSS** | Written inside a `<style>` tag in the document's `<head>` | `<style>p{color:navy;}</style>` |
| **External CSS** | Written in a separate `.css` file, linked via `<link>` | `<link rel="stylesheet" href="style.css">` |

**Recommendation:** External CSS is the professional standard — one file can style many pages, making maintenance far easier than repeating inline styles everywhere.

---

## Q6. Explain about application of computers in information storage and retrieval. [5 Marks]

**Definition:** Computers enable systematic electronic storage of large volumes of data and rapid, accurate retrieval when needed.

**Applications:**
1. **Patient Records (EHR):** Stores complete medical history, instantly retrievable
2. **Drug Databases:** Store and retrieve comprehensive drug monographs
3. **TIMS:** Manages and retrieves unstructured text (research literature, clinical notes)
4. **LIMS:** Stores and retrieves laboratory sample/test data

**Importance:** Reduces time to access critical information, supporting faster, safer clinical decisions.

---

## Q7. Explain the application of computers in Pharmacy. [5 Marks]

**Applications:**

| Domain | Application |
|--------|-------------|
| Clinical | Drug interaction checking, e-prescribing |
| Dispensing | Automated cabinets, barcode verification |
| Inventory | Stock tracking, expiry alerts |
| Records | EHR maintenance |
| Research | Bioinformatics-based drug discovery |
| Quality Control | CDS for drug purity testing |

**Conclusion:** Computers improve accuracy, safety, and efficiency throughout the medication-use process.

---

## Q8. Write about Objective of Bioinformatics. [5 Marks]

**Objectives:**
1. Organize biological data into accessible databases
2. Develop tools/algorithms for analyzing biological data
3. Interpret data to extract biological insights
4. Support drug discovery through target identification
5. Enable personalized medicine via genomic analysis

**Conclusion:** These objectives collectively accelerate pharmaceutical research and improve precision in treatment design.

---

## Q9. Write note on CDS (Chromatographic data systems). [5 Marks]

**Definition:** A **CDS** is software used to collect, process, and store data from chromatographic instruments (HPLC, GC) for pharmaceutical quality testing.

**Workflow:**
```
Sample injected → instrument separates components → CDS captures chromatogram
        → identifies peaks/retention time/area → generates validated report
```

**Key Functions:** Peak integration, calibration, audit trail (GxP compliance).

**Importance:** Verifies drug purity, ensuring batch-to-batch consistency before release to patients.

---

## Q10. Explain the process of planning and managing the project. [5 Marks]

**Steps:**

| Step | Description |
|------|--------------|
| 1. Initiation | Define objective and scope |
| 2. Planning | Identify tasks, timeline, resources |
| 3. Execution | Carry out planned tasks |
| 4. Monitoring | Track progress, manage risks |
| 5. Closure | Final review and documentation |

**Importance:** Ensures projects (e.g., implementing new pharmacy software) finish on time, within budget.

---

## Q11. Explain the process of Medication monitoring. [5 Marks]

**Definition:** **Medication monitoring** is the ongoing process of tracking a patient's response to prescribed drugs, ensuring efficacy and detecting adverse effects.

**Process:**
```
Drug prescribed → patient response & lab parameters tracked over time
        → pharmacist/doctor reviews data → dose adjusted if needed
        → continued monitoring until therapy goal achieved
```

**Tools used:** EHR systems, CDSS alerts, lab monitoring (LIMS), patient-reported outcome apps.

**Importance:** Detects therapeutic failure or toxicity early, enabling timely dose adjustment and improving patient safety.

---

**— End of 2022 Main & Backlog Examination (November 2022) Answer Key —**
