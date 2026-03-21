1. # Minmini Platform (மின்மினி)

> **Small sparks. Big innovations.**

Minmini is a developer community platform designed to host recurring hackathons, build an innovation ecosystem, and track builders' achievements across competitions. Just like fireflies lighting up the night, Minmini brings together creators whose ideas illuminate innovation.

## 🎯 Core Philosophy

**Create** → Build real projects and prototypes  
**Compete** → Participate in structured hackathons  
**Grow** → Develop portfolios, rankings, and skills

---

## 🏗️ System Architecture

### High-Level Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                         CLIENT LAYER                             │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐          │
│  │   Web App    │  │  Admin Panel │  │ Judge Portal │          │
│  │ (React + TW) │  │   (React)    │  │   (React)    │          │
│  └──────────────┘  └──────────────┘  └──────────────┘          │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ├─── HTTPS/REST API
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                      API GATEWAY LAYER                           │
│                       (FastAPI)                                  │
│  ┌──────────────────────────────────────────────────────────┐  │
│  │  Authentication Middleware (JWT)                          │  │
│  │  Rate Limiting │ CORS │ Validation │ Logging              │  │
│  └──────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ├─── Internal Service Calls
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                      SERVICE LAYER                               │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐          │
│  │ Auth Service │  │ User Service │  │ Team Service │          │
│  └──────────────┘  └──────────────┘  └──────────────┘          │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐          │
│  │  Hackathon   │  │ Submission   │  │   Scoring    │          │
│  │   Service    │  │   Service    │  │   Service    │          │
│  └──────────────┘  └──────────────┘  └──────────────┘          │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐          │
│  │ Leaderboard  │  │   GitHub     │  │ AI Evaluation│          │
│  │   Service    │  │   Analysis   │  │   Service    │          │
│  └──────────────┘  └──────────────┘  └──────────────┘          │
│  ┌──────────────┐  ┌──────────────┐                             │
│  │Notification  │  │    Admin     │                             │
│  │  Service     │  │   Service    │                             │
│  └──────────────┘  └──────────────┘                             │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ├─── Database Queries
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                       DATA LAYER                                 │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐          │
│  │  PostgreSQL  │  │    Redis     │  │   S3/Object  │          │
│  │  (Primary)   │  │   (Cache)    │  │   Storage    │          │
│  └──────────────┘  └──────────────┘  └──────────────┘          │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ├─── External APIs
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                    EXTERNAL SERVICES                             │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐          │
│  │  GitHub API  │  │  OpenAI API  │  │  Email/SMS   │          │
│  └──────────────┘  └──────────────┘  └──────────────┘          │
└─────────────────────────────────────────────────────────────────┘
```

### Service Architecture

#### 1️⃣ **Auth Service**
- User registration & login
- JWT token generation & validation
- Password reset & email verification
- Role-based access control (RBAC)

#### 2️⃣ **User Service**
- Profile management
- Academic year tracking
- Career statistics
- Portfolio building

#### 3️⃣ **Team Service**
- Team creation & management
- Team member invitation
- Division assignment logic
- Mixed-year team detection
- **Flexible team size:** min 2, max configurable per event (up to 8)
- Enforces event-level min/max constraints at registration

#### 4️⃣ **Hackathon Service**
- Event creation & management
- Registration handling
- Timeline management
- Division configuration

#### 5️⃣ **Submission Service**
- Project submission handling
- File uploads & validation
- GitHub repository linking
- Submission status tracking

#### 6️⃣ **Scoring Service**
- Jury score collection
- AI evaluation integration
- Final score calculation
- Score normalization

#### 7️⃣ **Leaderboard Service**
- Real-time ranking calculation
- Division-wise leaderboards
- Career points management
- Historical rankings

#### 8️⃣ **GitHub Analysis Service**
- Repository validation
- Commit history analysis
- Contributor verification
- Code quality metrics

#### 9️⃣ **AI Evaluation Service**
- Documentation analysis
- Architecture assessment
- Code organization scoring
- Innovation evaluation
- **Post-evaluation improvement suggestions** — after scoring, AI generates a personalized improvement report for each team (not shown to judges, only to the team)
- Highlights strengths and weak areas with actionable recommendations

#### 🔟 **Notification Service**
- Email notifications
- In-app notifications
- Real-time updates (WebSocket)
- Event reminders

#### 1️⃣1️⃣ **Admin Service**
- Platform configuration
- User management
- Content moderation
- Analytics & reporting

---

## 📁 Project File Structure

```
Minmini/
│
├── README.md                          # This file
├── .gitignore
├── docker-compose.yml                 # Multi-container orchestration
├── .env.example                       # Environment variables template
│
├── frontend/                          # React Frontend
│   ├── package.json
│   ├── tailwind.config.js
│   ├── vite.config.js
│   ├── .env.local
│   │
│   ├── public/
│   │   ├── favicon.ico
│   │   ├── logo.svg
│   │   └── assets/
│   │
│   └── src/
│       ├── main.jsx                   # Entry point
│       ├── App.jsx                    # Root component
│       │
│       ├── components/                # Reusable components
│       │   ├── common/
│       │   │   ├── Header.jsx
│       │   │   ├── Footer.jsx
│       │   │   ├── Button.jsx
│       │   │   ├── Card.jsx
│       │   │   └── Modal.jsx
│       │   │
│       │   ├── hackathon/
│       │   │   ├── HackathonCard.jsx
│       │   │   ├── HackathonDetails.jsx
│       │   │   └── RegistrationForm.jsx
│       │   │
│       │   ├── team/
│       │   │   ├── TeamCard.jsx
│       │   │   ├── TeamForm.jsx
│       │   │   └── MemberList.jsx
│       │   │
│       │   ├── project/
│       │   │   ├── ProjectCard.jsx
│       │   │   ├── ProjectDetails.jsx
│       │   │   └── SubmissionForm.jsx
│       │   │
│       │   ├── leaderboard/
│       │   │   ├── LeaderboardTable.jsx
│       │   │   ├── RankingCard.jsx
│       │   │   └── PlayerStats.jsx
│       │   │
│       │   └── profile/
│       │       ├── ProfileCard.jsx
│       │       ├── StatsPanel.jsx
│       │       └── ProjectHistory.jsx
│       │
│       ├── pages/                     # Page components
│       │   ├── Home.jsx
│       │   ├── Login.jsx
│       │   ├── Register.jsx
│       │   ├── Dashboard.jsx
│       │   ├── HackathonList.jsx
│       │   ├── HackathonDetails.jsx
│       │   ├── TeamManagement.jsx
│       │   ├── ProjectSubmission.jsx
│       │   ├── Leaderboard.jsx
│       │   ├── Profile.jsx
│       │   ├── Showcase.jsx
│       │   ├── HallOfFame.jsx
│       │   │
│       │   ├── admin/
│       │   │   ├── AdminDashboard.jsx
│       │   │   ├── CreateHackathon.jsx
│       │   │   ├── ManageUsers.jsx
│       │   │   └── Analytics.jsx
│       │   │
│       │   └── judge/
│       │       ├── JudgeDashboard.jsx
│       │       ├── EvaluateProject.jsx
│       │       └── ScoreSubmission.jsx
│       │
│       ├── hooks/                     # Custom React hooks
│       │   ├── useAuth.js
│       │   ├── useHackathon.js
│       │   ├── useTeam.js
│       │   └── useLeaderboard.js
│       │
│       ├── services/                  # API integration
│       │   ├── api.js                 # Axios base config
│       │   ├── authService.js
│       │   ├── hackathonService.js
│       │   ├── teamService.js
│       │   ├── submissionService.js
│       │   └── leaderboardService.js
│       │
│       ├── store/                     # State management
│       │   ├── index.js
│       │   ├── authSlice.js
│       │   ├── hackathonSlice.js
│       │   └── userSlice.js
│       │
│       ├── utils/                     # Utility functions
│       │   ├── validators.js
│       │   ├── formatters.js
│       │   └── constants.js
│       │
│       └── styles/                    # Global styles
│           ├── index.css
│           └── tailwind.css
│
├── backend/                           # FastAPI Backend
│   ├── requirements.txt
│   ├── Dockerfile
│   ├── .env
│   │
│   ├── main.py                        # FastAPI app entry
│   ├── config.py                      # Configuration
│   │
│   ├── api/                           # API routes
│   │   ├── __init__.py
│   │   ├── deps.py                    # Dependencies
│   │   │
│   │   ├── v1/
│   │   │   ├── __init__.py
│   │   │   ├── auth.py
│   │   │   ├── users.py
│   │   │   ├── teams.py
│   │   │   ├── hackathons.py
│   │   │   ├── submissions.py
│   │   │   ├── scoring.py
│   │   │   ├── leaderboard.py
│   │   │   └── admin.py
│   │   │
│   │   └── router.py                  # API router aggregation
│   │
│   ├── services/                      # Business logic
│   │   ├── __init__.py
│   │   ├── auth_service.py
│   │   ├── user_service.py
│   │   ├── team_service.py
│   │   ├── hackathon_service.py
│   │   ├── submission_service.py
│   │   ├── scoring_service.py
│   │   ├── leaderboard_service.py
│   │   ├── github_service.py
│   │   ├── ai_evaluation_service.py
│   │   ├── notification_service.py
│   │   └── admin_service.py
│   │
│   ├── models/                        # SQLAlchemy models
│   │   ├── __init__.py
│   │   ├── user.py
│   │   ├── team.py
│   │   ├── hackathon.py
│   │   ├── submission.py
│   │   ├── score.py
│   │   ├── leaderboard.py
│   │   └── notification.py
│   │
│   ├── schemas/                       # Pydantic schemas
│   │   ├── __init__.py
│   │   ├── user.py
│   │   ├── team.py
│   │   ├── hackathon.py
│   │   ├── submission.py
│   │   ├── score.py
│   │   └── leaderboard.py
│   │
│   ├── db/                            # Database
│   │   ├── __init__.py
│   │   ├── database.py                # DB connection
│   │   ├── session.py                 # Session management
│   │   └── migrations/                # Alembic migrations
│   │       └── versions/
│   │
│   ├── core/                          # Core utilities
│   │   ├── __init__.py
│   │   ├── security.py                # Password hashing, JWT
│   │   ├── config.py                  # Settings
│   │   └── exceptions.py              # Custom exceptions
│   │
│   ├── middleware/                    # Custom middleware
│   │   ├── __init__.py
│   │   ├── auth.py
│   │   ├── rate_limit.py
│   │   └── logging.py
│   │
│   ├── utils/                         # Helper functions
│   │   ├── __init__.py
│   │   ├── validators.py
│   │   ├── github_analyzer.py
│   │   ├── email.py
│   │   └── file_upload.py
│   │
│   └── tests/                         # Unit & integration tests
│       ├── __init__.py
│       ├── conftest.py
│       ├── test_auth.py
│       ├── test_teams.py
│       ├── test_hackathons.py
│       └── test_submissions.py
│
├── database/                          # Database scripts
│   ├── init.sql                       # Initial schema
│   ├── seed.sql                       # Seed data
│   └── indexes.sql                    # Performance indexes
│
├── scripts/                           # Utility scripts
│   ├── setup.sh                       # Initial setup
│   ├── migrate.sh                     # Run migrations
│   └── seed_data.py                   # Populate test data
│
├── docs/                              # Documentation
│   ├── API.md                         # API documentation
│   ├── DATABASE.md                    # Database schema
│   ├── DEPLOYMENT.md                  # Deployment guide
│   └── CONTRIBUTING.md                # Contribution guidelines
│
└── .github/                           # GitHub workflows
    └── workflows/
        ├── ci.yml                     # CI pipeline
        └── deploy.yml                 # Deployment pipeline
