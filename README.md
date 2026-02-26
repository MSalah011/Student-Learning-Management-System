# Student Learning Management System (LMS)

A client-side Learning Management System built with **HTML**, **CSS**, and **JavaScript**. All data is persisted using the browser's `localStorage`.

---

## Features

- **Authentication** — Login with username & password (min. 6 characters), with session persistence
- **Dashboard** — Live clock, rotating announcements, and real-time statistics
- **Task Manager** — Add, edit, delete, complete, search, and filter tasks by priority/date
- **Course Manager** — Add and delete courses with instructor info
- **Profile** — Update your username and persist changes
- **Route Protection** — All pages redirect to login if the user is not authenticated

---

## Project Structure

```
lms/
├── index.html        # Entry point – redirects to login
├── login.html        # Login page
├── dashboard.html    # Dashboard with clock, announcements & stats
├── tasks.html        # Task management page
├── courses.html      # Course management page
├── profile.html      # Profile/username editor
└── styles.css        # Global stylesheet
```

---

## Pages Overview

### Login (`login.html`)
- Username and password fields
- Password must be at least 6 characters
- Stores the logged-in username in `localStorage`
- Automatically skips to dashboard if already logged in

### Dashboard (`dashboard.html`)
- **Clock** — Displays current time, updated every second
- **Announcements** — Cycles through a hard-coded list via a "Next" button
- **Statistics** — Shows total tasks, completed tasks, pending tasks, and total courses

### Tasks (`tasks.html`)
- Add tasks with a **title**, **due date**, and **priority** (High / Medium / Low)
- Mark tasks as complete (strike-through styling)
- Edit task titles via prompt dialog
- Delete tasks with a confirmation dialog
- Search/filter tasks dynamically by title
- Statistics panel updates in real time

### Courses (`courses.html`)
- Add courses (name stored with current username as instructor)
- Two-column layout: manage courses on the left, view on the right
- Delete courses with confirmation
- Courses stored in `localStorage`

### Profile (`profile.html`)
- Displays current username in an editable field
- Save updated username to `localStorage`

---

## localStorage Keys

| Key            | Description                        |
|----------------|------------------------------------|
| `lms_user`     | Logged-in username                 |
| `lms_tasks`    | JSON array of task objects         |
| `lms_courses`  | JSON array of course objects       |

---

## Requirements

- Any modern web browser (Chrome, Firefox, Edge, Safari)
- JavaScript must be enabled

---

## Notes

- Logging out clears all `localStorage` data and returns to the login page
- All pages are protected — unauthenticated users are redirected to `login.html`
- Data persists across page reloads within the same browser
