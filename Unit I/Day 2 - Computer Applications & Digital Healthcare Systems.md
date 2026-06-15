# Unit I – Day 2 (2 Hours)
## Computer Applications in Pharmacy — IT in Pharmaceutical Sciences, Digital Healthcare Systems, EHR & Pharmacy Information Systems

---

## 🎯 Session Goals
By the end of this session, students will be able to:
- Explain the role of Information Technology in Pharmaceutical Sciences
- Describe what Digital Healthcare Systems are and how they are structured
- Distinguish between EHR and EMR and explain what EHR contains
- Explain how Pharmacy Information Systems work end-to-end
- Name key drug databases and information tools used in pharmacy practice

---

## ⏱️ Session Plan (2 Hours)

| Time | Topic |
|------|-------|
| 0:00 – 0:05 | Recap of Day 1, session overview |
| 0:05 – 0:35 | Role of IT in Pharmaceutical Sciences |
| 0:35 – 1:05 | Digital Healthcare Systems — components and structure |
| 1:05 – 1:35 | Electronic Health Records (EHR) — in depth |
| 1:35 – 1:55 | Pharmacy Information Systems (PIS) — end-to-end |
| 1:55 – 2:00 | Recap + Q&A |

---

---

# SECTION 1 — Role of Information Technology in Pharmaceutical Sciences
## (0:05 – 0:35 | 30 minutes)

---

## 1.1 What is Information Technology?

> **Information Technology (IT)** is the use of computers, software, networks, and electronic systems to store, retrieve, process, and exchange information.

In pharmaceutical sciences, IT connects every part of the healthcare chain:
- The doctor who diagnoses
- The pharmacist who dispenses
- The laboratory that tests
- The hospital that manages
- The regulator that approves drugs

---

## 1.2 Why Did Pharmacy Need IT?

### Before IT — The Paper Era

Think about a community pharmacy 30 years ago:

- Prescriptions were handwritten — illegible, easily misread
- Drug names looked similar on paper: Celebrex vs Cerebyx, Lasix vs Losec
- Dosage errors went undetected
- A patient's allergy record existed only in a paper file — if they came from another hospital, no one knew their history
- Inventory was managed manually — pharmacists counted tablets by hand
- Drug expiry was tracked using paper registers — misses happened often
- No way to check if a drug was recalled
- Billing was manual — slow and error-prone
- Research data was paper-based — no easy analysis

**The result:** Medication errors, stock-outs, dangerous drug dispensing, and massive inefficiency.

### After IT — The Digital Era

| Problem (Before IT) | Solution (After IT) |
|---------------------|---------------------|
| Illegible handwritten prescriptions | Digital prescriptions — clear, standardized |
| Missed drug interactions | Automatic interaction checking software |
| No allergy history available | Centralized digital patient records |
| Manual stock counting | Automated inventory tracking with alerts |
| Missed drug expiry | Software flags near-expiry stock |
| No drug recall notifications | Instant alerts from CDSCO / manufacturer |
| Manual billing | Automated billing with insurance integration |
| No access to latest drug information | Online drug databases (MIMS, Micromedex) |
| Research data difficult to analyse | Python, Excel, SPSS for data analysis |

---

## 1.3 Major Roles of IT in Pharmaceutical Sciences

### a) Clinical Role — Patient Safety
IT protects patients at every point of medication management:

- **e-Prescribing systems** — Doctors type prescriptions directly into software; pharmacy receives it digitally, removing handwriting errors entirely
- **Drug interaction checkers** — Software cross-references all of a patient's medications and alerts for dangerous combinations
- **Barcode medication administration (BCMA)** — Nurse scans drug barcode + patient wristband barcode before giving any medication; system confirms it's the right drug for the right patient
- **Automated dispensing cabinets** — Hospital pharmacies use machines (Pyxis, Omnicell) that dispense drugs only after electronic verification

