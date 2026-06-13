# Day 13
## Build Your AI Job Search Assistant
## Let Claude find your next opportunity

### Claude Connectors allow Claude to access external information sources and use them for personalized analysis. By connecting Indeed, Claude can help automate job discovery, role matching, opportunity prioritization, and career planning.

     1 Claude Connectors: Connect external platforms directly to Claude.
     2 AI Job Discovery: Automatically find matching opportunities.
     3 Market Analysis: Identify in-demand skills and hiring trends.
     4 Career Planning: Build a smarter job search strategy.

# In this we are using Claude connector with Indeed so that defines and review opportunities and gap analysis.

# PROMPTS 
PROMPT 1: Professional Profile

Describe your professional background, including:

Current role
Years of experience
Key skills and technologies
Industry/domain expertise
Current company type
Current location
Notable achievements, certifications, or accomplishments

PROMPT 2: Job Search Criteria

Specify your target job requirements, including:

Desired job titles
Preferred company types
Preferred locations (Remote/Hybrid/Onsite)
Salary expectations
Industries or companies to exclude
Job posting recency requirements
Any additional preferences or constraints

PROMPT 3: Job Discovery & Analysis

Using my professional profile and job search criteria:

Search for matching job opportunities using the available job connector(s)
Prioritize the highest-fit roles
Exclude jobs that do not meet my requirements
Return the top opportunities in a table containing:

Company
Role
Location
Posted Date
Direct Application Link
Match Score
Why It Fits My Profile
CTC

Also provide:

Most commonly required skills across the jobs
Skill gap analysis
Market demand insights
Recommendations to improve my chances of getting interviews
Overall fit assessment for my target roles and compensation goals.

# OUTPUT:
