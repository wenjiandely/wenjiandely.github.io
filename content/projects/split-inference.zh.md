---
title: "同态加密下的协同推理"
weight: 10
summary: "An OpenFHE prototype for CNN partitioning across end, edge, and cloud devices, accompanying a paper published at ProvSec 2026."
hideMeta: true
ShowToc: false
---

使用 OpenFHE 搭建原型，研究 CNN 在端、边、云之间的划分和加密推理。相关工作发表于 [ProvSec 2026]({{< relref "posts/latency-optimal-adaptive-split-inference.md" >}})。

端侧执行模型的前几层，加密中间结果，并将密钥保留在本地；边缘与云端在密文上完成后续计算。划分规划同时考虑计算、加密和通信开销。
