\# Secret Scanner Demo



\## Overview



This project demonstrates how to automate secret scanning using \*\*Gitleaks\*\*, a free and open-source secret detection tool, integrated with \*\*GitHub Actions\*\*.



The workflow automatically scans the repository for exposed credentials before they become a security risk.



\---



\## Objectives



\* Detect hardcoded secrets in source code

\* Automate security checks during development

\* Prevent accidental credential exposure

\* Demonstrate DevSecOps automation using GitHub Actions



\---



\## Technologies Used



\* GitHub Actions

\* Gitleaks

\* YAML

\* Git

\* PowerShell 7



\---



\## Workflow Triggers



The secret scanning workflow executes automatically under the following conditions:



\* Every push to the `main` branch

\* Every Pull Request

\* Every Monday at 3:00 AM UTC (scheduled scan)

\* Manual execution using `workflow\_dispatch`



\---



\## Project Structure



```text

.

├── .github

│   └── workflows

│       └── gitleaks.yml

├── .gitleaks.toml

└── README.md

```



\---



\## Demonstration



\### Initial Scan



A clean repository successfully completed the GitHub Actions workflow with no secrets detected.



\### Secret Detection



A custom Gitleaks rule was created for demonstration purposes. After adding a matching test secret, the workflow failed as expected, confirming that secret detection was functioning correctly.



\### Remediation



After removing the test secret, the workflow completed successfully, demonstrating proper remediation.



\---



\## Why These Triggers?



\### Push to Main



Scans code before it becomes part of the primary branch.



\### Pull Requests



Detects secrets before they are merged into production code.



\### Weekly Scheduled Scan



Allows older commits to be rescanned as Gitleaks detection rules improve over time.



\### Manual Scan



Enables developers or security teams to perform on-demand security reviews.



\---



\## Security Benefits



\* Prevents credential leakage

\* Automates repository security

\* Integrates directly into CI/CD pipelines

\* Requires no manual intervention after setup

\* Produces consistent and repeatable security checks



\---



\## Future Improvements



\* Slack or Microsoft Teams notifications

\* Automatic issue creation when secrets are detected

\* SARIF upload to GitHub Code Scanning

\* Enterprise policy enforcement

\* Integration with additional security scanners such as Trivy or Semgrep



