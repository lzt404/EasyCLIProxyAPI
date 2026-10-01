---
version: alpha
name: EasyCLIProxyAPI
description: 面向开发者的本地 AI 代理桌面控制台，以清晰的信息层级、青绿色交互强调和明暗主题保持一致体验。
colors:
  primary: "#0f766e"
  primary-hover: "#0b5d57"
  primary-active: "#094c47"
  on-primary: "#ffffff"
  primary-soft: "#d9f0ec"
  background: "#f6f7f5"
  surface: "#ffffff"
  surface-variant: "#eff3f0"
  surface-hover: "#f6f8f6"
  on-surface: "#202521"
  secondary: "#46524a"
  text-tertiary: "#566259"
  text-muted: "#5f6a62"
  text-disabled: "#7d877f"
  border: "#e2e8e3"
  border-strong: "#cfd7d0"
  success: "#2f6b3f"
  success-surface: "#eef7f0"
  warning: "#c77b30"
  on-warning-surface: "#8b5b21"
  warning-surface: "#fff7e9"
  error: "#9f2d20"
  error-surface: "#fff1ee"
  dark-primary: "#5dd3c7"
  dark-primary-hover: "#83e0d6"
  dark-primary-active: "#4ec4b8"
  dark-on-primary: "#0b0d11"
  dark-background: "#0b0d11"
  dark-surface: "#141720"
  dark-surface-variant: "#1c212c"
  dark-surface-hover: "#252b38"
  dark-on-surface: "#f8fafc"
  dark-secondary: "#d3dce8"
  dark-text-tertiary: "#b0bdcf"
  dark-text-muted: "#9aa9bf"
  dark-text-disabled: "#64748b"
  dark-border: "#222836"
  dark-border-strong: "#2e3646"
  dark-success: "#34d399"
  dark-warning: "#c65746"
  dark-on-warning-surface: "#fcd34d"
  dark-error: "#c65746"
typography:
  headline-display:
    fontFamily: "Noto Sans SC, Noto Sans CJK SC, Source Han Sans SC, PingFang SC, Microsoft YaHei UI, Microsoft YaHei, system-ui, sans-serif"
    fontSize: 28px
    fontWeight: 600
    lineHeight: 1.35
  headline-lg:
    fontFamily: "Noto Sans SC, Microsoft YaHei UI, system-ui, sans-serif"
    fontSize: 24px
    fontWeight: 600
    lineHeight: 1.35
  headline-md:
    fontFamily: "Noto Sans SC, Microsoft YaHei UI, system-ui, sans-serif"
    fontSize: 20px
    fontWeight: 600
    lineHeight: 1.35
  headline-sm:
    fontFamily: "Noto Sans SC, Microsoft YaHei UI, system-ui, sans-serif"
    fontSize: 18px
    fontWeight: 600
    lineHeight: 1.35
  section-title:
    fontFamily: "Noto Sans SC, Microsoft YaHei UI, system-ui, sans-serif"
    fontSize: 16px
    fontWeight: 600
    lineHeight: 1.35
  body-md:
    fontFamily: "Noto Sans SC, Microsoft YaHei UI, system-ui, sans-serif"
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.6
  body-sm:
    fontFamily: "Noto Sans SC, Microsoft YaHei UI, system-ui, sans-serif"
    fontSize: 13px
    fontWeight: 400
    lineHeight: 1.6
  label-md:
    fontFamily: "Noto Sans SC, Microsoft YaHei UI, system-ui, sans-serif"
    fontSize: 14px
    fontWeight: 500
    lineHeight: 1.6
  label-sm:
    fontFamily: "Noto Sans SC, Microsoft YaHei UI, system-ui, sans-serif"
    fontSize: 12px
    fontWeight: 400
    lineHeight: 1.6
  code-md:
    fontFamily: "Cascadia Code, SFMono-Regular, Consolas, Liberation Mono, monospace"
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.6
rounded:
  none: 0px
  xs: 4px
  sm: 6px
  md: 8px
  navigation: 10px
  lg: 12px
  xl: 14px
  full: 999px