### b) Administrative Role — Operations
- **Hospital Management Systems (HMS)** — Manages patient registration, bed allocation, billing, staff scheduling
- **Pharmacy Management Software** — Handles purchase orders, stock levels, sales, returns, reports
- **Insurance claim processing** — Software generates and submits insurance claims automatically

### c) Research Role — Drug Development & Analysis
- **Bioinformatics software** — Analyses genomic data for drug target identification
- **Clinical trial management systems (CTMS)** — Tracks patient enrollment, data collection, adverse events in drug trials
- **Statistical software (SPSS, R, Python)** — Analyses clinical data to determine drug efficacy
- **Drug regulatory submission portals** — Pharmaceutical companies submit drug approval applications to CDSCO (India) / FDA (USA) digitally

### d) Educational Role — Knowledge Access
- **PubMed** — Free database of 35 million biomedical research articles
- **MIMS India** — Drug information compendium used by Indian pharmacists and doctors
- **Micromedex** — Premium drug information database for hospitals
- **Online learning platforms** — Continuing education for pharmacists

### e) Regulatory Role — Drug Safety Monitoring
- **Pharmacovigilance systems** — Track adverse drug reactions reported by patients and clinicians
- **CDSCO Drug Database** — Central Drugs Standard Control Organisation of India maintains a database of approved drugs, banned drugs, recalls
- **Cold chain monitoring** — IoT sensors + software track temperature of vaccines during transport

---

## 1.4 Core IT Tools in a Typical Indian Hospital Pharmacy

| IT Tool | What It Does | Example |
|---------|-------------|---------|
| Hospital Information System (HIS) | Manages entire hospital operations | Meditech, Cerner |
| Pharmacy Management Software | Drug stock, billing, prescriptions | Marg ERP, Busy, WinMed |
| e-Prescribing Module | Digital prescriptions from doctors | Integrated in HIS |
| Drug Interaction Checker | Flags dangerous drug combinations | Micromedex, Lexicomp |
| Barcode Scanner | Drug identification + dispensing verification | Part of PIS |
| Electronic Health Record (EHR) | Complete patient medical record | Epic, OpenMRS |
| Drug Information Database | Clinical reference | MIMS, Micromedex |
| Inventory Management | Stock tracking, reorder alerts | Tally, Marg |
| Billing Software | Invoicing, insurance claims | SAP, Marg |

---

## 1.5 IT in Pharmaceutical Manufacturing

IT is not just in hospitals. Drug manufacturing also depends on IT:

- **Manufacturing Execution Systems (MES)** — Monitor and control drug production processes
- **LIMS (Laboratory Information Management System)** — Manages quality control lab data — testing results, batch records
- **ERP (Enterprise Resource Planning)** — Manages procurement, production, storage, and distribution of drugs (SAP used by companies like Sun Pharma, Cipla)
- **Track & Trace systems** — Unique codes on every drug package allow tracking from factory to patient
- **Regulatory submission software** — Formats data as per FDA/CDSCO requirements for drug approval submissions

---

---

# SECTION 2 — Digital Healthcare Systems
## (0:35 – 1:05 | 30 minutes)

---

## 2.1 What are Digital Healthcare Systems?

> **Digital Healthcare Systems** are integrated networks of software, hardware, and communication technologies that collect, store, process, and share health-related information to support clinical care, administration, and research.

A modern hospital is not just a building with doctors. It is a **complex digital ecosystem** where dozens of software systems work together.

---

## 2.2 Components of a Digital Healthcare System

```
DIGITAL HEALTHCARE ECOSYSTEM
│
├── CLINICAL SYSTEMS
│     ├── Electronic Health Record (EHR)
│     ├── Clinical Decision Support System (CDSS)
│     ├── Computerized Physician Order Entry (CPOE)
│     └── Nursing Information System
│
├── DIAGNOSTIC SYSTEMS
│     ├── Laboratory Information System (LIS)
│     ├── Radiology Information System (RIS)
│     └── Picture Archiving & Communication System (PACS)
│
├── PHARMACY SYSTEMS
│     ├── Pharmacy Information System (PIS)
│     ├── Automated Dispensing Cabinets
│     └── Drug Interaction Checking Software
│
├── ADMINISTRATIVE SYSTEMS
│     ├── Hospital Management System (HMS)
│     ├── Billing & Insurance System
│     ├── Appointment Scheduling
│     └── HR & Payroll
│
└── PATIENT-FACING SYSTEMS
      ├── Patient Portal
      ├── Telemedicine Platform
      └── Mobile Health Apps
```

