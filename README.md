Analysing Super Weight in Large Language Models

This repository explores the critical role of super weights in Large Language Models (LLMs) and their impact on model performance. Inspired by the findings from the paper The Super Weight in Large Language Models, this project investigates how pruning or modifying these weights affects the behavior of models like Mistral-7B and DeepSeek LLM 7B.

📄 Overview

Super weights are specific parameters within LLMs that, despite being few in number, have a disproportionate influence on the model's output. Altering these weights can lead to significant degradation in performance, including increased perplexity and reduced accuracy in zero-shot tasks.

This repository contains experiments that:

Identify super weights in Mistral-7B and DeepSeek LLM 7B models.
Analyze the effects of pruning these weights on model outputs.
Visualize changes in activation patterns and output distributions resulting from modifications to super weights.

🗂️ Repository Structure
superweight_mistral_7B.ipynb: Jupyter notebook analyzing super weights in the Mistral-7B model.
superweight_deepseek_llm_7b_base.ipynb: Jupyter notebook analyzing super weights in the DeepSeek LLM 7B model.
THE_SUPER_WEIGHT_IN_LARGE_LANGUAGE_MODELS.pdf: The original paper detailing the concept and significance of super weights.

🔬 Methodology

The analysis involves:

Identification: Detecting super weights by observing spikes in the mlp.down_proj layer's input and output distributions.
Pruning: Systematically removing identified super weights to assess their impact on model performance.
Evaluation: Measuring changes in output quality, including the prevalence of stopwords and overall coherence.
Visualization: Plotting activation patterns and output distributions to illustrate the effects of super weight modifications.

📊 Findings

Key observations from the experiments include:

Performance Degradation: Pruning a single super weight can significantly impair the model's ability to generate coherent text, often resulting in nonsensical outputs dominated by stopwords.
Activation Disruption: Removal of super weights leads to the disappearance of super activations, which are crucial for maintaining the model's internal representations.
Model Consistency: The location and influence of super weights are consistent across different models and layers, particularly in early layers' mlp.down_proj components.

📌 Conclusion

The experiments underscore the importance of preserving super weights during model compression and quantization processes. Even minimal alterations to these weights can lead to substantial declines in model performance, highlighting the need for targeted strategies that maintain these critical parameters.

📚 References

Yu, M., Wang, D., Shan, Q., Reed, C., & Wan, A. (2024). The Super Weight in Large Language Models. arXiv preprint arXiv:2411.07191.
