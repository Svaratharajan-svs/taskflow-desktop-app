# 📌 Task Manager Desktop App

> A Cross-Platform Productivity App Built with Electron.js, React, TypeScript, and SQLite

This project is a portfolio-ready, fully functional desktop application built using Electron.js with a clean architecture, secure IPC messaging, multi-window support, local database storage, analytics dashboard, background tasks, and modern UI.

**The goal of this project is to demonstrate strong software engineering skills, full-stack capability within desktop environments, and solid architectural patterns.**

---

## 🚀 Features

### Core Features

- ✔ Add, edit, delete tasks
- ✔ Task status, priority, due date
- ✔ Filter & search tasks
- ✔ Local SQLite database (offline-first)
- ✔ Persistent app settings
- ✔ Background worker for overdue tasks reminder
- ✔ System tray integration

### UI Features

- ✔ Modern React UI with TailwindCSS
- ✔ Multiple windows (Dashboard + Settings)
- ✔ Light/Dark theme
- ✔ Charts & Analytics (task completion trends)

### Architecture & Tech

- ✔ Electron.js (Main + Preload + Renderer processes)
- ✔ Clean Architecture: Domain → Services → IPC → UI
- ✔ Secure IPC communication
- ✔ TypeScript end-to-end
- ✔ SQLite + TypeORM ORM
- ✔ Background processes using Node worker threads
- ✔ Electron Builder packaging for `.exe`, `.dmg`, `.AppImage`

---

## 🏛️ Architecture Overview

The application follows a modular clean architecture:

```
/src
 ├── main/            # Electron main process
 ├── preload/         # Secure bridging (contextIsolation)
 ├── renderer/        # React front-end UI
 ├── database/        # SQLite entities, migrations, TypeORM
 ├── services/        # Domain services (task logic)
 ├── ipc/             # All IPC channels (typed)
 ├── workers/         # Background processes
 └── shared/          # Common types & utils
```

### Process Flow

1. **Renderer** sends validated request via IPC → **Preload**
2. **Preload** → **Main** handles the request
3. **Main** → **Services** → **Database**
4. Response returned back to **Renderer**
5. UI updates reactively

**This ensures:**

- 🔒 Security
- 📦 Separation of concerns
- ♻️ Maintainability
- ⚡ Performance

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|------------|
| Desktop Framework | Electron.js |
| UI Framework | React + Vite |
| Language | TypeScript |
| Styling | TailwindCSS |
| Database | SQLite + TypeORM |
| Charts | Recharts / Chart.js |
| Build | Electron Builder |
| Background Tasks | Worker Threads |

---

## 📂 Project Structure

```
root/
├── package.json
├── electron-builder.yml
├── src/
│   ├── main/
│   ├── preload/
│   ├── renderer/
│   ├── database/
│   ├── services/
│   ├── ipc/
│   ├── workers/
│   └── shared/
└── README.md
```

---

## 🧪 Running the Project

### 1. Install dependencies

```bash
npm install
```

### 2. Run in development mode

```bash
npm run dev
```

### 3. Build production installers

```bash
npm run build
```

---

## 🗃️ Database

**SQLite + TypeORM**

App stores all data locally in `taskmanager.db`

### Entity Example

```typescript
Task {
  id: number;
  title: string;
  status: "pending" | "completed";
  priority: "low" | "medium" | "high";
  dueDate: Date;
  createdAt: Date;
}
```

---

## 🔧 Key Modules Explained

### Main Process

- Manages windows
- Registers IPC handlers
- Loads database
- Runs background workers

### Preload

- Exposes secure, whitelisted functions to UI
- Protects against XSS and remote code execution

### Renderer

- React pages for dashboard, tasks, analytics, settings

### Background Worker

- Checks for overdue tasks
- Sends notifications to main process

---

## 🧰 Security

- ✅ `contextIsolation` enabled
- ✅ No `nodeIntegration`
- ✅ Strict preload APIs
- ✅ Validated IPC message shapes
- ✅ Input validation for DB operations

---

## 📊 Analytics Dashboard

The analytics page visualizes:

- Tasks completed per day
- Pending vs completed
- Priority distribution
- Task creation timeline

**Charts update dynamically from DB.**

---

## 🪄 Build & Distribution

Using **Electron Builder**, the project produces:

- **Windows:** `.exe`
- **Mac:** `.dmg`
- **Linux:** `.AppImage`

Icons and metadata are included for professional presentation.

---

## 🎯 Why This Project Is Portfolio-Ready

This project demonstrates:

- ✨ Desktop engineering with Electron
- ✨ Strong architecture patterns
- ✨ Secure IPC communication
- ✨ Full-stack TypeScript
- ✨ UI + Database + Background systems
- ✨ Packaging and deployment skills
- ✨ Clean code and documentation

**Perfect to showcase for software engineer, full stack, Electron developer, or desktop app roles.**

---

## 📸 Screenshots

![Dashboard](assets/dashboard.png)
![Task Page](assets/tasks.png)
![Analytics](assets/analytics.png)
![Settings](assets/settings.png)

---

## 📽️ Demo Video (Optional)

Upload a short video showing:

- Adding tasks
- Switching tabs
- Running analytics
- Using settings
- Notifications

---

## 📌 Roadmap

- 🔹 Cloud sync (Firebase / Supabase)
- 🔹 User authentication
- 🔹 Export data to CSV/PDF
- 🔹 Reminders with sound
- 🔹 Themes customization

---

---

**⭐ If you find this project useful, please consider giving it a star!**
