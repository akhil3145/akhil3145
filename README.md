<!--
  Assets required in this repo (akhil3145/akhil3145):
    assets/divider.svg
    assets/terminal.svg
  Everything else loads from public services or from your project repositories.
-->

<h1 align="center">Hi, I'm Akhil Pandey 👋</h1>

<p align="center">
  <b>AI/ML Developer · Building Intelligent Systems · Python &amp; Full-Stack Engineering</b>
</p>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=500&size=17&duration=3200&pause=1100&color=0891B2&center=true&vCenter=true&width=640&height=36&lines=Building+Intelligent+Systems;Exploring+Machine+Learning+%26+Generative+AI;Python+%E2%80%A2+AI+Engineering+%E2%80%A2+Full-Stack+Development;Turning+Ideas+Into+Working+Software" alt="Animated tagline: building intelligent systems, exploring machine learning and generative AI, Python, AI engineering and full-stack development" />
</p>

<p align="center">
  I'm a fourth-year B.Tech student in Data Science &amp; AI at SRMU, Lucknow, building AI-powered software end to end:
  from model training and evaluation to FastAPI backends and React interfaces. My strongest work so far pairs deep
  learning with explainability and monitoring, because a model is only useful if you can understand how it behaves.
</p>

<p align="center">
  <a href="#about"><img src="https://img.shields.io/badge/About-172338?style=flat-square" alt="Jump to About" /></a>
  <a href="#projects"><img src="https://img.shields.io/badge/Projects-172338?style=flat-square" alt="Jump to Projects" /></a>
  <a href="#tech-stack"><img src="https://img.shields.io/badge/Tech_Stack-172338?style=flat-square" alt="Jump to Tech Stack" /></a>
  <a href="#experience"><img src="https://img.shields.io/badge/Experience-172338?style=flat-square" alt="Jump to Experience" /></a>
  <a href="#github-analytics"><img src="https://img.shields.io/badge/GitHub_Analytics-172338?style=flat-square" alt="Jump to GitHub Analytics" /></a>
  <a href="#dsa"><img src="https://img.shields.io/badge/DSA-172338?style=flat-square" alt="Jump to DSA" /></a>
  <a href="#contact"><img src="https://img.shields.io/badge/Contact-172338?style=flat-square" alt="Jump to Contact" /></a>
</p>

<p align="center">
  <a href="https://github.com/akhil3145"><img src="https://img.shields.io/badge/GitHub-akhil3145-0891B2?style=flat-square&logo=github&logoColor=white&labelColor=111827" alt="GitHub profile: akhil3145" /></a>
  <a href="https://www.linkedin.com/in/akhil3145"><img src="https://img.shields.io/badge/LinkedIn-akhil3145-0891B2?style=flat-square&logo=linkedin&logoColor=white&labelColor=111827" alt="LinkedIn profile: akhil3145" /></a>
  <a href="mailto:akhilpandey1000@gmail.com"><img src="https://img.shields.io/badge/Email-akhilpandey1000%40gmail.com-0891B2?style=flat-square&logo=gmail&logoColor=white&labelColor=111827" alt="Email: akhilpandey1000@gmail.com" /></a>
</p>

<img src="assets/divider.svg" width="100%" height="12" alt="" />

## About

- **Education:** B.Tech in Computer Science (Data Science & AI), Shri Ramswaroop Memorial University, Lucknow. Fourth year, graduating 2027.
- **Direction:** Aspiring AI/ML engineer building end-to-end AI applications, from model to API to interface.
- **Exploring now:** Advanced ML, LLM applications, RAG and backend engineering.
- **Practice:** Data structures and algorithms in Python.
- **Open to:** AI engineering and software development opportunities.

<p align="center">
  <img src="assets/terminal.svg" width="760" alt="Decorative terminal panel: whoami akhil-pandey; focus AI Engineering, Machine Learning, Generative AI; current-project Vistara AI; status Building. Learning. Improving." />
</p>

<img src="assets/divider.svg" width="100%" height="12" alt="" />

## Projects

Each project shows the essentials first. Expand **Architecture & details** for the engineering behind it.

