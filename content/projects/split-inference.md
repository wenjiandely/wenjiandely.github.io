---
title: "Split Inference with Homomorphic Encryption"
weight: 10
summary: "An OpenFHE prototype for choosing where to split encrypted CNN inference."
hideMeta: true
ShowToc: false
---

This OpenFHE prototype supports the research published in my [ProvSec 2026 paper]({{< relref "posts/latency-optimal-adaptive-split-inference.md" >}}).

The end device runs the initial CNN layers and encrypts their output, keeping the secret key locally. Edge and cloud servers process the remaining layers on ciphertexts. The planner chooses partition points based on computation, encryption, and communication costs.
