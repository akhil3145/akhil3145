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
  <a href="#what-im-building">Featured work</a> ·
  <a href="#technical-arsenal">Stack</a> ·
  <a href="#dsa-and-problem-solving">DSA</a> ·
  <a href="#connect">Contact</a>
</p>

## About Me

- **Education:** B.Tech in Computer Science (Data Science & AI), Shri Ramswaroop Memorial University, Lucknow. Fourth year, graduating 2027.
- **Direction:** Aspiring AI/ML engineer building end-to-end AI applications, from model to API to interface.
- **Exploring now:** Advanced ML, LLM applications, RAG and backend engineering.
- **Practice:** Data structures and algorithms in Python.
- **Open to:** AI engineering and software development opportunities.

## What I'm Building

### Vistara AI: plant disease screening with explainability and monitoring

<table>
  <tr>
    <td width="50%">
      <img src="https://github.com/akhil3145/vistara-ai/raw/main/docs/screenshots/scanner.png" alt="Vistara AI scanner page showing ranked top-5 leaf disease predictions" width="100%" />
    </td>
    <td width="50%">
      <img src="https://github.com/akhil3145/vistara-ai/raw/main/docs/screenshots/gradcam.png" alt="Grad-CAM heatmap overlay highlighting the leaf regions behind a prediction" width="100%" />
    </td>
  </tr>
</table>

A deep learning application that classifies leaf images into **38 PlantVillage classes across 14 crop species** using MobileNetV2 transfer learning, served through a FastAPI backend and a React + TypeScript dashboard. Team project.

- **Explainable inference:** server-side Grad-CAM over MobileNetV2 feature maps, returned alongside ranked top-5 scores.
- **Monitoring built in:** SQLite telemetry powers request volume, class mix, mean score and p50/p95 latency views. Drift is reported as *unavailable* until a baseline exists, rather than faked.
- **Typed full-stack contract:** FastAPI with Pydantic v2 responses, batch prediction (up to 24 images) with CSV export, and a model evaluation report read from a stored artifact.
- **Benchmark result:** 98.04% test accuracy on the held-out PlantVillage split (8,146 images). This is a controlled-benchmark figure, not field accuracy, and the repository documents its limitations openly.

<code>Python</code> <code>TensorFlow / Keras</code> <code>MobileNetV2</code> <code>FastAPI</code> <code>Pydantic</code> <code>React</code> <code>TypeScript</code> <code>Vite</code> <code>Tailwind CSS</code> <code>SQLite</code>

<sub>Status: working local application with no hosted demo. Educational, preliminary decision-support software, not a diagnostic tool.</sub>

