# Unit I – Day 1 (2 Hours)
## Introduction to Artificial Intelligence & Healthcare Applications

---

## 🎯 Session Goals
By the end of this session, students will be able to:
- Define Artificial Intelligence and explain its core concepts clearly
- Distinguish between types of AI with real-world examples
- Explain how AI is applied in healthcare, pharmacy, and drug discovery
- Describe what Clinical Decision Support Systems are and how they work
- Identify digital healthcare innovations powered by AI

---

## ⏱️ Session Plan (2 Hours)

| Time | Topic |
|------|-------|
| 0:00 – 0:05 | Welcome, attendance, session overview |
| 0:05 – 0:35 | What is AI? — History, concepts, types |
| 0:35 – 0:55 | How machines learn — ML, Deep Learning, NLP |
| 0:55 – 1:15 | AI in Healthcare & Pharmacy — applications in depth |
| 1:15 – 1:35 | AI-Assisted Drug Discovery — detailed walkthrough |
| 1:35 – 1:50 | Clinical Decision Support Systems — how they work |
| 1:50 – 2:00 | Digital Health Innovations + Recap + Q&A |

---

---

# SECTION 1 — What is Artificial Intelligence?
## (0:05 – 0:35 | 30 minutes)

---

## 1.1 Definition

> **Artificial Intelligence (AI)** is the branch of computer science focused on building machines that can perform tasks that normally require human intelligence — such as understanding language, recognizing patterns, making decisions, and learning from experience.

The word "Artificial" means man-made. The word "Intelligence" means the ability to acquire knowledge and use it. So AI = man-made intelligence embedded into machines.

---

## 1.2 A Brief History of AI

Understanding where AI came from helps us appreciate what it is today.

| Year | Milestone |
|------|-----------|
| **1950** | Alan Turing proposes the "Turing Test" — can a machine think like a human? |
| **1956** | Term "Artificial Intelligence" coined at Dartmouth Conference |
| **1960s–70s** | Rule-based expert systems — AI given explicit rules to follow |
| **1980s** | AI winter — progress slows, funding dries up |
| **1997** | IBM Deep Blue defeats chess world champion Garry Kasparov |
| **2011** | IBM Watson wins Jeopardy! against human champions |
| **2012** | Deep Learning revolution — ImageNet breakthrough |
| **2016** | AlphaGo defeats world champion Go player — considered impossible before |
| **2020** | AlphaFold solves protein structure prediction — 50-year biological problem |
| **2022** | ChatGPT launched — AI becomes mainstream globally |
| **2023–present** | AI in every field — healthcare, law, education, pharmacy, drug discovery |

> 💬 **Say to class:** "AI is not new — it started in the 1950s. But in the last 10 years, the speed of progress has been extraordinary. The AI tools you use today — ChatGPT, Google Search, YouTube recommendations — are the result of 70 years of research."

---

## 1.3 Core Concepts of AI

AI systems are built on three foundational abilities:

### a) Learning
The machine learns from data — just like how you learned to recognize a mango by seeing many mangoes.

- Example: Show an AI system 10,000 X-rays labelled "normal" or "tumour" → it learns to identify tumours in new X-rays.

### b) Reasoning
Using what it has learned to draw logical conclusions.

- Example: "This X-ray has these features → this matches the patterns I learned → likely a tumour in stage 2."

### c) Self-Correction
When the AI makes a wrong prediction, it adjusts its internal parameters to do better next time. This is called **backpropagation** in neural networks.

- Example: AI predicted "normal" for an X-ray that was actually cancerous. It receives this correction, adjusts its weights, and becomes more accurate.

---

## 1.4 Types of AI

### Classification 1: By Capability

| Type | Description | Current Status | Example |
|------|-------------|----------------|---------|
| **Narrow AI (ANI)** | Does one specific task very well | EXISTS TODAY | ChatGPT, Google Translate, Siri, AlphaFold |
| **General AI (AGI)** | Can do any intellectual task a human can | DOES NOT EXIST | Fictional AI like in movies |
| **Super AI (ASI)** | Far surpasses human intelligence in every domain | DOES NOT EXIST | Science fiction only |

> 💬 **Important:** "Every AI application in healthcare today is Narrow AI. It is very good at one specific task — reading X-rays, predicting drug interactions — but it cannot do anything outside its training. A hospital AI that reads chest X-rays cannot answer questions about blood tests. Each system is specialized."

