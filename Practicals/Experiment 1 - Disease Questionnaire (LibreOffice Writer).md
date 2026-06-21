# Experiment 1
## Design a Questionnaire Using a Word Processing Package to Gather Information About a Particular Disease

**Software Used:** LibreOffice Writer

---

## 🎯 Objective

To design a structured, printable questionnaire using LibreOffice Writer that collects relevant clinical and lifestyle information about patients for a specific disease — in this exercise, **Type 2 Diabetes Mellitus**.

---

## 🧠 Why This Experiment Matters

Before any digital system (App, Access database, website) collects patient data, healthcare workers in clinics, health camps, and community screenings still rely heavily on **printed paper questionnaires**. A pharmacist or pharmacy student must know how to design a clean, professional, and clinically useful questionnaire — asking the right questions, in the right order, in a format that's easy for both the patient and the data-entry person later.

---

## 🛠️ Step-by-Step Procedure

### Step 1: Open LibreOffice Writer
1. Open **LibreOffice Start Center**
2. Click **Writer Document** to create a new blank document

### Step 2: Set Up the Page
1. Go to **Format → Page Style**
2. Set margins: Left/Right = 2 cm, Top/Bottom = 2 cm
3. Click **OK**

### Step 3: Add the Title and Header
1. Type the title at the top: `DIABETES SCREENING QUESTIONNAIRE`
2. Select the text → Go to **Styles** dropdown (top-left) → choose **Title**
3. Center-align using `Ctrl + E`
4. Press Enter, then add a subtitle:
   `Confidential — For Clinical Use Only`
   Apply **Subtitle** style, center-aligned

### Step 4: Add Institution Details
Below the subtitle, add a simple header block:
```
Aavanto Healthcare Screening Camp
Date: __________        Screening ID: __________
```
- Use **Insert → Table** (1 row, won't be needed — just type with tab spacing or use underscores as shown)
- Make this line italic and slightly smaller font (10pt)

### Step 5: Insert a Horizontal Line
1. Place cursor below the header
2. Type three hyphens `---` and press Enter — LibreOffice auto-converts this to a horizontal line
   (Or go to **Insert → Horizontal Line**)

### Step 6: Build Section 1 — Patient Demographics
1. Type heading: `SECTION 1: PATIENT INFORMATION`
   - Apply **Heading 1** style
2. Below it, add fields using a table for clean alignment:
   - Go to **Table → Insert Table**
   - Set: Columns = 2, Rows = 6
   - Fill in as follows:

| Field | Response |
|-------|----------|
| Full Name | ___________________________ |
| Age | _______ Years |
| Gender | ☐ Male ☐ Female ☐ Other |
| Contact Number | ___________________________ |
| Address | ___________________________ |
| Occupation | ___________________________ |

3. Select the table → **Table → Properties** → remove borders if you want a cleaner look, or keep light borders for printing clarity

### Step 7: Build Section 2 — Disease-Specific Questions (Diabetes)
1. New heading: `SECTION 2: DIABETES RISK ASSESSMENT`
2. Use **numbered list** (Toolbar → Ordered List icon) for each question:

```
1. Do you have a family history of diabetes (parents/siblings)?
   ☐ Yes    ☐ No    ☐ Not Sure

2. Do you experience frequent thirst or dry mouth?
   ☐ Yes    ☐ No

3. Do you urinate more frequently than usual, especially at night?
   ☐ Yes    ☐ No

4. Have you experienced unexplained weight loss in the last 6 months?
   ☐ Yes    ☐ No

5. Do you feel unusually tired or fatigued during the day?
   ☐ Yes    ☐ No

6. Do you have blurred vision?
   ☐ Yes    ☐ No

7. Do you have slow-healing wounds or frequent skin infections?
   ☐ Yes    ☐ No

8. What is your current waist circumference (if known)? _______ cm

9. Do you engage in regular physical activity (30 mins, 5 days/week)?
   ☐ Yes    ☐ No

10. Fasting Blood Glucose level (if known): _______ mg/dL
```

> 💬 To insert checkbox symbols (☐), go to **Insert → Special Character**, search "ballot box," and insert. You can also copy-paste once and reuse.

### Step 8: Build Section 3 — Additional Clinical Notes
```
SECTION 3: ADDITIONAL NOTES

Current Medications: _______________________________________________

Known Allergies: ____________________________________________________

Screened By: _____________________     Signature: __________________
```

### Step 9: Add a Footer
1. Go to **Insert → Header and Footer → Footer → Default Page Style**
2. Type: `Page` then **Insert → Field → Page Number** then type `of` then **Insert → Field → Page Count`
3. Add on the left: `Aavanto Healthcare — Confidential Patient Data`

### Step 10: Save the File
1. Go to **File → Save As**
2. Choose format: **ODF Text Document (.odt)** — LibreOffice's native format
3. Filename: `Diabetes_Screening_Questionnaire.odt`
4. Optionally also export as PDF: **File → Export As → Export as PDF** for easy printing/sharing

---

## ✅ Expected Output

A clean, printable, two-section (or three-section) questionnaire with:
- Clear title and institutional header
- A patient demographics table
- A numbered, checkbox-style disease risk assessment
- A notes/signature section
- Page numbering in the footer

---

## 📝 Viva/Record Questions

1. Why is patient demographic data collected separately from disease-specific questions?
2. Why are checkboxes preferred over open-ended text for risk-factor questions?
3. What is the difference between saving as `.odt` and exporting as `.pdf`?
4. Why is a "Screened By" and signature field important in a clinical questionnaire?

---

## 🔁 Practice Variation

Repeat this entire experiment to design a questionnaire for a **different disease** of your choice — Hypertension, Asthma, or Tuberculosis — using the same structured approach (Demographics → Risk Factors → Notes).
