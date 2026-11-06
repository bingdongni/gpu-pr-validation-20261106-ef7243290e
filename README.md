# GPU checks for pull requests

This repository records a single GitHub Actions run against the exact commits
listed in the workflow. It used an ephemeral, self-hosted Windows runner with
an NVIDIA GeForce RTX 4060 Laptop GPU, CUDA 12.4 and PyTorch 2.6.0. The runner
was removed after the job; these are not GitHub-hosted GPU results.

The workflow uses Python environments already present on the runner. In
particular, the TorchSim regression used PyTorch 2.6.0, whereas the installed
NVIDIA ALCHEMI toolkit's `torch` extra specifies PyTorch 2.8 or later. The
results therefore cover the selected tests, not a fully supported TorchSim GPU
installation, multi-GPU execution, or performance.

The checked changes are:

- [TorchMetrics ERGAS #3612](https://github.com/Lightning-AI/torchmetrics/pull/3612)
- [TorchMetrics RASE #3613](https://github.com/Lightning-AI/torchmetrics/pull/3613)
- [ForgeKernel #6](https://github.com/OpenBMB/ForgeKernel/pull/6)
- [HyInv #5](https://github.com/Tencent-Hunyuan/Hyra-results/pull/5)
- [TorchSim #639](https://github.com/TorchSim/torch-sim/pull/639)
