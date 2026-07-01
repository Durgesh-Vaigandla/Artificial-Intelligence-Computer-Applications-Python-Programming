# B.Pharmacy II Semester (PCI) — Computer Applications in Pharmacy
# 2019 — Main & Backlog Examination (August 2019)
## Answer Key

---

> **Instructions reflected in this key:** PART–A — **10 Marks each** (Q2 is split into two 5-mark sub-parts, (i) and (ii), totalling 10). PART–B — **5 Marks each**.

---

# PART – A  (10 Marks Each)

---

## Q1. What is number system? Write Binary to Decimal conversion and Decimal to Binary conversion. [10 Marks]

### 1. Definition (1.5 Marks)
A **number system** is a systematic method of representing numbers using a defined set of symbols (digits) and positional rules. Computers internally operate using the **Binary Number System** (base-2) because digital circuits have only two stable electrical states (ON/OFF), which map directly to the digits 1 and 0.

### 2. Binary Number System (1.5 Marks)
- **Base:** 2
- **Digits used:** 0, 1
- Every computer operation — storing a drug dose, displaying a patient record, running a pharmacy billing program — is ultimately represented as binary at the hardware level.

### 3. Binary to Decimal Conversion (3 Marks)

**Method:** Multiply each binary digit by 2 raised to its positional power (counting from the right, starting at 0), then sum all results.

**Worked Example 1:** Convert `1010` (binary) to decimal.
```
1010 = (1×2³) + (0×2²) + (1×2¹) + (0×2⁰)
     = 8 + 0 + 2 + 0
     = 10 (decimal)
```

**Worked Example 2:** Convert `11001` (binary) to decimal.
```
11001 = (1×2⁴) + (1×2³) + (0×2²) + (0×2¹) + (1×2⁰)
      = 16 + 8 + 0 + 0 + 1
      = 25 (decimal)
```

### 4. Decimal to Binary Conversion (3 Marks)

**Method:** Repeatedly divide the decimal number by 2, recording the remainder at each step, until the quotient becomes 0. Read remainders from bottom to top.

**Worked Example 1:** Convert `13` (decimal) to binary.
```
13 ÷ 2 = 6   remainder 1
 6 ÷ 2 = 3   remainder 0
 3 ÷ 2 = 1   remainder 1
 1 ÷ 2 = 0   remainder 1

Reading bottom→top: 1101
∴ 13 (decimal) = 1101 (binary)
```

**Worked Example 2:** Convert `25` (decimal) to binary.
```
25 ÷ 2 = 12  remainder 1
12 ÷ 2 = 6   remainder 0
 6 ÷ 2 = 3   remainder 0
 3 ÷ 2 = 1   remainder 1
 1 ÷ 2 = 0   remainder 1

Reading bottom→top: 11001
∴ 25 (decimal) = 11001 (binary)
```

### 5. Conclusion (1 Mark)
These two conversions are the most fundamental operations in digital computing, forming the basis by which every piece of pharmacy software internally translates human-readable decimal values into the binary form the computer's hardware can process.

---

## Q2. Write a note on Drug information storage and discuss briefly about applications of computers in dispensing of drugs.
### *(i) Write a note on web servers and server products.*
### *(ii) Write about MS-ACCESS.* [10 Marks Total]

> 📝 **Note:** This question appears to combine a primary question with two sub-parts in the original paper. Both the primary question and the two sub-parts are answered below for completeness; in the actual exam, confirm with your examiner whether to answer the primary question OR the (i)/(ii) sub-parts.

### PRIMARY — Drug Information Storage & Applications of Computers in Dispensing [10 Marks]

#### 1. Drug Information Storage (4 Marks)

**Definition:** **Drug Information Storage** refers to the systematic, electronic recording and organization of comprehensive data about every drug — composition, dosage, indications, contraindications, interactions, and storage conditions — typically maintained in a structured database.

**What a Drug Information System Stores:**

