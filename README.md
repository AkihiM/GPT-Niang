# GPT-Niang（GPT 娘）

让一只小龙娘，陪你看 Codex 的剩余额度。

基于 [T7moris/GPT-Niang](https://github.com/T7moris/GPT-Niang) 的桌面挂件，显示剩余额度和重置时间，支持语录、拖动与缩放。本版本新增 Windows **形象选择**功能，支持导入自己的图片，自定义挂件形象。顺便优化了额度显示UI，并改善挂件缩小时的锯齿，使线条更自然。

[快速上手](#快速上手windows) · [形象选择指南](docs/WINDOWS-CUSTOMIZATION.md) · [上游项目](https://github.com/T7moris/GPT-Niang)

<img src="gpt-niang-usage/assets/gpt-dragon-niang-bust.png" alt="GPT 娘默认形象" width="240">

## 功能

- **额度气泡**：查看当前 Codex 账号的剩余额度和重置时间，自动适配账号返回的额度周期。
- **语录互动**：点击气泡切换语录，可以编辑自己的台词。
- **拖动与缩放**：调整挂件大小和位置，选择跟随 Codex 窗口或独立显示在桌面。
- **声音设置**：按压反馈与提示音，支持音量调节和静音。

### 本版本新增与改进（Windows）

- **形象选择**：在外观设置中切换挂件形象，重启后保留选择。
- **自定义图片**：添加自己的图片作为挂件形象，内置默认形象为「龙娘1」。
- **更平滑的缩放**：改善挂件缩小时的锯齿，让不同尺寸的形象显示更自然。
- **更易读的额度气泡**：调整布局，简化信息，突出重点。修复了pro计划仅显示一行周额度时的布局错位问题。
- **音量修复**：重新打开挂件后，保留之前设置的音量。

形象选择和额度气泡调整目前仅支持 Windows。macOS 的安装与使用请参考[上游正式版](https://github.com/T7moris/GPT-Niang/releases/latest)和 [macOS 使用说明](macos/README.md)。

## 快速上手（Windows）

需要 **Windows 10 / 11**、**Node.js 20 或更新版本**，以及已用 ChatGPT 账号登录的 **Codex 桌面端**。缺少 Node.js 时，可从 [Node.js 官网](https://nodejs.org/)安装。

目前提供源码版本，尚未发布包含上述新增功能的独立安装包。获取源码需要 [Git](https://git-scm.com/downloads)。

1. 使用 Git 获取本版本，放到准备长期保留的位置：

   ```powershell
   git clone --branch feature/windows-character-library https://github.com/AkihiM/GPT-Niang.git
   ```

2. 打开下载后的项目文件夹，双击 **`安装GPT娘.cmd`**，等待安装完成。
3. 打开 Codex 主窗口，挂件会自动出现。

如果已经安装其他版本，请先在旧目录运行 `停用GPT娘.cmd`，再安装本版本。

只需要原版挂件时，可下载[上游正式安装包](https://github.com/T7moris/GPT-Niang/releases/latest)；该安装包不包含本版本新增的形象选择功能。

## macOS 安装

从[上游 Release](https://github.com/T7moris/GPT-Niang/releases/latest) 下载 macOS 安装包，将 `GPTNiangMac.app` 移入「应用程序」，打开应用和 Codex 主窗口。需要 macOS 13 或更新版本及 Node.js 20 或更新版本；首次打开遇到系统提示时，请参考 [macOS 使用说明](macos/README.md)。

## 常用操作

| 操作 | 效果 |
| --- | --- |
| 点击龙娘 | 查看剩余额度 |
| 点击额度气泡 | 切换到语录；再点一次收起 |
| 点击气泡底部的刷新按钮 | 更新额度 |
| 拖动龙娘 | 调整位置 |
| 右键龙娘 | 打开设置，调整外观、声音、语录和显示模式 |
| 外观设置 → 形象 | 选择或添加挂件形象 |
| 运行 `打开GPT娘.cmd` | 手动打开挂件 |

添加形象时推荐使用透明背景 PNG；也支持 JPG、BMP 和 GIF（静态显示）。详细操作见[形象选择指南](docs/WINDOWS-CUSTOMIZATION.md)。

本版本包含 34 条内置语录，也可以在设置中添加自己的台词。

## 更新与卸载

源码安装请在项目目录使用 `git pull` 更新当前分支，然后退出并重新打开挂件。挂件内的更新功能面向上游正式安装包。

需要移动或卸载时，先运行 `停用GPT娘.cmd`。停用会保留个人设置、导入的图片和自定义语录；移动后需在新目录重新安装。

## 数据与隐私

额度通过本机 Codex 查询，查询过程不会创建聊天或调用模型。个人设置、导入的图片和自定义语录保存在本机，不会通过本项目上传到服务器。

请使用 ChatGPT 账号登录 Codex；仅使用 API Key 时无法查询这类账户额度。

## 开发与反馈

欢迎提交问题或改进建议。反馈时请说明系统版本、复现步骤和预期结果；截图请遮挡个人信息。

运行共享测试：

```powershell
cd gpt-niang-usage
node --test tests/*.test.mjs
```

Windows 检查：

```powershell
npm run test:windows
```

更多开发说明见 [Windows 源码说明](gpt-niang-usage/README.md)与 [macOS 使用说明](macos/README.md)。

## 致谢与许可

感谢 [T7moris](https://github.com/T7moris) 创作和维护原项目，以及所有上游贡献者。交互参考 [MeteorNOX](https://github.com/MeteorNOX) 的 [DeepSeek-Balance-Whale-Widget](https://github.com/MeteorNOX/DeepSeek-Balance-Whale-Widget)。

<details>
<summary>上游贡献者与详细致谢</summary>

以下按 GitHub 用户名排列，记录代码、方案、审查、问题复现与功能建议。感谢每一位参与者；已合并代码、待审方案和开放建议分别标明状态。

状态核对日期：2026-10-12。后续进展见对应 PR／Issue。

| 贡献者 | 具体贡献与关联 PR／Issue | 当前状态 |
| --- | --- | --- |
| [@Admilkk](https://github.com/Admilkk) | [PR #1](https://github.com/T7moris/GPT-Niang/pull/1)：动态额度展示、账号快照隔离、单实例刷新、进程恢复与安装／生命周期回归；[PR #16](https://github.com/T7moris/GPT-Niang/pull/16)：Windows 内置更新、校验、失败回滚和中断事务恢复，整合于 [PR #17](https://github.com/T7moris/GPT-Niang/pull/17)；[PR #20](https://github.com/T7moris/GPT-Niang/pull/20)：修复 Windows 拖动与定位时原生尺寸回写导致的持续放大，改为只移动窗口、由 WPF 管理尺寸，并补充窗口内／桌面模式及不同 DPI 的连续拖动回归；[PR #12 审查](https://github.com/T7moris/GPT-Niang/pull/12#pullrequestreview-5484203142)：指出个人额度的空分钟数会破坏 macOS 解码，并建议补充混合额度兼容测试。 | PR #1／#16／#20 已合并；PR #12 个人额度兼容审查已在 1.3.4 补齐 |
| [@FusaishiHaruaki-afk](https://github.com/FusaishiHaruaki-afk) | [PR #8](https://github.com/T7moris/GPT-Niang/pull/8)：真实 Go 账号的 30 天窗口复现、后端／Mac 适配及可选 `GPT_NIANG_SDK` 构建参数；[PR #9](https://github.com/T7moris/GPT-Niang/pull/9)：按窗口自身时长分类，覆盖槽位互换、月度边界与未知时长，并提供 Go 回归及 Swift 标题验证；相关实现与回归由 [PR #10](https://github.com/T7moris/GPT-Niang/pull/10) 整合。 | PR #8／#9 已合并；当前标签沿用整合后的精确时长显示 |
| [@gyb13451576](https://github.com/gyb13451576) | [Issue #11](https://github.com/T7moris/GPT-Niang/issues/11)：提供 v1.3.1 混合 DPI 双屏环境中重启 Codex 后窗口塌缩为 2×2 的复现、DPI 反馈循环分析、固定设计尺寸与 DIP／物理像素换算方案，以及自动测试和实际 HWND 采样验证；关联 [Issue #2](https://github.com/T7moris/GPT-Niang/issues/2)。 | 问题报告保持开放；PR #20 已合入拖动／定位的尺寸回写修复，重启后的 2×2 塌缩仍待验证 |
| [@insightlacyrina](https://github.com/insightlacyrina) | [Issue #14](https://github.com/T7moris/GPT-Niang/issues/14)：建议增加可持久化的「双击角色打开设置」开关，保留其他设置入口，并提出 macOS 简体中文界面建议；描述了连续点击被设置窗口打断的场景。 | 1.3.4 按维护者最新要求取消双击设置；简／繁体与跟随系统选择已实现 |
| [@JCyxMio](https://github.com/JCyxMio) | [PR #12](https://github.com/T7moris/GPT-Niang/pull/12)：提出 Windows 多屏／混合 DPI 修复、Business `individualLimit` 个人额度显示，以及套餐标题、刷新按钮布局和命中修复；提供重复尺寸、额度解析及 WPF 验证。 | 方案整合于 1.3.4；DPI 定位以 PR #20 为准，并补齐 macOS 个人额度解码与显示 |
| [@maolilup](https://github.com/maolilup) | [PR #13](https://github.com/T7moris/GPT-Niang/pull/13)：针对 [Issue #2](https://github.com/T7moris/GPT-Niang/issues/2)，提出使用固定设计宽高计算跟随／拖动尺寸以避免 DPI 尺寸漂移，并提供不同设计画布、缩放与目标 DPI 下的连续原生尺寸回归。 | 固定设计尺寸与回归已适配到 1.3.4；原生调用保持只移动 |
| [@meaqua9420](https://github.com/meaqua9420) | [PR #3](https://github.com/T7moris/GPT-Niang/pull/3)：SwiftUI／AppKit 原生 macOS 挂件、原有气泡／动画／配色／音效移植、窗口跟随与原生点击设置、菜单栏和可选登录启动；新增只读本地聊天速度面板、Mac CLI 与 worker 锁支持、应用构建及双平台 CI。 | 已合并 |
| [@ShiroasabaMio](https://github.com/ShiroasabaMio) | [Issue #2](https://github.com/T7moris/GPT-Niang/issues/2)：报告 v1.2.3 跨不同 DPI 显示器移动时挂件放大、跳动与错位，提供 120／144 DPI 复现、尺寸反馈循环分析、固定设计尺寸与统一 DPI 上下文建议及本机修复结果。 | 问题报告保持开放；PR #20 已合入拖动修复，跨屏场景继续验证，其他方案见 PR #12／#13 |
| [@T7moris](https://github.com/T7moris) | 项目创作、维护、集成与发布。[PR #5](https://github.com/T7moris/GPT-Niang/pull/5)：Mac 跟随采样、限频与多窗口选择；[PR #6](https://github.com/T7moris/GPT-Niang/pull/6)：1.3.0 双平台安装包、版本与发布校验；[PR #7](https://github.com/T7moris/GPT-Niang/pull/7)：下载、安装、退出、迁移和卸载说明；[PR #10](https://github.com/T7moris/GPT-Niang/pull/10)：套餐自动识别与动态额度整合；[PR #17](https://github.com/T7moris/GPT-Niang/pull/17)：双平台内置更新、自动清理和 Mac 原生回退；[PR #18](https://github.com/T7moris/GPT-Niang/pull/18)：MIT 代码许可、素材使用边界及文档名称统一；[PR #21](https://github.com/T7moris/GPT-Niang/pull/21)：以 PR #20 为准整合 DPI、Business 个人额度、原生 Mac 交互与语言，补齐回归、旧偏好迁移和 1.3.4 双平台发布。 | 前述维护与整合 PR 已合并；PR #21 为 1.3.4 的统一整合 |
| [@TheRuabit](https://github.com/TheRuabit) | [PR #4](https://github.com/T7moris/GPT-Niang/pull/4)：安装器直接按 UTF-8 解码插件列表 JSON，避免 Windows 默认编码造成中文安装路径乱码。 | 已合并 |
| [@wzc20090621-gif](https://github.com/wzc20090621-gif) | [PR #15](https://github.com/T7moris/GPT-Niang/pull/15)：Windows 独立桌面模式、跨屏拖动和两种模式的位置保存，解除主窗口归属／裁切并支持桌面置顶；增加本机管道额度通信与文件队列回退，修复安装后的 Node／MCP 绝对路径配置。 | 已合并 |

本次完整致谢记录由 [@T7moris](https://github.com/T7moris) 在 [PR #19](https://github.com/T7moris/GPT-Niang/pull/19) 中补充。

交互参考 [@MeteorNOX](https://github.com/MeteorNOX) 的 [DeepSeek-Balance-Whale-Widget](https://github.com/MeteorNOX/DeepSeek-Balance-Whale-Widget)，感谢其公开的交互参考与 7 句上游语录来源。Windows WPF 与 Mac 原生界面分别实现，语录包含原创、用户提供及上游文本，来源和 MIT 许可见 [语录许可](gpt-niang-usage/assets/quotes-LICENSE.txt)。使用合成提示音，没有打包 DSH 原角色、动图或音效。具体对照见 [功能对照](gpt-niang-usage/DSH功能对照.md)。


</details>

## 许可与素材使用

Copyright © 2026 T7moris 及项目贡献者。代码和一般文档采用 [MIT License](LICENSE)，允许使用、修改、分发和商用，分发时应保留版权声明与许可文本。

| 内容 | 使用许可 |
| --- | --- |
| 代码与一般文档 | MIT License，可修改、分发及商用，保留版权与许可声明 |
| 龙娘图片、派生角色图标及图片副本 | 不属于代码的 MIT 授权范围；仅允许在本项目及其非商业副本中作为挂件或项目说明展示和分发，保留素材声明；商业用途需另行取得相关权利人许可 |
| 内置语录中的 7 句上游文本 | 按 [语录许可](gpt-niang-usage/assets/quotes-LICENSE.txt) 保留 MeteorNOX 的原始 MIT 版权与许可声明 |

龙娘图由 ImageGen 根据用户提供的角色参考生成，并非本项目对参考图或参考角色的版权声明。**参考图、角色设计及相关第三方素材的权利归各自权利人所有，代码开源不代表图片或角色可以随意商用。** 未经相关权利人授权，不得将角色或图片用于商业产品、广告、周边销售、收费素材包等用途，也不得作为独立素材包分发。需要商业使用代码时，可替换为具有适当授权的图片。

完整范围与使用条件见 [角色与图片素材声明](gpt-niang-usage/assets/CHARACTER-NOTICE.txt)，生成来源见 [素材说明](gpt-niang-usage/assets/生成说明.md)。