spacing:
  xs: 4px
  sm: 8px
  control-gap: 10px
  md: 12px
  lg: 16px
  section-gap: 18px
  xl: 24px
  xxl: 32px
  page-inline-max: 40px
  page-bottom-max: 48px
  sidebar-width: 264px
components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    typography: "{typography.label-md}"
    rounded: "{rounded.md}"
    height: 42px
  button-primary-hover:
    backgroundColor: "{colors.primary-hover}"
  button-primary-dark:
    backgroundColor: "{colors.dark-primary}"
    textColor: "{colors.dark-on-primary}"
  button-secondary:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.md}"
    height: 42px
  button-danger:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.error}"
    rounded: "{rounded.md}"
    height: 42px
  panel:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.lg}"
    padding: "{spacing.xl}"
  panel-dark:
    backgroundColor: "{colors.dark-surface}"
    textColor: "{colors.dark-on-surface}"
  input:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    rounded: "{rounded.md}"
  status-success:
    backgroundColor: "{colors.success-surface}"
    textColor: "{colors.success}"
    rounded: "{rounded.full}"
    height: 28px
  status-warning:
    backgroundColor: "{colors.warning-surface}"
    textColor: "{colors.on-warning-surface}"
    rounded: "{rounded.full}"
    height: 28px
  status-error:
    backgroundColor: "{colors.error-surface}"
    textColor: "{colors.error}"
    rounded: "{rounded.full}"
    height: 28px
---

# EasyCLIProxyAPI 设计系统

## Overview

EasyCLIProxyAPI 是 CLIProxyAPI 的跨平台桌面控制台，服务于需要管理本地代理、上游 Provider、OAuth 凭据、模型和智能体客户端的开发者。界面应让用户迅速判断服务是否可用、下一步该做什么，以及操作是否成功。

整体风格是克制、清晰、可信赖的工具界面：中性背景、适度圆角、轻量边框、紧凑但可读的信息密度，以及用于主要交互的青绿色。通过标题、分组、对齐和留白组织复杂配置，避免用装饰抢占工作空间。

本文依据现有代码提取设计规则，并为后续页面提供统一约束。YAML 中的精确值用于生成与对齐；正文解释应用方式。基础令牌来自 `src/styles.css`，页面样式还需参考 `src/styles/feature-pages.css` 与 `src/styles/ui-refinements.css`。间距和圆角是对现有常用值的归纳；交互与可访问性要求是后续实现的验收标准，不表示所有页面已完全满足。

## Colors

青绿色是唯一的全局交互强调色。主要操作、选中导航、焦点和选中项共享这一色系；Provider 品牌色仅用于其标识，不改变全局按钮样式。

| 用途 | 浅色主题 | 深色主题 | CSS 变量 |
| --- | --- | --- | --- |
| 主色 | `#0f766e` | `#5dd3c7` | `--primary-color` / `--ui-accent` |
| 主色悬停 | `#0b5d57` | `#83e0d6` | `--primary-hover` / `--ui-accent-strong` |
| 主色上的文字 | `#ffffff` | `#0b0d11` | `--primary-contrast` |
| 窗口背景 | `#f6f7f5` | `#0b0d11` | `--bg-secondary` |
| 内容表面 | `#ffffff` | `#141720` | `--bg-primary` / `--bg-card` |
| 次级表面 | `#eff3f0` | `#1c212c` | `--bg-tertiary` |
| 悬停背景 | `#f6f8f6` | `#252b38` | `--bg-hover` |
| 主要文字 | `#202521` | `#f8fafc` | `--text-primary` |
| 次要文字 | `#46524a` | `#d3dce8` | `--text-secondary` |
| 辅助文字 | `#566259` | `#b0bdcf` | `--text-tertiary` |
| 最弱可读文字 | `#5f6a62` | `#9aa9bf` | `--text-quaternary` |
| 默认边框 | `#e2e8e3` | `#222836` | `--border-color` |
| 强边框 | `#cfd7d0` | `#2e3646` | `--border-primary` |
| 成功 | `#2f6b3f` | `#34d399` | `--success-color` |
| 错误 / 危险 | `#9f2d20` | `#c65746` | `--error-color` / `--danger-color` |

