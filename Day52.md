# Capstone Project — Day 2 of 10
# Day 52
# System Design
# Turn Yesterday's Plan Into a Technical Blueprint

## Today you'll turn yesterday's PRD, Implementation Blueprint, and Pitch Deck into a complete technical design: a justified tech stack, a diagrammed system architecture, a validated database schema, a full API contract, a user flow with wireframes, and a project folder structure — all without writing production code.

1 Source of Truth Discipline: Read yesterday's PRD and Blueprint first and design against them — only deviate if Claude flags a real conflict and you approve the change.
2 Justified Tech Stack: Pick frontend, backend, database, auth, AI/API, and hosting choices with clear reasoning, preferring free tools where possible.
3 Diagrammed Architecture: Get the component diagram, data flow, request lifecycle, and external services mapped out in Mermaid before any implementation starts.
4 Schema and API Before Code: Validate the database schema against every PRD user story and specify every v1.0 endpoint's request, response, validation, auth, and error cases.
5 Day 3 Readiness Check: Catch and cut scope creep now so tomorrow can start building immediately instead of re-planning.

# Prompts:
System Design

Today is Day 2, continuing our chat from Day 1. Read the PRD, Implementation Blueprint, and Pitch Deck created yesterday. These are now the source of truth for the project. Do not redesign or rethink the project unless a critical issue is discovered.

Standing Rules

Whenever I need to perform a manual task outside this chat (creating a GitHub repository, installing software, using Git, configuring dashboards, etc.), stop and give me an exact numbered step-by-step guide using the real names of buttons, menus, fields, and commands.
Wait for my confirmation and a screenshot before moving on.
Do not assume I've completed any manual step.

Today's Goal

Today's objective is to transform the project plan into a complete technical blueprint that makes implementation straightforward.

Do not write production code today.

Follow the Day 2 section of the Implementation Blueprint, but improve it wherever necessary.

If any design decision conflicts with the approved PRD or Implementation Blueprint, explain why and ask for my approval before changing it.

Complete the following

0. Repository Setup

If I don't already have a GitHub repository for this project:

Walk me through creating one.
Clone it locally.
Create the initial project structure.
Explain every step before we continue.

1. Finalize the Tech Stack

Based on the project requirements:

Frontend
Backend
Database
Authentication
AI Model/API (if needed)
Hosting
Other tools or libraries

Explain why each choice is the best fit. Prefer free tools whenever possible.

2. System Architecture

Design the complete architecture. Include:

Component diagram
Data flow
Request lifecycle
AI interaction (if applicable)
External services

Show the architecture using diagrams (Mermaid preferred).

3. Database Design

If the project requires data storage: Design:

Tables / Collections
Fields
Relationships
Constraints

Validate the schema against every user story from the PRD.

4. API Design

List every endpoint required for the v1.0 product. For each endpoint include:

Purpose
Request
Response
Validation
Authentication
Error cases

No implementation yet.

5. UI & User Flow

Design the complete user journey. Include:

User Flow Diagram
Screen Flow
Wireframes (low fidelity is enough)
Navigation

Every screen should exist for a reason.

6. Project Structure

Design the complete folder structure. Explain:

What every major folder is responsible for.
Where future code will live.
Why the structure was chosen.

7. Day 3 Readiness Check

Review the remaining Implementation Blueprint. Confirm that:

The project can realistically be completed within the remaining days.
No unnecessary scope has crept in.
Tomorrow can begin implementation immediately.

If anything should be simplified, recommend it now.

Deliverables

Generate downloadable versions of:

ARCHITECTURE.md
SCHEMA.md
API.md
UI-WIREFRAMES.md
PROJECT-STRUCTURE.md

Also update the Implementation Blueprint if today's design decisions require any changes.

End of Day

Help me:

Commit today's work.
Push it to GitHub.
Update the project log.
Write a LinkedIn post summarizing today's progress.

Tomorrow should begin building immediately, with no additional planning required.

# Youtube:
https://youtu.be/e78ZLeXIkuI

# Output:

<img width="1200" height="627" alt="MediGuide_Day2_Thumbnail" src="https://github.com/user-attachments/assets/c21521e6-510d-4428-92fd-18b53eccdf8b" />

[day 2.txt](https://github.com/user-attachments/files/30341843/day.2.txt)

[UI-WIREFRAMES.md](https://github.com/user-attachments/files/30341863/UI-WIREFRAMES.md)

[SCHEMA.md](https://github.com/user-attachments/files/30341856/SCHEMA.md)

[PROJECT-STRUCTURE.md](https://github.com/user-attachments/files/30341848/PROJECT-STRUCTURE.md)

[ARCHITECTURE.md](https://github.com/user-attachments/files/30341834/ARCHITECTURE.md)

[API.md](https://github.com/user-attachments/files/30341794/API.md)
