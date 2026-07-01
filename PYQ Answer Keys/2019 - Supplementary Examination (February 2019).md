# B.Pharmacy II Semester (PCI) — Computer Applications in Pharmacy
# 2019 — Supplementary Examination (February 2019)
## Answer Key

---

> **Instructions reflected in this key:** PART–A — **10 Marks each**. PART–B — **5 Marks each**.

---

# PART – A  (10 Marks Each)

---

## Q1. Explain different number systems used in computers (binary, decimal, octal, hexadecimal). [10 Marks]

### 1. Introduction (1 Mark)
Computers represent all data — text, images, drug doses, patient records — internally as combinations of 0s and 1s. To work with this data conveniently, four number systems are used: **Binary, Decimal, Octal,** and **Hexadecimal**.

### 2. Binary Number System (2 Marks)
- **Base:** 2
- **Digits used:** 0, 1
- **Definition:** The fundamental number system of digital computers, where each digit (called a **bit**) represents one of two electrical states — ON (1) or OFF (0).
- **Example:** `1101` (binary)
- **Why computers use it:** Digital circuits (transistors) naturally have two stable states, making binary the only number system directly realizable in hardware.

### 3. Decimal Number System (2 Marks)
- **Base:** 10
- **Digits used:** 0–9
- **Definition:** The everyday number system used by humans, based on 10 digits, most likely originating from counting on ten fingers.
- **Example:** `245` (decimal)
- **Role in computing:** Used at the human interface level — when a pharmacist types `500` for a drug dose, the computer internally converts this decimal value to binary for processing.

### 4. Octal Number System (2 Marks)
- **Base:** 8
- **Digits used:** 0–7
- **Definition:** A base-8 system where each digit represents a group of exactly 3 binary digits, making it a compact way to represent binary data.
- **Example:** `372` (octal)
- **Conversion relationship:** `372` (octal) = `011 111 010` (binary), each octal digit expanding to exactly 3 bits.

### 5. Hexadecimal Number System (2 Marks)
- **Base:** 16
- **Digits used:** 0–9, then A, B, C, D, E, F (representing 10–15)
- **Definition:** A base-16 system where each digit represents a group of exactly 4 binary digits — widely used in programming and memory addressing because it represents large binary numbers very compactly.
- **Example:** `F2` (hexadecimal) = `11110010` (binary)

### 6. Comparative Summary Table (0.5 Mark)

| System | Base | Digits | Bits per digit (when grouping binary) | Example |
|--------|------|--------|------------------------------------------|---------|
| Binary | 2 | 0–1 | 1 | 1101 |
| Decimal | 10 | 0–9 | — | 245 |
| Octal | 8 | 0–7 | 3 | 372 |
| Hexadecimal | 16 | 0–9, A–F | 4 | F2 |

### 7. Conclusion (0.5 Mark)
Each number system serves a purpose: binary for hardware-level processing, decimal for human interaction, and octal/hexadecimal as convenient shorthand notations for binary data in technical contexts such as memory addresses and colour codes.

---

## Q2. Describe about laboratory information management system. [10 Marks]

### 1. Definition (1 Mark)
A **Laboratory Information Management System (LIMS)** is software designed to manage, track, and automate the entire workflow of a laboratory — from sample registration to final result reporting — ensuring accuracy, traceability, and regulatory compliance.

### 2. Why LIMS is Needed (1.5 Marks)
Before LIMS, laboratories tracked samples and results manually using paper logbooks — leading to:
- Sample mix-ups and mislabelling
- Lost or illegible results
- No audit trail for regulatory inspections
- Slow turnaround time for reporting results to doctors/patients

### 3. Core Functions of LIMS (3 Marks)

| Function | Description |
|----------|-------------|
| **Sample Tracking** | Assigns a unique barcode/ID to every sample upon receipt, tracked through every stage |
| **Workflow Management** | Routes samples automatically to the correct testing department/instrument |
| **Data Capture** | Receives results directly from lab analysers, reducing manual transcription errors |
| **Quality Control** | Tracks calibration status and QC checks for laboratory instruments |
| **Reporting** | Automatically generates and transmits formatted result reports to doctors/EHR |
| **Audit Trail** | Records every action taken on a sample/result, with user ID and timestamp |

### 4. Workflow Diagram (2 Marks)

```
Sample collected from patient
        ↓
Sample registered in LIMS, barcode assigned
        ↓
Sample routed to appropriate test department
        ↓
Automated analyser performs test, sends result to LIMS
        ↓
Lab technician/pathologist validates result
        ↓
LIMS generates formatted report
        ↓
Report transmitted to doctor's EHR / pharmacist
```