| Field | Example |
|-------|---------|
| Drug Name (Brand + Generic) | Crocin / Paracetamol |
| Category | Analgesic |
| Dose Strength | 500mg |
| Indications | Fever, mild pain |
| Contraindications | Severe hepatic impairment |
| Side Effects | Nausea, rash |
| Storage Conditions | Store below 25°C |

**Retrieval Process:**
```
Pharmacist/Doctor searches drug name in system
        ↓
System retrieves full monograph from database
        ↓
Information displayed: dosing, interactions, warnings
```

#### 2. Applications of Computers in Dispensing of Drugs (5 Marks)

| Application | Description |
|-------------|--------------|
| **Prescription Verification** | Software automatically checks dose, interactions, and allergies before dispensing |
| **Barcode Scanning** | Confirms the correct drug and batch is picked, reducing dispensing errors |
| **Automated Dispensing Cabinets** | Robotic systems dispense drugs only after electronic verification (e.g., Pyxis, Omnicell) |
| **Inventory Deduction** | Stock automatically decreases as drugs are dispensed, triggering reorder alerts |
| **Labelling** | Computer generates accurate, clear dispensing labels automatically |
| **Record Keeping** | Every dispensing event is logged with pharmacist ID, date, and batch number |

#### 3. Conclusion (1 Mark)
Computerized drug information storage and dispensing systems together drastically reduce medication errors, improve traceability, and ensure patients receive the correct medication safely and efficiently.

---

### (i) Web Servers and Server Products [5 Marks]

**Definition:** A **Web Server** is software (and hardware) that stores, processes, and delivers web pages to users upon request, using HTTP/HTTPS protocol.

**How it works:**
```
Browser sends HTTP Request → Web Server processes & fetches data → sends HTTP Response → Browser displays page
```

**Common Server Products:**

| Server Product | Notes |
|------------------|-------|
| **Apache HTTP Server** | Free, open-source |
| **Nginx** | High-speed, high-traffic handling |
| **Microsoft IIS** | Used with Windows Server |
| **Tomcat** | For Java-based web applications |

**Relevance to Pharmacy:** Hospital patient portals and drug databases are hosted on web servers.

---

### (ii) MS-ACCESS [5 Marks]

**Definition:** **MS Access** is a desktop Relational Database Management System (RDBMS) combining a database engine with a graphical interface, allowing users to build databases without extensive coding.

**Components:**

| Component | Function |
|-----------|----------|
| **Tables** | Store raw data in rows and columns |
| **Queries** | Retrieve specific data based on conditions |
| **Forms** | User-friendly data-entry interface |
| **Reports** | Formatted, printable data summaries |

**Example:** A pharmacy's `Patients` table holds demographic data; a Form allows easy data entry; a Query filters patients by age; a Report prints a formatted patient list.

---
---

# PART – B  (5 Marks Each)

---

## Q4. What is HTML? Application of HTML. [5 Marks]

**Definition:** **HTML (HyperText Markup Language)** is the standard markup language used to create the structure of web pages, using tags to define elements that the browser renders visually.

**Applications of HTML:**
1. Building drug information portals
2. Creating patient registration and screening forms
3. Designing hospital/pharmacy websites
4. Displaying tabular data (dosage charts, lab results)
5. Embedding images, links, and multimedia for patient education

**Example:**
```html
<html><body>
<h1>Paracetamol</h1>
<p>Used for fever and mild pain relief.</p>
</body></html>
```

---

## Q5. How to plan and manage new project? [5 Marks]

**Definition:** **Project planning and management** involves systematically defining, organizing, and controlling the resources, timeline, and tasks required to achieve a specific goal — such as implementing a new hospital pharmacy software system.

**Key Steps:**

| Step | Description |
|------|--------------|
| 1. **Initiation** | Define project objective and scope |
| 2. **Planning** | Identify tasks, resources, timeline, budget |
| 3. **Execution** | Carry out planned tasks |
| 4. **Monitoring** | Track progress against plan, manage risks |
| 5. **Closure** | Final review, documentation, handover |

