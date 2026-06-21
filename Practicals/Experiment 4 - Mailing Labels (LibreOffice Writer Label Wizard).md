# Experiment 4
## Creating Mailing Labels Using Label Wizard, Generating Labels

**Software Used:** LibreOffice Writer (Label Wizard) — *replaces MS Word Label Wizard*

---

## 🎯 Objective

To use the Label Wizard feature in LibreOffice Writer to generate a printable sheet of mailing labels — useful for patient address labels, drug courier labels, or pharmacy mailing campaigns.

---

## 🧠 Why This Experiment Matters

Pharmacies and hospital dispatch departments regularly mail medicines, reports, and reminders to patients. Generating dozens or hundreds of address labels by hand is impractical — the Label Wizard automates this by printing the same (or varying) label content across an entire sheet, formatted for standard label sheets.

> 💬 **Key Difference from MS Word:** In MS Word, this feature is called "Labels" under the Mailings tab. In **LibreOffice Writer**, the equivalent is found under **File → New → Labels**. The workflow concept is identical; only the menu location and exact dialog names differ.

---

## 🛠️ Step-by-Step Procedure

### Step 1: Open the Label Wizard
1. Open **LibreOffice Writer**
2. Go to **File → New → Labels...**
3. The "Labels" dialog box opens

### Step 2: Set Up Label Format (Options Tab)
1. In the dialog, go to the **Labels** tab
2. Under **Brand**, select a standard brand (e.g., "Avery Letter Size" or any available)
3. Under **Type**, choose a label size that matches your printer's label sheet (e.g., a standard address label format — commonly 2.625" x 1" or similar, depending on availability)
4. If you don't have physical label sheets, you can still continue — we are creating a printable layout for educational/practice purposes

### Step 3: Enter the Label Content
In the same **Labels** tab, under the **Inscription** box, type the content you want repeated on every label. For a simple single-content example:

```
Aavanto Pharmacy
123 MG Road, Tirupati
Andhra Pradesh - 517501
Ph: 0877-XXXXXXX
```

### Step 4: (Optional) Use a Database for Variable Labels — Mail Merge Style
If you want **different patient names/addresses on each label** (true mailing label functionality):

1. First, ensure you have a data source — for example, a LibreOffice Calc spreadsheet with patient names and addresses, OR use the LibreOffice Base database from Experiment 5
2. In the Labels dialog, check **Synchronize Contents** (if available) and go to the **Database** dropdown
3. Select your registered database/spreadsheet as the data source
4. Click **Insert Field** to drag fields like `PatientName`, `Address`, `City` into the Inscription box instead of typing static text:
   ```
   <PatientName>
   <Address>
   <City> - <PinCode>
   ```
5. This will pull a different patient's details into each label automatically

> 💬 If this is your first time, complete Step 3 (static content) first to understand the basic layout, then attempt Step 4 (database-linked) as the advanced version.

### Step 5: Choose Layout — New Document
1. Go to the **Format** tab inside the dialog to fine-tune label dimensions if needed (width, height, spacing)
2. Click **New Document** at the bottom of the dialog

### Step 6: Review the Generated Label Sheet
- LibreOffice creates a new document — a full page table-like grid, where each cell contains your label content
- If using static content, every cell will show the same text
- If using database fields, each cell will show the next record automatically (after running mail merge)

### Step 7: Save the Label Sheet
1. **File → Save As**
2. Filename: `Pharmacy_Mailing_Labels.odt`
3. Format: **ODF Text Document (.odt)**

### Step 8: Print Preview
1. Go to **File → Print Preview** to verify alignment before actual printing
2. If using real label sheets, do a test print on plain paper first and hold it against the label sheet to verify alignment

---

## ✅ Expected Output

A new LibreOffice Writer document structured as a grid of identical (or data-merged) mailing labels, ready to print onto adhesive label sheets — suitable for patient communication mailers, drug delivery packages, or appointment reminder envelopes.

---

## 📝 Viva/Record Questions

1. Where is the Label Wizard located in LibreOffice Writer, and how does this differ from MS Word's menu location?
2. What is the purpose of "Synchronize Contents" when generating labels from a database?
3. Why would a hospital pharmacy use mailing labels instead of manually writing addresses?
4. What should you check before sending a label sheet for actual printing on adhesive label paper?

---

## 🔁 Practice Variation

Create a second label sheet using patient data fields (Name, Drug Prescribed, Refill Date) instead of address details — useful for printing **medication refill reminder labels** to attach to pill bottles or pharmacy bags.