---

## 2.3 How These Systems Connect — A Patient's Journey

Let's trace a single patient visit through a hospital's digital systems:

```
PATIENT ARRIVES AT HOSPITAL
          ↓
[HMS] — Patient registered, unique ID assigned, appointment booked
          ↓
[EHR] — Past medical history, allergies, current medications loaded
          ↓
DOCTOR EXAMINES PATIENT
          ↓
[CPOE] — Doctor types orders: blood test + chest X-ray + Amoxicillin 500mg
          ↓
          ├──► [LIS] — Lab receives blood test order; results uploaded back to EHR
          │
          ├──► [RIS + PACS] — Radiology receives X-ray order; image stored digitally; 
          │                    radiologist reviews; report sent to EHR
          │
          └──► [PIS] — Pharmacy receives drug order
                    ↓
               [CDSS checks interaction + allergy]
                    ↓
               Pharmacist verifies, drug dispensed
                    ↓
               [EHR updated] — Medication recorded
                    ↓
               [HMS Billing] — Consultation + tests + drug billed
                    ↓
               [Patient Portal] — Patient views their results online
```

> 💬 "Notice how the doctor types ONE order and it automatically flows to the lab, radiology, and pharmacy simultaneously. Without IT, a nurse would carry physical paper slips to each department. With IT, everything is instant and traceable."

---

## 2.4 Benefits of Digital Healthcare Systems

### For Patients
- **Faster diagnosis** — Lab results in EHR within minutes of testing
- **Reduced errors** — No manual copying of drug names or doses
- **Continuity of care** — Any hospital can see full medical history (with consent)
- **Remote access** — View own lab reports, prescriptions via patient portal
- **Safety** — Allergy alerts fire automatically before any drug is given

### For Pharmacists
- **Digital prescriptions** — No misreading of handwriting
- **Automatic interaction checking** — System flags before pharmacist even reads the order
- **Stock management** — Know instantly what is in stock and what needs reordering
- **Dispensing record** — Every dispensing is logged with pharmacist ID and timestamp
- **Reduced paperwork** — More time for patient counseling

### For the Healthcare System
- **Data for research** — Millions of patient records can be analysed for disease trends
- **Epidemic detection** — Unusual patterns detected early (e.g., sudden spike in flu cases)
- **Resource planning** — Predict bed requirements, drug demand by season
- **Cost reduction** — Less duplication of tests, less waste, fewer preventable admissions

---

## 2.5 Challenges of Digital Healthcare Systems

| Challenge | Explanation |
|-----------|-------------|
| **Cybersecurity** | Patient data is extremely sensitive; hospitals are prime targets for ransomware attacks |
| **Interoperability** | Different hospitals use different software that may not communicate easily |
| **Training** | Staff need proper training; resistance to change is common |
| **Cost** | Implementing EHR systems costs crores — difficult for rural hospitals |
| **Power & connectivity** | In rural India, unreliable internet and power make digital systems difficult |
| **Data privacy** | Patient data must be protected under law (Digital Personal Data Protection Act, India 2023) |

---

---

# SECTION 3 — Electronic Health Records (EHR)
## (1:05 – 1:35 | 30 minutes)

---

## 3.1 Definition and Concept

> An **Electronic Health Record (EHR)** is a real-time, patient-centered, digital record of a patient's health information that can be created, managed, and shared by authorized healthcare providers across different organizations.

Think of the EHR as a **comprehensive, living digital file** that follows a patient everywhere — from their family doctor to a specialist to a hospital to a pharmacy — giving every authorized provider a complete picture of the patient's health.

---