**Importance:** Ensures projects (e.g., installing a new Pharmacy Information System) are completed on time, within budget, and meet intended requirements.

---

## Q6. What is the importance of Drug Database system in MySQL? [5 Marks]

**Definition:** A **drug database system in MySQL** is a structured, centralized, multi-user-accessible repository of drug information built using the MySQL Relational Database Management System.

**Importance:**

| Requirement | Why MySQL Satisfies It |
|--------------|------------------------|
| Many staff need access simultaneously | MySQL is a multi-user server, handling many connections at once |
| Data must remain consistent | MySQL enforces keys/constraints preventing invalid/duplicate entries |
| Must scale to large datasets | Built for efficient handling of millions of records |
| Integration with hospital software | Common backend for PHP/Python/Java-based systems |
| Fast retrieval during emergencies | SQL queries return results in milliseconds |
| Cost-effective | Free, open-source |

**Conclusion:** A MySQL-based drug database enables fast, accurate, simultaneous access to drug data across an entire hospital — essential for safe dispensing and interaction checking.

---

## Q7. What is the importance of Clinical studies? [5 Marks]

**Definition:** **Clinical studies** (clinical trials) are research investigations conducted on human participants to evaluate the safety, efficacy, and optimal dosing of new drugs or treatments.

**Importance:**
1. Establishes whether a new drug is safe and effective before public release
2. Identifies correct dosage and potential side effects
3. Provides scientific evidence required for regulatory approval (CDSCO, FDA)
4. Detects rare adverse effects only visible in larger populations
5. Supports evidence-based clinical decision-making by pharmacists and doctors

**Conclusion:** Clinical studies form the scientific foundation upon which all modern drug therapy and pharmacy practice is built.

---

## Q8. Write a short note on Bioinformatics. [5 Marks]

**Definition:** **Bioinformatics** is an interdisciplinary field combining biology, computer science, and statistics to collect, store, analyze, and interpret biological data such as genomic and protein sequences.

**Key Applications:**
1. Drug target identification
2. Protein structure prediction (e.g., AlphaFold)
3. Genomic analysis for personalized medicine
4. Disease mechanism research

**Importance in Pharmacy:** Accelerates drug discovery by allowing computational screening of potential drug candidates before expensive laboratory testing.

---

## Q9. Write a note on chromatographic data analysis system. [5 Marks]

**Definition:** A **Chromatographic Data System (CDS)** is software used to collect, process, and store data from chromatographic instruments (HPLC, GC) for drug quality testing.

**Workflow:**
```
Sample injected → instrument separates components → CDS captures chromatogram
        → identifies peaks, retention time, area → generates validated report
```

**Key Functions:** Peak integration, calibration against standards, audit trail for regulatory compliance (GxP).

**Importance:** Essential for verifying drug purity and ensuring batch-to-batch quality consistency.

---

## Q10. Explain Text Information Management System. [5 Marks]

**Definition:** A **Text Information Management System (TIMS)** stores, organizes, searches, and retrieves large volumes of unstructured textual data such as drug literature and clinical notes.

**Workflow:**
```
Documents indexed by TIMS → user submits search query
        → TIMS retrieves & ranks relevant documents → user extracts information
```

**Example:** PubMed functions as a large-scale TIMS, letting pharmacists search millions of articles instantly by keyword.

---

## Q11. Explain Electronic prescribing and Discharging system. [5 Marks]

**Definition:** **E-Prescribing** is the computer-based generation and transmission of prescriptions. **Electronic Discharge Systems** digitally generate a patient's discharge summary and medication instructions.

**e-Prescribing workflow:**
```
Doctor enters prescription → system checks interactions/allergies
        → transmitted to pharmacy → dispensed → recorded in EHR
```

**Discharge System:** Compiles diagnosis, treatment, discharge medications, and follow-up instructions digitally, ensuring continuity of care.

**Advantages:** Eliminates handwriting errors, automatic safety checks, faster processing, complete record continuity.

---

**— End of 2019 Main & Backlog Examination Answer Key —**
