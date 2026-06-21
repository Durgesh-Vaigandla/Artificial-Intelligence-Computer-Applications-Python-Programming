# Experiment 2
## Create an HTML Web Page to Show Personal Information

**Software Used:** Any text editor (Notepad / VS Code / LibreOffice Writer in Plain Text mode) + Web Browser

---

## 🎯 Objective

To create a basic, properly structured HTML web page that displays a pharmacy student's personal and academic information.

---

## 🧠 Why This Experiment Matters

This is the foundation of web technologies covered in Unit IV. Before you build drug information portals or patient-facing health pages, you need to be comfortable with the basic HTML skeleton — headings, paragraphs, tables, and lists.

---

## 🛠️ Step-by-Step Procedure

### Step 1: Choose a Code Editor
- Recommended: **VS Code** (free, has syntax highlighting)
- Alternative: **Notepad** (Windows) or **TextEdit in plain text mode** (Mac)
- You can also use LibreOffice Writer, but you must save as **Plain Text (.txt)** then rename to `.html` — Writer's normal `.odt` format will NOT work for HTML

### Step 2: Create a New File
1. Open your text editor
2. Create a new file
3. Save it immediately as `profile.html`
   - In VS Code: **File → Save As** → type `profile.html`
   - Ensure "Save as type" is set to **All Files**, not `.txt`

### Step 3: Write the Basic HTML Skeleton
Type the following structure first:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Student Profile</title>
</head>
<body>

</body>
</html>
```

Save the file (`Ctrl + S`).

### Step 4: Add the Heading and Basic Info
Inside the `<body>` tags, add:

```html
<h1>Student Profile</h1>

<p><b>Name:</b> Priya Sharma</p>
<p><b>Roll Number:</b> 2024PHARM042</p>
<p><b>Course:</b> B.Pharm — 2nd Year</p>
<p><b>College:</b> Aavanto School of Pharmaceutical Sciences</p>
<p><b>Email:</b> priya.sharma@university.edu</p>
```

### Step 5: Add a Table for Structured Details
```html
<h2>Academic Details</h2>
<table border="1" cellpadding="8">
    <tr>
        <th>Field</th>
        <th>Details</th>
    </tr>
    <tr>
        <td>Specialization</td>
        <td>Pharmaceutical Sciences</td>
    </tr>
    <tr>
        <td>Current Semester</td>
        <td>4th Semester</td>
    </tr>
    <tr>
        <td>CGPA</td>
        <td>8.4 / 10</td>
    </tr>
</table>
```

### Step 6: Add a Bio Paragraph
```html
<h2>About Me</h2>
<p>
    I am a second-year pharmacy student with a keen interest in clinical
    pharmacy and drug information systems. I am currently learning Python
    and web technologies for healthcare data analysis.
</p>
```

### Step 7: Add a List of Subjects
```html
<h2>Subjects This Semester</h2>
<ul>
    <li>Pharmacology II</li>
    <li>Pharmaceutical Chemistry</li>
    <li>AI & Computer Applications in Pharmacy</li>
    <li>Hospital Pharmacy</li>
</ul>
```

### Step 8: Save the File
- Press `Ctrl + S` in your editor

### Step 9: View the Output in a Browser
1. Locate `profile.html` in File Explorer / Finder
2. Right-click → **Open With** → choose your browser (Chrome/Firefox/Edge)
   OR
3. Simply double-click the file — it should open in your default browser automatically

### Step 10: Final Check
Your browser should now display:
- A large heading "Student Profile"
- Bold-labelled personal details
- A bordered table of academic details
- A bio paragraph
- A bulleted list of subjects

---

## ✅ Complete Final Code (Reference)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Student Profile</title>
</head>
<body>

    <h1>Student Profile</h1>

    <p><b>Name:</b> Priya Sharma</p>
    <p><b>Roll Number:</b> 2024PHARM042</p>
    <p><b>Course:</b> B.Pharm — 2nd Year</p>
    <p><b>College:</b> Aavanto School of Pharmaceutical Sciences</p>
    <p><b>Email:</b> priya.sharma@university.edu</p>

    <h2>Academic Details</h2>
    <table border="1" cellpadding="8">
        <tr>
            <th>Field</th>
            <th>Details</th>
        </tr>
        <tr>
            <td>Specialization</td>
            <td>Pharmaceutical Sciences</td>
        </tr>
        <tr>
            <td>Current Semester</td>
            <td>4th Semester</td>
        </tr>
        <tr>
            <td>CGPA</td>
            <td>8.4 / 10</td>
        </tr>
    </table>

    <h2>About Me</h2>
    <p>
        I am a second-year pharmacy student with a keen interest in clinical
        pharmacy and drug information systems. I am currently learning Python
        and web technologies for healthcare data analysis.
    </p>

    <h2>Subjects This Semester</h2>
    <ul>
        <li>Pharmacology II</li>
        <li>Pharmaceutical Chemistry</li>
        <li>AI & Computer Applications in Pharmacy</li>
        <li>Hospital Pharmacy</li>
    </ul>

</body>
</html>
```

---

## 📝 Viva/Record Questions

1. What does `<!DOCTYPE html>` do, and what happens if you omit it?
2. What is the difference between `<head>` and `<body>`?
3. Why must `profile.html` be saved with the `.html` extension and not `.txt`?
4. What is the purpose of the `alt` attribute if you were to add an image? (Try adding `<img src="photo.jpg" alt="Student photo">` as an extension)

---

## 🔁 Practice Variation

Add a photo placeholder image, a hyperlink to your college website, and a horizontal rule (`<hr>`) separating each section. Re-save and refresh the browser to see the updated output.
