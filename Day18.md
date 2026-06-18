# Day 18
# Build a Brain Dump Action Planner Skill
# Transform chaos into clarity using Claude Skills

## Skills allow Claude to remember complex workflows. Instead of manually organizing notes every time, you can create a reusable skill that automatically transforms unstructured information into project dashboards, action plans, and decision logs.
    
    1 Reusable Workflows: Create once and use forever.
    2 Information Management: Convert messy notes into structured outputs.
    3 Project Planning: Generate action plans, risks, and decisions automatically.
    4 Productivity: Reduce manual organization work significantly.

# Sample Resource: [pdf.pdf](https://github.com/user-attachments/files/29104849/pdf.pdf)

# Prompt:

Skill Name: brain-dump-action-planner

Description: Transform messy notes, meeting transcripts, voice memos, brainstorming sessions, and stream-of-consciousness thoughts into structured summaries, action plans, decisions, open questions, and task lists. Organize information clearly without inventing, assuming, or filling gaps. Preserve all names, dates, numbers, and terminology exactly as provided.

Instructions:

## Output Requirement

For Full Breakdown, Transcript Mode, and Merge Mode, generate the output as a complete interactive HTML artifact.

Requirements:

* Output a self-contained HTML artifact starting with <style>.
* Use a modern dashboard layout.
* Mobile responsive.
* Use cards, sections, badges, tables, and visual indicators.
* Do not use markdown.
* Use clean typography and strong visual hierarchy.
* Highlight important items using colored status badges.
* Make action items visually prominent.
* Use collapsible sections for long notes.
* Output only the HTML artifact.

### Required Sections

1. Summary

* Short overview of the note, meeting, transcript, or brain dump.

2. Key Takeaways

* Display as cards or structured highlights.

3. Action Items

* Interactive table containing:
* Task
* Owner
* Deadline
* Status

4. Open Questions

* Display unresolved topics and pending decisions.

5. Risks / Blockers

* Display dependencies, blockers, risks, and concerns.

6. Conflicts

* Display conflicting deadlines, owners, decisions, or information.

7. Additional Notes

* Supporting context that does not fit elsewhere.

8. Source Information (Merge Mode only)

* Display merged sources.

### Status Badges

Use:

* 🔴 High Priority
* 🟠 Medium Priority
* 🟢 Low Priority
* ⚠️ Conflict
* ❓ Open Question
* ✅ Completed
* ⏳ Pending

### Missing Information

If information is missing display:

'Not specified'

Never invent values.

### Transcript Mode

Include:

* Speaker Summary
* Decisions by Speaker
* Action Items by Speaker
* Attribution Notes when ownership is unclear

Use speaker labels exactly as provided.

### Merge Mode

Include:

* Duplicate Items Section
* Conflict Resolution Review Section
* Source Note

Never automatically resolve conflicts.

### Design Goals

The final artifact should feel like:

* Notion
* ClickUp
* Linear
* Asana
* Airtable
* Modern Project Dashboard

Use responsive cards, clean tables, section headers, badges, hover effects, soft shadows, and dashboard-style layouts.

Everything displayed must come directly from the provided notes.

Never add, infer, assume, predict, estimate, or complete missing information.

Generate the complete HTML directly starting with <style>.

# Output:
[quarterly_growth_strategy_dashboard.html](https://github.com/user-attachments/files/29105275/quarterly_growth_strategy_dashboard.html)
[dashboard.html](https://github.com/user-attachments/files/29105274/dashboard.html)

   
