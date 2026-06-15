# Unit IV – Day 1 (2 Hours)
## Web Technologies, HTML & Healthcare Web Applications

---

## 🎯 Session Goals
By the end of this session, students will be able to:
- Understand fundamentals of HTML and how web applications work
- Create a basic HTML page for patient/personal information
- Understand the role of web technologies in healthcare systems

---

## ⏱️ Session Plan (2 Hours)

| Time | Topic |
|------|-------|
| 0:00 – 0:10 | Recap Unit III |
| 0:10 – 0:35 | How the web works — overview |
| 0:35 – 1:10 | HTML fundamentals |
| 1:10 – 1:50 | Practical: Patient info webpage |
| 1:50 – 2:00 | Recap + Q&A |

---

## 1. How the Web Works

```
User types URL in browser
          ↓
DNS resolves to server IP
          ↓
Browser sends HTTP Request to server
          ↓
Server responds with HTML/CSS/JS
          ↓
Browser renders the page
```

### Key Technologies

| Technology | Role |
|------------|------|
| **HTML** | Structure (content) |
| **CSS** | Style (appearance) |
| **JavaScript** | Behaviour (interaction) |
| **Python/Java** | Backend (server logic) |
| **Database** | Data storage |

### Healthcare Web Applications Examples
- Hospital patient portals
- Online prescription systems
- Telemedicine platforms
- Drug information lookup sites
- Lab result viewing portals

---

## 2. HTML Fundamentals

### Basic Structure

```html
<!DOCTYPE html>
<html>
<head>
    <title>Page Title</title>
</head>
<body>
    <!-- Content goes here -->
</body>
</html>
```

### Key HTML Tags

| Tag | Purpose |
|-----|---------|
| `<h1>` to `<h6>` | Headings |
| `<p>` | Paragraph |
| `<a href="">` | Link |
| `<img src="">` | Image |
| `<ul>`, `<li>` | Bullet list |
| `<table>` | Table |
| `<form>` | Input form |
| `<input>` | Form field |
| `<button>` | Button |

---

## 3. Practical: Personal Information Webpage

### Experiment 2 from Syllabus

```html
<!DOCTYPE html>
<html>
<head>
    <title>Student Profile – Pharmacy</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 40px;
            background-color: #f0f8ff;
        }
        h1 {
            color: #003366;
        }
        table {
            border-collapse: collapse;
            width: 60%;
        }
        td, th {
            border: 1px solid #ccc;
            padding: 10px;
        }
        th {
            background-color: #003366;
            color: white;
        }
    </style>
</head>
<body>

    <h1>Student Profile</h1>

    <table>
        <tr>
            <th>Field</th>
            <th>Details</th>
        </tr>
        <tr>
            <td>Name</td>
            <td>Priya Sharma</td>
        </tr>
        <tr>
            <td>Roll Number</td>
            <td>2024PHARM042</td>
        </tr>
        <tr>
            <td>Course</td>
            <td>B.Pharm — 2nd Year</td>
        </tr>
        <tr>
            <td>Specialization</td>
            <td>Pharmaceutical Sciences</td>
        </tr>
        <tr>
            <td>Email</td>
            <td>priya.sharma@university.edu</td>
        </tr>
    </table>

    <h2>About Me</h2>
    <p>
        I am a second-year pharmacy student with a keen interest in clinical pharmacy 
        and drug information systems. I am currently learning Python for healthcare 
        data analysis.
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

Save as `profile.html` and open in browser.

---

## 4. HTML Form for Disease Questionnaire

### Experiment 1 from Syllabus

```html
<!DOCTYPE html>
<html>
<head>
    <title>Disease Information Questionnaire</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 40px; }
        label { display: block; margin-top: 15px; font-weight: bold; }
        input, select, textarea { width: 400px; padding: 8px; margin-top: 5px; }
        button { margin-top: 20px; padding: 10px 30px; background: #003366; color: white; border: none; cursor: pointer; }
    </style>
</head>
<body>

    <h1>Patient Disease Questionnaire</h1>
    <h3>Diabetes Screening</h3>

    <form>
        <label>Full Name:</label>
        <input type="text" placeholder="Enter your full name">

        <label>Age:</label>
        <input type="number" min="1" max="120">

        <label>Gender:</label>
        <select>
            <option>Male</option>
            <option>Female</option>
            <option>Other</option>
        </select>

        <label>Do you have a family history of diabetes?</label>
        <select>
            <option>Yes</option>
            <option>No</option>
            <option>Not Sure</option>
        </select>

        <label>Do you experience frequent thirst or urination?</label>
        <select>
            <option>Yes</option>
            <option>No</option>
        </select>

        <label>Fasting Blood Glucose Level (if known, mg/dL):</label>
        <input type="number" placeholder="e.g. 110">

        <label>Any current medications?</label>
        <textarea rows="3" placeholder="List medications here..."></textarea>

        <label>Additional notes:</label>
        <textarea rows="4" placeholder="Describe symptoms or concerns..."></textarea>

        <button type="submit">Submit Questionnaire</button>
    </form>

</body>
</html>
```

---

## 5. Role of Web in Healthcare Systems

### How Hospital Web Apps Work

```
Patient logs into portal (web browser)
          ↓
Browser sends request to hospital server (Python/Java backend)
          ↓
Server fetches patient record from database
          ↓
Server sends HTML page back to browser
          ↓
Patient sees their results, appointments, prescriptions
```

### Real Examples
- **Apollo Hospitals** — patient portal for reports and appointments
- **Practo** — online doctor consultation
- **eSanjeevani** — Government of India telemedicine platform
- **ABHA** (Ayushman Bharat Health Account) — India's national health ID system

---

## 🧠 Key Takeaways

1. HTML is the backbone of all web pages — structure and content
2. Web applications power modern healthcare — portals, EHR access, telemedicine
3. Forms collect patient data — symptoms, history, questionnaires
4. Tables display structured data cleanly — perfect for patient records

---

## 💻 Practice Exercises

**Exercise 1:** Create your own student profile HTML page with a photo placeholder, subject list, and a short bio.

**Exercise 2:** Build a "Drug Information Page" in HTML showing name, uses, dosage, side effects, and contraindications for any one drug.

**Exercise 3 (Challenge):** Create a 5-question health screening form in HTML for hypertension risk assessment.
