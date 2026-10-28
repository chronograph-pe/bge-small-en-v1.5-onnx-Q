# Provenance

Snapshot of the Hugging Face repository
[Qdrant/bge-small-en-v1.5-onnx-Q](https://huggingface.co/Qdrant/bge-small-en-v1.5-onnx-Q)
at commit `aa8f8b060edb00e03bfdd08813a2949946c8ba55` (last modified upstream
2026-09-24), taken 2026-10-28. It is a quantized ONNX port of
[BAAI/bge-small-en-v1.5](https://huggingface.co/BAAI/bge-small-en-v1.5).

Every file except this one, `LICENSE` and `SHA256SUMS` is byte-for-byte the
upstream file at that commit. `SHA256SUMS` lists their checksums; the
`model_optimized.onnx` checksum matches the LFS object id Hugging Face reports
for it. Upstream `.gitattributes` (LFS filters) is not included; this
repository stores the model as a plain git blob.

Why this mirror exists: `@mastra/fastembed` downloads this model
(`fast-bge-small-en-v1.5`) from Hugging Face `main`, which is not pinned.
Builds that bake the model in need an immutable, self-controlled source.
The copy of the model at `$HOME/.cache/mastra/fastembed-models/fast-bge-small-en-v1.5/`
is what the library reads; it needs `config.json`, `tokenizer.json`,
`tokenizer_config.json`, `special_tokens_map.json` and `model_optimized.onnx`.

Verify a download with:

    shasum -a 256 -c SHA256SUMS
