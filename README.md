# YokiFrame 2D 项目模板（Unity 6）

开箱即用的 Unity 6 2D 项目模板，预装 **YokiFrame** + **UniTask** + **DOTween**，面向线下 Game Jam / 快速原型。

## 已包含的依赖

| 依赖 | 类型 | 位置 |
|------|------|------|
| YokiFrame | UPM（Git URL） | `Packages/manifest.json` |
| UniTask | UPM（Git URL） | `Packages/manifest.json` |
| DOTween（HOTween v2） | 预编译 DLL + 源码模块 | `Assets/Plugins/Demigiant/DOTween/` |

> YokiFrame 的 `YOKIFRAME_UNITASK_SUPPORT` / `YOKIFRAME_DOTWEEN_SUPPORT` 宏会在打开项目后**自动检测并写入** PlayerSettings，无需手动配置。

## 如何使用

1. 在 GitHub 仓库页点 **Use this template** 创建新仓库；
2. clone 下来，用 **Unity 6000.3.x** 打开；
3. 等首次导入完成（自动下载 YokiFrame + UniTask，DOTween 直接可用）；
4. 改 `ProjectSettings` → Player 里的 productName / companyName；
5. 新建场景，开始写游戏。

## 说明

- **Input System**：已移除 `com.unity.inputsystem`，模板使用旧版 **Input Manager**。
- **Luban**：未包含在本模板（工具在本地，迁移时自行携带）。
- **DOTween 更新**：替换 `Assets/Plugins/Demigiant/DOTween/` 下对应文件即可（DLL + Modules）。
- **新增/更新插件**：改 `Packages/manifest.json` 加 Git URL，或按 YokiFrame 依赖接入方式添加。

## 目录约定

- `Assets/Scripts/Core/` —— 架构、事件契约、引导入口
- `Assets/Scripts/Data/` —— 数值与配表
- `Assets/Scripts/Systems/` —— 纯逻辑服务
- `Assets/Scripts/UI/` —— 表现层（预制体 + 运行时绑定）
