# Experiment 12
## Exporting Tables, Queries, Forms and Reports to XML Pages

**Software Used:** LibreOffice Base + LibreOffice Calc — *replaces MS Access*

---

## 🎯 Objective

To export data from LibreOffice Base (Tables and Queries) into XML format — producing structured, software-independent data files suitable for sharing with other healthcare systems.

---

## 🧠 Why This Experiment Matters

This connects directly to your **Unit IV — Day 4: Complete XML Guide**. While MS Access has a single-click "Export to XML" feature, LibreOffice handles this slightly differently — and understanding that difference deepens your understanding of what XML export actually does at a technical level (since you're doing a couple of the steps manually that Access automates).

> 💬 **Key Difference from MS Access:** MS Access exports a table directly to `.xml` (plus an optional `.xsd` schema file) with one right-click menu option. **LibreOffice Calc** has a **native, direct "XML Source"** import feature, but for straightforward table-to-XML *export*, the most reliable method available in standard LibreOffice is:
> 1. Save your table/query data as a `.csv` or `.ods` file from Calc
> 2. Use **LibreOffice's "Flat XML" export filter** OR a short Python script (which you already know from Units I–III!) to convert that data into clean, custom XML
>
> This experiment shows **both** methods so you understand the full picture.

---

## 🛠️ Step-by-Step Procedure

### METHOD A: Native LibreOffice Flat XML Export

### Step 1: Open Your Existing Database
1. Open **LibreOffice Base** → open `PatientDB.odb`

### Step 2: Copy Table Data into Calc
1. Open `Patients` table in Datasheet view
2. Select all (`Ctrl + A` or click the top-left grid corner)
3. Copy (`Ctrl + C`)
4. Open **LibreOffice Calc** → paste into cell A1 (`Ctrl + V`)

### Step 3: Export as Flat XML from Calc
1. In Calc, go to **File → Save As**
2. In "File type," look for: **Flat XML ODF Spreadsheet (.fods)**
3. Filename: `Patients_FlatXML_Export.fods`
4. Click **Save**

### Step 4: Inspect the Output
1. Open `Patients_FlatXML_Export.fods` in a text editor (VS Code)
2. You'll see this is a complete, well-formed XML document — every cell of your spreadsheet is represented as a structured XML element (following the OpenDocument XML schema)
3. Notice the strict XML rules from your Day 4 XML guide are all followed: proper nesting, closed tags, one root element

> 💬 **Important Note:** This `.fods` format is XML, but it follows LibreOffice's own internal "OpenDocument Flat XML" schema — meant for representing entire spreadsheets, not a custom simple structure like `<patient><name>...</name></patient>`. For a CLEANER, custom-structured XML (more like what a hospital system would actually use), proceed to Method B.

---

### METHOD B: Custom XML Export Using Python (Recommended — Cleaner Output)

This method uses the Python skills you already have from Units I–III, combined with your XML knowledge from Unit IV Day 4.

### Step 5: Export Table Data to CSV First
1. In **LibreOffice Base**, open the `Patients` table
2. Right-click on the table name in the left panel → **Copy**
3. Alternative simpler route: open the table in Datasheet view → select all → copy → paste into a new Calc sheet → **File → Save As → Text CSV (.csv)**
4. Filename: `patients.csv`

### Step 6: Write a Python Script to Convert CSV to Clean XML
Open **VS Code** or **Jupyter Notebook** and write:

```python
import csv
import xml.etree.ElementTree as ET

# Create root element
root = ET.Element("Patients")

# Read CSV and build XML structure
with open("patients.csv", "r") as f:
    reader = csv.DictReader(f)
    for row in reader:
        patient = ET.SubElement(root, "Patient", id=row["PatientID"])

        name = ET.SubElement(patient, "FullName")
        name.text = row["FullName"]

        age = ET.SubElement(patient, "Age")
        age.text = row["Age"]

        gender = ET.SubElement(patient, "Gender")
        gender.text = row["Gender"]

        blood = ET.SubElement(patient, "BloodGroup")
        blood.text = row["BloodGroup"]

        allergy = ET.SubElement(patient, "Allergies")
        allergy.text = row["Allergies"]

# Write to a clean XML file
tree = ET.ElementTree(root)
ET.indent(tree, space="    ")   # Pretty-print with indentation
tree.write("Patients_Custom_Export.xml", encoding="UTF-8", xml_declaration=True)

print("✅ Patients_Custom_Export.xml created successfully")
```

### Step 7: Run the Script
1. Save the script as `export_to_xml.py`
2. Make sure `patients.csv` is in the same folder
3. Run it:
```bash
python export_to_xml.py
```

### Step 8: Inspect the Clean Output

Your generated `Patients_Custom_Export.xml` should look like:

```xml
<?xml version='1.0' encoding='UTF-8'?>
<Patients>
    <Patient id="1">
        <FullName>Rahul Sharma</FullName>
        <Age>45</Age>
        <Gender>Male</Gender>
        <BloodGroup>B+</BloodGroup>
        <Allergies>Penicillin</Allergies>
    </Patient>
    <Patient id="2">
        <FullName>Priya Nair</FullName>
        <Age>32</Age>
        <Gender>Female</Gender>
        <BloodGroup>O+</BloodGroup>
        <Allergies>None</Allergies>
    </Patient>
</Patients>
```

This is exactly the kind of clean, custom, healthcare-style XML structure covered in your **Day 4 XML Guide** — far more readable and directly usable by other systems than the verbose `.fods` format from Method A.

### Step 9: Export the Invoices Table the Same Way (Practice)
Repeat Steps 5–8 for the `Invoices` table:
1. Export `Invoices` table → `invoices.csv`
2. Modify the Python script: change root tag to `Invoices`, child tag to `Invoice`, and update the field names to match (`InvoiceID`, `PatientID`, `DrugName`, `Quantity`, `TotalAmount`)
3. Run and generate `Invoices_Custom_Export.xml`

### Step 10: Validate the XML is Well-Formed
1. Open both exported `.xml` files in a web browser (drag and drop the file into Chrome/Firefox)
2. If the browser displays a clean, collapsible tree view of your data with no error message, your XML is well-formed
3. If there's a red error message, recheck your Python script's tag names and quoting

---

## ✅ Expected Output

Two outputs demonstrating XML export:
1. A native LibreOffice Flat XML (`.fods`) file showing the built-in spreadsheet export method
2. A clean, custom-structured `.xml` file (via Python) representing patient records in a healthcare-appropriate format — directly connecting your database, Python, and XML knowledge

---

## 📝 Viva/Record Questions

1. Why doesn't LibreOffice have a single-click "Export Table to Custom XML" button the way MS Access does?
2. What is the practical difference between the `.fods` output (Method A) and the custom Python-generated XML (Method B)?
3. In the Python script, what does `ET.SubElement(patient, "FullName")` actually do?
4. Why is validating that your XML is "well-formed" an important final step before sharing it with another system?

---

## 🔁 Practice Variation

Extend the Python script to also generate an accompanying `.xsd` schema file (refer to your Day 4 XML Guide, Section 5.3) that restricts `Age` to a sensible range (0–120) and `BloodGroup` to only the 8 valid blood group values.
