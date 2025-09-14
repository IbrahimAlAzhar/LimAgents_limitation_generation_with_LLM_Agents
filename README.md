# LimAgents_limitation_generation_with_LLM_Agents
Scientific Article's Limitation Generation with LLM Agents settings. 

LimAgents: Can LLM Agents Generate Meaningful Limitations from Scientific Articles?

This repository contains the code, prompts, datasets, and evaluation scripts for our paper "LimAgents: Can LLM Agents Generate Meaningful Limitations from Scientific Articles?".

Our work investigates whether LLM agents—specialized roles such as Extractor, Analyzer, Reviewer, and Citation—can generate more meaningful, contextually grounded, and peer-review–ready limitations than traditional zero-shot LLMs.

The repository is organized into modular folders, each reflecting a major component of our framework and experiments.

📂 Repository Structure
1. Ablation Study

Contains experiments testing different agent configurations:

9-agent full system.

3-agent minimal setup (Extractor, Analyzer, Reviewer) with GPT-4o mini.

Individual agent runs and performance evaluation.

Comparative results showing how agent decomposition improves outcomes.

2. Citation Agent

Implements and evaluates the Citation Agent, which grounds limitation generation in the broader scholarly context.

Retrieval-augmented generation (RAG) settings.

Cited-in and cited-by data collection.

LLM re-ranking for retrieved passages.

3. End-to-End LLM Agents

Runs the complete LimAgents pipeline:

Tested with GPT-4o mini and LLaMA 3 (8B).

Generates limitations using the optimal agent setup.

Includes evaluation scripts for assessing performance end-to-end.

4. Evaluation

Code for evaluating generated limitations.

Coverage: How many ground-truth limitations are matched.

Quality: LLM-based pairwise matching of generated vs ground-truth limitations.

Supports both coverage metrics and nuanced LLM-as-a-judge evaluation.

5. Experiment with Other Agents

Exploratory experiments with non-standard agents:

Gemini Agent (multi-modal reasoning).

Graph Agent (leveraging graph-based representations).

Image Agent (handling visual data in papers).

6. Ground Truth Extraction

Scripts to build high-quality ground truth datasets:

Extract author-stated limitations.

Collect peer-review limitations from OpenReview.

Merge both sources into a richer gold-standard set.

7. Judge and Self-Feedback

Implements Judge Agent and self-refinement loops:

Judge Agent scores limitations (depth, originality, actionability, coverage).

Underperforming outputs trigger self-feedback and re-generation.

8. LLM Agents – GPT-4o Mini

Experiments using GPT-4o mini with the optimal 4-agent setup (Extractor, Analyzer, Reviewer, Citation).

Demonstrates effectiveness of multi-agent orchestration.

Provides baseline for comparison against LLaMA and zero-shot settings.

9. LimAgents Prompt

A collection of carefully designed prompts for:

Each worker agent (Extractor, Analyzer, Reviewer, Citation).

Judge Agent and Master Agent.

Chain-of-limitations step-by-step workflow.

10. Zero-Shot Setting

Baselines where a single LLM is directly prompted to generate limitations.

Shows the shortcomings of zero-shot methods (vague, generic outputs).

Provides comparison against multi-agent setups.

🔑 Key Contributions in Code

Multi-agent orchestration: Explicit roles for Extractor, Analyzer, Reviewer, and Citation agents.

Integration with retrieval (RAG): Citation Agent retrieves cited and citing papers.

Judge + Self-feedback: Iterative refinement of limitations for higher quality.

Pointwise evaluation protocol: LLM-as-a-judge coverage assessment beyond n-gram metrics.

Ground-truth construction: Combining author-stated and OpenReview limitations for fair benchmarking.

🚀 Getting Started

Clone this repo:

git clone https://github.com/<your-username>/LimAgents.git
cd LimAgents


Install dependencies:

pip install -r requirements.txt


Run a zero-shot baseline:

python zero_shot_setting/run_zero_shot.py


Run the full LimAgents pipeline with GPT-4o mini:

python end_to_end_llm_agents/run_limagents.py
