# 🚀 CodeVeda

**CodeVeda** is a full-stack coding analytics and interview-preparation platform designed to help developers improve their problem-solving skills, track coding progress, practice company-specific problems, and prepare effectively for technical interviews.

The platform combines **LeetCode progress tracking, coding analytics, company-wise problem sheets, friend comparison, and AI-powered coding assistance** in one place.

---

## ✨ Features

* 🔐 **User Authentication**

  * JWT-based authentication
  * Secure password hashing
  * Protected routes

* 🧑‍💻 **LeetCode Profile Integration**

  * Link your LeetCode username
  * Synchronize coding statistics
  * Track solved problems and recent submissions

* 📊 **Coding Analytics Dashboard**

  * Total problems solved
  * Acceptance rate
  * Topic-wise problem distribution
  * Coding streak
  * Badges
  * Contest statistics
  * Recent submissions

* 📅 **Activity & Progress Tracking**

  * Coding activity heatmap
  * Submission history
  * Contest rating visualization
  * Personal progress monitoring

* 🏢 **Company-Wise Coding Sheets**

  * Practice problems from companies such as:

    * Amazon
    * Google
    * Microsoft
    * Salesforce
    * JPMorgan
    * Goldman Sachs
    * Atlassian
    * Flipkart
    * Expedia
    * DE Shaw
    * American Express
    * Wells Fargo

* ✅ **Problem Progress Tracking**

  * Track solved problems
  * Maintain individual progress for company-specific sheets
  * Search and filter problems

* 👥 **Friends & Comparison**

  * Add friends using their LeetCode usernames
  * Compare coding statistics
  * Track relative progress

* 🤖 **AI Coding Assistant**

  * AI-powered code review
  * Coding hints
  * Optimal solution suggestions
  * AI coding coach

* 🌓 **Theme Support**

  * Light mode
  * Dark mode

* 🔒 **Security**

  * Password hashing
  * JWT authentication
  * Protected API routes
  * Rate limiting
  * CORS protection
  * Secure environment variables
  * Encrypted sensitive session data

---

# 🛠️ Tech Stack

## Frontend

* React 19
* Vite
* React Router
* Axios
* Tailwind CSS
* Recharts
* Lucide React
* React Syntax Highlighter
* `@uiw/react-textarea-code-editor`

## Backend

* Node.js
* Express.js
* MongoDB
* Mongoose
* JWT
* bcryptjs
* Helmet
* CORS
* express-rate-limit
* NodeCache

## APIs & AI

* LeetCode GraphQL API
* Groq SDK
* Google Gemini API
* Axios

---

# 📁 Project Structure

```text
CodeVeda/
│
├── client/                         # React + Vite frontend
│   ├── public/                     # Static files and icons
│   └── src/
│       ├── api/                    # API configuration
│       ├── assets/                 # Images and frontend assets
│       ├── components/             # Reusable UI components
│       ├── context/                # Authentication and theme context
│       └── pages/                  # Application pages
│
├── server/                         # Express backend
│   └── src/
│       ├── config/                 # Database configuration
│       ├── middleware/             # Authentication middleware
│       ├── models/                 # MongoDB/Mongoose models
│       ├── routes/                 # API routes
│       ├── seeds/                  # Company problem seed data
│       └── services/               # LeetCode, AI and utility services
│
├── Company Sheet/                  # Company-wise problem data
│
├── package.json
└── README.md
```

---

# ⚙️ Getting Started

## Prerequisites

Before running CodeVeda, make sure you have:

* Node.js 18 or newer
* npm
* MongoDB Atlas or local MongoDB
* Groq API key for AI features
* Google Gemini API key (optional)

---

## 1. Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/CodeVeda.git
cd CodeVeda
```

Replace `YOUR-USERNAME` with your GitHub username.

---

## 2. Install Backend Dependencies

```bash
cd server
npm install
```

---

## 3. Install Frontend Dependencies

Open another terminal or return to the project root:

```bash
cd ../client
npm install
```

---

# 🔑 Environment Variables

## Backend

Create:

```text
server/.env
```

Add:

```env
PORT=5002

MONGODB_URI=your_mongodb_connection_string

JWT_SECRET=your_long_random_jwt_secret

ENCRYPTION_KEY=your_long_random_encryption_key

GROQ_API_KEY=your_groq_api_key

GEMINI_API_KEY=your_gemini_api_key

