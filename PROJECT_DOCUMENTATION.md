# 📘 Student Placement Dashboard - Technical & System Documentation

## 1. Executive Overview
The **Student Placement & Career Management Dashboard** (PlacementPulse) is designed to streamline the campus recruitment lifecycle for students and Placement Officers (TPOs). The platform unifies job drive discovery, candidate eligibility verification, application tracking, interview scheduling, offer letter management, and placement statistics analytics into a single responsive web interface.

---

## 2. Functional Modules & Implementation Details

### Module 1: Authentication & Profile Management
- **Context Provider**: `AuthContext.jsx`
- **Features**:
  - Pre-seeded student profile (`Alex Morgan`, 8.85 CGPA, CSE 2026).
  - Dynamic **Placement Readiness Score** algorithm evaluating:
    - Verified CGPA threshold (>= 8.0 adds +15 points).
    - Skill count (>= 5 skills adds +15 points).
    - Attached PDF Resume (+10 points).
    - GitHub & LinkedIn profile links (+10 points).
  - Interactive **Skills Studio**: Students can dynamically add or remove tech badges (React, Node, Python, SQL, DSA).
  - **Resume Management**: Simulated PDF resume upload with timestamp tracking.

### Module 2: Placement Opportunities (Job Openings)
- **Context Provider**: `DataContext.jsx`
- **Features**:
  - Pre-loaded placement drives from top recruiters (Google, Microsoft, Atlassian, Deloitte, Razorpay, Goldman Sachs).
  - Real-time search engine for company names, roles, and locations.
  - Multi-parameter filtering:
    - **Category**: Software Development, Frontend, Consulting, Product Management, FinTech.
    - **Work Mode**: Hybrid, On-site, Remote.
    - **CGPA Eligibility Filter**: Instantly hides drives where student's CGPA is below company cutoff.
  - **Job Details Modal**: Renders CTC breakdown, stipend, location, job description, requirements checklist, allowed engineering branches, and selection process rounds.

### Module 3: Application Tracking Hub
- **Kanban Pipeline Board**:
  - Columns: `Applied`, `Shortlisted`, `Interviewing`, `Offer Extended`.
  - Visual status badges with color-coded progression.
- **Recruitment History Timeline**: Click on any application to view step-by-step history logs and notes.
- **Offer Letter Viewer & Acceptance**:
  - Displays base salary, joining bonus, ESOPs, and total CTC.
  - Interactive "Accept Offer" button triggers `canvas-confetti` celebration.
  - Download PDF summary option.

### Module 4: Interview Schedule & Preparation OS
- **Upcoming Interviews**: Visual cards with company logo, interview date/time, interviewer designation, key topics to revise, and direct Google Meet / Teams links.
- **AI Interview Flashcards**: Categorized into DSA/Algorithms, System Design, and HR/Behavioral questions with a "Mark as Revised" toggle.

### Module 5: Dashboard Analytics
- **Visual Charts powered by Recharts**:
  - **Monthly Placement Trends**: Area chart visualizing application velocity vs interview conversions.
  - **Pipeline Distribution**: Donut pie chart displaying application statuses.
  - **Domain CTC Analysis**: Dual bar chart comparing Average CTC vs Highest CTC across domains.
  - **Branch-wise Performance**: Horizontal bar chart comparing placement percentages across CSE, IT, ECE, EEE, and Mechanical.

---

## 3. Data Schema & State Management

### Job Entity Schema
```javascript
{
  id: "job-1",
  company: "Google",
  logo: "url",
  role: "Software Engineering Intern / SDE-1",
  category: "Software Development",
  package: "28 - 32 LPA",
  stipend: "₹1,10,000 / month",
  minCgpa: 8.0,
  allowedBranches: ["Computer Science", "Information Technology"],
  location: "Bengaluru / Hyderabad (Hybrid)",
  workMode: "Hybrid",
  deadline: "2026-10-15",
  description: "...",
  requirements: ["..."],
  selectionProcess: ["OCA", "Tech R1", "Tech R2", "HR"],
  totalApplicants: 142,
  status: "Active"
}
```

### Application Entity Schema
```javascript
{
  id: "app-101",
  jobId: "job-1",
  company: "Google",
  role: "SDE-1",
  appliedDate: "2026-10-03",
  package: "28 - 32 LPA",
  status: "Technical Interview",
  statusHistory: [
    { status: "Applied", date: "2026-10-03", notes: "Submitted" },
    { status: "Technical Interview", date: "2026-10-06", notes: "Round 1 scheduled" }
  ],
  nextAction: "Attend Round 1 Technical Interview on Oct 10, 2026"
}
```

---

## 4. Deliverables Checklist
- [x] **Source Code Repository**: Clean React SPA codebase organized in `src/`.
- [x] **Project Documentation**: `README.md` and `PROJECT_DOCUMENTATION.md`.
- [x] **UI Design Screens**: Dark/light mode, glassmorphic layout with responsive CSS.
- [x] **Live Local Server**: Tested build (`npm run build`) with zero compilation errors.
- [x] **Role Switcher & Admin Feature**: Complete demonstration support for student and TPO admin flows.
