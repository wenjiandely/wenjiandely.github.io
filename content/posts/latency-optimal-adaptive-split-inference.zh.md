---
title: "Latency-Optimal Adaptive Split Inference for Privacy-Preserving Cloud-Edge-End Collaboration"
date: 2026-09-24
draft: false
summary: "A planner for encrypted CNN inference across end, edge, and cloud devices. It selects two partition points to reduce total latency while keeping the secret key on the end device."
publicationURL: "https://link.springer.com/chapter/10.1007/978-981-92-5737-9_1"
venue: "ProvSec 2026 · LNCS 17082 · pp. 3-26"
doi: "10.1007/978-981-92-5737-9_1"
hideMeta: true
hideAuthor: true
ShowToc: false
ShowPostNavLinks: false
---

[Springer 官方页面](https://link.springer.com/chapter/10.1007/978-981-92-5737-9_1)

## 研究简介

The end device computes the initial CNN layers, encrypts their output, and retains the secret key. Edge and cloud servers process the remaining layers on ciphertexts. The planner accounts for local computation, encryption, data transfer, and encrypted execution when choosing partition points.

Experiments on CIFAR-10 and PathMNIST report approximately 12.9× and 3.9× speedups over cloud-only FHE and block-level partitioning, respectively, using amortized end-to-end latency. Classification accuracy matches the corresponding plaintext models.

[查看 Springer 官方摘要](https://link.springer.com/chapter/10.1007/978-981-92-5737-9_1#Abs1)。

## 出版信息

| 字段 | 内容 |
| --- | --- |
| 会议 | ProvSec 2026 |
| 论文集 | Provable and Practical Security |
| 丛书 | Lecture Notes in Computer Science, vol. 17082 |
| 页码 | 3-26 |
| 首次在线发表 | 2026-09-24 |
| 引用年份 | 2027（以 Springer 引用记录为准）|
| DOI | [10.1007/978-981-92-5737-9_1](https://doi.org/10.1007/978-981-92-5737-9_1) |