---

### Classification 2: By Function

| Type | What it does | Healthcare Example |
|------|-------------|-------------------|
| **Reactive Machines** | Responds to current input only; no memory | Simple drug interaction checker |
| **Limited Memory AI** | Uses recent data to make decisions | AI that reads current patient vitals to alert nurses |
| **Theory of Mind AI** | Understands emotions and context (in research) | Empathetic chatbot for mental health support |
| **Self-Aware AI** | Has consciousness (does not exist) | Science fiction |

---

## 1.5 Branches of AI — What Powers It

AI is not just one thing. It has several sub-fields:

```
Artificial Intelligence
├── Machine Learning (ML)
│     ├── Supervised Learning
│     ├── Unsupervised Learning
│     └── Reinforcement Learning
│
├── Deep Learning (DL)
│     └── Neural Networks
│
├── Natural Language Processing (NLP)
│     ├── Text analysis
│     └── Speech recognition
│
├── Computer Vision
│     ├── Image recognition
│     └── Medical imaging analysis
│
└── Robotics
      └── Surgical robots
```

> 💬 "Don't worry — we will not go deep into all of these today. But knowing these names helps you read research papers and news articles about AI in pharmacy intelligently."

---

---

# SECTION 2 — How Machines Learn
## (0:35 – 0:55 | 20 minutes)

---

## 2.1 Machine Learning (ML)

> **Machine Learning** is the ability of computers to learn from data without being explicitly programmed with rules.

### Traditional Programming vs Machine Learning

```
TRADITIONAL PROGRAMMING:
Input Data + Rules → Computer → Output

MACHINE LEARNING:
Input Data + Output (labels) → Computer → Discovers the Rules itself
```

**Example in Pharmacy:**

Traditional: Programmer manually writes: "If glucose > 126, flag as diabetic."

ML approach: Feed 50,000 patient records (with age, weight, glucose, BP, etc.) and their diagnoses → ML model learns on its own which combinations of factors predict diabetes.

The ML model may discover subtle patterns — like a specific combination of borderline glucose + high BMI + family history — that a human rule-writer would miss.

---

### Types of Machine Learning

**a) Supervised Learning** — Most common in healthcare
- Training data has inputs AND correct labels
- Example: 10,000 chest X-rays labelled "Pneumonia" / "Normal" → model learns to classify new X-rays
- Used for: disease diagnosis, drug response prediction

**b) Unsupervised Learning** — Finding hidden patterns
- Training data has inputs only — no labels
- Machine groups similar data together on its own
- Example: Group 1,000 patients by their lab patterns — AI may discover 3 subtypes of diabetes not previously recognized
- Used for: patient segmentation, drug repurposing

**c) Reinforcement Learning** — Learning by trial and error
- AI takes actions, receives rewards or penalties, learns to maximize reward
- Example: AI learns optimal drug dosing by simulating patient responses over millions of virtual scenarios
- Used for: dosing optimization, robotic surgery training

---

## 2.2 Deep Learning & Neural Networks

> **Deep Learning** is a type of ML that uses **neural networks** — structures inspired by the human brain — to process data through many layers.

### How a Neural Network Works

```
INPUT LAYER          HIDDEN LAYERS           OUTPUT LAYER
(Patient data)       (Pattern detection)     (Prediction)

Age ──────────┐
Glucose ──────┤──► [Layer 1] ──► [Layer 2] ──► [Layer 3] ──► "Diabetic / Normal"
BP ───────────┤
BMI ──────────┘
```

Each layer learns increasingly complex patterns:
- Layer 1: basic patterns (is glucose high?)
- Layer 2: combinations (high glucose + high BMI together?)
- Layer 3: complex interactions (age + genetics + drug history?)

> 💬 "Deep Learning is why AI can now read MRI scans better than radiologists for certain tumour types. The layers process the image like a human eye-to-brain pathway."

---

## 2.3 Natural Language Processing (NLP)

> **NLP** is AI's ability to read, understand, and generate human language — text and speech.

### NLP in Pharmacy & Healthcare

| Application | How NLP is used |
|-------------|----------------|
| Prescription reading | NLP reads handwritten doctor prescriptions, converts to digital |
| Drug literature | NLP scans millions of research papers, extracts drug-drug interaction data |
| Patient records | NLP reads clinical notes, extracts diagnoses and medication lists automatically |
| Chatbots | Patient symptom checkers, appointment booking |
| Adverse event detection | NLP scans social media and patient reviews for unreported drug side effects |

