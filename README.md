# Azure Fundamentals: Governance forensics and deployment audit trail

## Scenario
A junior intern was granted temporary contributor access to create a test environment but failed to follow several company governance standards due to a lack of familiarity with established procedures. The investigation will assess the potential damage, identify governance and security control failures, and document evidence to determine the impact and required remediation.


## Environment
Live multi-user Azure training tenant

Azur Portal

## Investigation
1. Reviewed Resource Groups

I reviewed the resource groups in the Azure portal and identified one group that did not follow the company’s required naming convention of starting with rg. This indicated a potential governance violation.
<img width="951" height="452" alt="Screenshot 2026-10-27 173411" src="https://github.com/user-attachments/assets/f550437d-9e04-4c0f-99a2-1965f555276b" />

2. Inspected Resource Group Tags

I opened the non-compliant resource group and reviewed its tags. The tags were correctly configured to document the test resources, so the issue appeared to be with naming rather than tagging.
<img width="1518" height="731" alt="Screenshot 2026-10-28 143609" src="https://github.com/user-attachments/assets/8822288f-cf1c-492e-8814-f4c0c2aa1359" />

3. Reviewed Deployment History

I examined the deployment records and identified a deployment associated with the intern. The resource naming provided additional evidence linking the deployment to the test environment created by the intern.<img width="554" height="515" alt="Screenshot 2026-10-28 144246" src="https://github.com/user-attachments/assets/04646391-ff31-4d98-99f9-b2596c4d995c" />

4. Reviewed Azure Policy Compliance

I opened the Azure Policy blade to identify policies responsible for enforcing resource naming standards. I found a policy reporting the naming violation as non-compliant, confirming that the issue was being detected.
<img width="1872" height="538" alt="image" src="https://github.com/user-attachments/assets/8a832710-5989-4138-9151-86d504dd93fe" />

5. Investigated the Non-Compliant Policy

I opened the non-compliant policy to review its configuration. I found that the policy had an unusual name and investigated its parameters to understand how it evaluated resource naming.
<img width="1885" height="595" alt="Screenshot 2026-10-28 145416" src="https://github.com/user-attachments/assets/6c9510c6-48b8-4385-92ec-0905e39eab5d" />

6. Identified the Policy Effect

I reviewed the policy parameters and found that the effect was set to Audit. This allows non-compliant resources to be created while recording violations, explaining why the resource group could exist despite violating the naming standard.<img width="1898" height="599" alt="Screenshot 2026-10-28 150134" src="https://github.com/user-attachments/assets/d94ed5e2-daba-4524-a13c-b03a41799143" />


## What broke / what surprised me
The most credible section in the document. Dead ends, wrong guesses, the thing that took an hour. Employers know real work is messy. This section separates you from certificate collectors.

Challenges and Troubleshooting

Since this was my first time working with Azure, I got lost navigating the portal and had to revisit the instructions several times to figure out what I was missing. I initially struggled to understand terms like blades and Audit, as well as locating the Azure Policy settings and finding the policy's effect type. I made progress by slowing down, carefully rereading the instructions, and checking each step before moving forward. This helped me understand not only where to find the settings but also how the Audit effect allowed non-compliant resources to be created while recording the violation.

## Findings and recommendations
 1. Change the parameters to deny instead of the audit
 2. Make sure that interns are familar w/companies policiec before they area allowed to do any testing
 3. Have a surpersivor check info before its deployed

## What I learned
1. I learn how to navigate through Azura
2. I learn more about audits, perameters, and Policies.
3. What I do differently is to set the policy to deny and not audit
