# 🧪 FailProof LLM — Mini

> **Unit tests for prompts.**  
> Stress-test any LLM with edge cases (malformed JSON, jailbreaks, long/empty input, etc.) and see exactly where it breaks—then patch it and measure the lift.

**Demo (≤60s):** _add link_ • **Tech video (≤60s):** _add link_

*************************************************

## ⭐ Why

LLMs are charming… until the input is weird. Typos, conflicting instructions, or “ignore all previous” can quietly wreck your product.  
**FailProof LLM** gives you a repeatable way to shake the model and **measure robustness** before you ship.

****************************************************

## 🔧 Features

- **One-click run** against **11 edge cases**
  - `JSON_VALIDITY`, `TYPOS`, `AMBIGUITY`, `JAILBREAK`, `SAFETY`, `LOCALE`, `EMPTY`, `LONG`, `JSON_ONLY`, `TRUNCATE`, `CONFLICT`
- **Strict JSON checks** via `jsonschema` (no extra keys; typed fields)
- **Deterministic evaluator** (rule-based): JSON parsing, refusal detection, English reply check, jailbreak leakage check
- **Patch mode** (prompt hardening) → instant **before/after score** lift
- **Latency & export**: per-test latency + **Download JSON report**
- **Model switcher**: compare `gpt-4o-mini`, `gpt-4o`, etc.

****************************************************

## 🏗️ Architecture
![WhatsApp Image 2025-08-10 at 15 11 55_c54f21a8](https://github.com/user-attachments/assets/48c1993d-804d-41fd-aac9-3fb86a7b8bcc)


## 🚀 Quickstart

```bash
git clone https://github.com/<you>/failproof-llm-mini.git
cd failproof-llm-mini

# Create venv (Windows PowerShell)
python -m venv .venv
. .venv\Scripts\Activate.ps1

# macOS/Linux
# python3 -m venv .venv && source .venv/bin/activate

pip install -r requirements.txt

##API KEYS

Create a file named **.env** in the project root:
OPENAI_API_KEY=sk-********************************

**## 4) Run the app**
```bash
streamlit run app.py
# if the default port is busy:
# streamlit run app.py --server.port 8502

bash
Copy
Edit


##5) Baseline → Patched demo (60s)
In System Prompt, set: **You are a helpful assistant.**

Uncheck “Apply hardening patch” → click Clear cache → Run Tests.

Now check “Apply hardening patch” → Clear cache → Run Tests again.

Observe the score lift; Download JSON Report if needed.

6) Clear cache (optional, forces fresh calls)
streamlit run app.py

