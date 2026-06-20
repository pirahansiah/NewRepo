# ROADMAP.md — NewRepo

## 12-Month Vision

Transform NewRepo from a minimal CV template into a production-grade, multi-architecture computer vision framework with full hardware acceleration, automated CI/CD, and cross-platform deployment.

---

## Q1 (Months 1–3): Foundation & Core Pipeline

**Goal:** Modernize build system, establish core CV primitives, enable cross-platform builds.

| Milestone | Target Date | Status |
|-----------|-------------|--------|
| CMake 3.30 build system with C++26 support | Month 1 | Planned |
| OpenCV 5 integration (G-API + DNN modules) | Month 1 | Planned |
| Cross-platform CI (Windows 11, macOS 27, Ubuntu 26.04) | Month 2 | Planned |
| Core image processing primitives (filter, transform, segment) | Month 2 | Planned |
| Catch2 test suite with >80% coverage | Month 3 | Planned |
| Python 3.14 bindings via pybind11 | Month 3 | Planned |

**Deliverables:**
- `CMakeLists.txt` replacing `.vcxproj` for portable builds
- `src/` directory with modular CV components
- `.github/workflows/ci.yml` for automated builds
- `tests/` directory with unit and integration tests

---

## Q2 (Months 4–6): Hardware Acceleration

**Goal:** Implement GPU and Neural Engine acceleration across all target platforms.

| Milestone | Target Date | Status |
|-----------|-------------|--------|
| CUDA 13 kernel library (basic CV ops) | Month 4 | Planned |
| Apple M5 Max Neural Engine optimization | Month 4 | Planned |
| Intel Ultra 9 AVX-512 vectorized pipelines | Month 5 | Planned |
| NVIDIA Spark Tensor Core INT8 inference | Month 5 | Planned |
| Raspberry Pi 5 ARM64 optimized routines | Month 6 | Planned |
| Hardware-specific benchmark suite | Month 6 | Planned |

**Deliverables:**
- `src/gpu/cuda13/` — CUDA kernel implementations
- `src/gpu/metal/` — Apple Neural Engine integration
- `src/gpu/avx512/` — Intel vectorized pipelines
- `benchmarks/` — Performance regression tests

---

## Q3 (Months 7–9): Model Serving & Deployment

**Goal:** Production-grade inference pipeline with model management and deployment tooling.

| Milestone | Target Date | Status |
|-----------|-------------|--------|
| ONNX Runtime + TensorRT model serving | Month 7 | Planned |
| Docker multi-arch images (x64, ARM64) | Month 7 | Planned |
| Model quantization pipeline (FP32 → INT8) | Month 8 | Planned |
| REST API for inference endpoints | Month 8 | Planned |
| Kubernetes deployment manifests | Month 9 | Planned |
| End-to-end latency <5ms on target hardware | Month 9 | Planned |

**Deliverables:**
- `deploy/` — Docker, K8s, and systemd configs
- `src/inference/` — Model serving with dynamic batching
- `scripts/quantize.py` — Quantization-aware training support

---

## Q4 (Months 10–12): Polish & Production Release

**Goal:** Production hardening, documentation, and v1.0 release.

| Milestone | Target Date | Status |
|-----------|-------------|--------|
| Comprehensive documentation (API + usage) | Month 10 | Planned |
| Performance tuning pass (all platforms) | Month 10 | Planned |
| Security audit and hardening | Month 11 | Planned |
| v1.0 release candidate | Month 11 | Planned |
| Public release with PyPI and conda packages | Month 12 | Planned |
| Community contribution guidelines | Month 12 | Planned |

**Deliverables:**
- `docs/` — Sphinx/Doxygen generated documentation
- GitHub Release v1.0.0
- `CONTRIBUTING.md` and `CODE_OF_CONDUCT.md`
- PyPI package: `newrepo-cv`

---

## Technical Debt

| Item | Priority | Effort | Notes |
|------|----------|--------|-------|
| Replace `.vcxproj` with CMake-only builds | High | 2 days | VS project files retained for IDE compatibility only |
| Fix `void main()` → `int main()` in Source.cpp | High | 5 min | Undefined behavior in standard C++ |
| Add `#pragma once` / include guards to all headers | Medium | 1 hour | Currently no header files |
| Remove `iostream` dependency, use `std::print` (C++23) | Medium | 1 hour | Modernize all print statements |
| Add `.clang-format` and `.clang-tidy` configs | Medium | 2 hours | Enforce consistent code style |
| Upgrade toolset v142 → v143 in `.vcxproj` | Low | 30 min | VS2022 native toolset |
| Add Git LFS for model weights and test images | Low | 1 hour | `.gitattributes` already configured |
| Replace raw pointers with `std::unique_ptr`/`std::shared_ptr` | Medium | TBD | Depends on actual CV code added |

---

## Future Features

| Feature | Complexity | Dependencies |
|---------|-----------|--------------|
| Real-time video stream processing | High | CUDA 13, G-API |
| Multi-camera calibration toolkit | Medium | OpenCV calib3d |
| Edge deployment (ONNX, TensorRT, CoreML) | High | Model serving pipeline |
| Web-based visualization dashboard | Medium | WebSockets, HTML5 Canvas |
| Python SDK with async inference | Medium | pybind11, asyncio |
| Automated hyperparameter tuning | High | Optuna, model serving |
| Federated learning support | Very High | Distributed training infra |
| AR/VR overlay integration | High | Metal, Vulkan |
| Video understanding (temporal models) | Very High | ViT, Swin Transformer |
| AutoML pipeline for CV tasks | Very High | NAS, model serving |
