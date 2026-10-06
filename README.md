# DeadlineAI

**Don't just remember deadlines. Finish them.**

DeadlineAI is a web app that helps college students keep track of academic deadlines (assignments, labs, exams) and helps teachers publish them.

> **Project status:** This is a working **front-end prototype** built with demo data. It shows the main screens and flows. The AI, notifications and database are **not built yet**. See [What works today](#what-works-today) for details.

---

## The Problem

College information is scattered. Deadlines hide in PDFs, screenshots, WhatsApp messages and emails. Students miss assignments and exams because they never saw the notice, or forgot it.

## Our Idea

One place where:

- **Teachers** publish deadlines and notices.
- **Students** see every deadline, with a live countdown and a priority level.
- The student keeps the task open until they mark it as submitted.

The long-term goal is that AI reads a college notice, finds the deadlines automatically, and keeps reminding the student until the work is done. This part is on our roadmap (see [Roadmap](#roadmap)).

---

## What Works Today

### Working

| Feature | What it does |
|---|---|
| Role selection | Choose to continue as **Teacher** or **Student**. |
| Demo login | Sign in with a demo account. Pages are protected by role, so a student cannot open teacher pages and the other way round. |
| Student dashboard | Shows 4 live numbers: Due Today, Due This Week, High Priority, Completed. Also shows the next upcoming deadlines. |
| My Tasks | Lists all tasks with tabs: **All, Today, Upcoming, Completed**. |
| Task details | Shows title, subject, type, due date, live countdown, progress bar and the **source** of the deadline (file name, page and text). |
| Priority badges | Critical, High, Medium and Low. Each badge uses an icon, a text label and a color, so it is not only color. |
| Live countdown | Updates every second and shows "Overdue" after the deadline. |
| Notifications | Shows alerts. Click one to mark it as read. The sidebar shows the unread count. |
| Teacher dashboard | Shows published deadlines and stats, with a list of all deadlines. |
| Responsive layout | Sidebar on desktop, bottom navigation bar on mobile (student pages). |

### Coming soon (screens exist, features not built)

| Screen | Status |
|---|---|
| Upload Notice (PDF, image, text) | Placeholder page only. No upload yet. |
| AI deadline extraction | Not built. |
| AI Assistant | Placeholder page only. |
| Calendar | Placeholder page only. |
| Analytics | Placeholder page only. |
| Settings | Placeholder page only. |
| Mark as Submitted, Edit Task | Buttons are shown but not connected yet. |
| Accountability mode (repeating reminders) | Not built. |
| Teacher: Create, Edit, Delete deadlines | Buttons are shown but not connected yet. |
| Email / WhatsApp reminders | Not built. |

### Good to know

- All data is **demo data stored in the browser's memory**. There is no backend or database yet. Refreshing the page resets everything.
- Login is a **demo login** that runs in the browser. It is not real security.
- Countdowns use your computer's real clock. The demo tasks are due on 12, 16 and 18 October 2026.

---

## Try It Yourself (2 minutes)

1. Open the app and choose **Student**.
2. Click **Use demo account**, then **Sign in**.
3. On the **Dashboard**, check the stats and the upcoming deadlines.
4. Click a task card to open its details. See the live countdown and the source of the deadline.
5. Open **Notifications** and click a notification to mark it as read. Watch the unread number change.
6. Open **My Tasks** and switch between the tabs.
7. Log out, choose **Teacher**, and sign in with the teacher demo account to see the teacher dashboard.

### Demo accounts

| Role | Email | Password |
|---|---|---|
| Student | `student@deadlineai.com` | `student123` |
| Teacher | `teacher@deadlineai.com` | `teacher123` |

These are public demo accounts for testing only.

---

## Technology Used

| Technology | Used For |
|---|---|
| React 19 | Building the user interface |
| TypeScript | Safer, typed code |
| Vite | Fast development server and build tool |
| Tailwind CSS | Styling |
| React Router | Moving between pages and protecting routes |
| Zustand | Storing app data (tasks, notifications, login state) |
| lucide-react | Icons |
| clsx | Combining CSS class names |
| Oxlint | Checking code quality |

---

## How to Run the Project

You need **Node.js** (a recent version, 20 or newer) and **npm**.

```bash
# 1. Go to the app folder
cd Frontend/duebuddy

# 2. Install dependencies
npm install

# 3. Start the app
npm run dev
```

Then open the address shown in the terminal (usually <http://localhost:5173>).

Other commands:

| Command | What it does |
|---|---|
| `npm run build` | Creates a production build |
| `npm run preview` | Previews the production build |
| `npm run lint` | Checks the code with Oxlint |

**Environment variables:** none are needed right now.

---

## Project Structure

```
QUAD -AI/
└── Frontend/
    └── duebuddy/
        ├── src/
        │   ├── pages/        # One file for each screen
        │   ├── components/
        │   │   ├── layout/   # Sidebar, bottom nav, teacher layout
        │   │   ├── tasks/    # TaskCard, PriorityBadge, Countdown
        │   │   └── ui/       # Button, Input, Modal, LoginForm, EmptyState...
        │   ├── store/        # Demo data and login state (Zustand)
        │   ├── types/        # Shared TypeScript types
        │   ├── lib/          # Helper functions (dates, class names)
        │   └── App.tsx       # All routes and role protection
        ├── tailwind.config.js  # Colors and fonts
        └── package.json
```

Extra planning notes in the app folder: `DESIGN_TOKENS.md`, `COMPONENT_MAP.md`, `SCREEN_INVENTORY.md` and `PHASE_1_PLAN.md`. They describe the design plan, not only what is built.

### Main pages

| Who | Pages |
|---|---|
| Everyone | Role selection, Student login, Teacher login |
| Student | Dashboard, My Tasks, Task Detail, Upload Notice, Calendar, Notifications, AI Assistant, Analytics, Settings |
| Teacher | Dashboard, Upload Notice, Deadlines, Reports, Settings |

---

## Roadmap

These are **future plans**, not current features.

1. **Database and real login** to store tasks and users.
2. **Notice upload** for PDFs, images and pasted text.
3. **AI extraction** to find deadlines in notices, with the source shown for each one.
4. **Priority and conflict detection** to warn when many deadlines are close together.
5. **Accountability mode** with reminders that grow more urgent, and stop once the task is marked submitted.
6. **Email and WhatsApp reminders.**
7. **Calendar, analytics and AI assistant.**

---

## Summary

| | |
|---|---|
| **Problem** | Students miss deadlines because notices are scattered. |
| **Solution** | One place for teachers to publish deadlines and for students to track them with priority and countdowns. |
| **Next step** | Add AI notice reading and reminders that stay on until the task is submitted. |