## 3.2 EHR vs EMR — The Important Distinction

This distinction is commonly asked in exams:

| Feature | EHR (Electronic Health Record) | EMR (Electronic Medical Record) |
|---------|-------------------------------|--------------------------------|
| **Scope** | Covers care across multiple providers and settings | Covers care within a single practice or hospital |
| **Sharing** | Can be shared across hospitals, clinics, pharmacies | Stays within one organization |
| **Focus** | Patient-centered — belongs to the patient | Provider-centered — belongs to the clinic |
| **Portability** | Patient moves hospital; record follows them | Patient moves hospital; record stays behind |
| **Content** | Complete health history across all providers | Only records from that specific provider |
| **Standard** | Uses interoperability standards (HL7, FHIR) | May be proprietary format |
| **Example** | ABHA (India's national health record) | A single clinic's in-house patient software |

> 💬 "Imagine you visit Apollo Hospital in Hyderabad, then move to Chennai and visit Fortis. If both use EHR connected to ABHA, the Fortis doctor can see your Apollo records. With EMR, Fortis would know nothing about your Apollo visit."

---

## 3.3 What an EHR Contains

A complete EHR has multiple modules:

### Module 1: Patient Demographics
- Full name, date of birth, gender
- Address, contact number, emergency contact
- National health ID (ABHA number in India)
- Insurance details

### Module 2: Medical History
- Past illnesses and diagnoses
- Surgical history with dates
- Hospitalization records
- Family medical history (relevant for genetic conditions)
- Social history (smoking, alcohol, occupation)

### Module 3: Medications & Allergies
- Current medication list (drug name, dose, frequency, prescribing doctor)
- Past medications (with start and stop dates)
- Known drug allergies (drug name + type of reaction)
- Over-the-counter drugs and supplements

> 💬 **Pharmacy relevance:** "This is the most important module for a pharmacist. Before dispensing any drug, checking the EHR for current medications prevents dangerous interactions. Checking the allergy section prevents anaphylaxis."

### Module 4: Diagnoses and Problem List
- Active diagnoses (e.g., Type 2 Diabetes, Hypertension)
- Resolved diagnoses (e.g., Typhoid — 2019, resolved)
- Chronic conditions flagged prominently

### Module 5: Laboratory Results
- Blood test results with reference ranges
- Urine analysis, culture and sensitivity
- Glucose, lipid profile, liver function, kidney function
- Results stored with date — trends visible over time

### Module 6: Imaging & Radiology
- X-rays, CT scans, MRI reports
- PACS integration — actual images viewable by any authorized provider
- Radiologist reports attached

### Module 7: Vital Signs
- Blood pressure, heart rate, temperature, respiratory rate
- Oxygen saturation (SpO2)
- Weight and height over time — BMI tracking
- Trends graphed over multiple visits

### Module 8: Immunization Records
- Vaccines administered with dates and lot numbers
- Upcoming vaccinations due

### Module 9: Clinical Notes
- Doctor's consultation notes (SOAP format: Subjective, Objective, Assessment, Plan)
- Nurse notes
- Pharmacist's medication review notes

### Module 10: Prescriptions & Dispensing History
- Every prescription generated — with drug, dose, quantity, prescribing doctor
- Every dispensing recorded — with pharmacist, date, batch number

---

## 3.4 How an EHR Works in Practice — Pharmacy Scenario

**Scenario:** A 65-year-old diabetic patient on 5 medications comes to the pharmacy with a new prescription for Ciprofloxacin.

**Without EHR:**
- Pharmacist does not know what other drugs the patient is on
- Does not know patient has a documented Penicillin allergy
- Dispenses Ciprofloxacin without checking anything
- No record of this dispensing anywhere

**With EHR:**
```
Pharmacist opens patient EHR
          ↓
Sees current medications: Metformin, Gliclazide, Amlodipine, Atorvastatin, Warfarin
          ↓
Ciprofloxacin entered into PIS
          ↓
CDSS fires: "⚠️ INTERACTION — Ciprofloxacin + Warfarin increases INR, bleeding risk"
          ↓
Pharmacist contacts prescribing doctor
          ↓
Doctor reviews — switches to safer antibiotic
          ↓
Dispensing recorded in EHR
          ↓
Patient protected from potential harm
```

---

## 3.5 EHR in India — ABHA (Ayushman Bharat Health Account)

India's national EHR initiative:

- **ABHA Number** — 14-digit unique health ID for every Indian citizen
- Links records from AIIMS, government hospitals, private hospitals, pharmacies
- Patient controls who can access their records — consent-based sharing
- Part of the **Ayushman Bharat Digital Mission (ABDM)**
- Eventually will eliminate the need to carry paper prescriptions and test reports

> 💬 "In 5 years, when you practice as a pharmacist, a patient will show you their ABHA number or scan a QR code, and you will instantly see their complete medication history. This is already being piloted in Andhra Pradesh."

---

## 3.6 Well-Known EHR Systems

| System | Region | Notes |
|--------|--------|-------|
| **Epic** | USA | Used in most US hospitals; market leader |
| **Cerner (Oracle Health)** | USA/Global | Used in 1000+ hospitals worldwide |
| **OpenMRS** | India/Africa/Asia | Open-source; used in government hospitals |
| **Practo** | India | Used in private clinics; patient-facing app |
| **eVital (NIC)** | India | Government hospital system |
| **ABHA App** | India | Patient-held national health record |

---

---

# SECTION 4 — Pharmacy Information Systems (PIS)
## (1:35 – 1:55 | 20 minutes)

---

## 4.1 Definition

> A **Pharmacy Information System (PIS)** is a computer system specifically designed to manage all pharmacy operations — from receiving prescriptions to dispensing drugs, managing inventory, maintaining patient medication records, and generating reports.

PIS is to a pharmacy what a cockpit is to a plane — it centralizes all controls, gives real-time information, and prevents critical errors.

---

## 4.2 Core Functions of a PIS

### Function 1: Prescription Management
- Receives digital prescriptions from CPOE (doctor's order system) or EHR
- Displays prescription clearly — no handwriting ambiguity
- Pharmacist reviews, verifies, and approves the prescription
- System cross-checks against patient's allergy list and current medications
- Generates dispensing label automatically

### Function 2: Drug Interaction & Safety Checking
- When pharmacist enters a drug for a patient, PIS automatically queries the drug knowledge base
- Checks for: Drug-Drug Interactions, Drug-Allergy conflicts, Drug-Disease contraindications, Dose range violations, Duplicate therapy
- Alerts classified by severity: Critical / Major / Moderate / Minor
- Pharmacist must acknowledge or override each alert (with documented reason)

### Function 3: Drug Dispensing
- Generates a dispensing queue for the pharmacy
- Barcode scanning confirms correct drug picked
- Label printed automatically: patient name, drug, dose, frequency, warnings
- Pharmacist signs off digitally — accountability trail created
- In large hospitals: automated dispensing cabinets (robots) pick drugs

### Function 4: Inventory Management
- Real-time stock levels for every drug
- Automatically decrements stock when a drug is dispensed
- Sets reorder points — when stock falls below minimum, purchase order raised
- Expiry tracking — alerts sent 60/30/15 days before drug expiry
- Batch number and manufacturer tracked for every item
- If a drug is recalled by manufacturer or CDSCO, system immediately flags all units of that batch in stock

### Function 5: Patient Medication History
- Full record of every drug dispensed to a patient
- Useful for checking adherence — if patient hasn't refilled a chronic medication in months, pharmacist can follow up
- Prevents duplicate dispensing
- Supports medication reconciliation when patient is admitted to hospital

### Function 6: Reporting & Analytics
- Daily dispensing reports
- Most commonly prescribed drugs
- High-cost drug utilization analysis
- Near-expiry drug reports
- Controlled substance (narcotic) usage reports — legally required
- Revenue and billing reports

---

## 4.3 Complete Flow of a Drug Order Through PIS

```
STEP 1 → Doctor enters drug order in CPOE / EHR
              ↓
STEP 2 → Order transmitted digitally to PIS
              ↓
STEP 3 → PIS displays order to pharmacist:
          Patient: Priya Nair, 32F
          Drug: Amoxicillin 500mg, 3x daily, 7 days
              ↓
STEP 4 → PIS runs automatic safety checks:
          ✅ No drug-drug interactions found
          ✅ No allergy conflict
          ✅ Dose appropriate for age/weight
              ↓
STEP 5 → Pharmacist reviews and approves
              ↓
STEP 6 → PIS generates dispensing label:
          AMOXICILLIN 500mg
          Priya Nair | Batch: AMX2024B
          Take 1 capsule 3 times daily with food
          Dr. Sharma | Apollo Hospital
              ↓
STEP 7 → Pharmacy technician picks drug, scans barcode to confirm
              ↓
STEP 8 → Drug dispensed to patient / ward
              ↓
STEP 9 → PIS records: drug dispensed, by whom, at what time, from which batch
              ↓
STEP 10 → Inventory automatically updated: 21 capsules deducted from stock
              ↓
STEP 11 → EHR updated: Amoxicillin course recorded in patient medication history
              ↓
STEP 12 → Billing system updated: drug charge added to patient's account
```

---

## 4.4 Drug Information Databases Used in Pharmacy Practice

Every pharmacist needs access to reliable drug information. These are the key databases:

| Database | Country | What It Contains | Access |
|----------|---------|-----------------|--------|
| **MIMS India** | India | Drug monographs, dosing, interactions, indications for Indian market | Subscription |
| **Micromedex (Merative)** | USA/Global | Drug interactions, toxicology, dosing in special populations | Hospital subscription |
| **Lexicomp** | USA/Global | Drug information, patient counseling sheets, interactions | Subscription |
| **PubMed** | USA (NLM) | 35 million biomedical research articles | Free |
| **WHO Essential Medicines List** | Global | List of medicines that satisfy priority healthcare needs | Free |
| **CDSCO Drug Database** | India | Approved drugs, banned drugs, recalls, clinical trial information | Free (govt) |
| **Drug Bank** | Canada | Drug structures, targets, interactions for research | Free/Premium |
| **MedlinePlus** | USA | Patient-friendly drug information | Free |

> 💬 "As a pharmacist, MIMS and Micromedex are your most practical references. PubMed is where you find evidence when a clinical question has no clear answer in a textbook."

---

## 🧠 Full Session Key Takeaways

1. **IT transformed pharmacy** from error-prone paper-based practice to safe, efficient digital operations
2. **IT roles in pharmacy:** Clinical safety, administration, research, education, regulatory compliance
3. **Digital Healthcare Systems** are interconnected — EHR, LIS, RIS, PIS, HMS all talk to each other
4. **EHR** = patient-centered, shared across providers; **EMR** = single-provider, not shareable
5. **EHR contains:** Demographics, medical history, medications, allergies, labs, imaging, vitals, prescriptions
6. **ABHA** is India's national EHR initiative — pharmacists will use it in daily practice soon
7. **PIS** manages: prescription receipt, safety checks, dispensing, inventory, patient history, reporting
8. **Drug databases** (MIMS, Micromedex, PubMed) are essential clinical reference tools

---

## ❓ Discussion Questions

1. "A patient comes to your pharmacy with a paper prescription but tells you they also take 3 other drugs they bought from another pharmacy. You have no EHR access. What steps do you take to ensure safety?"
2. "If a hospital's PIS goes down during the night shift, how should the pharmacy continue operating?"
3. "Why do you think rural pharmacies in India struggle to adopt digital systems? What solutions could work?"

---

## 📝 Assignment
Look up the **ABHA (Ayushman Bharat Health Account)** on the official website: abdm.gov.in
Answer these 3 questions (5 lines each):
1. What is the ABHA number and how do you create one?
2. What types of health records can be linked to ABHA?
3. How will ABHA change a pharmacist's daily work in the future?