> 💬 Real example: **FDA Adverse Event Reporting System (FAERS)** uses NLP to scan millions of patient reports and automatically detect new side effects of approved drugs.

---

---

# SECTION 3 — AI in Healthcare & Pharmacy
## (0:55 – 1:15 | 20 minutes)

---

## 3.1 Medical Imaging — AI as a Radiologist's Assistant

Medical imaging is one of the most advanced AI applications in healthcare today.

### What AI Can Read

| Scan Type | What AI Detects |
|-----------|----------------|
| Chest X-ray | Pneumonia, tuberculosis, COVID-19, lung cancer |
| MRI (Brain) | Stroke, tumours, Alzheimer's changes |
| CT Scan | Internal bleeding, organ damage |
| Retinal Scan | Diabetic retinopathy, glaucoma, macular degeneration |
| Mammogram | Breast cancer, early-stage microcalcifications |
| Skin photos | Melanoma vs benign skin lesion |

### How it Works — Step by Step

```
Doctor orders scan
        ↓
Patient undergoes X-ray / MRI / CT
        ↓
Image sent to AI system
        ↓
AI compares image against millions of training images
        ↓
AI highlights suspicious areas (e.g., nodule in lung)
        ↓
AI gives probability: "87% probability of malignancy"
        ↓
Radiologist reviews AI output + makes final call
        ↓
Report sent to doctor
```

### Real-World Results
- **Google Health AI** — Detected breast cancer from mammograms with fewer false positives than human radiologists alone (published in Nature, 2020)
- **DeepMind Moorfields Eye Hospital** — AI detected 50+ eye diseases from retinal scans with accuracy matching expert ophthalmologists
- **qure.ai (India)** — AI reads chest X-rays for TB detection; deployed across public hospitals in India including Telangana and Andhra Pradesh

> 💬 **Local relevance:** "qure.ai is an Indian company whose AI is used in government hospitals in our state to screen for TB. This is AI in pharmacy and healthcare — right here."

---

## 3.2 Personalized Medicine

> **Personalized Medicine** (also called Precision Medicine) means giving the right drug, at the right dose, to the right patient, at the right time — based on their individual biology.

### Why One Drug Doesn't Work the Same for Everyone

Two patients with the same diagnosis may respond very differently to the same drug. Reasons include:
- **Genetics** — Some people metabolize drugs faster/slower due to gene variants (pharmacogenomics)
- **Age** — Elderly patients may process drugs differently
- **Kidney/Liver function** — Affects drug clearance
- **Body weight** — Affects drug distribution
- **Other medications** — Drug-drug interactions

### How AI Enables Personalized Medicine

```
Patient's genetic data (DNA sequencing)
        +
Medical history (diagnoses, previous drugs)
        +
Lab results (liver enzymes, kidney function)
        +
Current vitals
        ↓
AI Model
        ↓
Personalized recommendation:
"For this patient's CYP2D6 gene variant, standard codeine dose
will not metabolize properly — recommend tramadol instead at X mg"
```

### Pharmacogenomics — The Genetics of Drug Response

| Gene | Drug Affected | AI Application |
|------|--------------|----------------|
| CYP2D6 | Codeine, antidepressants | Predicts if patient is poor/fast metabolizer |
| BRCA1/2 | Chemotherapy drugs | Predicts cancer drug response |
| HER2 | Trastuzumab (Herceptin) | Only works in HER2-positive breast cancer |
| TPMT | Azathioprine | Predicts toxicity risk |

> 💬 "In the future, before a pharmacist dispenses any drug, they may first check the patient's genetic profile. AI will interpret that profile and flag if a standard dose is dangerous for that individual. This is already happening in some hospitals in the US."

---

## 3.3 AI in Pharmacy — Specific Applications

### a) Automated Prescription Verification
- AI reads digital prescriptions
- Checks: correct drug name, appropriate dose for age/weight, potential interactions, patient allergy history
- Flags issues before the pharmacist even sees the prescription
- Reduces human error significantly

### b) Drug Interaction Checking
- A patient may be on 5–10 drugs simultaneously (polypharmacy)
- AI cross-references all drugs against a database of millions of known interactions
- Classifies: Contraindicated / Major / Moderate / Minor interaction
- Generates alert for pharmacist to review

