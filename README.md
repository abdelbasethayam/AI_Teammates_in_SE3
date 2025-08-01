![](figs/AIDev_logo.png)

# The Rise of AI Teammates in Software Engineering (SE) 3.0: Replication Package

[![Paper](https://img.shields.io/badge/arXiv-2507.15003-b31b1b.svg)](https://arxiv.org/abs/2507.15003)
[![Hugging Face](https://img.shields.io/badge/HuggingFace-dataset-blue?logo=huggingface&logoColor=white)](https://huggingface.co/datasets/hao-li/AIDev)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1RZJL1My_2d_NtGwSlsGbfxT75oykuaut?usp=sharing)

- **Paper:** https://arxiv.org/abs/2507.15003
- **HuggingFace Dataset:** https://huggingface.co/datasets/hao-li/AIDev
- **Example Notebook:** https://colab.research.google.com/drive/1RZJL1My_2d_NtGwSlsGbfxT75oykuaut?usp=sharing

This repository contains the replication package for the paper "The Rise of AI Teammates in Software Engineering (SE)
3.0: How Autonomous Coding Agents Are Reshaping SE". Due to the size limit of GitHub repositories, the full dataset is
not included here. You can find our full dataset on HuggingFace: https://huggingface.co/datasets/hao-li/AIDev

> If you're interested in the Human-PRs we used in the paper, you can find them here: https://drive.google.com/file/d/1nKYtm3U3SFMk5_iLXt1oog9glFnEUJ3T/view?usp=sharing

## Overview

The overview of the AIDev dataset is as follows:

|                  | #PR         | #Developer | #Repo      |
|------------------|-------------|------------|------------|
| `OpenAI Codex`   | 411,621     | 41,619     | 53,702     |
| `Devin`          | 24,893      | 2,897      | 3,857      |
| `GitHub Copilot` | 16,531      | 1,916      | 3,097      |
| `Cursor`         | 1,981       | 753        | 828        |
| `Claude Code`    | 1,509       | 585        | 645        |
| **Total**        | **456,535** | **47,303** | **61,453** |

![](./figs/pr_cumulative.png)

## Repository Structure

```
├── AIDev-pop/              # AIDev-pop subset of AIDev
├── analysis/              # Analysis scripts and Jupyter notebooks
├── figs/                  # Generated figures and results
├── requirements.txt       # Python dependencies
└── README.md             # This file
```

## Installation

Install required dependencies:

```bash
pip install -r requirements.txt
```

## Key Findings

The key findings from the analysis of are based on AIDev-pop, a subset of the AIDev dataset.

### AIDev-pop: Filtered (>500 stars)

|                  | #PR       | #Developer | #Repo   |
|------------------|-----------|------------|---------|
| `OpenAI Codex`   | 2,686     | 522        | 467     |
| `Devin`          | 2,729     | 300        | 130     |
| `GitHub Copilot` | 1,462     | 309        | 215     |
| `Cursor`         | 144       | 66         | 52      |
| `Claude Code`    | 101       | 68         | 61      |
| **Total**        | **7,122** | **1,240**  | **856** |

### Productivity in Coding Agents Era

![pr_merge_compare_radar.png](figs%2Fpr_merge_compare_radar.png)

**Across all evaluated Autonomous Coding Agents, PR acceptance rates consistently lag behind human performance**, particularly for feature
development (feat), bug fixes (fix), and performance optimization (perf) tasks. Among the Autonomous Coding
Agents, OpenAI Codex achieves the highest acceptance rate at 64%, followed by Devin at 49% and GitHub Copilot
at 35%.

### Turnaround Time

![](figs%2Fturnaround_distribution.png)

**OpenAI Codex PRs cut review time by 10 times, boosting efficiency but questioning review
depth**. accepted PRs from OpenAI Codex close in a median of 0.3 hours (18 minutes),
which is significantly faster than Human-PRs (3.9 hours). Rejected PRs from OpenAI Codex
are also triaged significantly faster (2.4 vs. 27.6 hours).

![](figs/copilot_job_completion_time.png)

**GitHub Copilot delivers half of its PRs within 12.8 minutes**. While 75% of jobs are completed within 18.5 minutes, the distribution
exhibits a long tail extending up to 60 minutes, with the 95th percentile exceeding one hour. 

### Who Review the PRs?

![](./figs/reviewer_classification_stacked.png)

**Human reviewers remain dominant across Agentic-PRs yet GitHub Copilot drives a shift
toward automated hybrid collaboration in review**. Both Human-PRs and Agentic-PRs receive
no explicit review in the majority of cases (75.3% and 58.2%, respectively), while the second most common category
involves reviews conducted solely by humans, at 14.7% and 21.8%. Notably, bot reviewers are more prevalent in Agentic-
PRs (20.1%) than in Human-PRs (10.0%). 

![](./figs/bot_heatmap.png)

**Autonomous Coding Agents and their paired review bots often originate from the same
provider, forming closed PR-review loops that streamline workflows; but risk reinforcing provider-specific
biases.** We analyze the top 10 most active review bots to understand on which Autonomous Coding Agents they operate.
The heatmap illustrates a strong association between review bots and Autonomous Coding Agents from the same provider.

### Language Usage

![](figs%2Ftotal_language_percentages_top.png)

**Autonomous Coding Agents exhibit distinct language preferences reflecting domain specialization in their capabilities.** 
TypeScript is the most common language across all agents, underscoring its popularity in AI-assisted development.
However, notable divergences emerge: OpenAI Codex shows a pronounced skew toward Python, while GitHub
Copilot heavily favours C#, likely reflecting their respective integrations and user bases.

## Dataset Schema

![](figs%2Fdataset_schema.png)

## Citation

If you use this dataset or code in your research, please cite our paper:

```bibtex
@misc{li2025aiteammates,
      title={The Rise of AI Teammates in Software Engineering (SE) 3.0: How Autonomous Coding Agents Are Reshaping Software Engineering}, 
      author={Hao Li and Haoxiang Zhang and Ahmed E. Hassan},
      year={2025},
      eprint={2507.15003},
      archivePrefix={arXiv},
      primaryClass={cs.SE},
      url={https://arxiv.org/abs/2507.15003}, 
}
```
