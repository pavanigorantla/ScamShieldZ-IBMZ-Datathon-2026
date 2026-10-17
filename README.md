# ScamShield Z - IBM Z Datathon 2026

**Theme:** Real-Time AI for Critical Decisions  
**Platform:** IBM LinuxONE Community Cloud  
**Repo:** https://github.com/pavanigorantla/ScamShieldZ-IBMZ-Datathon-2026

## Problem
Digital payment scams trick users into approving transfers themselves (fake KYC, impersonation, mule-account diversion). Because the real user authorizes the payment, rule-based checks often miss it.

## Solution
ScamShield Z is a real-time AI system that scores each payment and returns:
- **ALLOW**
- **WARN USER**
- **HOLD FOR REVIEW**

with plain-language risk reasons.

## Dataset
Primary dataset: **PaySim** (Kaggle) - large-scale synthetic mobile-money transactions with fraud labels, designed to resemble real payment behaviour.  
No real personal banking data is used.

## Why IBM Z / LinuxONE
- In-transaction low-latency scoring
- Secure processing of financial workloads
- Scalable enterprise compute
- AI acceleration support (NNPA/Telum)

## Tech Stack
- IBM LinuxONE (Ubuntu)
- Docker + JupyterLab
- Python, pandas, scikit-learn / XGBoost
- PaySim dataset
- Development assist: Cursor

## Current Status
- LinuxONE environment configured
- Jupyter ML stack running
- Reference labs completed
- Project notebook in progress (`ScamShieldZ.ipynb`)

## Project Structure
- `notebooks/` - main solution notebook
- `data/` - PaySim sample / processed data notes
- `docs/screenshots/` - LinuxONE evidence
- `presentation/` - pitch deck

## Team
- Lead: Pavani Gorantla
- Member 2:
- Member 3:
- Member 4:

## Submission Title Format
`[TeamName_IBM Z Datathon 2026 Project]`
