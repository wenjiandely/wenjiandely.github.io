---
title: "Cloud-Assisted PPE Detection"
weight: 20
summary: "A local detector that sends selected frames to a larger server-side model for PPE checks."
hideMeta: true
ShowToc: false
repositoryURL: "https://github.com/wenjiandely/edge_computing"
---

[Repository: edge_computing](https://github.com/wenjiandely/edge_computing)

I led a PPE detection project using YOLOv8 models trained and fine-tuned on SH17 to detect people, helmets, reflective vests, and related objects.

A Raspberry Pi 4B runs YOLOv8n with NCNN, while an RTX 4060 runs YOLOv8x to review difficult frames. The device selects frames for upload based on detection confidence, blur, object size, crowding, and suspected violations.

IoU matching tracks people across frames. Spatial relationships between people and PPE detections determine compliance, and a five-frame state filter reduces transient alerts. FastAPI handles asynchronous communication between the device and server. If the connection fails, detection continues locally.
