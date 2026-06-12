Build a modern AI-powered Study Recommendation System for engineering students.

Project Name:
Adaptive AI Exam Preparation and Performance Tracking System

Features:

1. User Registration and Login
- Sign up and login pages.
- Store user details locally.

2. Dashboard
- Display upcoming exams.
- Show study progress and completed tasks.
- Show today's study plan.

3. Exam Details
- User enters exam date, subject name, and difficulty level (Easy, Medium, Hard).
- User enters available study hours per day.

4. AI Study Recommendation
- Automatically generate a personalized study timetable.
- Allocate more time to difficult subjects.
- Create revision sessions before the exam.
- Adjust the plan if a day is missed.

5. Progress Tracking
- Mark topics as completed.
- Display progress bars and percentage.
- Show weekly study statistics.

6. Pomodoro Timer
- 25-minute study timer.
- 5-minute break timer.

7. Dark Mode
- Toggle between light and dark themes.

8. Notifications
- Remind users about pending tasks and exams.

9. Analytics
- Display charts for study hours and subject progress.

10. Download Report
- Export study timetable and progress report as PDF.

UI Requirements:
- Modern responsive design.
- Blue and white theme.
- Card-based layout.
- Smooth animations.
- Mobile-friendly interface.

Technology Stack:
Frontend: HTML, CSS, JavaScript
Backend: Firebase
Database: Firestore
Authentication: Firebase Authentication
Charts: Chart.js
PDF Generation: jsPDF

Folder Structure:
index.html
login.html
signup.html
dashboard.html
style.css
script.js
firebase.js

Generate complete code for all files with comments and responsive design.
<!DOCTYPE html>
<html>
<head>
    <title>AI Study Recommendation System</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

<div class="container">
    <h1>AI Study Recommendation System</h1>

    <label>Exam Date:</label>
    <input type="date" id="examDate">

    <label>Subjects (comma separated):</label>
    <textarea id="subjects" placeholder="Maths, Physics, C Programming"></textarea>

    <label>Hours Available Per Day:</label>
    <input type="number" id="hours">

    <button onclick="generatePlan()">Generate Study Plan</button>

    <div id="output"></div>
</div>

<script src="script.js"></script>

</body>
</html>
body{
    font-family: Arial;
    background:#f2f2f2;
}

.container{
    width:400px;
    margin:50px auto;
    background:white;
    padding:20px;
    border-radius:10px;
    box-shadow:0 0 10px gray;
}

input, textarea{
    width:100%;
    padding:10px;
    margin:10px 0;
}

button{
    width:100%;
    padding:12px;
    background:blue;
    color:white;
    border:none;
    cursor:pointer;
}

#output{
    margin-top:20px;
    background:#e8f5e9;
    padding:15px;
}
function generatePlan() {

    let subjects = document.getElementById("subjects")
                    .value.split(",");

    let hours = document.getElementById("hours").value;

    let output = "<h3>Recommended Study Plan</h3>";

    subjects.forEach((subject,index)=>{

        output += `
        <p>
        Day ${index+1}: Study <b>${subject.trim()}</b>
        for ${hours} hours.
        </p>
        `;
    });

    document.getElementById("output").innerHTML = output;
}
