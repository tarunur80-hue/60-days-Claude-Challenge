# Capstone Project — Day 4 of 10
# Day 54
# Core Feature Implementation
# Day 4 of 10: One Verified Milestone at a Time

## Today you'll learn how to hold Claude to a strict daily scope from the Blueprint, and how milestone-gated implementation — complete files, your confirmation, then the next milestone — keeps a multi-day build from drifting or breaking silently.

1 Blueprint as Boundary: Only today's Blueprint section gets built — nothing redesigned, nothing from tomorrow started early.
2 Milestone Checkpoints: Each milestone pauses on your screenshot or error report before Claude continues to the next one.
3 Complete Files, No Snippets: Every file Claude generates is the full, final, copy-pasteable version — never a partial diff or TODO.
4 Debug Before Building Further: Any break gets fully resolved before the next milestone starts, so nothing is built on broken code.

# PROMPT:
DAY 4: Core Feature Implementation

Today is Day 4, continuing our chat from the previous days.

Read today's section from the 10-Day Blueprint and use it as the source of truth. Build only the features scheduled for today. Do not redesign the project or start tomorrow's work.

Assume I have zero technical experience unless I tell you otherwise.

Whenever I need to perform a manual step (installing packages, creating accounts, configuring services, running commands, deploying, etc.), stop and give me exact step-by-step instructions using the real button names, menu names, and terminal commands. Wait for my confirmation and a screenshot before continuing.

Prioritize implementation over explanation. Keep explanations brief and practical. Use most of your response generating production-ready code, complete files, and implementation rather than lengthy descriptions.

cut the steps short if they take longer than expected.

Build today's work one milestone at a time.

For each milestone:

Briefly explain what we're building and why.
Show every file that needs to be created, modified, or deleted.
Generate the complete final contents of every required file. Never generate snippets, placeholders, TODOs, "...existing code...", or "add this below..." instructions. Every file must be immediately copy-pasteable.
Clearly state where each file belongs and whether it is new or replaces an existing file.
Provide every command I need to run.
Treat each milestone as a checkpoint. Do not continue until I have added the files, run the project, tested the feature, and sent you a screenshot (or the error if something failed).

If anything breaks, help me debug it completely before moving forward. Never build on top of broken code.

Do not skip implementation because it seems repetitive. If today's work requires 2 files or 50 files, generate all of them completely.

Continue today's implementation across as many responses as necessary until every feature assigned to Day 4 in the Blueprint has been successfully implemented and verified.

When today's implementation is complete:

Verify every feature works as intended.
Update any affected documentation.
Help me review the code if improvements are obvious.
Help me commit and push today's work to GitHub with a meaningful commit message.
If the application is deployable today, guide me through deploying it (Vercel, Netlify, Render, Railway, or the chosen platform), wait for a screenshot of the live application, and verify everything works before ending the session.

Finish with a concise summary of what was completed today and what will be built tomorrow.

Never optimize your response for brevity. Optimize for helping me finish today's implementation.

Your goal is not simply to generate code. Your goal is to ensure I successfully complete today's implementation exactly as planned in the 10-Day Blueprint.

# Youtube:
https://www.youtube.com/watch?v=GnbK-v5rB9s

# Summary:

MediGuide — Day 4 Summary

Core Feature Implementation: AI Symptom Checker | AB Talks 60-Day Claude Challenge Capstone

✅ What Was Completed Today
Symptom Checker feature built end-to-end
/symptom-checker route (GET shows form, POST analyzes and shows results)
Input validation: minimum 3 characters, maximum 1000 characters
Flash messaging for validation errors, redirecting back to the form
AI service layer created (services/ai_service.py)
analyze_symptoms() function with a fixed, stable interface: returns condition, reasoning, severity, otc_suggestion, specialist_type, disclaimer
Currently running in placeholder mode using rule-based keyword matching (see decision note below)
Real Claude API version written and included as ready-to-activate reference code in the same file — swapping it in later requires no changes anywhere else in the app
UI built for both states
templates/symptom_checker.html — input form with loading state
templates/results.html — displays condition, reasoning, OTC suggestion or specialist recommendation, and a mandatory disclaimer box
Severity-based visual treatment: green "MILD" badge vs. orange "NEEDS ATTENTION" badge
Navigation wired
"Symptom Checker" navbar link now points to the real route
"Find Doctors" and "Login" remain placeholders (Day 5+ as scheduled)
Verified working
Mild case (cold symptoms) → correct OTC-suggestion result
Serious case (chest pain/breathing difficulty) → correct specialist recommendation, no OTC suggestion shown
Ambiguous/unmatched input → safely defaults to "see a doctor" rather than guessing — confirms the safety-first fallback behavior works
⚠️ Important Decision Made Today: AI Running in Placeholder Mode

What happened: Setting up the real Claude API required adding paid credits to the Anthropic Console (there is no free tier for the API). After discussing options (add credits vs. switch providers vs. pause), the decision was to pause the real API integration for now and build the full feature with a realistic placeholder so today's milestone could still be completed on schedule.

What this means technically: analyze_symptoms() currently uses keyword-matching rules instead of a real Claude API call. The function's inputs and outputs are identical to what the real version will use, so:

No other file in the app needs to change when the real API is activated
The real Claude API code is already written and included (commented out) directly inside services/ai_service.py, ready to uncomment and use

What's needed to activate the real AI:

Add credits to the Anthropic Console (console.anthropic.com → Billing)
Generate an API key and add it to .env as ANTHROPIC_API_KEY
Swap the placeholder function body for the commented-out real version in services/ai_service.py
No route, template, or other file changes are required

This is a deliberate, reversible scope decision — not a shortcut that compromises the final product. The PRD and Blueprint still call for the real Claude API in the finished v1.0, and this remains fully achievable before Day 10.

🚧 What's Ready to Build Tomorrow (Day 5)
The results page already includes a "Find a Doctor Nearby" button (currently disabled/marked "coming soon") — this becomes fully functional once the doctor directory exists
Homepage and navbar are ready for the "Find Doctors" link to go live
No blockers going into Day 5
🎯 Tomorrow's Objective

Build the Doctor & Hospital Directory (hero feature): create the mock dataset (20-30 doctors/hospitals), the repository/query helper, and the public browsing + filtering UI — exactly as scoped in the PRD and Blueprint.

Files Changed/Added Today
File	Status
app.py	Modified — added /symptom-checker route
services/__init__.py	New
services/ai_service.py	New
templates/symptom_checker.html	New
templates/results.html	New
templates/base.html	Modified — wired Symptom Checker nav link
static/css/style.css	Modified — added form, results, badge, disclaimer styles

# Output:

<img width="1920" height="954" alt="Untitled" src="https://github.com/user-attachments/assets/de77da58-eaca-420f-ab6f-60cdb8aa7e42" />

<img width="1914" height="947" alt="Untitled 3" src="https://github.com/user-attachments/assets/8a3fe595-b7f4-4bf1-9ec6-dfb043041661" />

<img width="1920" height="948" alt="Untitled 2" src="https://github.com/user-attachments/assets/73625e4c-8f66-4d97-a94d-f77ac7c22461" />

<img width="1920" height="947" alt="Untitled 1" src="https://github.com/user-attachments/assets/f01f202c-eab5-4f78-9467-0580c865e5d6" />

[DAY4-SUMMARY.md](https://github.com/user-attachments/files/30370450/DAY4-SUMMARY.md)

