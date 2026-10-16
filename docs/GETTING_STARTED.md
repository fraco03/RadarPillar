# View-of-Delft workflow

This checkout supports RadarPillar on View-of-Delft (VoD). Other OpenPCDet
detectors and the Astyx, nuScenes and KITTI dataset loaders have been removed.
KITTI-format parsing, calibration and evaluation utilities remain because VoD uses them.

Follow the installation, data preparation, training and evaluation commands in
[the project README](../README.md). The checkpoint configuration is
`tools/cfgs/vod_models/vod_radarpillar_rot.yaml`.

The retained pipeline is PillarVFE → PillarAttention → PointPillarScatter →
BaseBEVBackbone → AnchorHeadSingle. The detector retains the `PointPillar` name
and its parameter names for checkpoint compatibility.

CUDA extensions still required: `iou3d_nms_cuda` for detection/evaluation and
`roiaware_pool3d_cuda` for points-in-boxes operations in dataset preparation and
augmentation. `spconv` is still used for voxelization. PointNet++ and RoIPointPool
extensions are no longer built.

## Structural checks

Run `python tools/check_project_structure.py` from the repository root. This
checks Python syntax, local imports, configured model registry entries, base
config paths and CUDA build sources without importing PyTorch. Inference and
training still need a separate smoke test in the NVIDIA environment.