### c) Inventory Management
- AI predicts which drugs will run low based on:
  - Seasonal patterns (more cough syrups in winter)
  - Disease outbreaks in the region
  - Historical dispensing data
- Automatically places reorder alerts before stock runs out
- Reduces wastage by predicting expiry risk

### d) Medication Adherence Monitoring
- AI-powered apps remind patients to take medications
- Smart pill bottles detect if the lid was opened
- If patient misses doses, pharmacist or doctor is alerted
- Especially important for chronic conditions: diabetes, hypertension, TB

### e) Robotic Dispensing in Hospital Pharmacies
- Large hospital pharmacies use robotic systems
- Robot receives digital prescription → picks correct drug → labels it → sends to nurse station
- AI reduces dispensing errors to near-zero
- Example: **Omnicell** and **BD Pyxis** systems used in hospitals globally

---

---

# SECTION 4 — AI-Assisted Drug Discovery
## (1:15 – 1:35 | 20 minutes)

---

## 4.1 The Problem with Traditional Drug Discovery

Before AI, discovering and bringing a new drug to market was:
- **Time:** 10 to 15 years
- **Cost:** $2.6 billion on average
- **Success rate:** Only 1 in 10,000 screened compounds becomes an approved drug
- **Failure:** 90% of drugs that enter clinical trials still fail

The pharmaceutical industry desperately needed a faster, smarter way.

---

## 4.2 Where AI Steps In — The Drug Discovery Pipeline

```
STEP 1: TARGET IDENTIFICATION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
What: Find the biological target (protein/enzyme) responsible for a disease
Traditional: Years of basic research
AI Method: ML analyses genomic + proteomic data to identify disease-linked targets rapidly

STEP 2: HIT IDENTIFICATION
━━━━━━━━━━━━━━━━━━━━━━━━━━
What: Find molecules that interact with the target
Traditional: Physical screening of chemical libraries (months-years)
AI Method: Virtual screening — AI evaluates millions of molecules computationally in days

STEP 3: LEAD OPTIMIZATION
━━━━━━━━━━━━━━━━━━━━━━━━━
What: Modify the hit compound to improve efficacy, reduce toxicity
Traditional: Chemists manually modify and test — slow
AI Method: Generative AI designs new molecular structures with desired properties

STEP 4: PRECLINICAL TESTING
━━━━━━━━━━━━━━━━━━━━━━━━━━
What: Test in cell cultures and animals
AI Method: AI predicts toxicity from molecular structure — reduces animal testing

STEP 5: CLINICAL TRIALS (Phase I, II, III)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
AI Method: AI designs optimal trial protocols, identifies ideal patient populations,
           predicts trial outcomes, monitors safety signals in real-time

STEP 6: REGULATORY APPROVAL
━━━━━━━━━━━━━━━━━━━━━━━━━━━
AI assists in preparing submission documents, analyzing trial data
```

---

## 4.3 AlphaFold — The Biggest Breakthrough

### The Problem
Every drug works by binding to a specific protein in the body. To design a drug, scientists need to know the exact 3D shape of that protein. Determining this shape (protein structure) was one of biology's hardest problems.

The "protein folding problem" was unsolved for **50 years**.

### What AlphaFold Did
- DeepMind's AI system **AlphaFold** was trained on all known protein structures
- In 2020, it predicted the 3D structures of almost **every known protein** — 200 million proteins
- Accuracy matched experimental methods that take months in a lab
- The entire database was made free and open to researchers worldwide

### Impact on Pharmacy
- Researchers can now design drugs that precisely fit a protein target
- Drug discovery timelines shortened dramatically
- Diseases that had no druggable target now have candidates
- Malaria, tuberculosis, neglected tropical diseases now have new research leads

> 💬 "AlphaFold is considered one of the greatest scientific achievements of the 21st century. It was done by an AI system, not a human researcher. And it directly benefits pharmaceutical sciences — the field you are studying."

---

## 4.4 Real AI Drug Discovery Success Stories

### 1. COVID-19 Vaccine Development
- BioNTech/Pfizer used AI to design and optimize the mRNA sequence for their COVID-19 vaccine
- AI helped predict which sequences would produce the strongest immune response
- Traditional vaccine development: 5–15 years. COVID vaccine: under 1 year.

