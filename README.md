# 🗼 MAKER: Tower of Hanoi Solver Agent

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Ollama](https://img.shields.io/badge/Ollama-Enabled-orange)


This repository contains a functional implementation of the **MAKER framework** (Multi-Agent Knowledge & Enhanced Reasoning), designed to solve algorithmic puzzles using Local Large Language Models (LLMs) with high reliability.

### 📄 Research Basis
This project is an implementation of the concepts presented in the paper:

> **[Solving a Million-Step LLM Task with Zero Errors](https://arxiv.org/abs/2511.09030)**  
> *Elliot Meyerson, Giuseppe Paolo, Roberto Dailey, Hormoz Shahrzad, Olivier Francon, Conor F. Hayes, Xin Qiu, Babak Hodjat, Risto Miikkulainen* (2025)

This implementation reproduces the core logic of the paper—specifically the **Voting (Consensus)** and **Red Flag (Verification)** mechanisms—applied to the Tower of Hanoi puzzle to demonstrate how LLMs can solve long-horizon tasks without error.

---

## 🌟 Features

*   **🧠 Local LLM Inference:** Runs entirely offline using [Ollama](https://ollama.com/), compatible with models like `gpt-oss:20b`.
*   **🛡️ Verification System (Paper Implementation):**
    *   **Red Flag Checker:** Automatically rejects responses that violate format rules or token limits.
    *   **Consensus Voting:** Uses a "Best-of-N" voting mechanism to ensure the next move is statistically reliable before execution.
*   **📊 Comprehensive Metrics:** Tracks token usage, response times, hallucination rates, and compute cost estimations.
*   **🎬 Automated Visualization:** Generates an MP4 video of the solution using Matplotlib and FFMpeg.
*   **📈 Interactive Dashboard:** automatically produces a **self-contained HTML dashboard** with the solution video embedded (Base64), requiring no external files to view.

## 📂 Repository Structure

```text
.
├── Hanoi_MAKER_Enhanced.ipynb      # Main notebook containing all logic
├── dashboard_4_standalone.html     # Generated result (Self-contained HTML+Video)
├── hanoi_4_solution.mp4            # Generated raw video file
└── README.md                       # This file

```
## Usage
Open Hanoi_MAKER_Enhanced.ipynb.
Configure your run in the main() function:
```python
CONFIG = {
'num_disks': 4, # Difficulty (Start with 4 or 5)
'model_name': 'gpt-oss:20b', # Must match your pulled model
'max_attempts': 3, # Retries per step
'voting_k': 2, # Votes needed for consensus
}
```

Run all cells.
The script will:
Solve the puzzle step-by-step.
Render the solution video.
Generate and display the dashboard_X_standalone.html.


📚 Reference
If you use this code or concepts in your work, please credit the original authors of the paper:

```bibtex
@article{meyerson2025solving,
  title={Solving a Million-Step LLM Task with Zero Errors},
  author={Meyerson, Elliot and Paolo, Giuseppe and Dailey, Roberto and Shahrzad, Hormoz and Francon, Olivier and Hayes, Conor F and Qiu, Xin and Hodjat, Babak and Miikkulainen, Risto},
  journal={arXiv preprint arXiv:2511.09030},
  year={2025},
  url={https://arxiv.org/abs/2511.09030}
}