浅色警告使用浅琥珀背景与 `#8b5b21` 文字。当前深色 `--warning-color` 与错误色相同，警告标签应结合 `--amber-text`（`#fcd34d`）、图标和文案区分，不能仅靠颜色表示状态。成功与失败标签分别复用 `--success-badge-*` 和 `--failure-badge-*`；透明背景保留 CSS 中的 rgba 定义，不强行转换成不透明色。

主题支持浅色、深色和跟随系统，默认跟随系统；遵循 `src/theme.ts` 与 `src/themeController.ts` 的偏好持久化和原生窗口同步机制。`dark-*` 是本文件的主题令牌命名约定，消费者需要显式选择对应值，不依赖自动主题切换语义。

新增样式优先使用语义 CSS 变量。现有 `--theme-*` 是兼容映射，部分旧面板仍使用暖白表面和暖灰边框；修改这些页面时保持局部协调，并逐步迁移到语义变量。

## Typography

正文使用系统可用的无衬线字体，不要求额外在线加载字体。简体中文采用 YAML 中的中文字体栈；繁体中文使用 Noto Sans TC、PingFang TC、Microsoft JhengHei 等回退；日文使用 Noto Sans JP、Hiragino Kaku Gothic ProN、Yu Gothic UI、Meiryo；英文使用 Inter、Segoe UI 和系统字体。所有字号层级继承当前语言的字体栈，YAML 的简体中文值是默认值。

| 层级 | 字号 / 字重 | 应用 |
| --- | --- | --- |
| 大型数据 | 28px / 600 | 少量核心指标 |
| 页面标题 | 24px / 600 | 每页主标题；紧凑指标可复用字号 |
| 对话框标题 | 20px / 600 | 模态窗口标题 |
| 面板标题 | 18px / 600 | 内容卡片标题 |
| 分区标题 | 16px / 600 | 表单和列表分组 |
| 正文 | 14px / 400 | 说明、表格和内容 |
| 控件标签 | 14px / 500 | 按钮和字段标签 |
| 元数据 | 13px / 400 | 时间、版本、辅助信息 |
| 注释 | 12px / 400 | 次级标签与短注释 |

标题行高 1.35，正文行高 1.6，较长说明可使用 1.7。字重以 400、500、600 为主，避免通过连续加粗制造层级。正文和关键状态不缩小为注释字号。

API 地址、模型 ID、配置路径、命令和日志使用等宽字体栈。保留模型名和路径的原始大小写；数字表格宜使用等宽数字。长文本可换行或省略，但应提供完整内容的查看或复制方式。

## Layout

桌面默认窗口为 1280 × 800，最小窗口为 640 × 600，以 `src-tauri/tauri.conf.json` 为准。标准应用壳使用 264px 左侧导航和自适应工作区，主内容不设置固定最大宽度。

侧栏包含品牌、主要导航，以及底部的简单模式入口、主题、语言和联系入口。页面遵循“标题与主要操作 → 状态或概览 → 筛选与工作内容”的阅读顺序。现有主要入口为首页、API 接入、OAuth、智能体、使用记录、配置与版本管理；简单模式使用独立的步骤引导布局。

内容边距遵循现有 `clamp()`：顶部 20–32px，水平 18–40px，底部 28–48px。面板通常内边距 24px，页面分区间距 18px，面板标题与内容间距 16px。常用间距优先选择 4、8、12、16、24、32px，同时保留已有 10、14、18px 的紧凑布局。

当窗口宽度不超过 900px 时，标准壳将侧栏改为顶部区域，导航横向排列并允许滚动；700px 以下进一步压缩品牌与辅助控件。页面内部使用名为 `workspace` 的容器查询，依据实际内容宽度调整列数，避免只依据窗口宽度推断布局。

