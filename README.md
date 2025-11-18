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


Temp 	Chunk 	Context 	Output 	Accuracy vs GT 	Hallucination 	Robustness 	sample_outputs
0 	0.1 	128 	8000 	Correct 	Yes 	Low 	1.0 	[ Cancer is a disease in which abnormal cells ...
1 	0.1 	256 	8000 	Correct 	Yes 	Low 	1.0 	[ Cancer is a disease in which abnormal cells ...
2 	0.1 	512 	8000 	Correct 	Yes 	Low 	1.0 	[ Cancer is a disease in which abnormal cells ...
3 	0.5 	128 	8000 	Correct 	Yes 	Low 	1.0 	[ Cancer is a disease characterized by the unc...
4 	0.5 	256 	8000 	Correct 	Yes 	Low 	1.0 	[ Cancer is a disease characterized by the unc...
5 	0.5 	512 	8000 	Correct 	Yes 	Low 	1.0 	[ Cancer is a disease characterized by the unc...
6 	0.9 	128 	8000 	Correct 	Yes 	Low 	1.0 	[ Cancer is a complex and multifaceted disease...
7 	0.9 	256 	8000 	Correct 	Yes 	Low 	1.0 	[ Cancer is a complex and multifaceted disease...
8 	0.9 	512 	8000 	Correct 	Yes 	Low 	1.0 	[ Cancer is a complex and multifaceted disease...
