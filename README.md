[README.md](https://github.com/user-attachments/files/31418959/README.md)
# ExamMind AI 🎓
> **Autonomous AI Practice Exam Generator & Assessment Suite for BS Computer Science in Pakistan**  
> Formally aligned with the **HEC Pakistan BS Computer Science Curriculum (2025/2026 OBE Framework)** & Seoul Accord PLOs.

---

## 🌟 Overview

**ExamMind AI** provides BS Computer Science students and faculty with an end-to-end examination preparation, mock exam simulation, and automated AI grading platform. 

It ingests course materials (lecture slides, assignments, quizzes, and past midterm/final papers across `.pdf`, `.pptx`, `.docx`, `.txt`, and diagram/photo formats), extracts core concepts and topic weightages via Multimodal Vision, enforces mathematical mark equation balancing, and synthesizes realistic, university-standard practice examination papers mapped directly to official **Course Learning Outcomes (CLOs)** and **Seoul Accord Program Learning Outcomes (PLOs)**.

---

## 🚀 Key Features

1. **HEC Pakistan 2025/2026 Curriculum Bounded**:
   - Curated from the latest official HEC Computing Curriculum notification (October 2025).
   - 16 core & elective BSCS courses: *Data Structures, Database Systems, Object Oriented Programming, Programming Fundamentals, Design & Analysis of Algorithms, Theory of Automata, Operating Systems, Computer Networks, Artificial Intelligence, Information Security, Computer Organization & Architecture, Digital Logic Design, Cloud Computing, Calculus, Linear Algebra, Machine Learning*.
   - Audited mapping across all 10 Seoul Accord / NCEAC Program Learning Outcomes (PLO 1 to PLO 10).
2. **Context-Aware Exam Generation (Midterm vs. Final)**:
   - Ingests lecture slides, quizzes, assignments, and past papers.
   - Multimodal Vision AI extracts text, state machines, graphs, circuit diagrams, and math formulas from uploaded photos and figures.
3. **Strict Mathematical Mark Balancing**:
   - Real-time reactive verification: `(MCQs × marks) + (Short × marks) + (Long × marks) + (T/F × marks) == Total Marks`.
   - Prevents generation on mark mismatches and provides exact mathematical deficit/surplus feedback.
4. **Professor Verbal Hints & Constraints Priority**:
   - High-priority directive parser for teacher hints (e.g. *"Focus on A* search, Minimax, and Alpha-Beta Pruning"*, *"No numericals from Chapter 4"*).
5. **Interactive Mock Exam & AI Auto-Grader**:
   - Take the practice exam directly inside the desktop app with an active **Exam Timer**.
   - One-click **AI Auto-Grading** against official marking rubrics with per-question score breakdown, partial credit explanations, and **HEC CLO Attainment Diagnostics** (Mastered vs. Needs Revision).
6. **Pakistani University Presets & Rigor Calibration**:
   - Profiles for *FAST-NUCES, NUST (SEECS), COMSATS, PUCIT, UET, GIKI, IBA, IST Islamabad, Air University, and Bahria University*.
   - Selectable rigor: *Foundational*, *Standard HEC*, and *High Rigor (FAST-Style Boss Mode)*.
7. **Multi-Format Export Studio**:
   - 📄 **Printable PDF Export** (Formatted to Pakistani university examination standards).
   - 📝 **Microsoft Word Export (.docx)** (Editable document for students and instructors).
   - 📋 **Markdown / Plain Text Export**.
   - 🗄️ **Saved Exam Papers Database (SQLite)**.

---

## 🛠️ Installation & Setup

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Configure API Key (Optional)
Copy `.env.example` to `.env` and insert your free Gemini API key from [Google AI Studio](https://aistudio.google.com/app/apikey):
```bash
# In your .env file
GEMINI_API_KEY=your_actual_api_key_here
```
*(ExamMind AI also includes an Offline Synthesizer mode that operates without an external API key!)*

> ⚠️ **Security Notice**: Never commit `.env` containing live secrets to public repositories. `.env` is included in `.gitignore`.

---

## 🖥️ Running ExamMind AI

### Method 1: Native Windows Desktop App (Recommended)
Double-click the **`ExamMind AI`** shortcut directly on your **Desktop**, or run:
```bash
python main.py
```

### Method 2: Web Browser GUI (Streamlit)
```bash
streamlit run app.py
```
Open `http://localhost:8501` in your browser.

---

## 🏛️ Project Architecture

```
ExamMind AI/
├── desktop_app.py              # Native Windows CustomTkinter Desktop Application
├── main.py                     # Desktop Application Entry Point
├── app.py                      # Streamlit Interactive Web Application
├── create_desktop_shortcut.py  # Windows Desktop Shortcut & Icon Generator
├── requirements.txt            # Python dependencies
├── .env.example                # Example environment configuration template
├── .gitignore                  # Git secret and build artifact exclusion rules
├── curriculum/                 # HEC Pakistan Curriculum Database
│   ├── plos.json               # Seoul Accord / NCEAC PLO 1 to PLO 10 definitions
│   ├── loader.py               # Curriculum repository loader & querying
│   └── subjects/               # JSON datasets per BSCS course (16 subjects)
│       ├── programming_fundamentals.json
│       ├── object_oriented_programming.json
│       ├── database_systems.json
│       ├── data_structures.json
│       ├── design_and_analysis_of_algorithms.json
│       ├── theory_of_automata.json
│       ├── operating_systems.json
│       ├── computer_networks.json
│       ├── artificial_intelligence.json
│       ├── information_security.json
│       ├── computer_organization_and_architecture.json
│       ├── digital_logic_design.json
│       ├── cloud_computing.json
│       ├── calculus_and_analytical_geometry.json
│       ├── linear_algebra.json
│       └── machine_learning.json
├── database/
│   └── db.py                   # SQLite storage for saved papers and history
├── engine/
│   ├── parser.py               # Multi-format & Multimodal Vision parser (PDF, PPTX, DOCX, Images)
│   ├── analyzer.py             # Topic weightage & past paper style detector
│   ├── validator.py            # Mathematical exam mark & dynamic CLO/PLO validator
│   ├── generator.py            # LLM generation & offline synthesis engine
│   ├── grader.py               # Interactive AI Auto-Grader & CLO Diagnostic Engine
│   ├── pdf_export.py           # University standard PDF generation
│   └── docx_export.py          # Microsoft Word (.docx) exam paper exporter
├── assets/
│   └── app_icon.ico            # Application Icon
└── tests/
    ├── test_engine.py          # Core engine unit tests
    ├── test_enhancements.py    # Document context, grader, and DOCX unit tests
    └── stress_test_10x.py      # 10x full pipeline stress test suite
```

---

## 📜 License
Developed for BS Computer Science students in Pakistan. Academic Free-Tier Open Access.
