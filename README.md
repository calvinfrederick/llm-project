# llm-project

Building an LLM-powered workflow to analyze and explain logistics speed metrics across logistics providers, routes, and time periods—without writing complex SQL for every new question.

The main notebook is [`calvin_llm_project.ipynb`](calvin_llm_project.ipynb). It uses `deepseek-v4-flash` via the OpenAI-compatible API.

## Prerequisites

- **Python 3.10+** (3.11 or 3.12 recommended)
- **pip** (included with Python)
- A **DeepSeek API key** for LLM calls in the notebook

## Install dependencies

From the project root:

```bash
# 1. Create and activate a virtual environment
python3 -m venv .venv
source .venv/bin/activate   # macOS / Linux
# .venv\Scripts\activate    # Windows

# 2. Upgrade pip, then install packages
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### What gets installed

| Package | Purpose |
|---------|---------|
| `pandas`, `numpy` | Data loading and analysis |
| `matplotlib`, `seaborn` | Charts and visualizations |
| `openai` | DeepSeek API client (OpenAI-compatible) |
| `python-dotenv` | Load secrets from a `.env` file |
| `tabulate` | Formatted table output |

To run the notebook in Jupyter, install a kernel after the steps above:

```bash
pip install jupyter ipykernel
python -m ipykernel install --user --name=llm-project --display-name="Python (llm-project)"
```

Then open the notebook and select the **Python (llm-project)** kernel.

## Environment variables

Create a `.env` file in the project root (this file is gitignored):

```bash
DEEPSEEK_API_KEY=your_api_key_here
```

The notebook loads this with `load_dotenv()` and reads `DEEPSEEK_API_KEY` for API calls.

## Dataset

The notebook expects `llm_test_dataset_20260610-170741.csv` in the project root. That file is not tracked in git—place your copy there before running the data-loading cells.

## Quick start

```bash
source .venv/bin/activate
jupyter notebook calvin_llm_project.ipynb
```

Run the cells from top to bottom after dependencies are installed, the API key is set, and the dataset is in place.
