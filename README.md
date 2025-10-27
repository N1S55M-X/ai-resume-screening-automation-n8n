
# 🤖 AI Resume Screening & Scoring Automation (n8n)

A fully automated hiring workflow that extracts resume data, scores candidate fit, classifies talent, and stores structured insights in Google Sheets for data-driven recruitment.

---

## 🎯 Objective

Automate the resume intake process to:

1. Capture uploaded resumes
2. Extract structured candidate information using AI
3. Apply standardized scoring logic
4. Classify candidates into Strong/Medium/Weak Fit
5. Append clean results into Google Sheets

This system replaces slow manual screening with fast and consistent candidate evaluation.

---

## 🧠 Workflow Architecture

| Step | Node                          | Function                                 |
| ---- | ----------------------------- | ---------------------------------------- |
| 1    | **Form Trigger**              | Capture uploaded PDF resume              |
| 2    | **Extract From PDF**          | Read and convert CV to text              |
| 3    | **LLM Information Extractor** | Parse skillset, experience, contact info |
| 4    | **Code Node**                 | Scoring logic + format JSON              |
| 5    | **Google Sheets Append**      | Talent database for HR review            |

---

## ✅ Data Extracted from Resume

```json
{
  "name": "...",
  "email": "...",
  "phone": "...",
  "skills": "...",
  "projects": "...",
  "experience": "...",
  "score": 27,
  "classification": "Strong Fit",
  "created_at": "2025-10-26T20:49:15.000Z"
}
```

All fields stored as individual columns. No nested JSON.

---

## 🔍 Candidate Scoring Model

| Factor           | Logic                     | Points |
| ---------------- | ------------------------- | ------ |
| Skills Strength  | Number of top-tech skills | +10    |
| AI/Data Projects | Project relevance         | +10    |
| Experience       | Internship or job history | +5     |
| Keyword Match    | Alignment to role         | +5     |

**Classification Rules**

| Score | Category     |
| ----- | ------------ |
| 22+   | ✅ Strong Fit |
| 12–21 | ➖ Medium Fit |
| < 12  | ❌ Weak Fit   |

---

## 📊 Google Sheets Output

| Name | Email | Score | Classification | Skills | Projects | Experience | Created_at |
| ---- | ----- | ----- | -------------- | ------ | -------- | ---------- | ---------- |

HR can quickly filter and prioritize best candidates.

---

## 🛠️ Technologies Used

* **n8n** (workflow engine)
* **Groq LLM / OpenAI model support**
* **JavaScript** (custom logic)
* **Google Sheets API**

---

## 📈 Why This Matters

| Feature                 | Impact                  |
| ----------------------- | ----------------------- |
| Automated data intake   | Saves time              |
| Standardized evaluation | Reduces bias            |
| Structured analytics    | Better hiring decisions |
| Scalable pipeline       | Can process thousands   |

---

## 🌱 Future Enhancements

| Enhancements                          | Purpose            |
| ------------------------------------- | ------------------ |
| Email notification for top candidates | Faster action      |
| Duplicates check by email             | Cleaner talent DB  |
| Talent dashboard (scoring analytics)  | HR reporting       |
| ATS integration (Greenhouse, Workday) | Enterprise support |

---

## 📌 Folder Structure (Proposed)

```
ai-resume-screening-automation-n8n
│
├─ /workflow-json
│     resume-screening-workflow.json
│
├─ /docs
│     workflow-diagram.png
│
└─ README.md
```

---

## 📸 Workflow Screenshot Placeholder

> 
![WhatsApp Image 2025-10-27 at 12 03 23 AM](https://github.com/user-attachments/assets/3635ba9b-7afe-4879-b674-b280125f1f24)

---

## ✅ Status

🟢 Fully functional and ready for production or expansion.