### 5. Advantages of LIMS (1.5 Marks)
1. Eliminates manual transcription errors
2. Drastically reduces sample mix-up risk via barcoding
3. Speeds up turnaround time for critical results
4. Provides full audit trail for regulatory inspections (NABL, CDSCO)
5. Enables remote/instant access to results by authorized clinicians

### 6. Relevance to Pharmacy (0.5 Mark)
Pharmacists rely on LIMS-generated lab data (e.g., serum creatinine, liver function tests) to make safe, informed decisions about drug dosing and to flag dangerous drug-disease contraindications.

### 7. Conclusion (0.5 Mark)
LIMS is now considered indispensable in any modern hospital or pharmaceutical quality-control laboratory, forming a critical link between sample testing and clinical decision-making.

---

## Q3. Write about XML. [10 Marks]

### 1. Definition (1 Mark)
**XML (eXtensible Markup Language)** is a markup language designed to store and transport data in a structured, self-describing, platform-independent format. Unlike HTML — which is built to **display** data — XML's core purpose is to **carry and exchange** data between different software systems.

### 2. Key Characteristics of XML (2 Marks)
1. **Extensible** — you define your own tags; there is no fixed vocabulary like in HTML
2. **Self-describing** — the tag names themselves describe the meaning of the data they contain
3. **Platform-independent** — any system, on any operating system, in any programming language, can read XML
4. **Strict syntax** — must be "well-formed," following non-negotiable structural rules

### 3. XML vs HTML (2 Marks)

| Feature | HTML | XML |
|---------|------|-----|
| Purpose | Display data | Store/transport data |
| Tags | Fixed, predefined | User-defined |
| Case sensitivity | Not case sensitive | Case sensitive |
| Closing tags | Some optional | All mandatory |
| Validation | Browser-forgiving | Strict — must be well-formed |

### 4. Example XML Document (1.5 Marks)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<patient id="P001">
    <name>Rahul Sharma</name>
    <age>45</age>
    <medication>
        <drug>Metformin</drug>
        <dose unit="mg">500</dose>
    </medication>
    <allergy>Penicillin</allergy>
</patient>
```

### 5. Rules of Well-Formed XML (2 Marks)
1. Every opening tag must have a matching closing tag
2. Tags must be properly nested (no overlapping)
3. XML tags are case-sensitive (`<Drug>` ≠ `<drug>`)
4. Attribute values must always be quoted
5. There must be exactly one root element
6. Special characters (`<`, `>`, `&`) must be escaped (`&lt;`, `&gt;`, `&amp;`)

### 6. Importance of XML in Healthcare (1 Mark)
XML forms the structural basis of the **HL7 (Health Level 7)** standard, the internationally recognized format for exchanging clinical and administrative healthcare data — for example, a discharge summary generated by one hospital's system can be correctly read by a completely different hospital's software because both rely on this shared, structured XML-based format.

### 7. Conclusion (0.5 Mark)
XML remains foundational to healthcare data interoperability, enabling EHRs, lab systems, and pharmacy software to exchange patient information reliably and accurately across different platforms.

---
---

# PART – B  (5 Marks Each)

---

## Q4. Explain the concept of data flow diagrams. [5 Marks]

**Definition:** A **Data Flow Diagram (DFD)** is a graphical representation showing how data moves through a system — illustrating processes, data stores, external entities, and the flow of data between them.

**Components:**

| Symbol | Represents |
|--------|-----------|
| Circle/Oval | A **Process** that transforms data |
| Rectangle | An **External Entity** (e.g., a patient) |
| Open rectangle | A **Data Store** (e.g., a database) |
| Arrow | A **Data Flow** — direction data moves |

**Example — Pharmacy Prescription System:**
```
[Patient] → (Submit Prescription) → [Pharmacy System] → (Check Interactions)
        → [Drug Database] → (Verify) → [Pharmacist] → (Dispense) → [Patient]
