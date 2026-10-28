# [Title, outcome-flavored: "Investigating an Identity Attack in Entra ID"]

## Scenario
A junior intern was granted temporary contributor access to create a test environment but failed to follow several company governance standards due to a lack of familiarity with established procedures. The investigation will assess the potential damage, identify governance and security control failures, and document evidence to determine the impact and required remediation.


## Environment
Live multi-user Azure training tenant

Azur Portal

## Investigation
The core. Numbered steps IN YOUR OWN WORDS: what you looked at, what you found, what you concluded at each step. 6 to 12 screenshots of meaningful moments (portal views, query results, before/after).
1. I went to the resources groups and noticed that one of the group names didn't start with rg which is required to have.
<img width="951" height="452" alt="Screenshot 2026-10-27 173411" src="https://github.com/user-attachments/assets/f550437d-9e04-4c0f-99a2-1965f555276b" />

2. Next part I click on was the offending resources group and I looked at the intern tags. The tags were correct and was instructed to the documenting test resources. 
<img width="1518" height="731" alt="Screenshot 2026-10-28 143609" src="https://github.com/user-attachments/assets/8822288f-cf1c-492e-8814-f4c0c2aa1359" />

3. Went to look at the deployment to check on what was deployed and there was one person that did a deployment it was the intern. You can easily tell by how they named the resource.<img width="554" height="515" alt="Screenshot 2026-10-28 144246" src="https://github.com/user-attachments/assets/04646391-ff31-4d98-99f9-b2596c4d995c" />

4. Then I went into the Policy blade to check on the what compliances there is that supposed to enforce the naming that currently is flagged or non compliant 
<img width="1872" height="538" alt="image" src="https://github.com/user-attachments/assets/8a832710-5989-4138-9151-86d504dd93fe" />


## What broke / what surprised me
The most credible section in the document. Dead ends, wrong guesses, the thing that took an hour. Employers know real work is messy. This section separates you from certificate collectors.

## Findings and recommendations
What you determined, plus 2 or 3 recommendations as if you were reporting to the resource owner.

## What I learned
3 to 5 bullets. At least one technical, one "what I'd do differently."
