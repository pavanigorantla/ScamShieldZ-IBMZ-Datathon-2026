# ScamShield Z

**Real-Time, Privacy-Preserving Detection of Payment Scams and Mule Accounts on IBM LinuxONE**

IBM Z Datathon 2026 · Challenge: *Real-Time AI for Critical Decisions*  
Team: **Operation Code**

GitHub: [pavanigorantla/ScamShieldZ-IBMZ-Datathon-2026](https://github.com/pavanigorantla/ScamShieldZ-IBMZ-Datathon-2026)

---

## Problem

A lot of UPI-style scams are not “stolen password” fraud. Someone tricks the person into approving the payment themselves (fake KYC call, wrong-transfer story, etc.). The bank sees it as an authorised payment, money hits a mule account, and it moves out fast. Recovery is hard because classic “I didn’t authorise this” evidence is weak.

## Solution

**ScamShield Z** scores a payment **before** it completes and returns one of three decisions:

| Decision | What happens |
|----------|----------------|
| **ALLOW** | Looks normal → payment goes through (no noisy warning) |
| **WARN** | Medium risk → sender gets a clear warning in **English / Hindi / Telugu** and should confirm carefully |
| **HOLD** | High risk → payment is blocked/delayed; sender gets a short notice; a **bank manager / analyst case** is opened with investigation notes (also EN / HI / TE) |

So we help both the person sending money and the bank team reviewing risky transfers. We treat the case file as **investigation evidence**, not automatic legal proof.

## Why IBM LinuxONE

- We need scoring close to where payments run, inside a tight time window  
- LinuxONE / IBM Z is built for that kind of enterprise workload and on-chip AI acceleration  
- Our prototype runs on **IBM LinuxONE Community Cloud** (Jupyter on s390x, VM `ScamShieldZ`)

## What we built

1. **Data:** PaySim (2M-row sample from the full ~6.3M set)  
2. **Features:** balance/behaviour signals + mule-style **fan-in** (many senders → one receiver)  
3. **Model:** XGBoost with class weighting, 70/15/15 train/val/test, early stopping  
4. **Metrics:** ROC-AUC, PR-AUC, precision / recall / F1 (because fraud is rare)  
5. **Product layer:** ALLOW / WARN / HOLD + multilingual messages + operator queue CSV  
6. **Extras:** latency/TPS check on LinuxONE; model saved as `scamshield_z.json`

PaySim is synthetic, so scores can look very high. The useful part for the datathon is the **decision flow + explanations + analyst queue** running on LinuxONE.

## Repo contents

| Path | Description |
|------|-------------|
| `ScamShieldZ_v3.ipynb` | Main notebook (run on LinuxONE, with outputs) |
| `scamshield_operator_queue.csv` | Sample bank-manager investigation queue |
| `scamshield_z.json` | Exported model |
| `screenshots/` | Setup, labs, and notebook demo screenshots |
| `README.md` | This file |

We did **not** upload `paysim_2m.csv` (too large). Dataset source: Kaggle PaySim (`ealaxi/paysim1`).

## How to run

1. LinuxONE Jupyter up  
2. Upload `paysim_2m.csv` + `ScamShieldZ_v3.ipynb`  
3. Kernel: Python 3  
4. Restart kernel → Run All  
5. Last line should say: `ScamShield Z ready on IBM LinuxONE`

## Team — Operation Code

| Role | Name |
|------|------|
| Team lead | Gorantla Pavani |
| Member | Komal Sakode |
| Member | A Bhuvanesh |
| Member | Mrudul MM |

GitHub (lead): **pavanigorantla**

## License / data

PaySim stays under its original Kaggle license. No real customer banking data was used.
