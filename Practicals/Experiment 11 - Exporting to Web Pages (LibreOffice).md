# Experiment 11
## Exporting Tables, Queries, Forms and Reports to Web Pages

**Software Used:** LibreOffice Base + LibreOffice Calc — *replaces MS Access*

---

## 🎯 Objective

To export data from LibreOffice Base (Tables, Queries) and a Report into HTML web page format, making pharmacy and patient data viewable in any standard web browser.

---

## 🧠 Why This Experiment Matters

Sometimes hospital data needs to be shared with someone who doesn't have LibreOffice Base installed at all — a doctor checking a quick patient list on a shared computer, or a report uploaded to an internal hospital intranet page. Exporting to HTML produces a universally viewable file that opens in any browser, on any device, with zero special software required.

> 💬 **Key Difference from MS Access:** MS Access has a direct "Export → HTML Document" option for tables, queries, forms, and reports individually. **LibreOffice Base does not have a single direct "export to HTML" button for tables/queries** the same way Access does. Instead, the standard LibreOffice workflow is:
> 1. Open the table/query results in **LibreOffice Calc** (spreadsheet), OR copy the data there
> 2. Use Calc's **Save As → HTML Document** feature, which IS a direct, built-in export option
>
> This experiment walks through that exact equivalent workflow.

---

## 🛠️ Step-by-Step Procedure

### Step 1: Open Your Existing Database
1. Open **LibreOffice Base**
2. Open `PatientDB.odb`

### Step 2: Export a Table to HTML (via Calc)

**Step 2a — Copy table data:**
1. Click **Tables** → double-click `Patients` to open Datasheet view
2. Click the small grey box at the top-left corner of the grid (selects the entire table)
3. Press `Ctrl + C` to copy

**Step 2b — Paste into Calc:**
1. Open **LibreOffice Calc** (a new blank spreadsheet)
2. Click cell A1
3. Press `Ctrl + V` to paste — your full patient table now appears as a spreadsheet

**Step 2c — Export as HTML:**
1. In Calc, go to **File → Save As**
2. In "File type," choose **HTML Document (.html)**
3. Filename: `Patients_Table_Export.html`
4. Click **Save**
5. A dialog may appear about losing some formatting — click **Use HTML Document Format!**

**Step 2d — Verify the Output:**
1. Navigate to where you saved the file
2. Double-click `Patients_Table_Export.html`
3. It opens in your default web browser, displaying your patient data as an HTML table

### Step 3: Export a Query to HTML (Same Method)
1. Go back to **LibreOffice Base** → **Queries**
2. Double-click `Patient_Purchase_History` (created in Experiment 10) to run it
3. Select all results (`Ctrl + A` inside the results grid, or click the top-left corner box)
4. Copy (`Ctrl + C`)
5. Open a new **LibreOffice Calc** sheet → Paste (`Ctrl + V`)
6. **File → Save As → HTML Document (.html)**
7. Filename: `Patient_Purchase_History_Export.html`
8. Save, then open in browser to verify

### Step 4: Export a Report to HTML
LibreOffice Base reports can be exported more directly:

1. Go to **Reports** in the left panel
2. Right-click `Patient_Registration_Report` (created in Experiment 7)
3. Select **Open** — this generates/refreshes the report in a preview window
4. With the report open, go to **File → Export As → Export Directly as...**
   - If "Export as PDF" is the only direct option visible, instead use:
5. Go to **File → Save a Copy As** or check **File → Export As** for any HTML option present in your LibreOffice version
   - If no direct HTML export is available for reports in your version, export to **ODT** first (**File → Export As → Save as ODT**), then open that `.odt` file in LibreOffice Writer and use **File → Save As → HTML Document (.html)**

> 💬 **Why this extra step?** LibreOffice's report engine is primarily designed for print/PDF output. Routing through Writer's HTML export is the standard practical workaround used by LibreOffice users to get reports onto the web.

### Step 5: Open and Inspect the Exported HTML
1. Open `Patients_Table_Export.html` in a text editor (VS Code or Notepad) alongside viewing it in the browser
2. Notice that Calc/Writer automatically generated HTML tags like `<table>`, `<tr>`, `<td>` — connecting directly to what you learned in your HTML experiment (Experiment 2)

### Step 6: Organize Your Exported Files
Create a folder named `Web_Exports` inside your Practicals folder and move all three exported HTML files into it for easy submission:
```
Web_Exports/
├── Patients_Table_Export.html
├── Patient_Purchase_History_Export.html
└── Patient_Registration_Report_Export.html
```

---

## ✅ Expected Output

Three HTML files — one from a Table, one from a Query, and one from a Report — each viewable in any standard web browser without needing LibreOffice installed, demonstrating successful data export from the database environment to the web.

---

## 📝 Viva/Record Questions

1. Why doesn't LibreOffice Base export tables directly to HTML the same way MS Access does?
2. What role does LibreOffice Calc play in this export workflow?
3. Open the exported HTML file in a text editor — which HTML tags do you recognize from Experiment 2?
4. Why would a hospital want patient data available as a standalone HTML file instead of always requiring the database software to be open?

---

## 🔁 Practice Variation

Export the `Drugs` table to HTML and then manually edit the resulting `.html` file in a text editor to add a `<h1>` title and inline CSS styling (background colour, borders) — combining this experiment with your HTML skills from Unit IV.
