Optimized RAG Hyperparameter Evaluation Pipeline

A memory-efficient pipeline to evaluate Retrieval-Augmented Generation (RAG) models across multiple hyperparameters (temperature, chunk size, context window) while avoiding repeated LLM loads. Includes automatic metrics calculation and robustness scoring.

Features

Loads the LLM only once with the maximum context window.

Builds and caches VectorStoreIndex per chunk size to save memory.

Supports temperature emulation using prompt hints (avoids reloading heavy models).

Computes multiple evaluation metrics per question:

Cosine Similarity (embedding alignment with ground truth)

ROUGE (overlap-based text similarity)

BLEU (n-gram similarity)

Classifies answers into Correct / Partial / Wrong with hallucination labeling.

Aggregates results into a robustness score.

Saves detailed per-question logs and a hyperparameter matrix.

Optional heatmap visualization of robustness by temperature vs. chunk size. 