```

**Levels:** Level 0 (Context Diagram, whole system as one process); Level 1 (major sub-processes); Level 2+ (further detail).

**Importance:** Helps pharmacy IT teams visualize and plan data movement before building software systems.

---

## Q5. Discuss about web servers and server products. [5 Marks]

**Definition:** A **Web Server** is software (and hardware) that stores, processes, and delivers web pages to users upon request, using HTTP/HTTPS.

**How it works:**
```
Browser sends HTTP Request → Web Server processes & fetches data → sends HTTP Response → Browser displays page
```

**Common Server Products:**

| Server Product | Notes |
|------------------|-------|
| **Apache HTTP Server** | Free, open-source, widely used |
| **Nginx** | Known for speed, high traffic handling |
| **Microsoft IIS** | Used with Windows Server |
| **Tomcat** | For Java-based web applications |

**Relevance:** Hospital patient portals and drug information databases are hosted on web servers, accessible from any browser.

---

## Q6. Differentiate hospital and clinical pharmacy. [5 Marks]

**Definitions:**
- **Hospital Pharmacy:** The pharmacy department located within a hospital, responsible for procurement, storage, compounding, and dispensing of medicines for inpatients and outpatients.
- **Clinical Pharmacy:** A patient-care-focused area of pharmacy practice where pharmacists work directly with the healthcare team and patients, optimizing medication therapy through direct clinical involvement.

**Key Differences:**

| Aspect | Hospital Pharmacy | Clinical Pharmacy |
|--------|---------------------|---------------------|
| **Focus** | Drug supply, storage, dispensing | Direct patient care, therapy optimization |
| **Location** | Centralized pharmacy department | Wards, ICU, alongside doctors at bedside |
| **Role** | Procurement, inventory, dispensing | Medication review, dose adjustment, counselling |
| **Interaction** | Limited direct patient contact | Frequent, direct patient/doctor interaction |

**Conclusion:** Hospital pharmacy is the broader operational/logistics function; clinical pharmacy is a specialized, patient-facing extension of it focused on optimizing individual therapy outcomes.

---

## Q7. Discuss about databases of bioinformatics. [5 Marks]

**Definition:** **Bioinformatics databases** are organized, electronic repositories storing biological data — DNA sequences, protein structures, gene expression data — used in computational biology and drug research.

**Types of Bioinformatics Databases:**

| Type | Example | Stores |
|------|---------|--------|
| **Sequence Database** | GenBank | DNA/RNA sequences |
| **Protein Database** | UniProt, PDB | Protein sequences and 3D structures |
| **Literature Database** | PubMed | Biomedical research articles |
| **Pathway Database** | KEGG | Metabolic and signalling pathways |

**Importance in Pharmacy:** These databases support drug target identification, structure-based drug design, and understanding disease mechanisms at a molecular level.

---

## Q8. Write about electronic prescribing and discharge systems. [5 Marks]

**Definition:** **E-Prescribing** is the computer-based generation and transmission of prescriptions, replacing handwritten ones. An **Electronic Discharge System** digitally generates a patient's discharge summary and medication instructions.

**e-Prescribing workflow:**
```
Doctor enters prescription → system checks interactions/allergies
        → transmitted to pharmacy → pharmacist dispenses → recorded in EHR
```

**Advantages:** Eliminates handwriting errors; automatic safety checks; faster processing; complete medication history.

**Discharge System:** Compiles diagnosis, treatment given, discharge medications, and follow-up instructions digitally, ensuring continuity of care between hospital and home.

---

## Q9. Explain about HTML. [5 Marks]

**Definition:** **HTML (HyperText Markup Language)** is the standard markup language for creating the structure of web pages, using tags to define elements.

**Key Tags:**

| Tag | Purpose |
|-----|---------|
| `<html>`, `<head>`, `<body>` | Document structure |
| `<h1>`–`<h6>` | Headings |
| `<p>` | Paragraph |
| `<a>` | Hyperlink |
| `<table>` | Tabular data |

**Example:**
```html
<html><body>
<h1>Drug Information</h1>
<p>Paracetamol is an analgesic.</p>
</body></html>
```

**Importance:** Forms the basis of hospital websites, drug information portals, and patient registration pages.

---

## Q10. Write a note on biological databases. [5 Marks]

**Definition:** **Biological databases** are structured collections of biological data — genomic sequences, protein structures, and biochemical pathways — used in bioinformatics research.

**Categories:**

| Category | Example |
|----------|---------|
| Nucleotide sequence databases | GenBank, EMBL |
| Protein structure databases | PDB (Protein Data Bank) |
| Gene expression databases | GEO |
| Drug-target databases | DrugBank |

**Importance in Pharmacy:** Enable identification of drug targets, prediction of drug-protein interactions, and support rational drug design.

---

## Q11. What are objectives of bioinformatics? [5 Marks]

**Definition:** **Bioinformatics** is an interdisciplinary field combining biology, computer science, and statistics to analyze and interpret biological data.

**Key Objectives:**
1. Organize biological data into accessible, searchable databases
2. Develop tools/algorithms for analyzing biological data (e.g., sequence alignment)
3. Interpret data to extract meaningful biological insights
4. Support drug discovery through target identification and structure prediction
5. Enable personalized medicine through genomic analysis

**Conclusion:** Bioinformatics objectives directly support faster, more precise pharmaceutical research and development.

---

**— End of 2019 Supplementary Examination Answer Key —**
