# 🤖 JobMatch AI - AI-Powered Job Portal for Freshers

A revolutionary real-time job portal that solves major loopholes in existing platforms like LinkedIn with intelligent AI matching, verified listings, and direct recruiter communication.

## 🎯 Quick Start

```bash
npm install
npm run init-db
npm start
# Visit http://localhost:4173
```

## 🚀 What This Project Does

**For Candidates:**
- 📋 Upload resume → AI auto-extracts skills
- 🎯 Get personalized job recommendations (70%+ AI match)
- ✅ Apply once → Automatic shortlisting by AI
- 📊 Track applications in real-time
- 💬 Message verified recruiters directly

**For Recruiters:**
- 📝 Post verified jobs (no fake postings)
- 🤖 Auto-shortlist top 250 candidates by AI score
- 👥 See all applicants sorted by skill match
- 💬 Direct messaging with candidates
- 📊 Application dashboard

## 🔧 Project Structure

```
├── public/
│   ├── index.html       # UI with 7 tabs
│   ├── app.js          # Frontend logic
│   └── style.css       # Responsive styling
├── api/
│   └── routes.js       # REST API endpoints
├── db/
│   ├── init.js         # Database setup
│   └── models.js       # Database queries
├── ai/
│   └── matcher.js      # AI matching algorithm
├── server.js           # Express + WebSocket server
└── package.json
```

## 💡 How It Solves Problems

| Problem | Solution |
|---------|----------|
| **Fake Jobs** | ✅ Company verification required |
| **Poor Matching** | ✅ AI analyzes resume & skills |
| **Too Many Irrelevant Jobs** | ✅ Only shows 70%+ matches |
| **Application Spam** | ✅ Verified recruiter accounts only |
| **Stale Old Listings** | ✅ Auto-closes at 250 candidates |
| **No Feedback** | ✅ Real-time AI match scores & status |
| **Too Much Competition** | ✅ AI shortlists removes noise |

## 🤖 AI Matching Algorithm

```
Match Score = (Skill Match × 60%) + (Experience × 35%) + Location (5%)

Shortlist Threshold: ≥ 70% = AUTO-SHORTLISTED
```

**Example:**
```
Job: React Developer (requires JavaScript, React, Node.js)
Candidate: Has JavaScript, React, Python (2/3 skills = 67%)
Experience: 0 years vs 1 year required (0% points)
Location: Match (+5%)

Final = (67% × 0.6) + (0% × 0.35) + 5% = 45.2%
Status: Not shortlisted (need 70%+)
```

## 📡 API Endpoints

### Candidates
```
POST /api/candidates              # Create profile
GET  /api/candidates/:id          # Get profile
PUT  /api/candidates/:id          # Update profile
GET  /api/candidates/:id/recommendations  # AI job matches
GET  /api/candidates/:id/applications     # Track apps
```

### Jobs
```
POST /api/jobs                    # Post job (recruiter)
GET  /api/jobs                    # Browse active jobs
GET  /api/jobs/:id                # Job details
```

### Applications & Messaging
```
POST /api/applications            # Apply for job (auto-scored)
POST /api/messages                # Send message
GET  /api/users/:id/messages      # Get messages
```

## 🔌 WebSocket Real-Time

Server pushes live updates:
- 🆕 New jobs posted
- 💬 New messages received
- 📊 Application status changes

## 📝 Database Tables

- **candidates** - Profile, resume, skills, experience
- **jobs** - Listings, requirements, salary, status
- **applications** - Tracking with AI match scores
- **recruiters** - Verified company accounts
- **messages** - Direct communication
- **ai_matches** - Cached match scores

## 🎨 Frontend Features

### 7 Main Tabs
1. **Home** - Features & overview
2. **Browse Jobs** - Filter & search
3. **My Profile** - Resume upload & AI analysis
4. **Recommendations** - Personalized matches
5. **Applications** - Track status
6. **Messages** - Recruiter chat
7. **Admin** - Post jobs

### Responsive Design
- ✅ Mobile-friendly
- ✅ Real-time notifications
- ✅ Dark/light themes ready
- ✅ Smooth animations

## 🔒 Built-in Security

- Company verification before job posting
- Spam filtering (verified accounts)
- UUID-based IDs (no sequential enumeration)
- Timestamp auditing
- Data separation by user type

## 🚀 Deployment

### Local
```bash
npm start
```

### Production
```bash
NODE_ENV=production npm start
```

### Docker
```bash
docker build -t jobmatch-ai .
docker run -p 4173:4173 jobmatch-ai
```

## 📚 Technologies Used

**Frontend:**
- HTML5, CSS3, JavaScript ES6+
- WebSocket for real-time updates
- Responsive grid layouts

**Backend:**
- Node.js + Express.js
- WebSocket server (ws library)
- SQLite database
- Natural language processing (skill extraction)

**AI/ML:**
- Resume NLP parser
- Skill matcher algorithm
- Score calculator
- Auto-shortlisting engine

## 📊 Sample Data

The system auto-initializes with an empty database. To test:

1. **Create Candidate Profile**
   - Add skills: JavaScript, React, Node.js
   - Upload sample resume
   - Save profile

2. **Post Job (Admin Tab)**
   - Title: Junior Developer
   - Required: JavaScript, React
   - Save job

3. **Get Recommendations**
   - View AI-matched jobs
   - See match percentage
   - Apply for job

4. **Track Application**
   - See AI shortlist status
   - View match score
   - Message recruiter

## 🎓 Learning Outcomes

This project demonstrates:
- ✅ Full-stack web development
- ✅ Database design & queries
- ✅ REST API architecture
- ✅ WebSocket real-time communication
- ✅ AI/ML algorithms
- ✅ Responsive UI/UX
- ✅ Security best practices

## 🔄 Features To Implement Next

- [ ] Email notifications
- [ ] LinkedIn import
- [ ] Video resume
- [ ] Advanced analytics dashboard
- [ ] Salary prediction
- [ ] Interview prep chatbot
- [ ] Bulk CSV upload
- [ ] Background verification API

## 📖 Documentation

See also:
- `BUILD_GUIDE.md` - Detailed setup guide
- `FULL_GUIDE.md` - Complete feature documentation

## 💬 Need Help?

1. Check browser console for WebSocket status
2. Verify database: `npm run init-db`
3. Restart server: `npm start`
4. Check API responses in Network tab

---

**Built to solve real problems in fresher job hunting** 🎯

🚀 Smart Matching • ✅ Verified Jobs • 🤖 AI Screening • 💬 Direct Messaging
