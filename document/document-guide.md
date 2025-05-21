# 项目文档管理指南

## 文档目的

本指南规范项目文档的管理流程，确保信息的结构化、可追溯与易维护性，服务于跨角色协作与 AI 自动处理。

---

## 项目目录结构

```bash
document/
├── structure.md                     # 项目结构与模块关系说明
├── technical.md                     # 技术背景与技术栈说明
├── progress.md                      # 当前开发进度
├── status-report.md                 # 当前问题与风险
├── README.md                        # 项目背景介绍
│
├── modules/
│   ├── _index.md                    # 模块文档索引与依赖矩阵
│   ├── authentication.md           # 模块文档示例
│   ├── smartcard.md
│
├── prds/
│   ├── _index.md                    # 产品需求文档索引
│   ├── feature1.md
│
├── archive/
│   ├── _index.md                    # 历史版本归档索引
│   ├── v1_progress.md
│   ├── v1_status-report.md



⸻

AI 可读性规范

所有文档应在文件头部包含如下 YAML 元数据：

---
title: 身份认证模块
category: 模块
tags: [auth, login]
related: [../technical.md]
updated: 2025-05-20
---

	•	`_index.md` 文件应提供其所在目录文档的链接清单与概览表格。
	•	使用语义命名、统一格式，避免重复概念与缩写混乱。

⸻

模块文档通用指南 (modules/*.md)

模块文档旨在详细描述项目中的各个功能模块。通常应包含模块概述、技术实现细节、API接口说明（若有）、依赖关系和测试要点。

具体的章节结构和内容规范，请参考相应模块目录下的 `_index.md` 文件，或在模块文档自身的头部进行详细定义。

⸻

产品需求文档通用指南 (prds/*.md)

产品需求文档（PRD）用于清晰地阐述产品功能的需求。通常应包含背景与动机、用户故事、原型链接（若有）和验收标准。

具体的章节结构和内容规范，请参考 `prds/_index.md` 文件，或在各PRD文档自身的头部进行详细定义。

⸻

进度与状态（progress.md / status-report.md）

**目标**：这两个文档由 AI 全自动或半自动更新，以提供实时、准确的项目追踪。

**`progress.md` - 当前进度与任务清单**

此文档专注于当前正在进行的任务、整体进度和即将到来的里程碑。AI 将根据项目管理工具的更新、代码提交、合并请求以及与团队成员的互动来更新此文件。

其详细的 YAML frontmatter 结构、"总体进度"部分的具体条目、以及"任务清单"表格的列定义和状态说明，均定义在 `progress.md` 文件自身的起始部分。

**`status-report.md` - 状态报告、问题、反思**

此文档用于记录项目执行过程中的关键问题、解决方案、以及从中获得的经验反思。AI 将从错误报告、代码审查评论、以及团队讨论中收集信息并进行结构化记录，侧重于有价值的经验沉淀而非流水账式的日志。

其详细的 YAML frontmatter 结构、“日志条目”表格的列定义和类型说明（聚焦于Issue, Blocker, Risk, Learning），以及其他各部分的具体格式，均定义在 `status-report.md` 文件自身的起始部分。

⸻

归档与版本控制（archive/）

每次版本交付，将 progress.md 与 status-report.md 拷贝为：

archive/
├── v1_progress.md
├── v1_status-report.md

_index.md 记录历史版本列表与变更记录摘要。

⸻