### 1. Vistara AI

<a href="https://github.com/akhil3145/vistara-ai"><img src="https://github.com/akhil3145/vistara-ai/raw/main/docs/screenshots/scanner.png" width="720" alt="Vistara AI scanner page with ranked top-5 leaf disease predictions" /></a>

**Plant disease screening with MobileNetV2, Grad-CAM explainability and monitoring.** Team project.

<img src="https://skillicons.dev/icons?i=python,tensorflow,fastapi,react,ts,tailwind,sqlite" height="36" alt="Python, TensorFlow, FastAPI, React, TypeScript, Tailwind CSS, SQLite" />

<sub>Python · TensorFlow/Keras · MobileNetV2 · FastAPI · Pydantic v2 · React 19 · TypeScript · Vite · Tailwind CSS · SQLite</sub>

**[Repository](https://github.com/akhil3145/vistara-ai)** · No hosted demo (runs locally)

<details>
<summary><b>Architecture &amp; details</b></summary>

<br />

Classifies a leaf image into one of **38 PlantVillage classes across 14 crop species**. A scan returns ranked scores, a Grad-CAM overlay, latency and telemetry, with a clear distinction between a live backend response and a demo preview.

```mermaid
flowchart LR
  UI["React + TypeScript dashboard"] --> API["FastAPI REST API"]
  API --> V["Validate + preprocess to 224x224"]
  V --> M["MobileNetV2 classifier, 38 classes"]
  M --> R["Top-5 scores"]
  M --> G["Grad-CAM overlay"]
  API --> T["Telemetry service"]
  T --> DB[("SQLite")]
  DB --> API
```

**Features**
- Single-image upload with type and size validation, ranked top-5 predictions and a server-generated Grad-CAM overlay
- Batch analysis of up to 24 images with per-file status, accepted/rejected counts and filter-aware CSV export
- Monitoring dashboard: request volume, class distribution, mean score, p50/p95 latency and recent events
- Model evaluation report read from a stored artifact, plus a searchable library of the 38 classes
- Typed API boundary: Pydantic v2 contracts with explicit error codes

**Evaluation (PlantVillage held-out split, controlled benchmark)**
- 98.04% test accuracy on 8,146 test images; macro F1 97.47%
- Weakest class in the stored report: corn gray leaf spot (F1 0.8514)
- These figures are not field-condition accuracy

**Engineering considerations documented in the repo**
- A Grad-CAM failure never blocks a prediction
- If the model can't load, the API returns `model_unavailable` instead of fabricated scores
- Drift status is reported as unavailable until a verified baseline distribution exists
- Class order in `classes.json` must match the trained model, or labels are silently wrong

**Limitations:** closed-set 38-class model, scores are not calibrated probabilities, model artifacts are not committed, no authentication or production deployment configuration. Educational decision-support software, not a diagnostic tool.

**Screenshots:** [Overview](https://github.com/akhil3145/vistara-ai/blob/main/docs/screenshots/overview.png) · [Scanner](https://github.com/akhil3145/vistara-ai/blob/main/docs/screenshots/scanner.png) · [Grad-CAM](https://github.com/akhil3145/vistara-ai/blob/main/docs/screenshots/gradcam.png) · [Batch](https://github.com/akhil3145/vistara-ai/blob/main/docs/screenshots/batch.png) · [Monitoring](https://github.com/akhil3145/vistara-ai/blob/main/docs/screenshots/monitoring.png) · [Model report](https://github.com/akhil3145/vistara-ai/blob/main/docs/screenshots/model-report.png)

</details>

### 2. Orchestrix

**AI-native HR platform: policy Q&A with RAG, resume screening and workforce analytics.**

<img src="https://skillicons.dev/icons?i=python,fastapi,sqlite,pandas" height="36" alt="Python, FastAPI, SQLite, Pandas" />

<sub>Python · FastAPI · Streamlit · LangChain · Pinecone · Claude / Ollama · SQLite · Pandas · Plotly · pypdf</sub>

**[Repository](https://github.com/akhil3145/Orchestrix)** · No hosted demo

<details>
<summary><b>Architecture &amp; details</b></summary>

<br />

Combines deterministic HR workflows with LLM-powered assistance in one dashboard. Capabilities below are as described in the repository README.

```mermaid
flowchart TD
  UI["Streamlit dashboard"] --> API["FastAPI layer"]
  API --> AI["AI orchestration: LangChain, Claude, Ollama"]
  AI --> KB["Policy knowledge base: Pinecone RAG"]
  AI --> RE["Resume engine: ATS-style scoring"]
  API --> D["Employee data, analytics, SQLite"]
```

**Features**
- AI HR assistant with multi-route query handling, designed around Claude with a local fallback
- Resume intelligence: PDF parsing, ATS-style scoring, skill extraction, candidate ranking and downloadable reports
- HR policy retrieval and semantic search using RAG over a Pinecone index
- Workforce analytics: headcount, department insights, leave utilization and AI-generated summaries
- Employee operations: leave balances, payroll previews and HR request workflows

**Roadmap listed in the repo:** PostgreSQL migration, more advanced RAG pipelines, candidate-job matching, multi-tenant architecture.

**Status:** documented architecture and roadmap; no hosted demo.

</details>

### 3. PitchPilot <img src="https://img.shields.io/badge/status-in_development-A78BFA?style=flat-square&labelColor=172338" alt="Status: in development" />

**AI outreach generator for cold emails, LinkedIn DMs and follow-ups.**

> Adapted from the open-source starter [ShivaMani02/AI-COLD-MAIL-GENERATOR-MONOREPO](https://github.com/ShivaMani02/AI-COLD-MAIL-GENERATOR-MONOREPO). I'm customizing it to learn authentication, LLM integration and Docker, so it is a learning project, not entirely original work.

<img src="https://skillicons.dev/icons?i=react,vite,tailwind,nodejs,express,mongodb,docker" height="36" alt="React, Vite, Tailwind CSS, Node.js, Express, MongoDB, Docker" />

<sub>React · Vite · Tailwind CSS · Node.js · Express · MongoDB · Groq API · JWT · Nodemailer · Docker</sub>

**[Repository](https://github.com/akhil3145/PitchPilot)** · No hosted demo

<details>
<summary><b>Architecture &amp; details</b></summary>

<br />

```mermaid
flowchart LR
  C["React + Vite client"] --> S["Express API"]
  S --> DB[("MongoDB")]
  S --> G["Groq API"]
  S --> E["Nodemailer"]
```

**In the codebase**
- Generation of outreach messages through the Groq API
- Signup, login and OTP verification flows with JWT and bcrypt
- MongoDB models for users and email history
- Dockerfiles and a Docker Compose configuration

**Roadmap (from the repo):** verify MongoDB connectivity, test auth and OTP end to end, test Groq generation and email delivery, add automated tests and a CI workflow, then verify deployment.

**Status:** under active development; some features and deployment settings still need end-to-end testing.

</details>

### 4. ML Studio

<a href="https://github.com/akhil3145/ml_studio_codeveda"><img src="https://github.com/akhil3145/ml_studio_codeveda/raw/main/screenshots/dashboard.png.png" width="720" alt="ML Studio dashboard for uploading a dataset, training a model and making predictions" /></a>

**Browser-based ML workflow: upload a CSV, train a model, review metrics, predict.**

<img src="https://skillicons.dev/icons?i=python,fastapi,sklearn,pandas,numpy,react,vite" height="36" alt="Python, FastAPI, scikit-learn, Pandas, NumPy, React, Vite" />

<sub>Python · FastAPI · scikit-learn · Pandas · NumPy · React · Vite · Axios</sub>

**[Repository](https://github.com/akhil3145/ml_studio_codeveda)** · [Live demo](https://ml-studio-frontend-xe8i.onrender.com) <sub>(may take a moment to wake up)</sub>

<details>
<summary><b>Architecture &amp; details</b></summary>

<br />

```mermaid
flowchart LR
  FE["React + Vite"] -->|"HTTP / JSON"| BE["FastAPI"]
  BE --> ML["Pandas, NumPy, scikit-learn"]
```

**Features**
- CSV upload with dataset inspection (rows, columns, feature and target columns)
- Training routes for KNN, logistic regression, decision tree, random forest and linear regression
- Accuracy and training metrics shown in the dashboard, with loading and status feedback
- Prediction interface (a KNN prediction route is documented)

**Implementation notes**
- One route module and one model module per algorithm, plus a shared dataset service, keeps each workflow modular
- A preprocessing route and module are included in the backend

**Roadmap listed in the repo:** model persistence, more evaluation metrics, confusion matrices, hyperparameter tuning, prediction for all trained model types.

</details>

### 5. LearnFlow

**Turns a YouTube video or playlist into a structured, trackable bootcamp-style course.**

<img src="https://skillicons.dev/icons?i=js,react,vite,nodejs,express" height="36" alt="JavaScript, React, Vite, Node.js, Express" />

<sub>JavaScript · React · Vite · Node.js · Express · YouTube Data API v3</sub>

**[Repository](https://github.com/akhil3145/LMS_2.o)** · [Live demo](https://lms-2-o.vercel.app)

<details>
<summary><b>Architecture &amp; details</b></summary>

<br />

```mermaid
flowchart LR
  U["React + Vite client"] -->|"video or playlist URL"| S["Express API"]
  S --> Y["YouTube Data API v3"]
  U --> L[("Browser localStorage")]
```

**Features**
- Converts playlists into multi-module courses and splits long videos into sections
- A lesson can only be marked complete after 90% watch progress
- Course progress as a completion percentage, with a dashboard of bootcamp cards
- Interactive course player with sidebar navigation

**Implementation notes**
- The backend generates the bootcamp structure; the frontend saves the user, bootcamps and completed lessons in `localStorage`, so progress resumes in the same browser
- No authentication or database yet (both listed on the roadmap, along with AI summaries and chapter titles)

</details>

### 6. Strenzz

**A no-account, no-build strength tracker I made for my own training.**

<img src="https://skillicons.dev/icons?i=js,html,css" height="36" alt="JavaScript, HTML, CSS" />

<sub>Vanilla JavaScript · HTML · CSS · Chart.js · localStorage</sub>

**[Repository](https://github.com/akhil3145/strenzz)**

<details>
<summary><b>Architecture &amp; details</b></summary>

<br />

**Features**
- Lift logging: exercise, weight, sets, reps and notes
- Progress graphs by week, month or all time
- Strength rank: percentile comparison against general lifting standards for your bodyweight
- Calculators: one-rep max estimator, BMI and body fat percentage (Navy method)

**Implementation notes**
- Single `index.html`, no framework and no build step; Chart.js is loaded from a CDN
- All data stays in the browser's `localStorage`; nothing is sent anywhere
- Planned: CSV export, bodyweight tracking over time, custom exercise names, installable PWA

</details>

### More on GitHub

- **[Wbot](https://github.com/akhil3145/Wbot):** my first LLM application, a Python chatbot built on Groq's Llama 3 API.
- **[Titanic classification](https://github.com/akhil3145/titanic-classification-algorithms):** five scikit-learn classifiers compared on the Titanic dataset.

<img src="assets/divider.svg" width="100%" height="12" alt="" />

## Tech Stack

<table>
  <tr>
    <td><b>Languages</b></td>
    <td><img src="https://skillicons.dev/icons?i=python,js,ts,html,css" alt="Python, JavaScript, TypeScript, HTML and CSS" /></td>
  </tr>
  <tr>
    <td><b>AI &amp; ML</b></td>
    <td><img src="https://skillicons.dev/icons?i=tensorflow,sklearn,pandas,numpy" alt="TensorFlow, scikit-learn, Pandas and NumPy" /></td>
  </tr>
  <tr>
    <td><b>Backend</b></td>
    <td><img src="https://skillicons.dev/icons?i=fastapi,nodejs,express" alt="FastAPI, Node.js and Express" /></td>
  </tr>
  <tr>
    <td><b>Frontend</b></td>
    <td><img src="https://skillicons.dev/icons?i=react,vite,tailwind" alt="React, Vite and Tailwind CSS" /></td>
  </tr>
  <tr>
    <td><b>Databases</b></td>
    <td><img src="https://skillicons.dev/icons?i=sqlite,mongodb" alt="SQLite and MongoDB" /></td>
  </tr>
  <tr>
    <td><b>Tools</b></td>
    <td><img src="https://skillicons.dev/icons?i=git,github,vscode" alt="Git, GitHub and VS Code" /></td>
  </tr>
  <tr>
    <td><b>Learning</b></td>
    <td><img src="https://skillicons.dev/icons?i=docker" alt="Docker" /></td>
  </tr>
</table>

<details>
<summary><b>Where I've used each tool</b></summary>

<br />

- **TensorFlow / Keras, MobileNetV2, Grad-CAM:** Vistara AI
- **scikit-learn, Pandas, NumPy:** ML Studio, Titanic classification (Matplotlib and Jupyter / Colab as well)
- **FastAPI, Pydantic:** Vistara AI, Orchestrix, ML Studio
- **LangChain, Pinecone (RAG), Streamlit, Plotly:** Orchestrix
- **Groq API (Llama 3):** Wbot, PitchPilot
- **React, Vite:** Vistara AI, ML Studio, LearnFlow, PitchPilot (TypeScript and Tailwind CSS in Vistara AI)
- **Node.js, Express:** LearnFlow, PitchPilot
- **SQLite:** Vistara AI, Orchestrix
- **MongoDB, Docker (still learning):** PitchPilot
- **Vanilla JavaScript, Chart.js:** Strenzz

</details>

<img src="assets/divider.svg" width="100%" height="12" alt="" />

## Experience

- **Machine Learning Engineering Intern**, Codveda Technologies. Project work: [ML Studio](https://github.com/akhil3145/ml_studio_codeveda).
- **Intern**, InternPe.

<img src="assets/divider.svg" width="100%" height="12" alt="" />

## GitHub Analytics

<p align="center">
  <a href="https://github.com/akhil3145">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api?username=akhil3145&show_icons=true&hide_border=true&hide_rank=true&bg_color=0D1117&title_color=22D3EE&icon_color=A78BFA&text_color=E5E7EB" />
      <source media="(prefers-color-scheme: light)" srcset="https://github-readme-stats.vercel.app/api?username=akhil3145&show_icons=true&hide_border=true&hide_rank=true&bg_color=FFFFFF&title_color=0891B2&icon_color=7C3AED&text_color=1F2937" />
      <img width="49%" alt="GitHub statistics for akhil3145" src="https://github-readme-stats.vercel.app/api?username=akhil3145&show_icons=true&hide_border=true&hide_rank=true&bg_color=0D1117&title_color=22D3EE&icon_color=A78BFA&text_color=E5E7EB" />
    </picture>
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api/top-langs/?username=akhil3145&layout=compact&langs_count=6&hide_border=true&bg_color=0D1117&title_color=22D3EE&text_color=E5E7EB" />
      <source media="(prefers-color-scheme: light)" srcset="https://github-readme-stats.vercel.app/api/top-langs/?username=akhil3145&layout=compact&langs_count=6&hide_border=true&bg_color=FFFFFF&title_color=0891B2&text_color=1F2937" />
      <img width="49%" alt="Most used languages across akhil3145's public repositories" src="https://github-readme-stats.vercel.app/api/top-langs/?username=akhil3145&layout=compact&langs_count=6&hide_border=true&bg_color=0D1117&title_color=22D3EE&text_color=E5E7EB" />
    </picture>
  </a>
</p>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com?user=akhil3145&hide_border=true&background=0D1117&ring=22D3EE&fire=A78BFA&currStreakNum=E5E7EB&sideNums=E5E7EB&currStreakLabel=22D3EE&sideLabels=9CA3AF&dates=9CA3AF" />
    <source media="(prefers-color-scheme: light)" srcset="https://streak-stats.demolab.com?user=akhil3145&hide_border=true&background=FFFFFF&ring=0891B2&fire=7C3AED&currStreakNum=1F2937&sideNums=1F2937&currStreakLabel=0891B2&sideLabels=6B7280&dates=6B7280" />
    <img width="70%" alt="GitHub contribution streak for akhil3145" src="https://streak-stats.demolab.com?user=akhil3145&hide_border=true&background=0D1117&ring=22D3EE&fire=A78BFA&currStreakNum=E5E7EB&sideNums=E5E7EB&currStreakLabel=22D3EE&sideLabels=9CA3AF&dates=9CA3AF" />
  </picture>
</p>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-activity-graph.vercel.app/graph?username=akhil3145&bg_color=0D1117&color=22D3EE&line=A78BFA&point=E5E7EB&area=true&hide_border=true" />
    <source media="(prefers-color-scheme: light)" srcset="https://github-readme-activity-graph.vercel.app/graph?username=akhil3145&bg_color=FFFFFF&color=0891B2&line=7C3AED&point=1F2937&area=true&hide_border=true" />
    <img width="98%" alt="GitHub contribution activity graph for akhil3145" src="https://github-readme-activity-graph.vercel.app/graph?username=akhil3145&bg_color=0D1117&color=22D3EE&line=A78BFA&point=E5E7EB&area=true&hide_border=true" />
  </picture>
</p>

<p align="center"><sub>Live data from public GitHub activity. Language percentages reflect code volume, not proficiency.</sub></p>

<img src="assets/divider.svg" width="100%" height="12" alt="" />

## DSA

I practice data structures and algorithms in Python on NeetCode, with solutions synced to GitHub and organized into topic folders: Data Structures &amp; Algorithms, Python Coding Interviews and Python For Beginners. The goal is steady practice and sound problem-solving fundamentals rather than a leaderboard number.

**[Browse my solutions →](https://github.com/akhil3145/Neetcode_DSA)**

## Currently Exploring

<p>
  <img src="https://img.shields.io/badge/Advanced_ML-172338?style=flat-square" alt="Advanced machine learning" />
  <img src="https://img.shields.io/badge/Deep_Learning-172338?style=flat-square" alt="Deep learning" />
  <img src="https://img.shields.io/badge/Computer_Vision-172338?style=flat-square" alt="Computer vision" />
  <img src="https://img.shields.io/badge/LLM_Applications-172338?style=flat-square" alt="LLM applications" />
  <img src="https://img.shields.io/badge/RAG-172338?style=flat-square" alt="Retrieval-augmented generation" />
  <img src="https://img.shields.io/badge/AI_Agents-172338?style=flat-square" alt="AI agents" />
  <img src="https://img.shields.io/badge/Docker-172338?style=flat-square" alt="Docker" />
  <img src="https://img.shields.io/badge/DSA-172338?style=flat-square" alt="Data structures and algorithms" />
</p>

## Beyond Coding

When I'm not building AI systems, I'm usually exploring the universe, prehistoric life, or pushing my limits in the gym. Astronomy and space exploration, paleontology and dinosaurs, and strength training (which led to Strenzz) all feed the same habit: stay curious, be patient, make steady progress.

<img src="assets/divider.svg" width="100%" height="12" alt="" />

## Contact

<p>
  <a href="https://github.com/akhil3145"><img src="https://img.shields.io/badge/GitHub-akhil3145-0891B2?style=flat-square&logo=github&logoColor=white&labelColor=111827" alt="GitHub profile: akhil3145" /></a>
  <a href="https://www.linkedin.com/in/akhil3145"><img src="https://img.shields.io/badge/LinkedIn-akhil3145-0891B2?style=flat-square&logo=linkedin&logoColor=white&labelColor=111827" alt="LinkedIn profile: akhil3145" /></a>
  <a href="mailto:akhilpandey1000@gmail.com"><img src="https://img.shields.io/badge/Email-akhilpandey1000%40gmail.com-0891B2?style=flat-square&logo=gmail&logoColor=white&labelColor=111827" alt="Email: akhilpandey1000@gmail.com" /></a>
</p>

<p align="center">
  <sub>Early in the journey, building in public.</sub><br />
  <img src="https://komarev.com/ghpvc/?username=akhil3145&label=Profile+views&color=0891B2&style=flat-square" alt="Profile view counter" />
</p>
