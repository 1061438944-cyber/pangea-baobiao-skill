# 设计令牌

来源：Pangea Design 3 组件库（https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS）的颜色变量、Fonts 与 Shadows 画板，以及《集团报表规范》第 2 章。数据快照日期 2026-11-09。

## 1 两套颜色，各管各的用途

- **Pangea 组件色**：按钮、表单、反馈等组件的状态（品牌、错误、成功、警示、信息、中性）。
- **报表色**：指标涨跌（红色表示改善、蓝色表示恶化，反向指标反转）、业务语义（计划、实际、同期）、图表系列色。
- Pangea 的 danger 红、info 蓝是状态色，不能拿来表示涨跌；图表系列色又是第三套，三者不要混用。

## 2 Pangea 颜色令牌

写代码时优先用令牌名（例如 `primary-6`），HEX 只作为快照参考。

### 品牌色 Primary

| 令牌 | Figma变量 | 色值 | 用途 |
| --- | --- | --- | --- |
| primary-1 | Primary/primary-1 | #E8FFFB | 浅色 / 白色悬浮 |
| primary-2 | Primary/primary-2 | #ADEEE4 | 文字禁用 |
| primary-3 | Primary/primary-3 | #79DDD1 | 一般禁用 |
| primary-4 | Primary/primary-4 | #4ACCC1 | 特殊场景 |
| primary-5 | Primary/primary-5 | #22BBB3 | 悬浮 |
| primary-6 | Primary/primary-6 | #00AAA6 | 常规 |
| primary-7 | Primary/primary-7 | #009093 | 点击 |

### 线条色 Line

| 令牌 | Figma变量 | 色值 | 用途 |
| --- | --- | --- | --- |
| color-border-1 | 线条 Line/color-border-1 | #F2F3F5 | 浅 |
| color-border-2 | 线条 Line/color-border-2 | #E5E6EB | 一般 |
| color-border-3 | 线条 Line/color-border-3 | #C9CDD4 | 深 / 悬浮 |
| color-border-4 | 线条 Line/color-border-4 | #86909C | 重 / 按钮描边 |

### 填充色 Fill

| 令牌 | Figma变量 | 色值 | 用途 |
| --- | --- | --- | --- |
| color-background-white | 填充 Fill/color-background-white | #FFFFFF | 纯白填充 |
| color-fill-1 | 填充 Fill/color-fill-1 | #F7F8FA | 浅 / 禁用 |
| color-fill-2 | 填充 Fill/color-fill-2 | #F2F3F5 | 常规 / 白底悬浮 |
| color-fill-3 | 填充 Fill/color-fill-3 | #E5E6EB | 深 / 灰底悬浮 |
| color-fill-4 | 填充 Fill/color-fill-4 | #C9CDD4 | 重 / 特殊场景 |
| color-fill-5 | 填充 Fill/color-fill-5 | #4E5969 | 强调、图标、特殊场景 |

### 文字色 Text

| 令牌 | Figma变量 | 色值 | 用途 |
| --- | --- | --- | --- |
| color-text-1 | 文字 Text/color-text-1 | #1D2129 | 强调 / 正文标题 |
| color-text-2 | 文字 Text/color-text-2 | #4E5969 | 次强调 / 正文 |
| color-text-3 | 文字 Text/color-text-3 | #86909C | 次要信息 |
| color-text-4 | 文字 Text/color-text-4 | #C9CDD4 | 置灰信息 |
| color-white | 文字 Text/color-white | #FFFFFF | 纯白文字 |

### 错误色 Danger

| 令牌 | Figma变量 | 色值 | 用途 |
| --- | --- | --- | --- |
| danger-1 | 错误色 Danger/danger-1 | #FFECE8 |  |
| danger-2 | 错误色 Danger/danger-2 | #FDCDC5 |  |
| danger-3 | 错误色 Danger/danger-3 | #FBACA3 |  |
| danger-5 | 错误色 Danger/danger-5 | #F76560 |  |
| danger-6 | 错误色 Danger/danger-6 | #F53F3F |  |
| danger-7 | 错误色 Danger/danger-7 | #CB2634 |  |

### 成功色 Success

