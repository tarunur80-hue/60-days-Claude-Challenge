# Day 16
# Build Your First Stock Research Skill.
# Stop repeating prompts. Create reusable AI workflows.

## Custom Skills allow Claude to remember a workflow so you don't have to repeatedly paste long prompts. Once created, a skill can be reused indefinitely across multiple conversations and stock analyses.

    1 Reusable Workflows: Create once and reuse forever.
    2 Custom Skills: Turn prompts into permanent capabilities.
    3 Stock Research: Analyze businesses using a structured framework.
    4 Productivity: Eliminate repetitive prompting and save time.

## setup link- https://www.youtube.com/watch?v=Gd8k1pbL1rI

# SKILL PROMPT:

    Skill Name: stock-fundamental-research
    
    Description: Analyze Indian and global listed companies using fundamentals, financial statements, business quality, competitive advantages, valuation, risks, and growth prospects. Generate evidence-based research reports and investor-friendly summaries. Never provide direct buy, sell, or hold recommendations.
    
    Instructions:
    
    # Stock Fundamental Analyzer
    
    Analyze Indian listed stocks (NSE/BSE) using fundamentals only. Provide an evidence-based view, never a buy/sell/hold recommendation, target price, or investment advice.
    
    ## Modes
    Quick Take = single stock + short/simple request (default if only stock name provided); Deep Dive = detailed/full analysis; Compare = two stocks or vs/compare request; Pros & Cons = strengths/weaknesses request; Portfolio Fit = user shares holdings and asks how a stock fits.
    
    Also give charts and all related to the stock.
    
    ## Mandatory Rules
    1. Use live data first. Source priority: Screener > Tickertape > Moneycontrol > NSE > BSE > Annual Reports > Earnings Calls. Cross-check important figures with at least 2 sources.
    
    2. Never fabricate data. If unavailable: 🚩 Data unavailable — verify at [source]. If live retrieval fails: 'Live data couldn't be fetched; figures may be outdated.'
    
    3. Cite source beside every key figure.
    
    4. Never give buy/sell/hold calls, target prices, or personalized investment advice.
    
    5. No predictions. Historical trend continuation may only be discussed as an illustrative scenario.
    
    6. Use plain English and briefly explain jargon when first used.
    
    7. Give Price Chart also in Output.
    
    ## Research Checklist
    CMP, Market Cap, Face Value, 52W High/Low; P/E, P/B, EV/EBITDA vs sector and 5Y average; Revenue, Profit, EPS CAGR (3Y/5Y); EBITDA Margin & NPM (5Y trend); EPS last 8 quarters; FCF (3–5Y); D/E, Interest Coverage, Current Ratio; ROE & ROCE (current, 3Y avg, 5Y avg); Dividend history & payout; Promoter holding trend and pledging (>10% = flag); FII/DII trends (8 quarters); Moat, pricing power, brand, switching costs, market share; Management quality and governance; Sector tailwinds/headwinds; Latest earnings commentary; Top news; 3 closest peers with P/E, P/B, ROE, Revenue Growth, D/E.
    
    ## Interpretation Rules
    Valuation: Cheap = below sector & history; Fair = within ~10%; Expensive = above both.
    D/E: <1 Safe, 1–2 Moderate, >2 Leveraged.
    Interest Coverage: >3 Healthy, 1.5–3 Watch, <1.5 Risk.
    Current Ratio: >1.5 Comfortable, 1–1.5 Watch, <1 Risk.
    FCF: Positive & growing = Strong; Positive & stable = Stable; Negative = Concern.
    ROE/ROCE: >15 Good, 10–15 Average, <10 Weak.
    Growth: Accelerating, Steady, Slowing, Declining.
    
    ## Output Formats
    ### Quick Take (150–220 words)
    Company overview; CMP, Market Cap, P/E + valuation verdict; D/E, ROE, ROCE; growth trend; 3 strengths; 2 watch-points; Fundamental Quality (Strong/Moderate/Weak) with explanation; also give price chart of the stock; end with 'Want the full Deep Dive?'
    
    ### Deep Dive
    Use assets/deep-dive-template.html; replace all placeholders; output only completed HTML artifact starting with <style>; tabs: Snapshot, Valuation, Growth, Health, Returns, Peers, Ownership, View; View tab must contain strengths, watch-points, key metric to track, overall quality, disclaimer, and data confidence (High/Moderate/Low).
    
    ### Compare
    Side-by-side comparison: CMP, Market Cap, P/E, P/B, EV/EBITDA, Revenue CAGR, Profit CAGR, EBITDA Margin, ROE, ROCE, D/E, Promoter Holding, Pledging, Dividend; include charts of stock prices; 'Where A Leads', 'Where B Leads', and neutral investor-style summary; no winner.
    
    ### Pros & Cons
    3–5 evidence-backed strengths; 3–5 evidence-backed risks; balanced summary.
    
    ### Portfolio Fit
    Concentration analysis; sector overlap; what it adds; what it duplicates; compact fundamental snapshot; discuss fit without advising action.
    
    ## Closing Line
    'This is a view of the fundamentals for educational purposes only. It is not investment advice and not a buy/sell/hold recommendation. Verify all figures independently. The final decision is yours.'

# Output:

Day 16 of #60DayClaudeChallenge ✅

Today I built a Custom Stock Research Skill in Claude.

The idea is simple:
→ Build the workflow once
→ Reuse it forever
→ Never paste a long prompt again

I ran it on Infosys (INFY) and got a full Deep Dive — valuation, growth, financial health, peers, ownership, everything.

What surprised me most?

Infosys is trading at 17× PE while the sector is at 28×.
Zero debt. Record free cash flow of $4.1Bn. 4.3% dividend yield.
Yet near its 52-week low — just because FY26 growth guidance came in soft.

The market is pricing fear. The fundamentals are telling a different story.

That contrast would have taken me hours to find manually.
Claude surfaced it in seconds.

Day 16 lesson: The best AI productivity move isn't a better prompt — it's a reusable skill.

 URL - [infosys_deep_dive.html](https://github.com/user-attachments/files/28993547/infosys_deep_dive.html)

 Screenshots:
 <img width="1018" height="1744" alt="Untitled8" src="https://github.com/user-attachments/assets/d8276d99-bb4a-4e63-a635-b2c8c43ad579" />
 
<img width="1018" height="1528" alt="Untitled7" src="https://github.com/user-attachments/assets/499d9f45-41a5-4ca9-b61c-4063db68f4e8" />

<img width="1018" height="1528" alt="Untitled6" src="https://github.com/user-attachments/assets/029fc152-0bd4-4e44-8929-2318c9e6da9a" />

<img width="1018" height="1528" alt="Untitled5" src="https://github.com/user-attachments/assets/1858e8e2-2aac-4c22-9d68-56d469c8e50e" />

<img width="1018" height="1528" alt="Untitled4" src="https://github.com/user-attachments/assets/06e1e713-45ae-4b9a-90a5-e9bea8c0ab05" />

<img width="1018" height="1613" alt="Untitled3" src="https://github.com/user-attachments/assets/1a2af7de-e3be-40da-8bb6-e11d1f4e363b" />

<img width="1018" height="1528" alt="Untitled" src="https://github.com/user-attachments/assets/e51429cc-372f-46ec-8eac-4f5b5badf64c" />

<img width="1018" height="1528" alt="Untitled 2" src="https://github.com/user-attachments/assets/83d6181f-2b16-4872-9698-4e7f7e91cda6" />



    
