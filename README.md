Markdown# Student Performance Analyzer 📊

[![Python Version](https://img.shields.io/badge/python-3.7%2B-blue.svg)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-Web%20Framework-green.svg)](https://flask.palletsprojects.com/)
[![License](https://img.shields.io/badge/license-MIT-yellow.svg)](LICENSE)

A comprehensive web application designed to analyze student performance data using statistical and data science principles. The application processes test score datasets, detects knowledge gaps, ranks weak areas by severity, generates automated 7-day study schedules, and recommends tailored free learning resources.

---

## 🚀 Key Features (5 Stages)

### 1. Collect Student Performance Data
* Upload student test scores easily via CSV files.
* Built-in support for multiple subjects and students.
* Real-time client and server-side file validation.

### 2. Analyze & Detect Weaknesses
* In-depth statistical analysis of subject-wise performance (Mean, Median, Standard Deviation).
* Identification of critical weak areas (scores below 60%).
* Tracking student failure counts per subject.

### 3. Rank Weak Areas
* Severity-based ranking system ($Severity = 100 - Average\ Score$).
* Identification of priority subjects needing immediate attention.
* Performance distribution analysis via quartiles ($Q1, Q3$, and Median).

### 4. Generate 7-Day Problem-Focused Plan
* Automated study schedule targeting weak areas.
* Tailored daily goals, learning activities, and progressive difficulty levels.
* Dedicated revision block on Day 7.

### 5. Recommend Free Study Material
* Subject-specific curated resources.
* Direct links to platforms like Khan Academy, Brilliant, and OpenStax.
* Actionable study tips for each subject.

---

## 🛠️ Tech Stack

### **Backend**
* **Python / Flask**: Core web framework and server logic.
* **Pandas**: Data manipulation and statistical analysis.
* **NumPy**: Numerical computations.

### **Frontend**
* **HTML5 / CSS3**: Responsive, clean layout and styling.
* **Vanilla JavaScript**: Dynamic interactions and API communication.
* **Chart.js**: Interactive data visualizations and dashboards.

---

## 📋 Project Structure

```text
student-performance-analyzer/
├── backend/
│   ├── app.py              # Main Flask application
│   ├── analyzer.py         # Performance analysis logic
│   ├── planner.py          # 7-day plan generation
│   └── recommendations.py  # Study material recommendations
├── frontend/
│   ├── index.html          # Upload page
│   ├── dashboard.html      # Analysis results page
│   └── static/
│       ├── styles.css      # Custom UI styling
│       ├── app.js          # File upload & validation logic
│       └── dashboard.js    # Chart rendering & dynamic views
├── data/
│   └── sample_data.csv     # Sample test data for demo
├── requirements.txt        # Python package dependencies
└── README.md               # Project documentation
🚀 Installation & SetupPrerequisitesPython 3.7+pip (Python package manager)Step 1: Clone the RepositoryBashgit clone [https://github.com/your-username/student-performance-analyzer.git](https://github.com/your-username/student-performance-analyzer.git)
cd student-performance-analyzer
Step 2: Install DependenciesBashpip install -r requirements.txt
Step 3: Run the Flask ApplicationBashcd backend
python app.py
The application will start locally at http://localhost:5000.📝 CSV File FormatYour input CSV file should follow this exact structure:Code snippetname,Math,Physics,Chemistry,English,History
John Doe,75,80,85,90,88
Jane Smith,65,70,75,80,82
Bob Johnson,55,60,65,78,85
Requirements:First column: Student names (header: name or student_id).Remaining columns: Subject scores scaled from 0-100.Validation: No header rows should be left blank, and scores must be numeric.🔧 API EndpointsEndpointMethodDescription/api/uploadPOSTAccepts a CSV file and returns comprehensive analysis, plan, and recommendations./api/sampleGETReturns pre-loaded sample analysis data for instant testing/demos./api/healthGETService status health check.🐛 TroubleshootingFile Upload Error: Ensure your file is saved as a valid .csv, is under the 16MB limit, and matches the header requirements.Charts Not Displaying: Clear your browser cache, check the developer console for JavaScript errors, and verify internet connectivity for CDN-hosted scripts like Chart.js.Port Already in Use: If port 5000 is busy, open backend/app.py and modify the run configuration:Pythonapp.run(debug=True, port=5001)
📄 LicenseThis project is open-source and available under the MIT License for educational and developmental purposes.👨‍💻 AuthorCreated as an MVP for academic performance analytics and personalized intervention strategies.