```

---

## 🗄️ Database Schema Overview

### Core Entities

```
users
├── id (PK)
├── email (unique)
├── password_hash
├── name
├── college
├── academic_year
├── role (enum: participant, judge, admin)
├── career_points
├── current_rank
├── best_rank
└── created_at

teams
├── id (PK)
├── name
├── hackathon_id (FK)
├── division (enum: freshman, sophomore, junior, senior, open)
├── created_by (FK -> users)
└── created_at

team_members
├── id (PK)
├── team_id (FK)
├── user_id (FK)
├── role (enum: leader, member)
└── joined_at

hackathons
├── id (PK)
├── name (e.g., "Minmini League - Edition 1")
├── description
├── start_date
├── end_date
├── registration_deadline
├── status (enum: upcoming, active, evaluation, completed)
├── min_team_size (default: 2)
├── max_team_size (default: 4, max allowed: 8)
└── created_at

submissions
├── id (PK)
├── team_id (FK)
├── hackathon_id (FK)
├── project_name
├── description
├── github_url
├── demo_video_url
├── deployment_url
├── submitted_at
└── status (enum: pending, under_review, scored)

scores
├── id (PK)
├── submission_id (FK)
├── judge_id (FK -> users)
├── innovation_score
├── technical_score
├── architecture_score
├── presentation_score
├── impact_score
├── total_jury_score
├── ai_score (nullable)
├── final_score
└── feedback_text

