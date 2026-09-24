# AGENTS.md

面向 AI 协作者的项目协作规范。AI 在改动本仓库前必须遵守。

## 项目

- 基于本模板的 Unity 6 + YokiFrame 2D 项目。
- 本文件只写工程规范，不写具体需求数值。

## 技术栈与结构

- 框架：YokiFrame（`com.hinatayoki.yokiframe`）。
  - `Architecture<T>` + `AbstractService` 组织逻辑服务。
  - `EventKit.Type` 做跨模块通知（强类型只读 struct 事件）。
  - 可选依赖：UniTask / DOTween 已预装；Luban（TableKit）按需接入。
- 目录：
  - `Assets/Scripts/Core/` —— 架构、事件契约、引导入口
  - `Assets/Scripts/Data/` —— 数值与配表
  - `Assets/Scripts/Systems/` —— 纯逻辑服务
  - `Assets/Scripts/UI/` —— 表现层（预制体 + 运行时绑定）

## 三条硬约束（不可违反）

1. **时间只有一个驱动源**：单一 TimeManager 发 Tick，其它系统只消费，禁止各自写 Update 计时。
2. **逻辑/表现纵切**：逻辑层不引用 UI，表现层不改逻辑状态；两层只在「事件」这条线上交汇。
3. **先冻结接口再写逻辑**：事件契约冻结后，改动前必须先明确并说明。

## 工作纪律

- 每个任务开始前 commit 一次、完成后 commit 一次。
- 只允许修改当前任务涉及的文件夹，禁止「顺手优化」别的文件。
- 完成任务后必须打开 Unity 进入 Play Mode 亲手验证，再报告完成。
- 「AI 说已完成」不等于「真的能跑」——以 Play Mode 实测为准。

## 环境备忘

- Unity MCP：`127.0.0.1:8080`（见 `.mcp.json`）。
