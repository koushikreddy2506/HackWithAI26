Student Performance Analyzer MVP
A comprehensive web application designed to analyze student performance data using machine learning principles. The MVP includes 5 key stages of analysis.

📊 MVP Features (5 Stages)
1. Collect Student Performance Data
Upload student test scores via CSV files
Support for multiple subjects and students
Real-time file validation
2. Analyze & Detect Weaknesses
Statistical analysis of subject-wise performance
Identification of weak areas (scores below 60%)
Student failure count per subject
3. Rank Weak Areas
Severity-based ranking system
Identification of priority subjects
Performance distribution analysis (Q1, Q3, median)
4. Generate 7-Day Problem-Focused Plan
Automated study schedule targeting weak areas
Daily goals and activities
Progressive difficulty levels
Revision on Day 7
5. Recommend Free Study Material
Subject-specific free resources
Links to Khan Academy, Brilliant, OpenStax, etc.
Study tips for each subject
🛠️ Tech Stack
Backend:

Flask (Web Framework)
Pandas (Data Analysis)
NumPy (Numerical Computing)
Frontend:

HTML5
CSS3 (Responsive Design)
JavaScript (Vanilla)
Chart.js (Data Visualization)
📋 Project Structure
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
│       ├── styles.css      # Styling
│       ├── app.js          # Upload logic
│       └── dashboard.js    # Dashboard logic
├── data/
│   └── sample_data.csv     # Sample test data
├── requirements.txt        # Python dependencies
└── README.md              # This file
🚀 Installation & Setup
Prerequisites
Python 3.7+
pip (Python package manager)
Step 1: Install Dependencies
pip install -r requirements.txt
Step 2: Run the Flask Application
cd backend
python app.py
The application will start at http://localhost:5000

📝 CSV File Format
Your input CSV should have this structure:

name,Math,Physics,Chemistry,English,History
John Doe,75,80,85,90,88
Jane Smith,65,70,75,80,82
Bob Johnson,55,60,65,78,85
Requirements:

First column: Student names (header: name or student_id)
Remaining columns: Subject scores (0-100)
No header row should be blank
Scores should be numeric values
🎯 How It Works
Stage 1: Data Collection
Navigate to http://localhost:5000
Upload a CSV file with student performance data
Alternative: Click "View Sample Analysis" to see demo data
Stage 2: Analysis
The analyzer calculates:

Mean, median, standard deviation for each subject
Quartile ranges (Q1, Q3)
Min/max scores
Failure count (scores < 40)
Stage 3: Weakness Detection
Identifies subjects with mean score < 60%
Calculates severity score (100 - average_score)
Counts students below 60% and 40% thresholds
Stage 4: Planning
Ranks weak areas by severity
Creates a 7-day study schedule
Focuses most on weakest areas (Days 1-2)
Includes revision day (Day 7)
Stage 5: Recommendations
Suggests free online resources:
Khan Academy courses
Problem-solving platforms
Textbooks and tutorials
Provides personalized study tips
📊 Dashboard Features
The analysis dashboard displays:

Statistics Cards: Total students, average score, weak areas
Performance Chart: Bar chart of subject-wise scores
Ranking Chart: Line chart showing severity and performance trends
Detailed Analysis: Subject statistics with quartile ranges
7-Day Plan: Day-by-day study schedule with activities
Recommendations: Free study materials for each weak area
Study Tips: Subject-specific learning strategies
🔧 API Endpoints
Upload & Analyze
POST /api/upload
- Accepts: CSV file
- Returns: Comprehensive analysis with plan and recommendations
Sample Data
GET /api/sample
- Returns: Pre-loaded sample analysis for demo
Health Check
GET /api/health
- Returns: Service status
📈 Analysis Metrics
Severity Scoring
Severity = 100 - Average Score
Weakness Threshold
Weak Area: Average Score < 60%
Failing: Score < 40
Needs Improvement: Score < 60
💾 Data Storage
Currently, data is processed in-memory during the session. For production:

Implement database (PostgreSQL, MongoDB)
Store student profiles
Track progress over time
Generate historical reports
🎨 Customization
Modify 7-Day Plan
Edit backend/planner.py:

Change focus distribution
Add new activity types
Adjust study time recommendations
Add Study Resources
Edit backend/recommendations.py:

Add more resource links
Include local resources
Add paid premium options
Customize Theme
Edit frontend/static/styles.css:

Change color scheme
Modify responsive breakpoints
Adjust typography
🐛 Troubleshooting
File Upload Issue
Ensure CSV format is correct
Check file size (max 16MB)
Verify column headers
Chart Not Displaying
Clear browser cache
Check console for errors
Verify Chart.js is loaded
Flask Port Already in Use
# Change port in app.py:
app.run(debug=True, port=5001)  # Use different port
📱 Browser Support
Chrome/Chromium (Latest)
Firefox (Latest)
Safari (Latest)
Edge (Latest)
🚀 Future Enhancements
 Database integration
 User authentication
 Multi-year comparison
 AI-powered recommendations
 Email notifications
 Mobile app
 PDF report generation
 Real-time collaboration
 Adaptive learning paths
📄 License
This project is open source and available for educational purposes.

👨‍💻 Author
Created as an MVP for student performance analysis and personalized learning recommendations.

📞 Support
For issues or suggestions, please create an issue or contact the development team.