leaderboards
├── id (PK)
├── hackathon_id (FK)
├── division
├── team_id (FK)
├── rank
├── final_score
└── updated_at

player_points
├── id (PK)
├── user_id (FK)
├── hackathon_id (FK)
├── points_earned
├── reason (enum: winner, runner_up, third, participation)
└── awarded_at

notifications
├── id (PK)
├── user_id (FK)
├── type (enum: team_invite, submission_deadline, score_published)
├── title
├── message
├── is_read
└── created_at

ai_improvement_reports
├── id (PK)
├── submission_id (FK)
├── hackathon_id (FK)
├── team_id (FK)
├── strengths (JSON)
├── improvement_areas (JSON)
├── recommendations (text)
├── generated_at
└── is_visible_to_team (bool)

builder_tiers
├── id (PK)
├── user_id (FK, unique)
├── tier (enum: bronze, silver, gold, platinum, legend)
├── career_points_at_tier_change
└── updated_at

alumni_network
├── id (PK)
├── user_id (FK, unique)
├── is_opted_in (bool, default: false)
├── open_to_mentoring (bool, default: false)
├── open_to_future_hackathons (bool, default: false)
├── visible_skills (text[])
├── contact_permission (enum: nobody, organizers_only, public)
└── updated_at
```

---

## 🛠️ Technology Stack

### Frontend
- **Framework:** React 18
- **Styling:** TailwindCSS
- **State Management:** Redux Toolkit / Zustand
- **Routing:** React Router v6
- **HTTP Client:** Axios
- **Form Handling:** React Hook Form
- **Validation:** Zod
- **Build Tool:** Vite
- **Deployment:** Vercel

### Backend
- **Framework:** FastAPI (Python 3.11+)
- **Database:** PostgreSQL 15
- **ORM:** SQLAlchemy 2.0
- **Authentication:** JWT (PyJWT)
- **Validation:** Pydantic v2
- **Migration:** Alembic
- **Task Queue:** Celery + Redis (async tasks)
- **Caching:** Redis
- **Deployment:** Railway / Render / AWS

### External Services
- **GitHub API:** Repository analysis
- **OpenAI API:** AI-powered evaluation
- **AWS S3 / Cloudinary:** File storage
- **SendGrid / Resend:** Email notifications
- **Twilio:** SMS notifications (optional)

### DevOps
- **Containerization:** Docker + Docker Compose
- **CI/CD:** GitHub Actions
- **Monitoring:** Sentry (error tracking)
- **Analytics:** Plausible / PostHog
- **Logging:** Structured logging with JSON

---

## 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/yourusername/Minmini.git
cd Minmini

# Setup backend
cd backend
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env
# Configure .env with your database and API keys
alembic upgrade head
python main.py

# Setup frontend (in a new terminal)
cd frontend
npm install
cp .env.example .env.local
# Configure .env.local
npm run dev
```

