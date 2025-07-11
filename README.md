# 🧠 HCI_LLD – Design-Level Protocol

This repository documents the **Low-Level Design (LLD)** of a Human-Computer Interaction (HCI)-based hiring automation system. The system focuses on improving efficiency in the recruitment pipeline using interactive bots, automated resume screening, and intelligent evaluation.

---

## 📌 Objective

Design a system that automates:
- Resume parsing and filtering
- Bot-assisted online tests
- Candidate evaluation and decision-making

All logic and workflows are defined at the **design level**, without implementation.

---

## 🧱 System Modules (Design Phase Only)

| Module Name         | Description |
|---------------------|-------------|
| **Resume Parser**   | Extracts and structures data (skills, education, experience) from uploaded resumes using NLP techniques |
| **Eligibility Filter** | Compares extracted data with company-defined criteria to shortlist candidates |
| **Online Test Bot** | Presents questions and records answers in an interactive test environment |
| **Answer Evaluator** | Compares user answers to model answers using similarity algorithms (e.g., Cosine Similarity) |
| **Decision Engine** | Aggregates evaluation and filtering results to generate a final hiring decision |

---

## 🔁 Workflow

1. **Resume Upload**
   - Input: PDF/DOC file
   - Output: Structured JSON object with name, skills, experience, education

2. **Filtering Process**
   - Compares extracted fields with job criteria
   - Outputs: `Shortlisted` or `Rejected`

3. **Bot-Based Online Test**
   - Presents job-related questions to the candidate
   - Stores responses mapped to question IDs

4. **Evaluation Engine**
   - Uses text similarity to compare candidate answers with ideal (bot) answers
   - Calculates total score and determines qualification

5. **Final Result**
   - Combines filtering and evaluation results
   - Output: Final JSON report with decision (`Selected` / `Rejected`)

---

## 🔄 Data Flow

Resume Upload
↓
Resume Parsing (NLP)
↓
Eligibility Filtering
↓
Online Test with Bot
↓
Answer Evaluation (Text Similarity)
↓
Final Decision & Report


---

## 📊 Evaluation Logic (Sample)

- **Skill Match Score** = (Matched Skills / Required Skills) × 100
- **Answer Score** = CosineSimilarity(UserAnswer, IdealAnswer)
- **Final Score** = Weighted sum of filtering score + test score

Thresholds and weightages are configurable.

---

## 🔧 Tools (Planned)

| Function               | Planned Technology |
|------------------------|--------------------|
| Resume Parsing         | Python (NLP, spaCy) |
| Test Interface         | HTML + JS          |
| Backend APIs           | Node.js / Express  |
| Evaluation Engine      | Python (scikit-learn / spaCy) |
| Database (if needed)   | PostgreSQL         |



## 🧭 Next Steps (Post-Design)

- Convert modules into microservices or routes
- Build resume parser prototype
- Implement test UI and evaluation logic
- Host backend APIs
- Deploy and test full pipeline
