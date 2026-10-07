# 🚀 Student Placement & Career Management Dashboard (PlacementPulse)

**PlacementPulse** is a modern, high-performance, full-featured Student Placement Dashboard built using React, Vite, Context API, React Router, and Recharts. It empowers students to monitor campus recruitment opportunities, track application statuses, prepare for technical & HR interviews, view offer letters, and analyze placement statistics.

---

## 🌟 Key Functional Requirements Implemented

### 1. 🔑 Student Authentication & Role Management
- **User Authentication**: Student Login, Registration, and Session Persistence.
- **Profile Management**: Profile info, verified CGPA, department branch, skills manager, and resume upload simulator.
- **Role Switcher**: Toggle between **Student Candidate Mode** and **TPO Placement Cell Admin Mode** (to post job drives, shortlist candidates, and extend offers live!).
- **Placement Readiness Score**: Dynamic 0-100% readiness index gauge calculated from academic CGPA, verified skills, and resume status.

### 2. 💼 Placement Opportunities (Job Board)
- **Comprehensive Listings**: Detailed job openings from top tier companies (Google, Microsoft, Atlassian, Deloitte, Razorpay, Goldman Sachs).
- **Search & Multi-filtering**: Search by company/role/location, filter by Category, Work Mode (Remote/Hybrid/Onsite), and Min CGPA Cutoff.
- **CGPA Eligibility Verification**: Real-time eligibility badge calculation against student's current CGPA.
- **Interactive Job Modal**: Detailed company profile, selection process timeline, requirements, and allowed branches.
- **1-Click Application**: Submit customized cover notes and verified PDF resume with instant status tracking.

### 3. 📊 Application Tracking Hub
- **Kanban Board & Table View**: Toggle between pipeline columns (`Applied` ➔ `Shortlisted` ➔ `Interviewing` ➔ `Offer Extended`) and structured data table.
- **Detailed Recruitment Timeline**: Step-by-step history tracking every status change and note.
- **Offer Letter Studio**: High-fidelity salary breakdown (Base Salary, Joining Bonus, ESOPs, Total CTC), downloadable PDF summary, and **Interactive Offer Acceptance with Confetti Celebration** 🎉!

### 4. 📅 Interview Hub & AI Preparation OS
- **Scheduled Rounds Calendar**: Upcoming technical & HR interviews with Google Meet / Teams live room links.
- **Interviewer & Round Meta**: Key topics to revise and round tips.
- **Interview Preparation Flashcards**: Interactive revision cards for DSA/Algorithms, System Design, and Behavioral HR questions.

### 5. 📈 Dashboard Analytics & Placement Statistics
- **KPI Metrics Cards**: Total Applications, Interviews Scheduled, Offers Secured, Open Placement Drives.
- **Visual Recharts Graphs**:
  - Monthly Application & Placement Trends (Area Chart).
  - Application Pipeline Status Distribution (Donut Chart).
  - Industry Domain CTC Breakdown (Bar Chart).
  - Branch-wise Placement Percentage & Target Comparison.

### 6. 🔔 Real-Time Notifications Drawer
- Categorized notifications (Offer Letters, Interview Alerts, Company Announcements, Deadlines).
- Mark as read, filter by category, and clear options.

---

## 🛠️ Technical Stack & Architecture

- **Frontend Core**: React 19, JavaScript (ES6+)
- **Build Tool**: Vite 8.3
- **Routing**: React Router DOM v7
- **Icons**: Lucide React
- **Data Visualization**: Recharts
- **Celebration Effects**: Canvas Confetti
- **State Management**: React Context API (`AuthContext` & `DataContext`) + LocalStorage Persistence

---

## 📂 Project Structure

```
c:\Users\venka\Downloads\Student Placement Dashboard\
├── src/
│   ├── components/
│   │   ├── Navbar.jsx / Navbar.css          # Top navigation & search bar
│   │   ├── Sidebar.jsx / Sidebar.css        # Responsive sidebar & role switcher
│   │   ├── StatCard.jsx / StatCard.css      # KPI metric card component
│   │   ├── JobCard.jsx / JobCard.css        # Placement opportunity listing card
│   │   ├── JobDetailModal.jsx               # Job requirements & selection timeline
│   │   ├── ApplyModal.jsx                   # Application submission modal
│   │   ├── OfferModal.jsx                   # Offer letter viewer & confetti celebration
│   │   ├── NotificationDrawer.jsx           # Notification panel
│   │   ├── PostJobModal.jsx                 # Admin job posting modal
│   │   └── StatusBadge.jsx                  # Color-coded status badge utility
│   ├── context/
│   │   ├── AuthContext.jsx                  # Authentication & readiness score logic
│   │   └── DataContext.jsx                  # Placement data, applications, persistence
│   ├── data/
│   │   └── mockData.js                      # Seed data for jobs, apps, interviews, stats
│   ├── pages/
│   │   ├── Dashboard.jsx / Dashboard.css    # Primary overview & metrics
│   │   ├── Jobs.jsx / Jobs.css              # Job openings board with search & filters
│   │   ├── Applications.jsx / Apps.css      # Application tracking Kanban & Table
│   │   ├── Interviews.jsx / Interviews.css  # Interview schedule & prep flashcards
│   │   ├── Analytics.jsx / Analytics.css    # Placement stats & CTC charts
│   │   ├── Profile.jsx / Profile.css        # Student profile & skills studio
│   │   ├── Login.jsx                        # Login page with demo quick fills
│   │   └── Register.jsx                     # Student registration form
│   ├── App.jsx / App.css                    # Route configurations & layout
│   └── index.css                            # Glassmorphism design tokens & global CSS
├── package.json
└── README.md
```

---

## 🚀 How to Run Locally

1. **Install Dependencies** (if needed):
   ```bash
   npm install
   ```

2. **Start Development Server**:
   ```bash
   npm run dev
   ```

3. Open your browser and navigate to `http://localhost:5173`.

---

## 💡 Quick Demo Shortcuts

- **Login as Student**: Click **"Fill Student (Alex)"** on the login screen (`alex.morgan@university.edu`, password: `password123`).
- **Toggle Admin Mode**: Use the **"Switch to TPO Admin"** button in the sidebar to simulate posting new job drives and advancing candidate statuses.
- **Reset Demo Data**: Click **"Reset Demo Data"** in the sidebar footer anytime to reset LocalStorage back to initial state.
