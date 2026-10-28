# Provenance

## Current files (fp32, from Qdrant's 2023 fastembed tarball)

The model files here and on the `fp32-2023-10-16` release are the files from
Qdrant's original fastembed distribution,
`https://storage.googleapis.com/qdrant-fastembed/fast-bge-small-en-v1.5.tar.gz`
(sha256 `3858004b3822f64f940280874b8f2d2dc25b34a4f3eb3cdf617bdceeb21ed9ed`),
file dates 2023-10-16. That bucket now returns 403.

They were copied on 2026-10-28 from the Grand server image that had extracted
the tarball:
`750910107203.dkr.ecr.us-east-1.amazonaws.com/cg-factory@sha256:9582ad4c427607b78ab71eca81432b66b28693b0898b1af4f24b76b1e1101e20`,
path `/home/node/.cache/mastra/fastembed-models/fast-bge-small-en-v1.5/`.
Checksums are in `SHA256SUMS`.

`ort_config.json` records an Optimum 1.13.2 export, optimization level 2,
no quantization, no fp16.

## Earlier commit (not used)

The first commit in this repository, `728ff68`, holds a snapshot of the
Hugging Face repo
[Qdrant/bge-small-en-v1.5-onnx-Q](https://huggingface.co/Qdrant/bge-small-en-v1.5-onnx-Q)
at `aa8f8b060edb00e03bfdd08813a2949946c8ba55`. Its `model_optimized.onnx`
(66,465,124 bytes, sha256 `51f1bd0a…`) is a different, smaller export of the
same base model. It is what `@mastra/fastembed` 1.3.4 downloads on a cold
cache, and it is NOT the model Recall's vectors were produced with. Only
tokenizer.json and vocab.txt are identical between the two.
