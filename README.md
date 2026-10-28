# fast-bge-small-en-v1.5 (fp32 ONNX)

The fastembed model `fast-bge-small-en-v1.5` that Chronograph's Grand server
(Mastra Factory) bakes into its image for Recall. It is an fp32 ONNX export of
[BAAI/bge-small-en-v1.5](https://huggingface.co/BAAI/bge-small-en-v1.5),
384-dimension embeddings.

`model_optimized.onnx` (132,883,455 bytes) is over GitHub's per-file limit, so
it lives on the [`fp32-2023-10-16` release](../../releases/tag/fp32-2023-10-16)
with every other model file. The files in this tree are the same bytes, kept
for review. Verify a download with `shasum -a 256 -c SHA256SUMS`.

**Do not swap this for another export.** Recall's stored vectors were produced
by these exact weights; a different file (including Qdrant's quantized
`Qdrant/bge-small-en-v1.5-onnx-Q` on Hugging Face) gives different vectors and
silently degrades search. Changing it means re-embedding. See PROVENANCE.md.
