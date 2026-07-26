# AI Research & Decision Intelligence
# Day 48
# Build The Verdict Engine
# The AI That Renders a Verdict on Your Toughest Decisions

## Today you'll learn how to build a decision-support application that grounds every claim in real, citable data rather than fabricated numbers, letting users adjust their own priorities and instantly see how the ranked outcome changes.

1 Grounded Research: Force an AI system to cite only real, named sources instead of inventing data points.
2 Weighted Decision Scoring: Let users assign personal priority weights to criteria and see rankings update live.
3 Transparency by Design: Surface sources, estimates, and resolved conflicts openly instead of hiding them.
4 Decision-Support UX: Design a premium, responsive interface for comparing real-world options.

# Prompts:

Compare & Decide Builder

You are an expert research analyst, data journalist, UX designer, and frontend developer.

Before generating anything, interview the user ONE QUESTION AT A TIME in quiz form (MCQs only).

1. What are you trying to decide between? (Ask for the general category, then present four realistic examples of comparable options in that category.)
2. Who is this tool for, and what's the one decision they need to walk away confident about?
3. What criteria matter in this comparison? (Ask for at least four measurable criteria, e.g. cost, time, risk, quality, availability.)
4. Where should the underlying data come from? (Ask the user to name at least two real, citable sources per criterion, or confirm you should research and cite real sources yourself.)
5. Should the user be able to weight criteria by personal priority, or see one fixed ranking?

After collecting the answers:

1. Research and verify real data points for each option against each criterion, using only sources you can name and cite. Do not invent numbers, benchmarks, or scores.

2. Build a premium single-file HTML application (HTML/CSS/JavaScript only, no external libraries) that lets the user adjust criteria weights and see a ranked result update live.

The application should:
- Display a visible sources panel listing every citation used.
- Flag clearly if any data point is an estimate or a synthetic placeholder rather than sourced fact.
- Handle loading states, empty states, and edge cases gracefully.
- Be fully responsive with clean, professional visual design.

3. Add a collapsible "How this was researched" panel explaining where each data point came from and any conflicts between sources you had to resolve.

Generate the complete application only after all interview questions have been answered.

Return ONLY the complete HTML inside one code block.

# Youtube:

https://youtu.be/FZW0-4RuDms

# Output:
