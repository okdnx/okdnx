# Kosei Okudono

**LLM inference, evaluation, and ML systems**

I build small LLM experiments with inspectable code, recorded measurements, and per-example evaluation results. My current work uses PyTorch, Hugging Face Transformers, and LoRA/GRPO on Apple Silicon and CUDA.

I'm interested in inference engineering roles and in understanding how generation latency, memory use, and output quality interact.

## Featured work

### [Qwen inference profiling & post-training experiments](https://github.com/okdnx/rl-training)

A Qwen3-1.7B pipeline covering local inference measurement, adapter training, and verifiable arithmetic evaluation.

- **Inference:** recorded 31.56 output tok/s median on MPS FP16, with one warm-up and three measured runs. This is single-request generation timing, not a serving-throughput benchmark.
- **Evaluation:** base → LoRA SFT → SFT + GRPO accuracy of **26.0% → 37.5% → 39.5%** on the same 200-question test split.
- **Reviewability:** raw JSON results, dataset hashes, an AST-based verifier, paired comparisons, and a separate CUDA training environment.

[Read the results and reproduction steps](https://github.com/okdnx/rl-training#recorded-results) · [Inspect the profiler](https://github.com/okdnx/rl-training/blob/main/profile_inference.py) · [Inspect the verifier](https://github.com/okdnx/rl-training/blob/main/scripts/verifier.py)

## Current direction

- Measure prefill/decode behavior, time to first token, memory, and latency distributions.
- Learn SGLang serving internals and GPU performance fundamentals; compare backends under controlled workloads.
- Extend small experiments into reproducible inference benchmarks with explicit hardware and workload definitions.

These are areas I am developing. The linked repositories distinguish recorded results from planned work.

## More code

[File Lab](https://github.com/okdnx/01file_lab) — a small Python CLI for text, CSV, JSON, and JSONL, with function-level and CLI tests.

日本語: LLM推論・評価・MLシステムに取り組んでいます。実測条件と結果を確認できる実験を公開し、推論エンジニアを目指しています。
