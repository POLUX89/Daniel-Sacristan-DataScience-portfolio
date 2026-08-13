<img src="./assets/banner.svg" alt="Daniel Felipe Sacristán Ávila — Helicopter Pilot to Data Scientist · 1500+ flight hours" width="100%">

<div align="center">

### 🌐 [**View the live portfolio »**](https://polux89.github.io/Daniel-Sacristan-DataScience-portfolio/)

</div>

---

## 👨‍✈️ About Me

Colombian Air Force captain (UH-60 Black Hawk copilot / UH-1 pilot) transitioning into **data science**. I discovered data while recovering from a stroke — building dashboards to track my own rehabilitation — and turned it into a career path. I bring cockpit discipline to data work: reproducible pipelines, statistical rigor, and clear communication.

---

## 📂 Projects

### 1️⃣ Rehab Strength Dashboard (Streamlit) ✅
**Repo:** [POLUX89/rehab-strength](https://github.com/POLUX89/rehab-strength)  
**Live app:** [rehab-strength.streamlit.app](https://rehab-strength.streamlit.app)  

> 🧪 **Nothing to upload.** The app ships a fully synthetic dataset: one click loads every tab, model and SHAP plot with **zero real health data**. A personal-data dashboard that a stranger can still explore end to end.

Streamlit dashboard integrating **three independent data sources** (workouts, sleep, recovery), with estimated 1RM (Epley), stationarity testing (ADF/KPSS), hypothesis testing, and regression + classification models explained with **SHAP**. CI, tests and a live deployment.

Sleep-quality classification under **5-fold cross-validation**: **ROC-AUC 0.77**, accuracy 0.70.

> **Finding:** that AUC swings from **0.56 to 0.92 across folds** (±0.15) on a small personal sample. The spread is wide enough that the model is **directional, not diagnostic** — reporting the mean alone would overstate it. The same discipline applies to the data itself: no forward-filling, no assumed "today"; delayed data is shown as delayed, which in a rehabilitation context is the difference between a real trend and an artifact.

---

### 2️⃣ NLP – Fake News Colombia ✅
**Repo:** [POLUX89/NLP-Fake-News-Colombia](https://github.com/POLUX89/NLP-Fake-News-Colombia)  
**Live demo:** [beto-colombiacheck.streamlit.app](https://beto-colombiacheck.streamlit.app/)  
**Model:** 🤗 [polux89/beto-colombiacheck](https://huggingface.co/polux89/beto-colombiacheck) *(published on the Hugging Face Hub)*  
**BETO** fine-tuned on **2,935 fact-checks** harvested from ColombiaCheck's **ClaimReview markup** (schema.org JSON-LD), published on the **Hugging Face Hub** with model card, datasheet and data statement. The model input is the *neutral claim* (~10 words), not the headline — the headline states the verdict and would leak the label. Split 70/15/15 frozen by seed; test evaluated once.

> **Finding:** macro-F1 **0.405** vs **0.386** for the TF-IDF baseline (95% bootstrap CI 0.371–0.440) — but the `Verdadero` class scores **0.00**, with only 93 examples in the corpus. It is a `Falso`/`Cuestionable` discriminator, **not a truth detector**, and the model card says so explicitly.

---

### 3️⃣ Energy Price Forecasting – Colombia 🚧
**Repo:** [POLUX89/Forecast-Energy-StockChange-Colombia](https://github.com/POLUX89/Forecast-Energy-StockChange-Colombia)  
**Status:** in progress  
Forecasting Colombia's **hourly wholesale electricity spot price** (*precio de bolsa*) from public **SIMEM/XM** data. A **self-updating pipeline** on GitHub Actions backfilled **1,107,336 raw records into 101,256 continuous hourly observations** since 2015 — **no gaps, no nulls** — and refreshes every morning with no server and no manual step. Ingestion is idempotent; the raw layer keeps every settlement version, accumulating a point-in-time record for honest backtesting.

> **Finding:** XM's settlement versions **don't mature in name order** — the `TX3`+ adjustments are published *after* the `TXF` invoice. Using the naive ordering left **47% of hours stale**. Over 89% of hours are revised by more than 1 COP/kWh between first and definitive version.

---

### 4️⃣ ASRS Rotorcraft NLP – MSc Thesis 🎓
**Status:** in progress — *repository private until defense*  
**NLP** on **NASA ASRS** aviation safety reports: taxonomic coverage of incident narratives in **rotorcraft operations**. Combines transformer-based classification with **disaggregated evaluation**, auditing model output against the ~250 reports covering the aircraft I have flown (UH-60, UH-1) with **1500+ flight hours** of domain expertise. Documented with model card, datasheet and data statement.

> **Finding (by design):** ASRS is **voluntary and self-selected**, so it cannot be used to measure incident rates or compare operators. Stating what the dataset *cannot* answer is part of the thesis, not a footnote.

---

## 🛠 Tech & Tools

- **Python** — pandas, scikit-learn, ETL, statistical testing
- **NLP** — Hugging Face Transformers, BETO, spaCy, web scraping
- **Time series** — forecasting, self-updating ingestion pipelines
- **Streamlit** — interactive dashboards, deployed apps
- **Git & GitHub Actions** — version control, CI, automated pipelines
- **SQL** — querying and data extraction
- **Power BI / Excel** — dashboards, KPIs, modeling

---

## 🔗 Links

- 🌐 Portfolio: [polux89.github.io/Daniel-Sacristan-DataScience-portfolio](https://polux89.github.io/Daniel-Sacristan-DataScience-portfolio/)
- 💼 LinkedIn: [daniel-felipe-sacristán-ávila](https://www.linkedin.com/in/daniel-felipe-sacristán-ávila-b82aa61ab)
- 📧 Email: [sacristandanielfelipe@gmail.com](mailto:sacristandanielfelipe@gmail.com)