| 令牌 | Figma变量 | 色值 | 用途 |
| --- | --- | --- | --- |
| success-1 | 成功色 Success/success-1 | #E8FFEA |  |
| success-2 | 成功色 Success/success-2 | #AFF0B5 |  |
| success-3 | 成功色 Success/success-3 | #7BE188 |  |
| success-5 | 成功色 Success/success-5 | #23C343 |  |
| success-6 | 成功色 Success/success-6 | #00B42A |  |
| success-7 | 成功色 Success/success-7 | #009A29 |  |

### 警示色 Warning

| 令牌 | Figma变量 | 色值 | 用途 |
| --- | --- | --- | --- |
| warning-1 | 警示色 Warning/warning-1 | #FFF7E8 |  |
| warning-2 | 警示色 Warning/warning-2 | #FFE4BA |  |
| warning-3 | 警示色 Warning/warning-3 | #FFCF8B |  |
| warning-5 | 警示色 Warning/warning-5 | #FF9A2E |  |
| warning-6 | 警示色 Warning/warning-6 | #FF7D00 |  |
| warning-7 | 警示色 Warning/warning-7 | #D25F00 |  |

### 信息色 Info

| 令牌 | Figma变量 | 色值 | 用途 |
| --- | --- | --- | --- |
| info-1 | 信息色 Info/info-1 | #E8F3FF |  |
| info-5 | 信息色 Info/info-5 | #4080FF |  |
| info-6 | 信息色 Info/info-6 | #165DFF |  |

### 中性灰 Gray

| 令牌 | Figma变量 | 色值 | 用途 |
| --- | --- | --- | --- |
| gray-1 | 中性灰 Gray/gray-1 | #F7F8FA |  |
| gray-2 | 中性灰 Gray/gray-2 | #F2F3F5 |  |
| gray-3 | 中性灰 Gray/gray-3 | #E5E6EB |  |
| gray-4 | 中性灰 Gray/gray-4 | #C9CDD4 |  |
| gray-5 | 中性灰 Gray/gray-5 | #A9AEB8 |  |
| gray-6 | 中性灰 Gray/gray-6 | #86909C |  |
| gray-8 | 中性灰 Gray/gray-8 | #4E5969 |  |
| gray-9 | 中性灰 Gray/gray-9 | #272E3B |  |
| gray-10 | 中性灰 Gray/gray-10 | #1D2129 |  |

## 3 报表色（《集团报表规范》2.3，色值读自规范配图）

配套色板图：`references/图片和附件/品牌色.png`、`图表色.png`、`业务语义色.png`、`中性色.png`。

### 报表品牌色

| 名称 | 色值 | 用途 |
| --- | --- | --- |
| 品牌色 | #00AAA6 | 主操作、选中、链接 |
| 浅色 | #F2FBFB | 品牌色浅底 |

### 涨跌语义色

默认红色表示指标改善，蓝色表示恶化，适用于正向指标。成本、费用、周期、不良率等反向指标颜色逻辑反转，并在页面标注“反向”。不能因为数值上升就判断为向好。

| 名称 | 色值 | 用途 |
| --- | --- | --- |
| 改善 / 表现好 | #F53F3F | 正向指标上升、反向指标下降 |
| 恶化 / 表现差 | #3491FA | 正向指标下降、反向指标上升 |

### 语义状态色

| 名称 | 色值 | 用途 |
| --- | --- | --- |
| 负面 | #F76560 | 不可行、严重、危险、失败、逾期 |
| 警告 | #FF8000 | 警告、注意 |
| 提醒 | #FFC124 | 提醒、关注 |
| 恶化 | #3491FA | 指标恶化、暂未达标 |
| 正面 | #00BBB3 | 可行、安全、成功 |

### 业务语义色（图表系列的固定含义）

| 含义 | 色值 |
| --- | --- |
| 计划 & 目标 | #FF4F31 |
| 实际 / 主色 1 | #00BBB3 |
| 同期 | #FF9A2E |
| 同比 | #ECB500 |
| 环比 | #F754A8 |
| 完成率 | #5082F9 |
| 年累 & 累计值 | #31CEE5 |
| 基准 | #A195FF |
| 链接文字 | #00AAA6 |

### 图表色（其余系列按顺序取用，共 17 个）

1. `#00BBB3`
2. `#5B8FF9`
3. `#31CEE5`
4. `#FFC124`
5. `#FF8000`
6. `#FF5555`
7. `#B02700`
8. `#A9E400`
9. `#59C286`
10. `#00D5C9`
11. `#FF93C4`
12. `#597EC3`
13. `#A87BE7`
14. `#009396`
15. `#00C3FF`
16. `#984AE2`
17. `#F624E2`

