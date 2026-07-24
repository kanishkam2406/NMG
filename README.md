# AgileBoard - A Premium AI-Orchestrated Kanban Board by Kanishka Mishra

AgileBoard is a collaborative, Trello-style Kanban board application. It features a modern Light/Dark mode glassmorphic user interface inspired by the **Cursor developer brand guidelines** (warm cream editorial canvas, dark slate theme, hairline depth, and Cursor Orange accents) built with React (Vite) and backed by a robust REST API built with Laravel (PHP 8.3 & SQLite).

This project was built entirely by orchestrating a team of two AI agents (**Hermes** & **OpenClaw**) wired through Slack sockets.

---

## 📹 Evidence Walkthrough Video

> [!IMPORTANT]
> **Evaluators & Reviewers**: The full screen-recording demonstration video for submission guidelines is located inside the repository at:
> 
> 📁 **[evidence/walkthrough.mp4](file:///c:/Users/kanis/OneDrive/Desktop/Forge2-Qualifier-AyushMishra-main/Forge2-Qualifier=Kanishka%20Mishra/evidence/walkthrough.mp4)** (32.7 MB)
> 
> **Demonstrates**:
> 1. ✅ **Demo Board Seeding**: Pre-populated card initialization with active demo tasks.
> 2. ✅ **Fluid Swimlane Drag & Drop**: Card movement across `To Do`, `In Progress`, and `Done`.
> 3. ✅ **Card Customization**: Tag toggles, assignee assignment (Kanishka Mishra), and due date picking.
> 4. ✅ **Overdue Date Flagging**: Red boundary highlights denoting past due tasks.
> 5. ✅ **Board & Column Management**: Multi-board creation and column customization.

---

## Core Features

-   **Multi-Board Workspace**: Create, switch, and delete boards.
-   **Structured Columns (Swimlanes)**: Boards start with `To Do`, `In Progress`, and `Done` lists. Add new columns dynamically.
-   **Interactive Cards**: Create, edit, and delete cards within lists.
-   **Interactive Drag-and-Drop**: Drag cards between lists using HTML5 drag-and-drop actions.
-   **Task Assignment**: Add board members (Lead: Kanishka Mishra) and assign cards.
-   **Categorization Tags**: Create colored tags and toggle them on cards.
-   **Due Date Tracking**: Select a due date/time. Overdue tasks are highlighted with a soft crimson boundary glow.
-   **Theme Toggle**: Toggle between **Warm Cream (Light)** and **Premium Slate (Dark)** themes.
-   **Built-in LocalStorage Fallback**: Fully functional Offline Mode that detects backend offline state and saves all data to local browser storage automatically.
-   **AI Agent Build Simulation**: An interactive in-workspace simulation demonstrating Hermes & OpenClaw planning, editing, and compiling the board inside Slack in real-time.

---

## Tech Stack & Configuration Files

-   **Backend**: Laravel (PHP 8.3), SQLite Database, Eloquent ORM.
-   **Frontend**: React 19 (Vite), Vanilla CSS (Custom Glassmorphism, Google Fonts).
-   **System Architecture**: Read [ARCHITECTURE.md](file:///c:/Users/kanis/OneDrive/Desktop/Forge2-Qualifier-AyushMishra-main/Forge2-Qualifier=Kanishka%20Mishra/ARCHITECTURE.md) for full architecture specification.
-   **Orchestration Config**: [hermes-config.yaml](file:///c:/Users/kanis/OneDrive/Desktop/Forge2-Qualifier-AyushMishra-main/Forge2-Qualifier=Kanishka%20Mishra/hermes-config.yaml) and [openclaw.json](file:///c:/Users/kanis/OneDrive/Desktop/Forge2-Qualifier-AyushMishra-main/Forge2-Qualifier=Kanishka%20Mishra/openclaw.json) (No secrets hardcoded, all credentials loaded from host environment).
-   **Agent Work Logs**: Read [agent-log.md](file:///c:/Users/kanis/OneDrive/Desktop/Forge2-Qualifier-AyushMishra-main/Forge2-Qualifier=Kanishka%20Mishra/agent-log.md) for the unedited task execution trace.
-   **Agent Skills**: Configured under the [skills/status-report](file:///c:/Users/kanis/OneDrive/Desktop/Forge2-Qualifier-AyushMishra-main/Forge2-Qualifier=Kanishka%20Mishra/skills/status-report/SKILL.md) folder.

---

## Model Routing Rationale

All models used in this build are 100% free:

1.  **Hermes (Brain / Planning)**: Guided by **Google Gemini 2.5 Flash** & **Groq gpt-oss-120b**.
    *   *Why*: Gemini and Groq's high-tier models have outstanding logic structure and zero-shot reasoning. This is crucial for Hermes to break down abstract user goals into task files.
2.  **OpenClaw (Hands / Execution)**: Guided by **Ollama qwen2.5-coder** (local) & **Groq llama-3.3-70b-versatile**.
    *   *Why*: Local Ollama execution offers unlimited token throughput, bypassing API rate limit thresholds, while Groq provides extremely fast compilation and syntax validation checks.

---

## Local Run Instructions

### 1. Launch the Frontend (Includes Offline Mode & Simulation)
Since the app features a built-in LocalStorage fallback database with pre-populated demo data, you can run the entire frontend immediately without setting up PHP or Laravel locally:

1. Navigate to the `/frontend` directory:
   ```bash
   cd frontend
   ```
2. Install npm packages:
   ```bash
   npm install --no-audit --no-fund
   ```
3. Start the Vite dev server:
   ```bash
   npm run dev
   ```
4. Open `http://localhost:5173/` in your browser.
5. Click **"Launch Workspace"** or click **"🤖 Simulate AI Build"** to run the agent compile simulation.

### 2. Launch the Backend API (Optional)
If you have PHP 8.2+ and Composer installed:

1. Navigate to the `/backend` directory:
   ```bash
   cd backend
   ```
2. Copy the environment template:
   ```bash
   copy .env.example .env
   ```
3. Generate the application key:
   ```bash
   php artisan key:generate
   ```
4. Run the database migrations:
   ```bash
   php artisan migrate
   ```
5. Start the local development server:
   ```bash
   php artisan serve
   ```
   The API will now be running at `http://127.0.0.1:8000`.

---

## Live Deployments

-   **Frontend**: [Live Demo on Vercel](https://forge2-qualifier-kanishka-mishra-ir4yk7gpi.vercel.app)
-   **Backend API**: Run locally ([http://127.0.0.1:8000](http://127.0.0.1:8000))
-   **Owner / Author**: Kanishka Mishra
