Chemistry SLM Finetuning: Phi-2 vs. Gemma3
Fine-tuning and evaluation of two Small Language Models (SLMs) — Microsoft Phi-2 and Google Gemma3 — on a custom chemistry Q&A dataset, using parameter-efficient fine-tuning (LoRA). The project compares both models on their ability to answer chemistry questions and generate educational content, with quantitative evaluation via perplexity and F1 scores.

Project Overview:
Small Language Models are increasingly attractive for domain-specific applications where cost, latency, and deployability matter more than raw scale. This project explores how well two popular SLMs adapt to a specialized domain — chemistry education — after fine-tuning on the same custom dataset, and measures the resulting quality difference using F1 score and perplexity.

Highlights:
1.	Custom dataset — 7,161 curated chemistry Q&A pairs spanning physical, organic, and inorganic chemistry
2.	Parameter-efficient fine-tuning — LoRA adapters used on both models to keep training lightweight and reproducible on limited compute
3.	Head-to-head comparison — Same dataset, same evaluation pipeline, applied consistently across both architectures
4.	Quantitative evaluation — F1 score and perplexity used to benchmark answer correctness and generation fluency, not just qualitative inspection

Methodology:
1.	Data preparation — Curated 7,161 chemistry question-answer pairs covering physical, organic, and inorganic chemistry.
2.	Fine-tuning — Applied LoRA to both Phi-2 and Gemma3 to adapt each base model to the chemistry QA task without full-parameter retraining.
3.	Evaluation — Generated responses from both fine-tuned models on a held-out test set and scored them using F1 score (answer correctness/overlap with references) and perplexity (fluency/confidence) to quantify performance.
4.	Comparison — Aggregated metrics across both models to identify which architecture adapted better to the domain.

Results:
Phi-2 (fine-tuned)
i.	F1 Score — 0.90
ii.	Perplexity — 2.68

Gemma3 (fine-tuned)
i.	F1 Score — 0.83
ii.	Perplexity — 12.73

Phi-2 outperformed Gemma3 on both metrics after fine-tuning — a higher F1 score (better alignment with reference answers) and a substantially lower perplexity (more confident, fluent generations). This suggests Phi-2 adapted more effectively to the chemistry QA domain under LoRA fine-tuning with this dataset size.

Tech Stack:
1.	Models — Microsoft Phi-2, Google Gemma3
2.	Fine-tuning — LoRA (parameter-efficient fine-tuning / PEFT)
3.	Frameworks — PyTorch, Hugging Face Transformers, PEFT
4.	Evaluation — F1 Score, Perplexity

# Open phi-2.ipynb or gemma-3.ipynb to run fine-tuning, and metrics.ipynb to reproduce the evaluation.

This project was built to explore how small, efficiently fine-tuned language models perform on specialized educational tasks — a step toward accessible, low-cost domain-specific AI tools.


