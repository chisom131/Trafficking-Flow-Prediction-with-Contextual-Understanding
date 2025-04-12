# 🚨 Detection of Human Trafficking Flows Using Machine Learning and NLP

![Python](https://img.shields.io/badge/Python-3.10-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![NLP](https://img.shields.io/badge/NLP-spaCy|GPT--3.5-orange.svg)
![ML](https://img.shields.io/badge/ML-RandomForest|XGBoost-lightgrey.svg)

## 🧠 Project Overview

This project was developed as part of my MSc Data Science dissertation in collaboration with **Stop the Traffik (STT)**, a London-based anti-human trafficking organization. It leverages NLP and supervised machine learning to classify geographic locations in trafficking case narratives as **Source**, **Transit**, or **Destination**. The output aids NGOs and law enforcement in identifying and monitoring trafficking routes more effectively.

---

## 🎯 Objectives

- Extract geopolitical locations from human trafficking narratives.
- Use GPT-3.5-turbo for **context-aware role classification** of each location.
- Train ML models (Random Forest, XGBoost, etc.) on encoded geospatial data.
- Visualize trafficking routes via choropleth maps and bar plots.
- Build a modular and scalable pipeline for real-world deployment.

---

## 🔬 Scope and Impact

- Converts unstructured text into actionable intelligence.
- Enables STT and other NGOs to **prioritize interventions** based on predicted flows.
- Scalable to large corpora (10,000+ articles).
- Supports **real-time classification integration** via APIs in future versions.

---

## 🧰 Tools & Technologies Used

| Tool                  | Purpose                                                  |
|-----------------------|----------------------------------------------------------|
| Python                | Scripting, data analysis, and model integration          |
| spaCy (NER)           | Extracting city/country names (GPEs)                     |
| OpenAI GPT-3.5-turbo  | Contextual classification of location roles              |
| GeoPy + Nominatim     | Standardize city-country pairs                           |
| Scikit-learn          | Preprocessing, model training, and evaluation            |
| Random Forest, XGBoost| Main classifiers for role prediction                     |
| Pandas / NumPy        | Data wrangling and feature engineering                   |
| Plotly / Seaborn      | Visualization of routes and class distributions          |

---

## ⚙️ System Pipeline

```text
Raw Articles → spaCy NER → GPT-3.5 Role Classification
        → GeoPy Geocoding → Categorical Encoding
              → ML Model Training → Trafficking Role Predictions
                         → Visual Insights + Reporting
❌ Tools Considered but Not Used
Tool / Method	Reason for Exclusion
SVM	Poor generalization and high computational cost
Autoencoders	Inadequate semantic inference in this use case
LAMLa	Required larger training corpus; lacked explainability
HuggingFace Transformers	Overhead too high for NER at prototype phase
Google Maps API	Usage limits and non-open-source licensing
📊 Evaluation & Results
Model	Accuracy	Macro F1-Score	Best Parameters
Random Forest	87.9%	0.87	n_estimators=100, max_depth=None
XGBoost	81.8%	0.79	n_estimators=200, max_depth=6
SVC (RBF Kernel)	66.7%	0.65	kernel='rbf', C=10
Logistic Regression	42.4%	0.40	C=10
✅ Best Performer: Random Forest (high generalization, scalable, interpretable)

🧪 Observations & Limitations
GPT-3.5 is powerful but incurs cost & latency at scale — future versions may replace it with fine-tuned LLaMA/Mistral.

GeoPy can struggle with ambiguous or low-population cities.

Imbalanced dataset was mitigated via stratified sampling and SMOTE.

🚀 Future Enhancements
Switch to open-source LLMs for cost-effective, real-time annotation.

Extend classification schema to include more nuanced roles.

Implement REST APIs for integration into analyst dashboards.

Add streamlit or React frontend for real-time case uploads and visualizations.

🫶 Social and Organizational Impact
This project empowers Stop the Traffik (STT) by automating trafficking flow analysis, thus:

Reducing manual workload for analysts.

Accelerating the discovery of emerging trafficking routes.

Helping protect vulnerable populations through faster data-driven intervention.
```
.
├── data/                  # (No sensitive data stored per ethical guidelines)
├── notebooks/             # Jupyter notebooks for EDA and model experiments
├── models/                # Trained ML models (optional)
├── src/                   # Python scripts for NER, GPT calls, ML training
├── visualizations/        # Choropleth maps, label distribution plots
├── docs/                  # Flowcharts, README assets, project report
└── README.md              # This file

📄 License
This project is released under the MIT License.

🤝 Acknowledgements
Special thanks to:

Stop the Traffik for data collaboration and domain insights.

MSc Data Science program, University of Salford.

OpenAI and the open-source Python community.