---

## 📊 Key Features

### For Participants
- Register and create/join teams
- Compete in division-based hackathons
- Submit projects with GitHub integration
- Track personal rankings and achievements
- Build public builder portfolio
- Earn certificates with QR verification

### For Judges
- Review submissions systematically
- Score projects across multiple criteria
- Provide detailed feedback
- Track evaluation progress

### For Admins
- Create and manage hackathons
- Configure divisions and rules
- Moderate submissions
- Generate leaderboards
- Issue certificates
- Access platform analytics

---

## 🎯 Platform Concepts

### Minmini League
Recurring hackathon series. Each edition is a complete competition cycle.

### Minmini Builders
Community members who create, compete, and grow together.

### Minmini Showcase
Portfolio of all projects built during hackathons.

### Division System
- **Freshman Division** → 1st year
- **Sophomore Division** → 2nd year
- **Junior Division** → 3rd year
- **Senior Division** → 4th year
- **Open Championship** → Mixed-year teams

### Team Size Rules
- Minimum team size: **2 members** (always)
- Maximum team size: **configurable per event**, up to **8 members**
- Default max: **4** for standard editions
- Larger events (e.g., multi-college) can allow up to **8**
- Solo participation is **not allowed** — collaboration is a core value

---

## 🏆 Scoring System

