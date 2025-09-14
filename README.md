### LimAgents: Can LLM Agents Generate Meaningful Limitations from Scientific Articles?

- Scientific Article Limitation Generation with LLM Agents

- This repository contains the code, prompts, datasets, and evaluation scripts for our paper:
📄 "LimAgents: Can LLM Agents Generate Meaningful Limitations from Scientific Articles?"

Our work investigates whether LLM agents—specialized roles such as Extractor, Analyzer, Reviewer, and Citation—can generate more meaningful, contextually grounded, and peer-review–ready limitations than traditional zero-shot LLMs. 


### 1. Ablation Study

Experiments testing different agent configurations:

9-agent full system

3-agent minimal setup (Extractor, Analyzer, Reviewer) with GPT-4o mini

Individual agent runs and evaluations

Comparative results showing the effect of agent decomposition

### 2. Citation Agent

Implements and evaluates the Citation Agent, grounding limitation generation in broader scholarly context:

Retrieval-augmented generation (RAG) settings

Cited-in and cited-by data collection

LLM re-ranking for retrieved passages

### 3. End-to-End LLM Agents

Runs the full LimAgents pipeline:

Tested with GPT-4o mini and LLaMA-3 (8B)

Generates limitations using the optimal agent setup

Includes evaluation scripts for end-to-end assessment

### 4. Evaluation

Code for evaluating generated limitations:

Coverage: how many ground-truth limitations are matched

Quality: LLM-based pairwise matching of generated vs. ground-truth limitations

Supports both coverage metrics and LLM-as-a-judge evaluation

### 5. Experiment with Other Agents

Exploratory experiments with non-standard agents:

Gemini Agent (multi-modal reasoning)

Graph Agent (graph-based representations)

Image Agent (handling visual content in papers)

### 6. Ground Truth Extraction

Scripts for building high-quality ground truth datasets:

Extract author-stated limitations

Collect peer-review limitations from OpenReview

Merge both sources into a richer gold-standard set

### 7. Judge and Self-Feedback

Implements the Judge Agent and self-refinement loops:

Judge Agent scores limitations (depth, originality, actionability, coverage)

Underperforming outputs trigger re-generation via self-feedback

### 8. LLM Agents – GPT-4o Mini

Experiments using GPT-4o mini with the optimal 4-agent setup (Extractor, Analyzer, Reviewer, Citation):

Demonstrates effectiveness of multi-agent orchestration

Provides baseline vs. LLaMA and zero-shot settings

### 9. LimAgents Prompt

Collection of prompts used in experiments:

Worker agents (Extractor, Analyzer, Reviewer, Citation)

Judge Agent and Master Agent

Chain-of-limitations step-by-step workflow

### 10. Zero-Shot Setting

Baselines with direct prompting (no agents):

Shows shortcomings of zero-shot methods (vague, generic outputs)

Provides baseline for comparison against LimAgents

### 🔑 Key Contributions in Code

Multi-agent orchestration: Explicit roles for Extractor, Analyzer, Reviewer, Citation

Retrieval integration (RAG): Citation Agent retrieves cited & citing papers

Judge + Self-feedback: Iterative refinement for higher-quality limitations

Pointwise evaluation protocol: LLM-as-a-judge coverage assessment beyond n-gram metrics

Ground-truth construction: Combining author-stated + OpenReview limitations for benchmarking
