# Conde public model artifacts

This repository distributes checksum-pinned public model derivatives and their licenses. It contains no private application source, credentials, customer photographs or customer records.

## Hair detector

The hair-clipseg-refined-v1 release exports CIDAS/clipseg-rd64-refined revision 999e0328d9e10b484360c477313983f9afdd7050 to CPU ONNX, with a fixed hair prompt and image geometry. Upstream weights are Apache-2.0 according to the pinned model card. See LICENSE, NOTICE.md, hair-runtime.json and SHA256SUMS for the upstream source, modifications, preprocessing and artifact integrity.

The graph segments hair; it does not by itself establish a reliable hair-shade recommendation or a customer accuracy rate. No fine-tuning or customer images were used for this export.
