# Experiment 7
## Generate and Print Reports from the Patient Database

**Software Used:** LibreOffice Base — *replaces MS Access*

---

## 🎯 Objective

To generate a formatted, printable report from the `Patients` table — grouping, sorting, and presenting patient data in a professional document layout suitable for hospital records or hand-off to administration.

---

## 🧠 Why This Experiment Matters

Raw database tables are great for storage and search but terrible for printing or sharing with non-technical staff (like hospital administrators or auditors). A **Report** transforms structured data into a clean, formatted, print-ready document — similar to how a pharmacy might generate a "Daily Patient Registration Report" to file or hand to a supervisor.

> 💬 **Key Difference from MS Access:** Access has a built-in Report Wizard accessible from the Create tab. LibreOffice Base's reporting tool is functionally similar but works through **Reports → Use Wizard to Create Report**, and for advanced formatting, it may prompt you to use the **Oracle Report Builder extension** if it's not already installed. The basic Wizard (used in this experiment) works out of the box with no extra installation.

---

## 🛠️ Step-by-Step Procedure

### Step 1: Open Your Existing Database
1. Open **LibreOffice Base**
2. Open `PatientDB.odb`

### Step 2: Navigate to Reports
1. In the left panel, click **Reports**
2. Click **Use Wizard to Create Report...**

### Step 3: Select Fields (Step 1 of Wizard)
1. Under "Tables or Queries," select `Patients`
2. From **Available Fields**, select the fields you want in the report. For a registration report, choose:
   - `FullName`
   - `Age`
   - `Gender`
   - `BloodGroup`
   - `ContactNumber`
   - `RegistrationDate`
3. Click **>>** or move them individually with **>**
4. Click **Next**

### Step 4: Set Labels (Step 2)
1. You can rename the column headers shown on the report (e.g., change `FullName` label to "Patient Name")
2. Click **Next**

### Step 5: Grouping (Step 3)
1. This step lets you group records — for example, by `Gender` or by `BloodGroup`
2. Select `Gender` and click **>** to add it as a grouping level
3. This means the report will show all **Male** patients together, then all **Female** patients together, each under its own subheading
4. Click **Next**

### Step 6: Sort Options (Step 4)
1. Within each group, choose how records should be sorted
2. Select `FullName` and set sort order to **Ascending** (A to Z)
3. Click **Next**

### Step 7: Choose Layout (Step 5)
1. Select a layout style — **Tabular** is recommended for a clean row-by-row report
2. Choose page orientation: **Landscape** (recommended if you have many columns, to avoid cramped text)
3. Click **Next**

### Step 8: Name and Finish (Step 6)
1. Title the report: `Patient_Registration_Report`
2. Choose: **Dynamic Report** — this means the report automatically refreshes with the latest data from the table every time you open it (recommended over "Static Report," which freezes the data at creation time)
3. Click **Finish**

### Step 9: Review the Generated Report
- LibreOffice Base generates and opens the report, showing:
  - A title at the top
  - Patients grouped by Gender (e.g., "Female" section, then "Male" section)
  - Within each group, names sorted A–Z
  - Column headers matching your renamed labels

### Step 10: Export the Report as PDF (For Printing/Sharing)
1. With the report open, go to **File → Export As → Export as PDF**
2. Choose a filename: `Patient_Registration_Report.pdf`
3. Click **Export**

### Step 11: Print the Report (If a Printer is Available)
1. Go to **File → Print**
2. Select your printer
3. Preview the layout in **Print Preview** first to check that columns are not cut off
4. Click **Print**

### Step 12: Save the Report Definition
1. Close the report preview window
2. The report definition (`Patient_Registration_Report`) is automatically saved inside `PatientDB.odb`, listed under **Reports**
3. You can re-open and re-generate it anytime — it will reflect any new patients added since

---

## ✅ Expected Output

A professionally formatted, exportable, and printable report titled **Patient_Registration_Report**, showing all patients grouped by Gender and sorted alphabetically by name, with a corresponding PDF export for sharing or filing.

---

## 📝 Viva/Record Questions

1. What is the difference between a Form and a Report in a database system?
2. Why is grouping by `Gender` or `BloodGroup` useful in a hospital report?
3. What is the benefit of choosing "Dynamic Report" instead of "Static Report"?
4. Why would a hospital export a report to PDF rather than just sharing the live database file?

---

## 🔁 Practice Variation

Create a second report grouped by `BloodGroup` instead of `Gender` — useful for a blood bank or emergency department wanting a quick reference of which patients share a given blood type.
