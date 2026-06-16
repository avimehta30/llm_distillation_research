# Does Distillation of Large Language Models Preserve Watermarks?

Research conducted at the Chinese University of Hong Kong (CUHK) under the
supervision of Dr. Xixin Wu, in collaboration with Jaehyun Kim
(Sungkyunkwan University).

## Overview
As LLMs grow in scale, two trends have emerged in parallel: watermarking
techniques to verify machine-generated content, and knowledge distillation
to compress large models into smaller, faster ones. This research asks a
critical question — do watermarks survive the distillation process?

We fine-tuned GPT-2 Large as a teacher model, applied a token-based
watermarking scheme (green/red token manipulation), and distilled it to a
student model using MiniLLM. Our findings show that distillation does NOT
preserve watermarks. In response, we proposed a joint optimization framework
with regularization to maintain watermark integrity through distillation.

## Key Findings
- Distillation does not preserve LLM watermarks — the student model's output
  was classified as unwatermarked (z-score: 0.473, well below the threshold of 4.0)
- MiniLLM outperformed standard KD on the DollyEval benchmark (Rouge-L: 10.485 vs 6.865)
- Proposed a joint loss function combining task loss, watermark distance, and
  regularization to preserve watermarks through distillation

## Tech Stack
- **Models:** GPT-2 Large (774M params, teacher), GPT-2 Medium (345M params, student)
- **Distillation:** MiniLLM (Policy Gradient-based knowledge distillation)
- **Watermarking:** Green/red token manipulation with z-score detection
- **Evaluation:** Rouge-L, Z-score, P-value, KL Divergence
- **Frameworks:** PyTorch, HuggingFace Transformers

## Poster
![Research Poster](poster.png)

[Download PDF](https://github.com/avimehta30/llm_distillation_research/raw/main/Large%20Language%20Model%20Distillation%20Poster.pdf)
