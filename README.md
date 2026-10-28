<p align="center">
  <img src="./diagrams/product_logo.png" width="280" alt="EyeKnow — Cognitive Load Tracker" />
</p>

# EyeKnow

<p align="center">
  <strong>用普通摄像头，把算法学习中的认知黑箱变成可解释的证据</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Project-Beijing%20Municipal%20Innovation-blue?style=for-the-badge" alt="Beijing Municipal Innovation Project" />
  <img src="https://img.shields.io/badge/Status-V1.0%20Pilot-brightgreen?style=for-the-badge" alt="Status V1.0 Pilot" />
  <img src="https://img.shields.io/badge/Target-Algorithm%20Learners%20%26%20Teachers-green?style=for-the-badge" alt="Target Audience" />
</p>

---

## 这是什么

EyeKnow 是一个面向**算法学习者和任课教师**的认知负荷评估平台。它不需要昂贵的专业眼动仪，只用电脑自带的普通摄像头，就能在不打断解题的前提下，捕捉你的注意力分配模式，告诉你：

> 你刚才在题目描述和样例之间反复回看了 2 分 14 秒，当前负荷偏高——可能需要换个策略。

教师端则把班级层面的共性卡点可视化，让"后排那位一直沉默的同学"不再被埋没。

---

## 产品长什么样

### 整体框架

<p align="center">
  <img src="./diagrams/framework.png" width="800" alt="EyeKnow 四层架构：采集 → 特征 → 模型 → 应用" />
</p>

---

### 学生端界面 —— 低干扰 HUD

任务中默认只有一个小胶囊显示状态，不遮挡代码区。只有高负荷持续一段时间才会提示，而且提示可忽略、可暂停、可标记"不准确"。

<p align="center">
  <img src="./diagrams/user_interface.png" width="800" alt="学生端 HUD 界面" />
</p>

---

## 核心亮点

| 亮点 | 一句话 |
|---|---|
| 零硬件门槛 | 普通 RGB 摄像头（L2CS-Net），9 点校准即可 |
| 不打扰解题 | 默认折叠 HUD，提示可忽略/暂停/标记不准 |
| 全链路隐私 | 原始摄像头帧不落盘不上传，云端仅存派生特征 |
| 质量门控 | 校准/遮挡/帧率异常时不强行给"确定结论" |
| 可解释模型 | KMeans 无监督聚类 + SVM 4 级分类，输出置信度和原因码 |

---

## 快速开始（V1.0 教学试点版）

```bash
# 1. 克隆仓库
git clone https://github.com/CoWora/cognitive-load-tracker.git

# 2. 安装 Chrome/Edge 浏览器插件（洛谷页面连接与 AOI 上报）
# 参考插件目录下的 README，开启开发者模式加载

# 3. 运行 Python 学生端采集程序
cd cognitive-load-tracker/client
python main.py
```

首次启动会引导你完成：知情同意 → 设备检查 → 9 点校准 → 进入洛谷做题。详细流程见 [PRD_Product_Design.md](./PRD_Product_Design.md)。

---

## 我的角色与贡献

本仓库为**产品侧作品集**，核心算法与工程代码由技术团队维护。作为产品负责人，我的主要工作：

- **架构与 PRD**：主导设计"采集 → 特征 → 模型 → 应用"四层架构，独立撰写完整 PRD（含状态机、质量门控、异常降级、数据 schema、试点研究设计等）
- **用户研究**：通过课堂观察和教师访谈，从"结果评价"反推"过程可见性"的核心痛点，确立非侵入、低干扰的产品定位
- **从原型到可试点**：补齐"判断可靠性、隐私合规、教师工作流、验收标准"四项产品化关键缺口，推动从 10 秒轮询原型到 2–3 秒端到端刷新的体验升级
- **项目统筹**：协调算法与工程团队推进，主导赛事路演。项目获评**北京市级大学生创新创业训练计划**立项、中国大学生计算机设计大赛**二等奖**

---

## 文档导览

| 文档 | 内容 |
|---|---|
| [PRD_Product_Design.md](./PRD_Product_Design.md) | 核心产品设计：四层架构、功能清单、详细设计、试点方案、验收标准、开放问题 |
| [EyeKnow_Project_Proposal_Full.pdf](./EyeKnow_Project_Proposal_Full.pdf) | 项目计划书：市场背景、技术路线、团队与落地情况 |
| [EyeKnow_Business_Plan_Full.pdf](./EyeKnow_Business_Plan_Full.pdf) | 商业计划书：竞品分析、SWOT、财务测算与风险控制 |

---

## 致谢

EyeKnow 项目团队的算法和工程同学，以及指导教师和试点课程的师生们。

---

> ⚠️ **重要声明**：V1.0 明确不做情绪识别、人格判断、疾病诊断；不把负荷等级用于成绩、排名、奖惩；不承诺仅凭眼动判断"会不会做"。产品定位是**认知过程的镜子**，不是注意力监控器。