# Experiment 6
## Design a Form to View, Add, Delete, and Modify Patient Records

**Software Used:** LibreOffice Base — *replaces MS Access*

---

## 🎯 Objective

To design a user-friendly Form in LibreOffice Base that allows viewing, adding, editing, and deleting patient records from the `Patients` table created in Experiment 5 — without needing to interact with the raw table grid.

---

## 🧠 Why This Experiment Matters

In a real pharmacy or hospital, front-desk staff and pharmacists never interact directly with raw database tables — that's confusing and error-prone. They use **Forms**: clean, labelled, point-and-click interfaces designed specifically for this purpose. This experiment teaches you to build that interface layer.

> 💬 **Key Difference from MS Access:** MS Access has a one-click "Form Wizard" under the Create tab. LibreOffice Base achieves the same result via **Forms → Use Wizard to Create Form**. The resulting form's functionality (add/edit/delete/navigate records) is identical in concept.

---

## 🛠️ Step-by-Step Procedure

### Step 1: Open Your Existing Database
1. Open **LibreOffice Base**
2. Open `PatientDB.odb` (created in Experiment 5)

### Step 2: Navigate to Forms
1. In the left panel of the Base window, click **Forms**
2. Click **Use Wizard to Create Form...**

### Step 3: Select the Data Source (Step 1 of Wizard)
1. Under "Tables or Queries," select the `Patients` table from the dropdown
2. In the **Available Fields** box, you'll see all your table's fields
3. Click the **>>** button to move ALL fields into "Fields in the Form"
   (Or select individual fields and use **>** to add one at a time)
4. Click **Next**

### Step 4: Set Up a Subform (Step 2 — Skip for This Experiment)
- Since `Patients` is a single table with no related child table yet, select **No subform**
- Click **Next**

### Step 5: Arrange the Controls (Step 3)
1. Choose a layout style for how fields appear on the form:
   - **Columnar — Labels Left** is recommended (clean, easy to read)
2. Click **Next**

### Step 6: Set Data Entry Mode (Step 4)
1. Leave default: "The form is to display all data"
2. Ensure these are checked (they usually are by default):
   - ☑ New data entry possible
   - ☑ Existing data may be modified
   - ☑ Existing data may be deleted
3. Click **Next**

### Step 7: Apply Styles (Step 5)
1. Choose a border style (e.g., "3D look") and a colour scheme you like
2. Click **Next**

### Step 8: Name and Finish (Step 6)
1. Name the form: `PatientEntryForm`
2. Select **Work with the form** (so it opens immediately)
3. Click **Finish**

### Step 9: Use the Form — View Records
- The form opens showing **Record 1** with each field clearly labelled (PatientID, FullName, Age, etc.)
- Use the navigation arrows at the bottom of the form (◄ ◄| record number |► ►) to move between existing patients

### Step 10: Use the Form — Add a New Record
1. Click the **"New Record"** button (often shown as a `*` or a blank-page icon in the navigation bar at the bottom)
2. Fill in all fields for a new patient, e.g.:
   ```
   FullName: Anitha Reddy
   Age: 28
   Gender: Female
   BloodGroup: AB+
   ContactNumber: 9876523456
   Allergies: None
   ```
3. Press `Tab` to move between fields
4. Once done, click on another record or press `Ctrl + S` — LibreOffice Base saves automatically when you move off the record

### Step 11: Use the Form — Modify a Record
1. Navigate to any existing patient (e.g., Record 2 — Priya Nair)
2. Click into the `ContactNumber` field
3. Edit the number
4. Move to another record — the change saves automatically

### Step 12: Use the Form — Delete a Record
1. Navigate to the record you want to remove
2. Go to the menu: **Edit → Delete Record**
   (Or right-click the small grey row-selector tab on the left edge of the form, if visible → Delete Rows)
3. Confirm the deletion when prompted

> ⚠️ **Caution:** Deleting a record is permanent in most configurations. Always double-check the PatientID before deleting in a real-world setting.

### Step 13: Save and Close
1. Press `Ctrl + S` one final time
2. Close the form window
3. Your form `PatientEntryForm` is now saved permanently inside `PatientDB.odb`, listed under **Forms**

---

## ✅ Expected Output

A working, styled data-entry form named `PatientEntryForm` linked to the `Patients` table, capable of:
- Browsing existing patient records one at a time
- Adding new patients through labelled input fields
- Editing any existing patient's details
- Deleting a patient record

---

## 📝 Viva/Record Questions

1. Why do real-world healthcare staff use Forms instead of directly editing the raw table?
2. What is the purpose of the navigation bar at the bottom of a form?
3. What happens to the underlying `Patients` table when you add a record through the form?
4. Why should deleting patient records be done cautiously in a real hospital system?

---

## 🔁 Practice Variation

Re-open the Form Wizard and create a second form named `QuickViewForm` that only displays `FullName`, `Age`, and `ContactNumber` — a simplified, read-only-style view for receptionists who only need basic lookup information.