### 2. Insilico Medicine
- Used AI to design a novel drug molecule for Idiopathic Pulmonary Fibrosis (IPF)
- The AI designed the molecule from scratch — never seen in nature before
- From concept to clinical trial candidate: 18 months (normally 5–6 years)

### 3. Drug Repurposing
- AI scans existing approved drugs and matches them against new disease targets
- Example: During COVID-19, AI identified existing drugs (like Baricitinib — an arthritis drug) as potential COVID treatments
- Repurposing is faster because safety testing is already done

---

---

# SECTION 5 — Clinical Decision Support Systems (CDSS)
## (1:35 – 1:50 | 15 minutes)

---

## 5.1 What is a CDSS?

> A **Clinical Decision Support System (CDSS)** is a health information technology system designed to assist clinicians and pharmacists in making clinical decisions by providing relevant, organized information at the point of care.

Key principle: **AI provides information. The human makes the final decision.**

---

## 5.2 How a CDSS Works — Detailed Flow

```
┌─────────────────────────────────────────┐
│           PATIENT DATA INPUT            │
│  Demographics, vitals, lab results,     │
│  diagnosis, current medications,        │
│  allergy history, genetic profile       │
└───────────────────┬─────────────────────┘
                    │
                    ▼
┌─────────────────────────────────────────┐
│           KNOWLEDGE BASE                │
│  Drug database, clinical guidelines,   │
│  interaction rules, dosing protocols,  │
│  contraindication lists                │
└───────────────────┬─────────────────────┘
                    │
                    ▼
┌─────────────────────────────────────────┐
│           AI INFERENCE ENGINE           │
│  Matches patient data against           │
│  knowledge base, applies ML models,    │
│  generates ranked recommendations      │
└───────────────────┬─────────────────────┘
                    │
                    ▼
┌─────────────────────────────────────────┐
│           ALERT / RECOMMENDATION        │
│  "⚠️ Drug-Drug Interaction: Warfarin +  │
│   Aspirin — High Bleeding Risk"        │
│  "✅ Dose appropriate for patient age"  │
│  "📋 Consider dose reduction — CKD"    │
└───────────────────┬─────────────────────┘
                    │
                    ▼
┌─────────────────────────────────────────┐
│        PHARMACIST / DOCTOR REVIEWS      │
│        Makes Final Clinical Decision    │
└─────────────────────────────────────────┘
```

---

## 5.3 Types of CDSS Alerts in Pharmacy

### 1. Drug-Drug Interaction (DDI) Alerts
- Patient is prescribed Warfarin (blood thinner) + Aspirin (pain relief)
- CDSS flags: "MAJOR INTERACTION — Combined use significantly increases bleeding risk"
- Pharmacist reviews and either counsels patient or contacts prescribing doctor

### 2. Drug-Allergy Alerts
- Patient's record shows allergy to Penicillin
- Doctor prescribes Amoxicillin (a type of Penicillin)
- CDSS flags: "⚠️ ALLERGY ALERT — Patient has documented Penicillin allergy"

### 3. Dose Range Checking
- Doctor prescribes Paracetamol 2000mg 4 times daily = 8000mg/day
- Standard max daily dose = 4000mg
- CDSS flags: "OVERDOSE ALERT — Prescribed dose exceeds maximum safe daily limit"

### 4. Renal/Hepatic Dose Adjustment
- Patient has chronic kidney disease (CKD Stage 3)
- Standard Metformin dose prescribed
- CDSS flags: "DOSE ADJUSTMENT REQUIRED — Metformin is contraindicated in CKD Stage 3+ due to lactic acidosis risk"

### 5. Duplicate Therapy
- Patient is already on Omeprazole 20mg
- Doctor prescribes Pantoprazole 40mg (another PPI)
- CDSS flags: "DUPLICATE THERAPY — Patient already receiving a proton pump inhibitor"

---

## 5.4 Famous CDSS Systems

| System | Used For |
|--------|---------|
| **IBM Watson for Oncology** | Cancer treatment recommendations based on patient profile + medical literature |
| **Epic CDS** | Drug interaction, allergy, dose alerts embedded in Epic EHR |
| **Cerner PowerChart** | Clinical decision support integrated into hospital workflows |
| **Theradoc** | Antimicrobial stewardship — AI recommends correct antibiotics |
| **Dosis** | AI-powered dosing for ICU patients |

