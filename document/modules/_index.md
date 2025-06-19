---
title: "模块文档索引与规范"
category: "索引"
updated: 2025-05-21
ai_managed: true
---

## 简介

本索引列出了项目中的所有模块文档，并定义了模块文档（`modules/*.md`）应遵循的标准结构和内容规范。

## 文档清单

| 文档标题              | 文件名 (链接)       | 最后更新日期 | 简要描述                           | 状态   |
| :-------------------- | :------------------ | :----------- | :--------------------------------- | :----- |
| 身份认证模块          | `authentication.md` | YYYY-MM-DD   | 处理用户登录、注册、会话管理等。   | 规划中 |
| 智能卡模块            | `smartcard.md`      | YYYY-MM-DD   | 负责与智能卡硬件的交互和数据处理。 | 规划中 |
| *（更多模块文档）...* |                     |              |                                    |        |

## 模块文档结构规范 (`modules/*.md`)

所有模块文档应遵循以下结构：

```markdown
---
title: "[模块名称]" # 例如：身份认证模块
category: "模块"
tags: [主要技术或功能点] # 例如：[auth, jwt, oauth2]
related: ["../technical.md", "其他相关模块或PRD的相对路径"] # 例如：["../prds/user_login.md"]
updated: YYYY-MM-DD
version: "v1.0.0" # 模块版本
status: "Draft" # Draft | Review | Active | Deprecated | Archived
maintainers: ["@username1", "@username2"]
---
