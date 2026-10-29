---
title: "SHA-2 与 LZ4 的 HLS 实现"
weight: 30
summary: "SHA-224, SHA-256, and LZ4 operator development in Vivado HLS, with work on pipelining, parallel execution, resource reuse, and interfaces."
hideMeta: true
ShowToc: false
repositoryURL: "https://github.com/wenjiandely/hlstrack2025-master"
---

[GitHub 仓库: hlstrack2025-master](https://github.com/wenjiandely/hlstrack2025-master)

我参与了 SHA-224、SHA-256 和 LZ4 算子的 C/C++ 实现，以及 Vivado HLS 综合优化。

优化主要围绕流水线、并行计算、资源复用和硬件接口展开，分别处理计算和数据传输中的开销。