多列面板在空间不足时改为单列，工具栏允许换行。表格可在自己的容器内横向滚动，页面本身不应产生无意的横向溢出。使用记录等复杂页面为表格和图表提供明确的滚动区域，保持标题和操作容易找到。简单模式沿用自己的响应式规则，不直接套用标准侧栏布局。

## Elevation & Depth

背景、面板和次级表面通过明度差与 1px 边框建立层级。阴影作为辅助：普通控件使用 `--shadow-sm`，面板使用 `--ui-panel-shadow`，主要按钮使用 `--ui-accent-shadow`。

现有浅色面板阴影为 `0 8px 24px rgba(32, 42, 36, 0.07)`；深色面板使用 `0 1px 2px rgba(0, 0, 0, 0.28), 0 12px 32px -10px rgba(0, 0, 0, 0.45)`。复用这些变量，不在不同页面各自创建更重的投影。

弹出菜单和对话框位于内容之上；提示通过现有 Portal 机制显示。遮罩应让用户明确识别当前操作层，同时保留底层上下文。避免渐变大背景、玻璃效果和多层装饰阴影。

## Shapes

按钮与输入框默认 8px 圆角，导航项约 10px，面板 12px，部分较大容器可使用 14px。紧凑菜单子项使用 4–6px；状态标签、开关和计数徽标使用胶囊形。

圆角随组件角色变化，同类组件保持一致。普通表单按钮采用圆角矩形；胶囊形用于短状态和可切换标签。分隔线保持细且低对比，避免厚边框和不必要的嵌套卡片。

## Components

### 按钮与操作

标准按钮最小高度 42px，水平内边距 14px，文字 14px / 500。主按钮采用主色填充，次按钮采用表面背景与细边框，危险按钮采用错误色文字和边框。深色主按钮文字使用 `--primary-contrast`，避免亮青绿色背景搭配白字造成低对比。

每个独立任务区域突出一个当前主要操作。加载时保留按钮尺寸，显示进度并禁止重复提交；禁用态使用不可用光标与适度透明度，必要时解释原因。复制后就近显示“已复制”，不改变整个页面布局。

### 表单与配置

字段具备可见标签，说明和错误放在相关字段附近；placeholder 仅作为示例。使用统一的输入背景、边框、焦点和错误状态。Provider 表单将名称、地址、密钥、模型与高级选项分组，避免让长表单挤压对话框底部操作。

密钥默认遮蔽，显示和复制使用显式操作；错误信息不回显完整凭据。开关表示二元设置，复选框表示独立选择，单选框表示互斥选择；尽量采用原生语义和现有控件样式。

### 面板、列表与状态

面板标题、说明与操作保持一致对齐。Provider、凭据和客户端列表突出名称、可用状态及下一步操作，辅助信息放在次级层。状态标签至少包含文字，必要时加图标，明确区分未安装、未运行、连接中、可用与错误。

异步请求分别呈现初始加载、空数据、筛选无结果、局部失败和成功状态。刷新已有数据时尽量保留内容与滚动位置。空状态提供具体下一步，例如添加 Provider 或安装内核；失败状态提供原因和可执行的重试入口。

### 导航、标签页与对话框

主导航使用图标与文字，选中项采用青绿色强调和柔和背景。依照 `src/navigation.ts` 显示内核可用性约束；受限入口说明原因，首页、配置、版本管理等可用入口保持可达。

复用 `ConfirmationDialog` 和 `useDialogFocusTrap`：对话框有标题、清晰的操作结果说明和明确按钮。删除凭据、覆盖或恢复客户端配置等操作遵循现有确认流程。支持适用的 Escape 关闭、焦点圈定与关闭后焦点恢复；处理期间的关闭行为遵循组件既有约束。

### 图表与使用记录

先呈现请求量、Token、成功率等概览，再呈现趋势、筛选和明细。时间范围、单位和筛选范围必须可见，成本注明预估性质。图表系列颜色稳定，并配合图例、标签或线型，不让颜色承担全部含义。

