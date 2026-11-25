<div align="center">

# 🛡️ DroidSentry

### Mobile Security Assessment & Triage Platform
*Securing what connects you — one APK at a time.*

![Python](https://img.shields.io/badge/Python-3.11-3776AB?logo=python&logoColor=white)
![Django](https://img.shields.io/badge/Django-REST-092E20?logo=django&logoColor=white)
![React](https://img.shields.io/badge/React-TypeScript-61DAFB?logo=react&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-Helm-326CE5?logo=kubernetes&logoColor=white)
![OWASP MASVS](https://img.shields.io/badge/OWASP-MASVS-000000?logo=owasp&logoColor=white)
![MITRE ATT&CK](https://img.shields.io/badge/MITRE-ATT%26CK%20Mobile-C7362F)

</div>

---

## 💡 Why I built this

As a cybersecurity engineering student, I wanted to go beyond running existing tools and
**build my own end-to-end mobile security pipeline** — from APK upload, to automated static
analysis, to analyst-ready reports. **DroidSentry** is my take on what a modern, cloud-native
Android assessment platform should look like: deterministic, explainable, evidence-first, and
careful about where AI is (and isn't) allowed to act.

It's an academic / portfolio project, but engineered like a real product: containers,
async workers, object storage, RBAC, a Helm chart, and a bounded AI agent that can never touch
a device directly.

---

## 📖 What it does

DroidSentry provides a traceable workflow for **authorized Android APK assessments**:

1. 📤 Securely upload APKs into private object storage
2. ⚙️ Run bounded, asynchronous static analyzers
3. 🧩 Normalize evidence and apply deterministic security rules
4. 📊 Score OWASP MASVS coverage and overall risk
5. 🎯 Cautiously map suspicious signals to MITRE ATT&CK Mobile
6. 📱 Run approved dynamic checks in an isolated Android lab
7. 🧾 Generate evidence-first JSON and PDF reports

> ⚠️ DroidSentry **supports analysis — it does not guarantee a malware/benign verdict.**
> Findings are decision support for a qualified analyst, on applications you are authorized to test.

---

## ✨ Key Features

- 🔍 **Static analysis** — manifest, DEX, resources, strings, certificates, optional JADX source indexing
- 📐 **Explainable scoring** — severity, confidence, MASVS coverage and audit scores
- 🧩 **Rules engine** — versioned YAML catalogs (MASVS + ATT&CK-oriented)
- 📱 **Dynamic lab** — rootable emulator with ADB, Frida, mitmproxy, runtime CA overlay
- 🤖 **Bounded AI agent** — plan → approve → execute → observe, with hard budgets and redaction;
  the model never gets direct ADB, shell, filesystem, Docker, DB or storage access
- 🔐 **Secure by design** — session auth, CSRF protection, role-based access control

---

## 🧰 Tech Stack

| Layer | Technologies |
| --- | --- |
| **Backend** | Python · Django REST Framework · Celery · Redis · PostgreSQL · MinIO |
| **Frontend** | React · TypeScript · Vite |
| **Security** | Frida · mitmproxy · ADB · JADX · OWASP MASVS · MITRE ATT&CK Mobile |
| **Infra** | Docker · Compose · Kubernetes · Helm · GitLab CI/CD |

---

## 🚀 Quick Start (local demo)

```bash
cp .env.compose.example .env
docker compose up --build
# Frontend : http://localhost:5173
# API      : http://localhost:8000
```

Full walkthrough in [`docs/20_MVP_Demo_Runbook.md`](docs/20_MVP_Demo_Runbook.md).

---

## 📂 Structure

```
DroidSentry/
├── backend/        # Django REST API, Celery workers, 16 domain apps
├── frontend/       # React + TypeScript analyst interface
├── agent_runtime/  # Bounded agentic assessment harness
├── rules/          # Versioned YAML rule catalogs (MASVS / ATT&CK)
├── helm/           # Kubernetes Helm chart
├── docs/           # Architecture, API, security & deployment docs
└── tests/          # Integration tests & sample fixtures
```

---

## ⚖️ Authorized Use

DroidSentry is an academic and institutional cybersecurity assessment platform. Use it only on
applications you are **explicitly authorized** to test. Dynamic instrumentation can alter app
behavior — keep the lab isolated and have an analyst validate every conclusion.

---

## 👤 Author

**Abdelaziz AIT BEN IHYA**
Cybersecurity & IT Engineering Student @ ENSA Agadir 🇲🇦
Interests: Offensive Security · Mobile Security · GRC · AI Security

🔗 [GitHub](https://github.com/aziz-benihya) · [LinkedIn](https://www.linkedin.com/)

<div align="center">
<sub>⭐ If you find this project interesting, feel free to star it!</sub>
</div>