CLIENT_URL=http://localhost:5173
```

## Frontend

Create:

```text
client/.env
```

Add:

```env
VITE_API_URL=http://localhost:5002/api
```

> ⚠️ Never commit `.env` files or real API keys to GitHub.

---

# 🗄️ Database Setup

Make sure MongoDB is running or your MongoDB Atlas database is accessible.

From the `server` directory, run:

```bash
npm run seed
```

This imports the company-specific coding problems into MongoDB.

---

# ▶️ Running CodeVeda

CodeVeda has two parts:

```text
Frontend → React + Vite
Backend  → Node.js + Express
```

## Start Backend

From:

```text
server/
```

run:

```bash
npm run dev
```

The backend will normally run on:

```text
http://localhost:5002
```

## Start Frontend

Open another terminal and go to:

```bash
cd client
```

Then:

```bash
npm run dev
```

The frontend will normally be available at:

```text
http://localhost:5173
```

---

# 📜 Available Scripts

## Backend

Run from `server/`:

```bash
npm run dev
```

Starts the backend in development mode.

```bash
npm start
```

Starts the backend normally.

```bash
npm run seed
```

Imports company problem data into MongoDB.

## Frontend

Run from `client/`:

```bash
npm run dev
```

Starts the Vite development server.

```bash
npm run build
```

Creates a production build.

```bash
npm run preview
```

Previews the production build.

```bash
npm run lint
```

Runs ESLint.

---

# 🔌 API Overview

Base API URL:

```text
http://localhost:5002/api
```

## Authentication

```text
POST /auth/register
```

Create a new user account.

```text
POST /auth/login
```

Authenticate an existing user.

```text
GET /auth/me
```

Retrieve the authenticated user's information.

---

## LeetCode Integration

```text
PUT /user/leetcode-link
```

Link a LeetCode username.

```text
PATCH /user/leetcode-username
```

Update the user's LeetCode username and trigger synchronization.

```text
POST /user/sync
```

Synchronize LeetCode profile information and recent submissions.

---

## Dashboard

```text
GET /dashboard/overview
```

Retrieve dashboard statistics.

```text
GET /dashboard/heatmap
```

Retrieve coding activity data.

```text
GET /dashboard/recent-submissions
```

Retrieve recent submissions.

```text
GET /dashboard/ai-coach
```

Generate AI coaching information for recent coding activity.

---

## Company Problems

```text
GET /companies
```

Retrieve available companies.

```text
GET /companies/:companyName/problems
```

Retrieve company-specific coding problems.

```text
GET /companies/:companyName/statuses
```

Retrieve the user's progress for a company sheet.

```text
POST /companies/:companyName/problems/:problemSlug/toggle
```

Update the solved status of a problem.

---

## AI Features

```text
POST /ai/review
```

Generate an AI code review.

```text
POST /ai/hint
```

Generate a coding hint.

```text
POST /ai/optimal
```

Generate an optimized solution approach.

---

## Friends

```text
GET /friends
```

Retrieve saved friends.

```text
POST /friends
```

Add a friend using their LeetCode username.

```text
DELETE /friends/:friendId
```

Remove a friend.

```text
GET /friends/:friendId/compare
```

Compare LeetCode statistics.

---

# 🗃️ Data Models

CodeVeda uses MongoDB with Mongoose.

Main models include:

* **User** — User account and authentication information
* **ProfileSnapshot** — LeetCode profile and statistics
* **SubmissionRecord** — Recent accepted submissions
* **CompanyProblem** — Company-specific coding problems
* **UserProblemStatus** — Individual problem-solving progress
* **Friend** — Saved LeetCode friends and comparison data
* **AIInteractionLog** — AI interaction information

---

# 🔐 Security

CodeVeda follows several security practices:

* Passwords are hashed using bcrypt
* Authentication uses JWT
* Protected API routes require authentication
* API requests are rate-limited
* Helmet is used for security headers
* CORS is configured for allowed origins
* Sensitive environment variables are kept outside source control
* Sensitive session information is encrypted before storage

> Never commit API keys, database credentials, JWT secrets, or `.env` files to GitHub.

---

# 🚀 Deployment

CodeVeda can be deployed using:

### Frontend

* Vercel
* Netlify
* Other static hosting platforms

### Backend

* Render
* Railway
* Fly.io
* Other Node.js hosting platforms

### Database

* MongoDB Atlas

### Deployment Steps

1. Configure backend environment variables.
2. Configure the frontend API URL.
3. Set the deployed frontend URL in the backend CORS configuration.
4. Build the frontend:

```bash
cd client
npm run build
```

5. Start the backend:

```bash
cd server
npm start
```

6. Seed the production database if required:

```bash
npm run seed
```

---

# 🎯 Future Improvements

Some planned improvements for CodeVeda include:

* 📚 Spaced-repetition based problem revision
* 📈 Advanced coding performance analytics
* 🏆 Leaderboards and achievement system
* 📅 Personalized interview preparation roadmap
* 🔔 Revision and interview reminders
* 🧠 Improved AI coding coach
* 📱 Mobile-friendly progressive web application
* 📊 More detailed company-wise preparation analytics

---

# 👨‍💻 Author

**Priyanshu Tiwari**

B.Tech Computer Science Engineering Student

GitHub: `priyanshu-tiwari2005`

---

# ⭐ Support

If you find CodeVeda useful, consider giving the repository a ⭐ on GitHub.

---

## 📄 License

This project currently does not include a license.

If you plan to distribute or publish the project, add an appropriate open-source license after reviewing the licensing requirements of the original project and its dependencies.
