<div align="center">

# Sargam Sahu

**AI/ML Engineer · Applied Research · Software Engineering**

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=18&pause=1200&center=true&vCenter=true&width=700&lines=LLM+reliability+and+evaluation;Hallucination+detection+in+coding+models;Calibrated+ML+systems+that+ship;Research+deeply.+Build+practically.+Measure+honestly." alt="Typing SVG" />

<p>
  <a href="https://arxiv.org/abs/2608.23897"><img src="https://img.shields.io/badge/arXiv-2608.23897-B31B1B?style=flat-square&logo=arxiv&logoColor=white"></a>
  <a href="https://linkedin.com/in/sargamsahu1011"><img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin&logoColor=white"></a>
  <a href="https://github.com/sargamsahu1011"><img src="https://img.shields.io/badge/GitHub-Follow-181717?style=flat-square&logo=github&logoColor=white"></a>
</p>

</div>

---

I work on **making language models trustworthy enough to deploy** — measuring where they fail, building detectors for those failures, and shipping the result as software someone can actually use.

Most recently: a first-author-adjacent arXiv paper on package-name hallucinations in local coding LLMs, and a calibrated scam-detection system where I cared as much about the Brier score as the F1.

B.Tech CSE @ JUET (2024–2028). **Open to AI/ML, applied research, and software engineering roles and internships.**

---

## Research

### Names Can Hurt: Spotting Slopsquatting Risks Caused by Package Name Hallucinations in Local Coding LLMs

*Akash Raj, Sargam Sahu* — [arXiv:2608.23897](https://arxiv.org/abs/2608.23897) · 2026

Local coding LLMs invent package names that don't exist. Attackers register those names. We measured how often it happens, built a classifier to catch it, and tested whether developers actually notice.

```text
Coding prompt → Coding LLM → Generated import
                                    ↓
                        PyPI existence + metadata check
                                    ↓
                     Name & metadata feature extraction
                                    ↓
                          Random Forest classifier
                                    ↓
                            Risk classification
```

| | |
| --- | --- |
| Curated prompts | **300** |
| Hallucination-free generations | **76%** |
| Unmitigated failure rate | **79% → 28.7%** |
| User study participants | **24** |

**Contributions:** dataset curation · PyPI metadata pipeline · name-based feature engineering · classifier training and evaluation · user-study analysis

---

### Cross-Model Hallucination Detection

A companion system for the harder half of the problem: an import name is not a package name, so naive PyPI lookups produce false alarms on perfectly valid code.

```text
LLM output:  import cv2
                  ↓
           Package resolver          cv2 ≠ opencv-python
                  ↓                         ↓
          PyPI verification  ──→  Name reconciliation
                                            ↓
                                     Risk detection
```

Reconciles Python import names against their true distribution names, then combines registry verification with ML scoring so real packages aren't flagged and hallucinated ones aren't missed.

---

## Engineering

### JobShield AI — Fake Job & Scam Detection

Classifies suspicious job postings, extracts the evidence behind the call, and generates a grounded explanation instead of an opaque score.

```text
Job posting → Preprocessing → ┌──────────────────────────┐
                              │ TF-IDF + LogReg (Platt)  │
                              │ DistilBERT (control)     │
                              └───────────┬──────────────┘
                                          ↓
                    Scam-signal rules → Evidence extraction
                                          ↓
                          LLM explanation → Risk assessment
```

**Held-out evaluation** — 17,880 postings, leakage-controlled splits

| Metric | Result |
| --- | ---: |
| Precision | **96.63%** |
| Recall | **80.37%** |
| F1 | **87.76%** |
| Brier score | **0.01236** |
| ECE | **0.76%** |

The calibration numbers matter more than the F1 here: a fraud tool that says *"87% likely scam"* has to mean it. Platt scaling brought expected calibration error under 1%, and DistilBERT ran as a control to confirm the linear model wasn't leaving accuracy on the table.

**Stack:** Python · scikit-learn · Transformers · Flask REST API · React + Vite
**Also built:** rule-based scam-signal layer, evidence extraction, prompt-injection defense testing

---

## Experience

**AI Research Intern** — Kruman Corporations · *May 2026 – Jul 2026*
LLM package-hallucination detection, PyPI metadata analysis, ML classification, LangGraph workflows, Streamlit delivery, research evaluation.

**Frontend Web Development Intern** — Kruman Corporations · *Jun 2025 – Jul 2025*
Built and deployed the company's [production website](https://krumancorporations.netlify.app/) and AI-integrated web experiences. HTML5 · CSS3 · JavaScript · Tailwind · Netlify

---

## Stack

| | |
| --- | --- |
| **Languages** | Python · Java · C++ · JavaScript · SQL |
| **ML / DL** | scikit-learn · TensorFlow · Transformers · pandas · NumPy |
| **Methods** | Logistic Regression · Random Forest · TF-IDF · DistilBERT · Platt calibration · Explainable AI |
| **LLM engineering** | LangGraph · prompt engineering · LLM evaluation · agentic workflows · prompt-injection testing |
| **Software** | Flask · React · Vite · REST APIs · Streamlit · Git/GitHub · Agile/SDLC |

<p align="center">
<img src="https://skillicons.dev/icons?i=python,java,cpp,js,mysql,react,vite,flask,tailwind,git,github" />
</p>

---

## Writing

- **Designing AI SaaS Websites: A Strategic Guide Inspired by Leading AI Companies** — trust signals, clarity, and how AI products present capability without overclaiming.
- **Designing AI Demos for Business: A Practical Guide Using Streamlit and Modern Web Integration** — turning ML systems into demos non-engineers can evaluate.

---

## Beyond the code

**Coordinator, Code Conquerors Programming Club** — ran contests and DSA workshops for 100+ students; volunteer → coordinator in 5 months.
**Coordinator, Training & Placement Cell / BITWISE** — placement activities, technical events, recruiter coordination.

**Certifications:** Deloitte Australia Technology Virtual Experience · Certificate of Merit, Kodeathon · Hacktron Hackathon · Certificate of Appreciation, ICMME 2025

---

<div align="center">

<br><br>

***Research. deeply. Build practically. Measure honestly.***

</div>
