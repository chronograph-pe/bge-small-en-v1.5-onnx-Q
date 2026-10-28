# fast-bge-small-en-v1.5 (fp32 ONNX)

The fastembed model `fast-bge-small-en-v1.5` that Chronograph's Grand server
(Mastra Factory) bakes into its image for Recall. It is an fp32 ONNX export of
[BAAI/bge-small-en-v1.5](https://huggingface.co/BAAI/bge-small-en-v1.5),
384-dimension embeddings.

`model_optimized.onnx` (132,883,455 bytes) is over GitHub's per-file limit, so
it lives on the [`fp32-2023-10-16` release](../../releases/tag/fp32-2023-10-16)
with every other model file. The files in this tree are the same bytes, kept
for review. Verify a download with `shasum -a 256 -c SHA256SUMS`.

**Compatibility.** Recall's stored vectors were produced with these weights.
Qdrant's smaller Hugging Face export
(`Qdrant/bge-small-en-v1.5-onnx-Q`, 66,465,124 bytes) gives the same vectors:
cosine 1.000000 against these on sample texts, identical neighbour ranking,
pairwise similarities within 0.0002. A different base model or a different
pooling would not; changing that means re-embedding. See PROVENANCE.md.
