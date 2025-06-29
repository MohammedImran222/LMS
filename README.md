# LMS
SmartLms
# 🎓 Gamified Learning Management System (LMS)

A Django + PostgreSQL-based Learning Management System designed to create a gamified, structured learning environment for both students and teachers. This LMS introduces **level-based course progression**, **wallet points for students**, and **role-based access** for enhanced engagement, performance tracking, and internal mark rewards.

---

## 🔑 Core Features

### 👨‍🏫 Teacher Phase
- Create and manage courses
- Upload videos and downloadable notes
- Assign homework and assessments
- Host **Continuous Assessment Tests (CAT)**
- Conduct **proctored final level tests**
- Evaluate student performance and submissions

### 👨‍🎓 Student Phase
- Enroll in courses
- Progress through 8 structured levels (0 to 7)
- Attempt CATs and final level assessments
- Earn **wallet points** based on attempt performance
- Burn points to **boost internal marks**

---

## 🌟 Gamification Highlights

### 🎮 Level Progression
Each course is broken into 8 levels:
- Students complete tasks and assessments (CAT) at each level.
- Upon completing CATs, they take a **final proctored test** to unlock the next level.
- Failure to clear results in retaking the level from scratch.

### 💰 Wallet Points System
Students earn points when passing levels:
| Attempt | Points Earned |
|---------|----------------|
| 1st     | 100            |
| 2nd     | 90             |
| 3rd     | 80             |
| 4+      | 70             |

Students can **burn wallet points** to:
- Add internal marks
- Unlock premium content (future scope)
- Join exclusive contests (future scope)

---

## 🛠️ Tech Stack

| Layer       | Technology            |
|-------------|------------------------|
| Backend     | Django 4.x             |
| Database    | PostgreSQL             |
| Frontend    | HTML, Bootstrap        |
| Media       | File/Video Uploads     |
| Auth        | CustomUser with Roles  |

---

## 🧱 Database Schema Overview

- `CustomUser` — extends Django user model with `user_type` and `wallet_points`
- `Course` — created by teachers
- `CourseLevel` — defines level (0–7) structure within each course
- `LevelAttempt` — stores each student's attempt and result for a level
- `WalletTransaction` — logs all earn/burn transactions
- `Assignment`, `Content`, `Submission` — extendable for future

---

## 🚀 Future Enhancements

- 🔹 Leaderboards & badges
- 🔹 Live class scheduling (Zoom/GMeet)
- 🔹 Certificate generation
- 🔹 Contest hosting and ranking
- 🔹 Admin dashboard for analytics and moderation
- 🔹 Detailed progress reports in PDF/Excel

---

## 📦 Installation & Setup

```bash
# Clone the repo
git clone https://github.com/yourusername/lms.git
cd lms

# Create a virtual environment
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows

# Install dependencies
pip install -r requirements.txt

# Configure PostgreSQL settings in settings.py
# Run migrations
python manage.py migrate

# Create superuser
python manage.py createsuperuser

# Start the server
python manage.py runserver
