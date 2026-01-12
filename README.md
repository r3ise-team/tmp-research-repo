# tmp-research-repo

This repository serves as the **official template** for all research repositories under the **r3ise-team** GitHub organization. All new projects, tools, datasets, and paper artifacts should be created using this template to ensure consistency, reproducibility, and professional software engineering practices.

---


## ✅ How to Use This Template

1. Click **Use this template** on GitHub
2. Name the new repository following R3ISE conventions (`proj-*`, `tool-*`, etc.)
3. Update `README.md`, `CITATION.cff`, and `LICENSE`
4. Create `dev`, `dep`, and `prd` branches.
5. If you want to develop something use `dev` branch (you can also create more branches off from `dev`, e.g., `dev-frontend`, `dev-backend-fix-bug-something`)
6. Make sure you only merge from `dev-*` to `dev` (NOT `main` or `prd` or `dep`)
7. Start committing research code

---

## 📁 Standard Repository Structure

```
repo-root/
├── README.md
├── CONTRIBUTING.md
├── LICENSE
├── CITATION.cff
├── .gitignore
├── docs/
│   └── index.md
├── src/
├── experiments/
│   ├── README.md
│   └── configs/
├── data/
│   └── README.md
├── scripts/
├── tests/
└── .github/
    ├── workflows/
    │   └── ci.yml
    └── ISSUE_TEMPLATE/
        ├── bug_report.yml
        ├── research_task.yml
        └── experiment_request.yml
```

---

## 📄 README.md (Template)

```md
# Project Title

## Overview
Brief description of the research problem, motivation, and key contributions.

## Research Context
Explain how this project fits within the broader R3ISE research agenda.

## Repository Structure
High-level explanation of important directories.

## Installation
Step-by-step setup instructions.

## Usage
How to run the code, tools, or experiments.

## Experiments & Reproducibility
- Experimental setup
- Configuration files
- Hardware/software requirements

## Students & Contributors
List student contributors and supervisors.

## Citation
See `CITATION.cff` for how to cite this work.
```

---

## 📜 CONTRIBUTING.md

```md
# Contributing Guidelines

## Workflow
- Create a feature branch from `main`
- Commit small, meaningful changes
- Open a pull request
- Ensure CI checks pass

## Code Quality
- Write clear, documented code
- Add tests when applicable
- Follow project-specific style guidelines

## Research Contributions
- Clearly document assumptions
- Ensure experiments are reproducible
- Update documentation alongside code
```

---

## 🧾 CITATION.cff (Template)

```yaml
cff-version: 1.2.0
title: "Project Title"
message: "If you use this software in your research, please cite it."
authors:
  - family-names: Babaei
    given-names: Majid
date-released: 2026-01-01
version: 0.1.0
license: MIT
```

---

## ⚙️ GitHub Actions CI (.github/workflows/ci.yml)

```yaml
name: CI

on:
  push:
  pull_request:

jobs:
  build-and-test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.11'

      - name: Install dependencies
        run: |
          python -m pip install --upgrade pip
          if [ -f requirements.txt ]; then pip install -r requirements.txt; fi

      - name: Run tests
        run: |
          if [ -d tests ]; then pytest tests; else echo "No tests directory"; fi
```

---

## 🐞 Issue Templates

### Bug Report (`bug_report.yml`)

```yaml
name: Bug Report
description: Report a reproducible bug
labels: ["type: bug"]
body:
  - type: textarea
    attributes:
      label: Description
      description: What went wrong?
    validations:
      required: true
```

### Research Task (`research_task.yml`)

```yaml
name: Research Task
description: Research or investigation task
labels: ["type: research"]
body:
  - type: textarea
    attributes:
      label: Research Question or Task
    validations:
      required: true
```

### Experiment Request (`experiment_request.yml`)

```yaml
name: Experiment Request
description: Propose or request an experiment
labels: ["type: experiment"]
body:
  - type: textarea
    attributes:
      label: Hypothesis / Goal
    validations:
      required: true
```

---

## 🧪 data/README.md

```md
# Data Directory

This directory contains datasets used in this project.

- Large or sensitive datasets should NOT be committed directly
- Provide download scripts or external links
- Document preprocessing steps clearly
```

---

## 🧠 experiments/README.md

```md
# Experiments

This directory contains experiment configurations and scripts.

Each experiment should:
- Be configurable via files (not hard-coded)
- Be repeatable
- Log results and metadata
```

---

Maintained by the **R3ISE Research Team**.