### Jury Evaluation (70%)
- Innovation: 20 points
- Technical Implementation: 20 points
- Architecture: 15 points
- Presentation: 10 points
- Real-world Impact: 5 points

### AI Evaluation (30%)
- Code Quality: 10 points
- Documentation: 10 points
- Architecture Description: 5 points
- Repository Activity: 5 points

**Final Score = (Jury Score × 0.7) + (AI Score × 0.3)**

---

## 🎖️ Points System

- **Winner:** 50 points
- **Runner-up:** 30 points
- **Third Place:** 20 points
- **Participation:** 5 points

Points accumulate across hackathons to build career rankings.

---

## 🏅 Builder Tier System

Tiers are awarded based on **total career points** accumulated across all hackathons.

| Tier | Points Required | Badge |
|------|----------------|-------|
| **Bronze** | 0 – 49 pts | 🥉 New spark |
| **Silver** | 50 – 149 pts | 🥈 Rising builder |
| **Gold** | 150 – 299 pts | 🥇 Seasoned creator |
| **Platinum** | 300 – 499 pts | 💎 Elite innovator |
| **Legend** | 500+ pts | ⚡ Minmini Legend |

### Tier Rules
- Tiers are calculated **automatically** after each hackathon results are published
- Tiers are **never downgraded** — a builder's tier can only go up
- Displayed prominently on the builder's public profile and the leaderboard
- Special badge shown alongside the builder's name in the Showcase

---

## 🤝 Alumni Network

Builders who have completed at least one hackathon can join the **Minmini Alumni Network**.

### Key Principles
- **100% opt-in** — builders explicitly choose to join; default is off
- **Permission-first** — no data is shared without the builder's consent
- **Granular control** — builders can configure exactly what they allow

