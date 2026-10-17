# ScamShield Z - IBM Z Datathon 2026

**Theme:** Real-Time AI for Critical Decisions  
**Platform:** IBM LinuxONE Community Cloud  
**Repo:** https://github.com/pavanigorantla/ScamShieldZ-IBMZ-Datathon-2026

## Problem
Digital payment scams (especially UPI-style scams) trick users into approving payments themselves. Because the real user authorizes the transfer, normal fraud checks often miss it, and money moves to mule accounts quickly.

## Solution
ScamShield Z is an AI system that scores each payment before completion and returns one decision:

- **ALLOW** - looks normal
- **WARN USER** - suspicious, show warning
- **HOLD FOR REVIEW** - high risk, pause for analyst review

It also shows a plain-language reason (example: unusual amount, new payee, many new senders).

## Why IBM Z / LinuxONE
- Real-time scoring needs low latency
- Payment data needs strong security
- LinuxONE provides enterprise compute + AI acceleration (NNPA/Telum)
- Suitable for high-volume transaction workloads

## Tech Stack
- IBM LinuxONE (Ubuntu VM)
- Docker + JupyterLab
- Python, pandas
- scikit-learn / XGBoost
- Development assist: Cursor

## Project Structure
- `notebooks/` - ScamShieldZ notebook
- `data/` - datasets
- `docs/screenshots/` - LinuxONE evidence screenshots
- `presentation/` - pitch deck

## How to Run
1. Start LinuxONE Jupyter Lab
2. Open `notebooks/ScamShieldZ.ipynb`
3. Run all cells
4. Check Allow / Warn / Hold outputs

## Team
- Lead: Pavani Gorantla
- Member 2: Komal Sakode 
- Member 3: Mrudul 
- Member 4: Bhuvanesh

## Submission Title Format
`[TeamName_IBM Z Datathon 2026 Project]`

## Open-source / Resources
- IBM LinuxONE Jupyter ML Lab: https://github.com/linuxone-community-cloud/jupyter-lab-ml
- pandas, scikit-learn, XGBoost (to be linked in final README)
