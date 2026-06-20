# NewRepo

[![C++](https://img.shields.io/badge/C++-20/23-00599C?style=for-the-badge&logo=cplusplus)](https://isocpp.org)
[![Visual Studio](https://img.shields.io/badge/Visual_Studio-2022-5C2D91?style=for-the-badge&logo=visualstudio)](https://visualstudio.microsoft.com)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.11+-5C3EE8?style=for-the-badge&logo=opencv)](https://opencv.org)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## Overview

C++ Visual Studio project template for computer vision and image processing applications using OpenCV.

## Project Structure

```
NewRepo/
├── .gitattributes              # Git LFS configuration
├── .gitignore                  # VS/C++ ignore rules
├── FarshidPirahanSiah.sln      # Visual Studio solution
├── FarshidPirahanSiah.vcxproj  # VS project file
├── FarshidPirahanSiah.vcxproj.filters  # VS filter groups
├── Source.cpp                  # Main source file
└── README.md
```

## Requirements

| Component | Version |
|-----------|---------|
| Visual Studio | 2022 (v17.x) |
| MSVC | v143+ |
| Windows SDK | 10.0.22621.0 |
| OpenCV | 4.11+ |
| C++ Standard | C++20/23 |

## Build Instructions

### Prerequisites

1. **Visual Studio 2022** with "Desktop development with C++" workload
2. **OpenCV 4.11+** — Download from [opencv.org](https://opencv.org/releases/)
3. **CMake 3.30+** (optional, for alternative builds)

### Visual Studio Build

1. Open `FarshidPirahanSiah.sln` in Visual Studio 2022
2. Configure OpenCV include/lib paths in project properties
3. Select build configuration (Debug/Release) and platform (x64)
4. Build → Build Solution (Ctrl+Shift+B)

### CMake Build (Alternative)

```cmake
cmake_minimum_required(VERSION 3.30)
project(FarshidPirahanSiah LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(OpenCV REQUIRED)
add_executable(FarshidPirahanSiah Source.cpp)
target_link_libraries(FarshidPirahanSiah ${OpenCV_LIBS})
```

```bash
cmake -B build -G "Visual Studio 17 2022"
cmake --build build --config Release
```

## 2025-2026 C++ & Computer Vision

### C++ Standards Evolution

| Standard | Key Features |
|----------|--------------|
| C++20 | Concepts, ranges, coroutines, modules |
| C++23 | `std::expected`, `std::print`, `std::flat_map` |
| C++26 | Contracts, reflection, `std::sender` |

### OpenCV 4.x (2025-2026)

| Feature | Description |
|---------|-------------|
| OpenCL backend | GPU acceleration across vendors |
| G-API | Graph-based image processing pipeline |
| CUDA module | NVIDIA GPU acceleration |
| DNN module | ONNX, TensorRT, OpenVINO inference |
| Vision Transformers | ViT, Swin Transformer support |

### Modern C++ Best Practices

```cpp
// C++23: std::print (replaces iostream for debugging)
#include <print>
std::print("Image size: {}x{}", width, height);

// C++20: Ranges for cleaner image processing
#include <ranges>
auto filtered = pixels | std::views::filter([](auto p) { return p > threshold; });

// C++23: std::expected for error handling
#include <expected>
std::expected<Image, Error> loadImage(const std::string& path);
```

### Dependencies (2025-2026)

| Library | Purpose | Version |
|---------|---------|---------|
| OpenCV | Computer Vision | 4.11+ |
| Eigen | Linear Algebra | 3.4+ |
| fmt | String Formatting | 11.x |
| Catch2 | Unit Testing | 3.7+ |
| spdlog | Logging | 1.14+ |
| pybind11 | Python Bindings | 2.13+ |

## Resources

- [C++ Reference](https://en.cppreference.com)
- [OpenCV Tutorials](https://docs.opencv.org/4.x/)
- [Visual Studio Docs](https://learn.microsoft.com/en-us/cpp/)
- [C++ Core Guidelines](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)

## License

MIT License

---

**Maintainer:** [Farshid Pirahansiah](https://github.com/pirahansiah)