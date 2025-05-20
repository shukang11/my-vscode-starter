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

	•	_index.md 文件应提供文档链接清单与概览表格
	•	使用语义命名、统一格式，避免重复概念与缩写混乱

⸻

模块文档统一模板（modules/*.md）

# 模块名称（如：Authentication 身份认证模块）

## 1. 模块概述
简述功能职责、入口位置、典型使用流程。

## 2. 技术实现细节
- 技术选型、架构概览
- 状态流转、数据结构
- 特殊逻辑、异常处理方式

## 3. API 接口说明
| 方法 | 路由   | 描述 | 权限 |
| ---- | ------ | ---- | ---- |
| POST | /login | 登录 | 公共 |

## 4. 依赖关系
- 引用模块：`user-profile`
- 被依赖模块：`session`

## 5. 测试要点
- 测试边界：重复登录、token 失效
- mock 要求：第三方认证模拟



⸻

产品需求文档规范（prds/*.md）

# 功能名称：用户登录

## 背景与动机
用户需要在多个端安全登录系统。

## 用户故事
- 作为用户，我希望能输入账号密码登录；
- 作为新用户，我希望能快速注册账户。

## 原型链接
[登录界面原型](https://example.com)

## 验收标准
- 正确输入可登录，错误输入提示原因
- 登录后跳转至首页


⸻

进度与状态（progress.md / status-report.md）

# 当前进度（2025-W21）

## 本周目标
- 完成认证模块初版
- 对接测试框架

## 实际进展
- 接口完成 80%
- 单测覆盖率达 70%

# 当前状态报告

## 已知问题
- Token 自动刷新偶发失败

## 风险与缓解
- 风险：第三方认证服务不稳定
- 缓解：增加本地降级缓存策略



⸻

归档与版本控制（archive/）

每次版本交付，将 progress.md 与 status-report.md 拷贝为：

archive/
├── v1_progress.md
├── v1_status-report.md

_index.md 记录历史版本列表与变更记录摘要。

⸻