表格保持表头与列对齐；数字右对齐，名称左对齐。保留已有列宽调整、筛选和滚动行为，窄窗口通过内部滚动容纳明细。

### 图标与品牌资源

通用功能图标使用 `lucide-react`，保持一致线条风格和同层级尺寸，通常为 16–20px。纯图标按钮必须提供可访问名称。产品标识复用 `src/assets/logo.jpg`，Provider 和客户端标识复用 `src/assets/icons/` 中的资源，保持原比例并验证明暗背景的可见性。

## Do's and Don'ts

- 使用语义令牌和现有组件；修改设计值时同步更新本文与代码。
- 用文字、图标和颜色共同说明状态，普通正文达到 WCAG AA 4.5:1 对比度，大字号文字达到 3:1。
- 保留可见的键盘焦点；按钮、菜单、标签页、表单和对话框均可通过键盘操作。
- 为简体中文、繁体中文、英文和日文预留空间，使用 `src/i18n/`，避免将用户可见文案写死在组件中。
- 使用简洁、明确的动作文案，例如“启动内核”“添加 Provider”“恢复配置”，避免只写含义不明确的“确定”。
- 避免用多个鲜艳主色、超大标题或装饰图形稀释工作内容。
- 避免隐藏关键失败信息、只依赖颜色区分状态，或以低对比小字承载重要配置说明。
- 尊重 `prefers-reduced-motion`；普通反馈沿用约 140–160ms 的轻量过渡，不添加持续装饰动画。

## 页面应用规则

| 页面 | 首要信息与操作 | 设计重点 |
| --- | --- | --- |
| 首页 | 内核状态、启动 / 停止、可复制 API 地址 | 服务状态与地址具有明确层级，错误就近呈现 |
| API 接入 | Provider 列表、添加、搜索、健康检测 | 品牌标识辅助识别，配置字段与操作统一 |
| OAuth / 凭据 | 授权入口、授权进度、回调与凭据状态 | 提供明确阶段和手动回调路径，保护敏感信息 |
| 智能体 | 客户端检测、模型选择、应用与恢复配置 | 区分检测、待应用和已应用状态，说明配置操作的影响 |
| 使用记录 | 概览、时间筛选、趋势和请求明细 | 保持指标范围一致，控制内部滚动和表格密度 |
| 配置 | 分组设置、保存与操作反馈 | 字段解释就近呈现，高级选项不淹没常用设置 |
| 版本管理 | 软件与内核版本、检查、安装与进度 | 软件与内核分别呈现，检查结果和安装操作清楚区分 |
| 简单模式 | 分步完成本地代理与客户端接入 | 突出当前步骤、完成状态和下一步操作 |

## 维护与验证

新增或修改 UI 时，先复用已有组件与样式，再按本文补充缺失规则。若调整基础视觉令牌，同时核对 `src/styles.css`、主题窗口背景和本文件；YAML 引用必须指向已定义令牌，规范章节不重复。

至少检查浅色和深色、1280 × 800 与 640 × 600、长路径或模型名、空状态与失败状态，以及键盘导航。语言相关变更覆盖四种语言，动效变更检查减少动态效果偏好。本文中的目标要求若与旧组件表现有差异，应在对应 UI 改动中修正并验证。

代码验证采用项目既有检查，例如 `bun run check`；涉及应用壳可访问性或 Provider 对话框布局时，按需运行 `bun run test:ui:accessibility`、`bun run test:ui:api-provider-dialog` 及相关现有测试。仅修改本文无需执行应用构建。

格式依据：[What is DESIGN.md?](https://app-companion-430619.appspot.com/docs/design-md/overview/) 与 [The DESIGN.md specification](https://app-companion-430619.appspot.com/docs/design-md/specification/)。本文件保留规范的英文二级章节名及顺序，使用中文解释项目规则；额外章节用于桌面应用的领域约束。
