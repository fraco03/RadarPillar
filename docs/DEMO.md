# RadarPillar visualization

Run inference using the checkpoint and matching config described in
[the README](../README.md), then use `tools/visualize_bev.py` to inspect results.
Run `python tools/visualize_bev.py --help` for its inputs.

The optional interactive `tools/demo.py` accepts VoD-format binary point clouds
with the feature layout in the selected config, or `.npy` arrays. It requires
Mayavi, which is not part of the training dependencies. Run it from the repository
root with `--cfg_file tools/cfgs/vod_models/vod_radarpillar_rot.yaml`,
`--data_path <point-cloud-directory>` and `--ckpt <checkpoint>`.