---

## 5.5 Limitations of CDSS — Alert Fatigue

> **Alert Fatigue** = When CDSS generates too many alerts, clinicians start ignoring them — even important ones.

Studies show that in some hospitals, pharmacists override **80–90% of drug alerts** — many of which are low-priority.

**AI Solution:** Modern CDSS systems use ML to prioritize alerts — showing only the most clinically significant ones prominently, reducing noise. This is itself an AI problem being solved by AI.

> 💬 "This is a good lesson: even a helpful AI system can create new problems. Good design matters as much as good algorithms."

---

---

# SECTION 6 — Digital Healthcare Innovations
## (1:50 – 2:00 | 10 minutes — brief overview + recap)

---

## 6.1 Key Digital Health Technologies

### Wearables & Continuous Monitoring
- **Apple Watch / Samsung Galaxy Watch** — Heart rate, blood oxygen (SpO2), ECG, fall detection
- **Continuous Glucose Monitors (CGM)** — e.g., FreeStyle Libre, Dexterity — measure glucose every few minutes without blood pricks
- AI analyses trends in this continuous data: "Patient's glucose has been rising for 3 hours — insulin may be needed"
- Pharmacists can monitor patients remotely using this data

### Telemedicine
- Video consultations replacing in-person visits for routine follow-ups
- AI triage systems assess patient symptoms before the consultation
- Platforms: Practo, Apollo 24|7, eSanjeevani (Government of India)
- Pharmacists participate in teleconsultation, dispensing based on digital prescriptions

### AI Chatbots for Healthcare
- **Ada Health** — Symptom checker chatbot used by 11 million people
- **Babylon Health** — AI doctor chatbot for UK NHS
- Patient describes symptoms → AI asks follow-up questions → provides triage recommendation
- Limitation: Cannot replace diagnosis — these tools direct patients to appropriate care

### NLP for Prescription Reading
- Handwritten prescriptions are a major source of dispensing errors in India
- NLP systems trained on doctor handwriting can digitize prescriptions automatically
- Reduces misreading of drug names, doses, and frequencies

### India-Specific Initiatives
| Initiative | What it Does |
|------------|-------------|
| **ABHA (Ayushman Bharat Health Account)** | National Health ID — links all health records digitally |
| **eSanjeevani** | Government telemedicine platform — 200 million consultations |
| **CoWIN** | AI-driven COVID-19 vaccination management for 1.4 billion people |
| **NPPA Drug Price Monitor** | AI monitors drug pricing across India's market |

---

## 🧠 Full Session Key Takeaways

1. **AI = machine simulation of human intelligence** — learning, reasoning, self-correction
2. **Three levels:** Narrow AI (exists), General AI (doesn't exist), Super AI (doesn't exist)
3. **ML learns from data; Deep Learning uses neural networks; NLP understands language**
4. **Medical imaging** — AI reads X-rays, MRI, retinal scans at expert-level accuracy
5. **Personalized medicine** — AI + genomics = right drug for the right patient
6. **Drug discovery** — AI reduces 15-year timelines; AlphaFold solved a 50-year problem
7. **CDSS** — AI assists pharmacists and doctors; humans always make the final decision
8. **Alert fatigue** is a real problem; good AI design matters as much as the algorithm
9. **India is actively deploying AI** in healthcare — ABHA, eSanjeevani, qure.ai, CoWIN
10. **AI assists. It does not replace.** Pharmacists with AI skills are more valuable than those without.

---

## ❓ Discussion Questions (use remaining time)

1. "A patient comes to your pharmacy with 8 prescriptions from 3 different doctors. The CDSS flags a major drug interaction. What do you do?"
2. "If AI can read X-rays as accurately as a radiologist — should hospitals stop hiring radiologists? Why or why not?"
3. "Would you trust an AI chatbot to tell you whether you have diabetes? What would you want to verify?"

---

## 📝 Assignment for Next Class
Pick **ONE** of the following and write a one-page note (200–250 words):
- How AlphaFold changed drug discovery (search: "AlphaFold DeepMind impact")
- How AI is used in an Indian hospital (search: "AI healthcare India qure.ai" or "Apollo AI")
- One example of a CDSS alert that could have saved a patient's life (search: "clinical decision support case study")

Come prepared to share your findings in the next session.
