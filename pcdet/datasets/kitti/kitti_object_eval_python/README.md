# Evaluation helpers used by View-of-Delft

Adapted from [traveller59/kitti-object-eval-python](https://github.com/traveller59/kitti-object-eval-python).
The evaluator and rotated-IoU implementation are retained because `VodDataset`
uses KITTI-format annotations and calls `eval.get_vod_eval_result`.

Run evaluation through `tools/test.py` using a VoD configuration, as described
in the project README. The unused KITTI dataset loader and standalone KITTI
`evaluate.py` entry point have been removed. This directory does not provide
a separate KITTI dataset workflow.

Evaluation requires NumPy, Numba and a working CUDA environment.