**[View repository →](https://github.com/akhil3145/vistara-ai)**

## Featured Projects

<table>
  <tr>
    <td width="50%" valign="top">
      <h4><a href="https://github.com/akhil3145/Orchestrix">Orchestrix</a></h4>
      <p>AI-native HR platform combining policy Q&amp;A, resume screening and workforce analytics.</p>
      <ul>
        <li>RAG over HR policy documents with LangChain and a Pinecone vector index</li>
        <li>Resume PDF parsing with ATS-style scoring and candidate ranking</li>
        <li>FastAPI service layer behind a Streamlit dashboard; LLM layer designed for Claude with a local Ollama fallback</li>
      </ul>
      <p><code>Python</code> <code>FastAPI</code> <code>Streamlit</code> <code>LangChain</code> <code>Pinecone</code> <code>SQLite</code> <code>Pandas</code> <code>Plotly</code></p>
    </td>
    <td width="50%" valign="top">
      <h4><a href="https://github.com/akhil3145/ml_studio_codeveda">ML Studio</a></h4>
      <p>Browser-based ML workflow: upload a CSV, train a model, review metrics, make predictions.</p>
      <ul>
        <li>FastAPI backend with one modular route per algorithm: KNN, logistic regression, decision tree, random forest, linear regression</li>
        <li>Dataset upload and inspection, target-column selection and scikit-learn training with accuracy metrics</li>
        <li>React + Vite dashboard with loading and status feedback</li>
      </ul>
      <p><code>Python</code> <code>FastAPI</code> <code>scikit-learn</code> <code>Pandas</code> <code>React</code> <code>Vite</code></p>
      <p><a href="https://ml-studio-frontend-xe8i.onrender.com">Live demo</a> <sub>(may take a moment to wake up)</sub></p>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h4><a href="https://github.com/akhil3145/LMS_2.o">LearnFlow</a></h4>
      <p>Turns any YouTube video or playlist into a structured, trackable bootcamp-style course.</p>
      <ul>
        <li>Express backend calls the YouTube Data API v3 to build multi-module courses and split long videos into sections</li>
        <li>A lesson can only be marked complete after 90% watch progress</li>
        <li>React course player with sidebar navigation; progress resumes from browser storage</li>
      </ul>
      <p><code>JavaScript</code> <code>React</code> <code>Vite</code> <code>Node.js</code> <code>Express</code> <code>YouTube Data API</code></p>
      <p><a href="https://lms-2-o.vercel.app">Live demo</a></p>
    </td>
    <td width="50%" valign="top">
      <h4><a href="https://github.com/akhil3145/strenzz">Strenzz</a></h4>
      <p>A no-account, no-build strength tracker I made for my own training.</p>
      <ul>
        <li>Lift logging with weekly, monthly and all-time progress graphs</li>
        <li>Strength-rank percentiles against general lifting standards, plus 1RM, BMI and Navy-method body-fat calculators</li>
        <li>Runs from a single <code>index.html</code>; all data stays in the browser</li>
      </ul>
      <p><code>JavaScript</code> <code>HTML</code> <code>CSS</code> <code>Chart.js</code></p>
    </td>
  </tr>
</table>

### More on GitHub

| Project | What it is |
| :-- | :-- |
| [PitchPilot](https://github.com/akhil3145/PitchPilot) | Full-stack AI outreach generator (React, Express, MongoDB, Groq) that I'm customizing from an open-source starter to learn authentication, LLM integration and Docker. In development. |
| [Wbot](https://github.com/akhil3145/Wbot) | My first LLM application: a Python chatbot built on Groq's Llama 3 API. |
| [Titanic classification](https://github.com/akhil3145/titanic-classification-algorithms) | Five scikit-learn classifiers compared on the Titanic dataset: preprocessing, training and evaluation. |

## Technical Arsenal

**Core: what I build with most**

<table>
  <tr>
    <td><b>Languages</b></td>
    <td><img src="https://skillicons.dev/icons?i=python,js,ts,html,css" alt="Python, JavaScript, TypeScript, HTML and CSS" /></td>
  </tr>
  <tr>
    <td><b>AI &amp; ML</b></td>
    <td>
      <img src="https://skillicons.dev/icons?i=tensorflow,sklearn,pandas,numpy" alt="TensorFlow, scikit-learn, Pandas and NumPy" /><br />
      <sub>TensorFlow · Keras · scikit-learn · Pandas · NumPy · Matplotlib · Grad-CAM</sub>
    </td>
  </tr>
  <tr>
    <td><b>Backend</b></td>
    <td>
      <img src="https://skillicons.dev/icons?i=fastapi,nodejs,express" alt="FastAPI, Node.js and Express" /><br />
      <sub>REST APIs · Pydantic · Uvicorn</sub>
    </td>
  </tr>
  <tr>
    <td><b>Frontend</b></td>
    <td><img src="https://skillicons.dev/icons?i=react,vite,tailwind" alt="React, Vite and Tailwind CSS" /></td>
  </tr>
  <tr>
    <td><b>Data</b></td>
    <td><img src="https://skillicons.dev/icons?i=sqlite" alt="SQLite" /></td>
  </tr>
  <tr>
    <td><b>Tools</b></td>
    <td>
      <img src="https://skillicons.dev/icons?i=git,github,vscode" alt="Git, GitHub and VS Code" /><br />
      <sub>Jupyter Notebook · Google Colab</sub>
    </td>
  </tr>
</table>

**Growing: applying and learning**

<table>
  <tr>
    <td><b>LLM apps</b></td>
    <td><sub>LangChain · RAG with Pinecone · Groq API · Ollama</sub></td>
  </tr>
  <tr>
    <td><b>Infra &amp; data</b></td>
    <td>
      <img src="https://skillicons.dev/icons?i=docker,mongodb" alt="Docker and MongoDB" />
    </td>
  </tr>
</table>

## Experience

- **Machine Learning Engineering Intern**, Codveda Technologies. Project work: [ML Studio](https://github.com/akhil3145/ml_studio_codeveda).
- **Intern**, InternPe.

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

<p align="center"><sub>Language percentages reflect code volume in public repositories, not proficiency.</sub></p>

<!--
OPTIONAL: contribution streak. Uncomment if you want it.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com?user=akhil3145&hide_border=true&background=0D1117&ring=22D3EE&fire=A78BFA&currStreakNum=E5E7EB&sideNums=E5E7EB&currStreakLabel=22D3EE&sideLabels=9CA3AF&dates=9CA3AF" />
    <source media="(prefers-color-scheme: light)" srcset="https://streak-stats.demolab.com?user=akhil3145&hide_border=true&background=FFFFFF&ring=0891B2&fire=7C3AED&currStreakNum=1F2937&sideNums=1F2937&currStreakLabel=0891B2&sideLabels=6B7280&dates=6B7280" />
    <img width="70%" alt="GitHub contribution streak for akhil3145" src="https://streak-stats.demolab.com?user=akhil3145&hide_border=true&background=0D1117&ring=22D3EE&fire=A78BFA&currStreakNum=E5E7EB&sideNums=E5E7EB&currStreakLabel=22D3EE&sideLabels=9CA3AF&dates=9CA3AF" />
  </picture>
</p>

OPTIONAL: contribution activity graph.

<p align="center">
  <img width="98%" alt="GitHub contribution activity graph for akhil3145" src="https://github-readme-activity-graph.vercel.app/graph?username=akhil3145&bg_color=0D1117&color=22D3EE&line=A78BFA&point=E5E7EB&area=true&hide_border=true" />
</p>
-->

## DSA and Problem Solving

I practice data structures and algorithms in Python on NeetCode, with solutions synced to GitHub and organized by topic. The goal is steady practice and clear problem-solving fundamentals rather than a leaderboard number.

**[Browse my solutions →](https://github.com/akhil3145/Neetcode_DSA)**

## Currently Exploring

- Advanced machine learning
- Deep learning and computer vision
- LLM applications and retrieval-augmented generation (RAG)
- AI agents
- Model deployment
- Data structures and algorithms

## Beyond the Terminal

When I'm not building AI systems, I'm usually exploring the universe, prehistoric life, or pushing my limits in the gym. Astronomy and space exploration, paleontology and dinosaurs, and strength training (which led to Strenzz) all shape how I think about curiosity, patience and steady progress.

## Connect

<p>
  <a href="https://github.com/akhil3145"><img src="https://img.shields.io/badge/GitHub-akhil3145-0891B2?style=flat-square&logo=github&logoColor=white&labelColor=111827" alt="GitHub profile: akhil3145" /></a>
  <a href="https://www.linkedin.com/in/akhil3145"><img src="https://img.shields.io/badge/LinkedIn-akhil3145-0891B2?style=flat-square&logo=linkedin&logoColor=white&labelColor=111827" alt="LinkedIn profile: akhil3145" /></a>
  <a href="mailto:akhilpandey1000@gmail.com"><img src="https://img.shields.io/badge/Email-akhilpandey1000%40gmail.com-0891B2?style=flat-square&logo=gmail&logoColor=white&labelColor=111827" alt="Email: akhilpandey1000@gmail.com" /></a>
</p>

<p align="center"><sub>Early in the journey, building in public.</sub></p>