### 报表中性色

| 用途 | 色值 |
| --- | --- |
| 强调 / 正文标题 | #1D2129 |
| 次强调 / 辅助文本 | #4E5969 |
| 次要 / 次要信息 | #89909C |
| 辅助 / 置灰信息 | #C9CDD4 |
| 白色 | #FFFFFF |
| 背景 / 看板底色 | #F2F3F5 |
| 分割背景 | #F9FAFB |
| 线框 1 | #F2F3F5 |
| 线框 2 | #E5E6EB |
| 线框 3 | #C9CDD4 |
| 线框 4 | #86909C |

## 4 字体与字号

- 中文：PingFang SC，字重只用 Regular 400 和 Semibold 600。字体栈：`"PingFang SC","Microsoft YaHei","Helvetica Neue",Helvetica,sans-serif`。
- 指标数值：Nunito Sans 600（woff2 在 `assets/fonts/`，内嵌到页面），配合 `font-variant-numeric: tabular-nums`。字体栈：`"Nunito Sans","PingFang SC",Arial,sans-serif`。报表规范原文写的是 D-DIN-PRO，现已统一改为 Nunito Sans。
- 文字颜色：#1D2129 主要、#4E5969 次要、#86909C 辅助、#C9CDD4 禁用；小字号不改用品牌深色。
- 桌面端最小 12px，移动端最小 10px，正文 14px；主副层级字号相差 2–4px。

| 字号 | 行高 | 用途 | Figma文字样式 |
| --- | --- | --- | --- |
| 10px | 18px | 辅助文案 / 次要文案，移动端最小 | 10/CN-Regular · 10/CN-Semibold |
| 12px | 20px | 辅助文案 / 次要文案，桌面端最小 | 12/CN-Regular · 12/CN-Semibold |
| 13px | 22px | 正文-常规-小 | 13/CN-Regular · 13/CN-Semibold |
| 14px | 22px | 正文-常规-大 | 14/CN-Regular · 14/CN-Semibold |
| 16px | 24px | 正文-常规-大 | 16/CN-Regular · 16/CN-Semibold |
| 20px | 28px | 标题-中 | 20/CN-Regular · 20/CN-Semibold |
| 24px | 32px | 标题-大 | 24/CN-Regular · 24/CN-Semibold |
| 36px | 44px | 运营标题-小 | 36/CN-Regular · 36/CN-Semibold |
| 48px | 56px | 运营标题-中 | 48/CN-Regular · 48/CN-Semibold |
| 56px | 64px | 运营标题-大 | 56/CN-Regular · 56/CN-Semibold |

## 5 阴影

| 令牌 | box-shadow | 用途 |
| --- | --- | --- |
| shadow-1 | 0 2px 5px 0 rgba(0,0,0,.1) | 低层级元素、卡片等 |
| shadow-2 | 0 4px 10px 0 rgba(0,0,0,.1) | 悬停交互、一级下拉菜单 |
| shadow-3 | 0 8px 20px 0 rgba(0,0,0,.1) | 二级下拉菜单、模态框 |
| shadow-BackTop | 0 4px 10px 0 rgba(0,0,0,.1) | 返回顶部 |
| shadow1-left | -2px 0 5px 0 rgba(0,0,0,.1) | 左侧投影 |
| shadow1-right | 2px 0 5px 0 rgba(0,0,0,.1) | 右侧投影 |
| shadow1-left-up | -2px -2px 5px 0 rgba(0,0,0,.1) | 左上投影 |
| shadow1-right-up | 2px -2px 5px 0 rgba(0,0,0,.1) | 右上投影 |
| shadow1-left-down | -2px 2px 5px 0 rgba(0,0,0,.1) | 左下投影 |

## 6 布局与栅格

- 报表与大屏统一 24 列栅格，用 CSS Grid `fr` 均分；卡片宽度取整数列跨度。
- 页面左右边距和槽宽默认 12px，可按内容调整，槽宽取 4 的倍数。
- PC 报表基准宽 1440，会议大屏基准 1920×1080。

列宽计算：`列宽 = (画布宽 − 2 × 边距 − 23 × 槽宽) / 24`，跨 n 列宽度 = `n × 列宽 + (n − 1) × 槽宽`。