### Visibility Settings (Builder Controlled)
| Setting | Options |
|---------|--------|
| Profile in alumni directory | Off / On |
| Open to future hackathon invitations | Off / On |
| Open to mentoring newcomers | Off / On |
| Contact permission | Nobody / Organizers only / Public |
| Skills visible | Choose which skills to display |

### How It Works
1. Builder opts in from their profile settings
2. Organizers can browse alumni directory to invite for upcoming editions
3. Alumni receive opt-in invitations for new hackathons — **never spam**
4. Alumni who opt into mentoring are listed for new builders to reach out
5. Builder can opt out or change settings at any time

### Alumni Profile Shows
- Name, college, graduation year
- Builder tier and career points
- List of past hackathons participated
- Showcase projects (public)
- Self-selected skills

---

---

## 📋 Platform Design Decisions — Discussion Summary

This section tracks all confirmed design decisions made during platform planning (as of March 2026).

---

### ✅ Platform Identity
- **Name:** Minmini (மின்மினி) — means *Firefly* in Tamil
- **Tagline:** *Small sparks. Big innovations.*
- **Concept:** Developer community platform combining hackathons, portfolios, rankings, and collaboration
- **Philosophy pillars:** Create → Compete → Grow

---

### ✅ Competition Structure
- Recurring events branded as **Minmini League — Edition N**
- Year-based divisions ensure fair competition:
  - Freshman (1st yr), Sophomore (2nd yr), Junior (3rd yr), Senior (4th yr)
- Mixed-year teams → **Open Championship Division** (eligible only for Grand Championship Prize)

---

### ✅ Team Size Rules
- **Minimum:** 2 members (solo not allowed — collaboration is core)
- **Maximum:** Configurable per event, up to **8 members**
- **Default max:** 4 for standard editions; larger events may allow up to 8
- Solo participation explicitly excluded

---

### ✅ Scoring — Jury + AI Hybrid
- **70% Jury:** Innovation, Technical, Architecture, Presentation, Impact
- **30% AI:** Code quality, Documentation, Architecture description, Repo activity
- **Final Score = (Jury × 0.7) + (AI × 0.3)**
- AI scores are **not visible to judges** (avoids bias)

---

### ✅ AI Improvement Suggestions (Post-Evaluation Feature)
- After results are published, AI generates a **personalized improvement report** for each team
- Report is visible **only to the team**, not judges or other participants
- Highlights: strengths, weak areas, specific recommendations
- Goal: Turn every hackathon into a **learning opportunity** regardless of result
- This feature helps builders improve across editions

---

### ✅ Builder Tier System
- Tiers awarded based on **career points** accumulated across all hackathons:
  - Bronze (0–49) → Silver (50–149) → Gold (150–299) → Platinum (300–499) → Legend (500+)
- Tiers are **permanent** (never downgraded)
- Displayed on builder profile, leaderboard, and Showcase
- Pure points-based — transparent and merit-driven

---

### ✅ Alumni Network (Opt-in Only)
- Builders who complete ≥1 hackathon can join the alumni directory
- **Default is OFF** — builder must explicitly opt in
- Opt-in scope is fully granular: future invites, mentoring, contact permission
- Organizers can discover alumni to invite for future editions — no spam, invitation-only
- Alumni who opt in for mentoring are visible to new builders
- Builder can change or revoke consent at any time

---

### 🔄 Still Under Discussion
- Specific badge designs and names for tiers
- Exact AI evaluation prompt design
- Certificate design and QR verification chain
- Multi-college expansion criteria
- Challenge tracks per edition (domain-specific problem statements)
- Community voting / People's Choice Award

---

## 📜 License

MIT License - See LICENSE file for details

---

## 🤝 Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](docs/CONTRIBUTING.md) for guidelines.

---

## 📧 Contact

For questions or feedback, reach out to:
- Email: team@minmini.dev
- GitHub: [@minmini-platform](https://github.com/minmini-platform)

---

**Built with ❤️ by the Minmini Community**

*Small sparks. Big innovations.* ✨
