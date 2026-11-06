# GPU checks for pull requests

This repository records a single GitHub Actions run against the exact commits
listed in the workflow. It used an ephemeral, self-hosted Windows runner with
an NVIDIA GeForce RTX 4060 Laptop GPU, CUDA 12.4 and PyTorch 2.6.0. The runner
was removed after the job; these are not GitHub-hosted GPU results.

The [Actions run](https://github.com/bingdongni/gpu-pr-validation-20261106-ef7243290e/actions/runs/42237540425)
passed. The [exported job log](gpu-validation.log) copies GitHub's redacted
output with terminal color codes removed. GitHub may require sign-in to view
the Actions log itself.

The workflow uses Python environments already present on the runner. In
particular, the TorchSim regression used PyTorch 2.6.0, whereas the installed
NVIDIA ALCHEMI toolkit's `torch` extra specifies PyTorch 2.8 or later. The
results therefore cover the selected tests, not a fully supported TorchSim GPU
installation, multi-GPU execution, or performance.

The checked changes are:

- [TorchMetrics ERGAS #3612](https://github.com/Lightning-AI/torchmetrics/pull/3612): 19 CUDA cases passed.
- [TorchMetrics RASE #3613](https://github.com/Lightning-AI/torchmetrics/pull/3613): 8 CUDA cases passed.
- [ForgeKernel #6](https://github.com/OpenBMB/ForgeKernel/pull/6): 21 CPU and CUDA cases passed.
- [HyInv #5](https://github.com/Tencent-Hunyuan/Hyra-results/pull/5): 7 cases passed, including reference-model CUDA inference.
- [TorchSim #639](https://github.com/TorchSim/torch-sim/pull/639): 12 cases passed, including 6 on CUDA.
