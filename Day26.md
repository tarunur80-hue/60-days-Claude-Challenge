# Business Workflow Simulation with Claude
# Day 26
# Build a Prior Authorization Workflow Simulator
# Learn healthcare workflows through interactive gameplay

## Claude can build complete interactive simulations that teach complex business workflows through visual storytelling and gamification. This project demonstrates how AI can transform complicated healthcare processes into engaging educational experiences.
    
    1 Workflow Simulation: Model real-world healthcare processes interactively.
    2 Gamification: Improve learning through drag-and-drop interactions and progress tracking.
    3 Healthcare Operations: Understand how Prior Authorization works between patients, providers, and insurers.
    4 Interactive Development: Generate fully functional browser applications using Claude.

# PROMPT
Prior Authorization Workflow Simulator (gamified, drag-and-drop)

Build a single-file, self-contained HTML application (HTML + CSS + vanilla JavaScript, no external dependencies, no build step) that visually simulates the US healthcare Prior Authorization (PA) workflow as an interactive, gamified, drag-and-drop experience.

The simulator should include:

• Three workflow lanes: Patient, Provider, and Payer.
• Interactive drag-and-drop movement of cases between stages.
• Multiple patient scenarios (elective surgery, MRI, specialty medication, inpatient admission).
• Medical necessity evaluation.
• Prior Authorization document collection.
• Submission to payer.
• Review outcomes including Approval, Pend, Denial, Appeal, and Peer-to-Peer Review.
• Educational explanations after every step.
• Progress tracker across the top.
• Days elapsed counter.
• Efficiency score.
• Celebration animation on approval.
• Workflow summary on completion.
• Responsive modern UI using shades of blue with black text.
• Working Restart / New Patient button.
• Fully functional buttons and interactions.

Technical Requirements:
- Single HTML file.
- HTML, CSS and Vanilla JavaScript only.
- No frameworks.
- No CDNs.
- No localStorage.
- All workflow state managed in JavaScript memory.
- Well-commented code.
- Scenario data stored in an editable array near the top.
- Output only the complete HTML file without truncation.

  # Output
  
<img width="2720" height="1520" alt="day26_prior_auth_thumbnail" src="https://github.com/user-attachments/assets/53343ead-4c20-4331-beb3-922821ba19fb" />
[prior-auth-simulator.html](https://github.com/user-attachments/files/29388931/prior-auth-simulator.html)

