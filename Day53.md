# Capstone Project — Day 3 of 10
# Day 53
# Project Setup & Foundation
# Capstone Day 3: From System Design to a Running Hello World

## Today you'll learn how to translate a System Design document into a real, running project foundation — environment setup, project initialization, version control with a branching strategy, and just enough scaffolding to verify everything works, without starting on features yet.

1 Environment Setup: Install and configure the runtime, IDE extensions, package managers, and SDKs your System Design actually calls for, and understand why each one is needed.
2 Project Initialization & Verification: Create the project, install dependencies, and confirm it runs locally before writing any feature code.
3 Repository & Branching Strategy: Connect to GitHub with an intentional branch structure instead of committing everything to main.
4 Foundational Scaffolding: Build only what feature development depends on — routing, layout, auth scaffold, database connection, API client, state management — and understand every file created.

# Prompt:
Day 3: Project Setup & Foundation

Today is Day 3, continuing the same capstone. Before doing anything, read the following documents from the previous days:

* Product Requirements Document (PRD)
* 10-Day Blueprint
* System Design Documents
* Architecture
* Database Design
* API Design
* Project Structure

These documents are now the source of truth. Do not redesign the project unless a critical issue is discovered. If any document is unavailable, ask me to upload it.

Standing Rules

* Assume I need guidance for every manual step unless I tell you otherwise.
* Whenever I need to perform a task outside this chat, explain it using the exact buttons, menus, commands, and terminal instructions.
* Wait for my confirmation and a screenshot before continuing.
* Never assume I've completed a manual step.
* Explain every technical concept in beginner-friendly language before using it.

Today's Goal

Today's objective is to build the project's foundation. By the end of today I should have:

* Development environment fully configured
* Project running locally
* Complete folder structure
* Git repository initialized and connected
* Dependencies installed
* Configuration files completed
* Database connected (if required)
* Authentication scaffolded (if required)
* Basic navigation/routing working
* A working "Hello World" version of the application running successfully

Do not begin implementing the core features yet unless the Day 2 blueprint specifically schedules a small foundation feature. Follow the Day 3 section of the 10-Day Blueprint while adapting to any issues that arise.

Complete the Following

1. Environment Setup
Guide me through installing and configuring everything required for this project. Examples include:

* Runtime
* IDE extensions
* Package managers
* Framework CLI
* SDKs
* Environment variables

Explain why each tool is needed.

2. Project Initialization
Walk me through:

* Creating the project
* Installing dependencies
* Initializing configuration
* Running the project
* Verifying everything works

3. Repository Setup
If not already completed:

* Connect local project to GitHub
* Create appropriate branches
* Explain the branching strategy
* Make the initial commit

4. Build the Foundation
Implement only the foundational pieces required before feature development. Examples:

* Routing
* Layout
* Navigation
* Authentication scaffold
* Database connection
* API client setup
* Shared components
* State management
* Configuration

Explain every major file that is created.

5. Verify the Project
Confirm that:

* The application builds successfully.
* There are no errors.
* The project structure matches the System Design.
* Everything is ready for feature development tomorrow.

If problems occur, help me debug them before moving on.

Deliverables

Generate downloadable versions of:

* SETUP.md (installation and setup guide)
* PROJECT-STRUCTURE.md (updated if necessary)
* ENVIRONMENT.md (all environment variables, tools, and configuration)
* DAY3-SUMMARY.md

Update the 10-Day Blueprint if today's implementation required any changes.

End of Day

Help me:

* Commit today's work using a meaningful commit message.
* Push it to GitHub.
* Update the project log.
* Write a LinkedIn post summarizing today's progress.

Finally, summarize:

* ✅ What was completed today
* 🚧 What's ready to build tomorrow
* 🎯 What tomorrow's objective will be

Tomorrow should begin implementing the first major user-facing feature, with no additional setup or planning required.


# Youtube:
https://youtu.be/HzMaGLTVV0w?si=aNqECkGoAKRthDiT

# Project Log Update
Day 3 — Project Setup & Foundation (Completed)
- Configured Python venv, installed Flask/SQLAlchemy/Flask-Login/dotenv/anthropic/gunicorn
- Built app.py (app factory), extensions.py, models/user.py
- Created base.html, index.html, style.css — homepage live and styled
- Created .env with SECRET_KEY; .env.example committed as template
- Initialized SQLite database (instance/mediguide.db), confirmed users table
- Verified "Hello World" running at http://127.0.0.1:5000
- Generated SETUP.md, ENVIRONMENT.md, updated PROJECT-STRUCTURE.md, DAY3-SUMMARY.md
- No blueprint changes required; Day 4 (AI Symptom Checker) ready to start immediately

# OUTPUT:

<img width="1920" height="951" alt="Untitled" src="https://github.com/user-attachments/assets/3d7d153e-f460-4ffd-9140-c00c3f6d86e2" />

[SETUP.md](https://github.com/user-attachments/files/30360457/SETUP.md)

[PROJECT-STRUCTURE.md](https://github.com/user-attachments/files/30360456/PROJECT-STRUCTURE.md)

[ENVIRONMENT.md](https://github.com/user-attachments/files/30360452/ENVIRONMENT.md)

[DAY3-SUMMARY.md](https://github.com/user-attachments/files/30360449/DAY3-SUMMARY.md)

<img width="1536" height="1024" alt="ChatGPT Image Jul 25, 2026, 12_59_54 AM" src="https://github.com/user-attachments/assets/851bb28e-f770-4d91-8790-b4bb42e3250c" />

