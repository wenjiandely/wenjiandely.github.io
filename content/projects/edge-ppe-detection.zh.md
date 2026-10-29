---
title: "云边协同 PPE 检测"
weight: 20
summary: "PPE detection using YOLOv8n on Raspberry Pi 4B and YOLOv8x on RTX 4060, with selective offloading and temporal state filtering."
hideMeta: true
ShowToc: false
repositoryURL: "https://github.com/wenjiandely/edge_computing"
---

[GitHub 仓库: edge_computing](https://github.com/wenjiandely/edge_computing)

我负责这个 PPE 检测项目，基于 SH17 数据集训练和微调 YOLOv8 模型，识别人员、安全帽、反光背心等目标，并判断防护装备的佩戴情况。

树莓派 4B 通过 NCNN 运行 YOLOv8n，RTX 4060 上的 YOLOv8x 负责复核较难判断的画面。端侧根据检测置信度、图像模糊度、目标大小、人员密集程度及疑似违规情况，选择需要上传的帧。

系统用 IoU 匹配追踪人员，结合人员与装备的位置关系判断是否合规，再用连续 5 帧的结果减少误报。图像和结果通过 FastAPI 异步传输；连接中断时，端侧仍可继续检测。
