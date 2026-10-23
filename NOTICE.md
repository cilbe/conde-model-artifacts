# Packaged CLIPSeg hair detector

Upstream model: [CIDAS/clipseg-rd64-refined](https://huggingface.co/CIDAS/clipseg-rd64-refined/tree/999e0328d9e10b484360c477313983f9afdd7050), pinned revision `999e0328d9e10b484360c477313983f9afdd7050`.

The upstream model card identifies these weights as Apache-2.0. The complete license accompanies this notice in `hair-runtime.LICENSE.txt`. CLIPSeg was introduced by Timo Lüddecke and Alexander Ecker in *Image Segmentation Using Text and Image Prompts* (2022). This distribution does not claim authorship of the original model or an endorsement by its authors.

Conde's modification freezes the single text prompt `hair`, exports the vision and decoder graph to ONNX opset 17, fixes the input at 352×352 and batch size one, then restores logits to 512×512 using bilinear interpolation before sigmoid. No fine-tuning, quantization, color correction, or additional training occurs. The original weights are loaded from safetensors with remote code disabled. Their SHA-256 is `d00ca85d6b859f9d07b7cfb8ef26fe9771cb275b34c9368f2ecf603139307f55`.

`hair-runtime.json` records the derived graph's size, SHA-256, preprocessing, tool versions, and public release source. `python -m app.cli.export_hair_runtime --output <new-directory>` reproduces the export in the optional environment (`requirements-color-offline.txt`), using the local model cache by default. Exported bytes can vary with exporter versions; any change requires a new reviewed manifest, parity checks, reference evaluation, and immutable release asset. Production uses CPU ONNX Runtime and never installs Torch/Transformers or downloads weights during a customer request.
