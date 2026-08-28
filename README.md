# Customer Support Agent — Braintrust Evaluation

This project is part of the **Week 4 course content of Mastering Agentic AI** and demonstrates how to evaluate a customer-support classification agent using Braintrust.

## What the project does

The agent classifies e-commerce support tickets into five categories:

- `order_status`
- `refund_request`
- `product_issue`
- `account_help`
- `other`

The notebook walks through a practical evaluation workflow using a labeled dataset, Braintrust experiments, evaluation metrics, failure analysis, prompt iteration, and regression testing.

## Project structure

```text
customer-support-braintrust/
├── customer_support_braintrust_evals.ipynb
├── README.md
├── requirements.txt
├── .env.example
└── .gitignore
```

## Setup

### 1. Create a virtual environment

macOS/Linux:

```bash
python -m venv .venv
source .venv/bin/activate
```

Windows PowerShell:

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Add API keys

Copy `.env.example` to `.env` and add your own keys:

```text
OPENAI_API_KEY=...
BRAINTRUST_API_KEY=...
```

The `.env` file is ignored by Git and should not be committed.

### 4. Run the notebook

Open `customer_support_braintrust_evals.ipynb` in VS Code or Jupyter and select the Python environment where the requirements were installed.

Run the notebook cells in order. Some evaluation steps make model API calls and may take a short time to complete.

## Human Review

The notebook creates a small experiment containing selected cases for human review.

When you reach the Human Review checkpoint:

1. Open the generated `human-review-v1` experiment in Braintrust.
2. Review the selected examples using the configured Human Review fields.
3. Export the reviewed experiment as a CSV.
4. Create a `data/` folder in the project if it does not already exist.
5. Save the exported file as:

   `data/human-review-v1.csv`

6. Return to the notebook and continue with the LLM judge calibration section.

The exported CSV is intentionally not included in the repository to encourage self-review and exploring Braintrust features.

## Braintrust

The notebook creates datasets and experiments in Braintrust. After running an experiment, open the corresponding Braintrust project to inspect individual results, scores, traces, and experiment comparisons.
