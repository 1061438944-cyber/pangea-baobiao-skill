---
name: pangea-baobiao
description: 集团报表UI组件库（海信 Pangea Design 3 + 《集团报表规范》）。用于设计、开发、改版或检查 PC 报表、移动端报表、会议大屏和企业中后台页面：提供颜色令牌、报表涨跌与图表色、字体、栅格、84 个组件的 Figma 参数与可复用 HTML/CSS、461 个 Pangea 图标 SVG。内含页面生成与优化流程、截图自检与交付底线清单。替代旧的 pangea-ui 与 pangu-baobiao。
---

# 集团报表UI组件库

本 Skill 由“集团报表UI规范组件库”站点生成：组件参数读自 Pangea Design 3 组件库（Figma `9Vwl2qVz65nnrY6CgR4HpS`），图标读自 Pangea 3 图标库（Figma `RdbGEZDeeMRcWbKbd7ycZr`），报表规则来自《集团报表规范文档》。数据快照日期 2026-11-06。

先读本文件，再按任务只读需要的参考文件，不要一次全读。

## 文件索引

| 文件 | 内容 | 何时读取 |
| --- | --- | --- |
| `references/report-spec.md` | 《集团报表规范》原文：设计原则、布局、颜色、字体、PC 与移动端报表组件、图表词典、开发工具选择 | 所有报表任务；选图表；判断涨跌颜色 |
| `references/tokens.md` | Pangea 颜色令牌、报表色（涨跌、状态、业务语义、17 个图表色、中性色）、字号、阴影、24 栅格算法 | 需要任何色值、字号、阴影、栅格时 |
| `references/components-general.md` | Button（640 个变体完整色表）、Icon、Link、Typography、Divider | 按钮、链接、文字、分割线 |
| `references/components-layout.md` | Grid、Layout、Space | 页面骨架与间距 |
| `references/components-display.md` | Avatar、Badge、Calendar、Card、Carousel、Comment、Collapse、Descriptions、Empty、HPTable、Image、List、Popover、Statistic、Table、Tag、Tabs、Timeline、Tooltip、Tour、Tree | 数据展示 |
| `references/components-input.md` | AutoComplete、Cascader、Checkbox、CodeEditor、ColorPicker、DatePicker、Form、IconPicker、ImageSelect、Input、i18n、InputTag、InputNumber、VerificationCode、Jira、Mention、Radio、Rate、Select、Signature、Slider、Switch、RichTextEditor、TimePicker、Transfer、TreeSelect、Upload | 表单与输入 |
| `references/components-feedback.md` | Alert、Drawer、Message、Modal、Notification、Popconfirm、Progress、Result、Spin、Skeleton、Watermark | 反馈与弹层 |
| `references/components-navigation.md` | Anchor、BackTop、Breadcrumb、Dropdown、Filter、ResizeBox、Header、Menu、MenuPlatform、Pagination、Steps、TabBar | 导航 |
| `references/components-business.md` | ActionBar、Approval、Condition、FilePreview、PTContainer、UserPicker、SliderVerify | 海信业务组件 |
| `references/report-components.md` | 报表组件（筛选栏、标题栏、标签页、指标卡，PC 与移动端）、图表词典、开发工具的站点实例与 HTML | 做报表页面时直接参考 |
| `references/dashboard.md` | 会议大屏样本参数（1920×1080、卡片、图表系列色）与 Figma 来源差异 | 做或改会议大屏 |
| `references/icons.md` | 图标使用规则、语义映射、461 个图标全名单 | 选择、推荐、替换图标 |
| `references/assumptions.md` | 不是读自 Figma 的补充值与未还原项 | 用到这些值时，向用户说明 |
| `references/charts-echarts.md` | ECharts 图表规范（坐标轴、网格线、标签、系列色 1–12）与柱形、折线、面积、组合、堆积图配置 | 页面里有图表时 |
| `references/review-workflow.md` | 页面生成与优化流程：扫描 → 诊断 → 修正、首屏小样、截图自检分辨率、设计审计清单、交付底线、修正顺序（参考 UEDMaster 改写） | 每次生成或优化页面；交付前自检 |
| `references/图片和附件/` | 规范配图、色板、D-DIN-PRO 字体安装包（旧规范，已不作为默认） | 核对色板或示例图 |
| `assets/pangea-components.css` | 渲染组件实例所需的全部 CSS（变量、按钮 `.pb`、报表样例、`q-` 组件） | 生成 HTML 页面时引入或内联 |
| `assets/icons/*.svg`、`assets/icons/index.json` | 461 个图标 SVG，及名称到分类的索引 | 页面里需要图标时 |
| `assets/集团报表UI组件库.html` | 完整站点（单文件，可离线打开，组件可交互） | 需要看效果或核对交互时打开 |

## 一、先判断任务类型

1. **PC 报表**：基准宽 1440，按 `report-spec.md` 第 2、3 章，组件参考 `report-components.md`。
2. **会议大屏**：基准 1920×1080，按 `report-spec.md` 2.2 节和 `dashboard.md`。
3. **移动端报表**：按 `report-spec.md` 3.5–3.7 节，最小字号 10px。
4. **中后台页面（表单、列表、详情、审批）**：按对应 `components-*.md`。
5. **图标**：按 `icons.md`。

用户提供了设计稿、截图或已有页面时，**先完整保留原有结构、模块顺序、指标名称、数据和交互**，只在视觉层面按规范优化。未经明确要求，不增删模块、不改图表类型、不替换业务数据。

## 二、规范冲突时的优先级

1. 用户在当前任务中明确给出的参数。
2. 用户提供的设计稿、截图和已建立的页面视觉语言。
3. 《集团报表规范》（`report-spec.md`、`tokens.md` 第 3 节）。
4. Pangea 组件参数（`components-*.md`，读自 Figma）。
5. 会议大屏样本观察值（`dashboard.md`）。
6. `assumptions.md` 中的补充值。
7. 通用设计经验。

采用第 4 级以下来源的参数时，在结果说明中写明来源。

## 三、已知冲突与默认处理

| 项目 | 集团报表规范 | 大屏样本 | 默认做法 |
| --- | --- | --- | --- |
| 页面左右边距 | 12px | 32px | 12px；用户另有要求时从其要求 |
| 栅格槽宽 | 12px，按 4 的倍数调整 | 卡片间距 16px | 12px |
| 栅格 | 24 列，CSS Grid `fr` 均分 | 三等分卡宽 608 | 24 列，卡片取整数列跨度 |
| 文字色 | #1D2129 / #4E5969 | 同 | 一致 |
| 字体 | PingFang SC；数值 D-DIN-PRO 600 | 数值 DIN Bold | 数值统一用 Nunito Sans 600（woff2 在 `assets/fonts/`），不再用 D-DIN-PRO |
| 字重 | 400 / 600 | 中文 Medium 500 | 报表用 400 / 600；延续已有大屏时可保留 500 |
| 指标卡背景 | PC 只读 #F5F7FB，移动端 #F7F8FA | 浅青色摘要带 | 报表用规范色；会议大屏可用浅青渐变摘要带 |
| 卡片圆角与阴影 | 未规定 | 圆角 12，阴影 0 4 14 0 黑 6% | 大屏用样本值；PC 报表沿用现有系统或 Pangea Card |
| 计划 / 实际 / 同期 | #FF4F31 / #00BBB3 / #FF9A2E（同比 #ECB500） | 计划 #FF4F31、实际 #00BBB3、同期 #ECB500 | 按规范；先核对用户原图例，同一指标跨页一致 |

## 四、必须遵守的核心规则

**三套颜色不能混用**
- Pangea 功能色（danger 红、success 绿、warning 橙、info 蓝）只表示组件状态：错误、成功、警示、提示。
- 报表涨跌色：正向指标**红色 #F53F3F 表示改善，蓝色 #3491FA 表示恶化**；成本、费用、周期、不良率等反向指标颜色反转，并标注“反向”。不因数值上升就判断为向好。
- 图表系列：计划、实际、同期、同比、环比、完成率等用业务语义色，其余系列按 17 个图表色顺序取用。

**布局与字体**
- 24 列栅格，页面边距和槽宽按第三节。
- 同一类文字（卡片标题、小标题、数值、表格、说明）在所有页面用同一个字号，只用 `tokens.md` 字号表里的整数档。会议大屏默认一屏展示、不出现滚动（与业务确认过的长页面可以纵向滚动，保持原有结构，不为塞进一屏而重排）：每页内容按 1920×1080 设计画布排进一屏（放不下先收紧间距、并排排列、降低图表高度，不删模块），再把整页（含顶栏）按同一个比例 min(屏宽/1920, 屏高/1080) 缩放；禁止每页按内容多少单独缩放。每页内容撑到底部边距（底部留白统一等于页面下边距）：先拉高表格行高，再统一拉高趋势图；结构相似的页面，同类元素高度一致。内容本来就少的明细页（如人员数量、研发指标明细）不撑满：图表用常规高度、表格用常规行高（约 40px），不要为填空而拉高。
- 背景、卡片、指标摘要带用纯色，不加底纹、噪点、光晕、装饰圆环和花哨渐变。
- 正文 14px；最小字号桌面 12px、移动 10px；主副层级字号差 2–4px；行高 1.5。
- 中文 PingFang SC，只用 400 / 600；指标数值用 Nunito Sans（600，开启 `font-variant-numeric: tabular-nums`），字体文件内嵌 `assets/fonts/` 里的 woff2，保证离线可用。
- 文字颜色只用规范文字色：主要文字 #1D2129、次要文字 #4E5969、辅助文字 #86909C、禁用 #C9CDD4。不要为了对比度把小字号文字改成品牌深色（如 primary-8 #00757B）；品牌色只用于链接、选中态、图标和按钮等组件令牌规定的位置。
- 大屏缩到较低分辨率时，先收紧间距和内边距，再按需降字号，不低于 12px。

**组件**
- 优先使用 `components-*.md` 中的组件和参数，不自创近似样式。尺寸、圆角、颜色按“样式参数”表；状态按“Figma 变体属性”表确认实际存在。
- 写 HTML 时引入 `assets/pangea-components.css`，结构照抄对应“实例” HTML，再改文字和数据。
- 实例中的 `<svg data-icon="名称" class="i"/>` 要替换成 `assets/icons/名称.svg` 的内容，并加 `class="i" aria-hidden="true"`。
- 实例里的 `data-*` 属性只是站点交互钩子，交互（下拉、拖动、切换）要自己实现；下拉类组件必须做出能展开的下拉面板。
- 按钮用 `.pb` 加行内 CSS 变量：`--h --px --r --fs --lh --is --bg --bd --tx`，悬停 `--bg-h --bd-h --tx-h`，按下 `--bg-a --bd-a --tx-a`，可交互时加 `live` 类。数值从 Button 色表中取。

**数据表达**
- 保留指标名称、统计时间、单位、口径，以及当月 / 累计、计划 / 实际 / 同期的区别。
- 同比、环比、完成率、改善值分开表达；百分比变化与百分点（“点”）不混写。
- 缺失数据显示“--”，不填 0；不擅自修正用户提供的异常数值。
- 生成示例数据前需用户允许，并明确标识为示例。

**图表**
- 统一用 ECharts 绘制，样式按 `charts-echarts.md`：x 轴线 #C9CDD4、隐藏刻度、文字 #4E5969；y 轴网格线 #E5E6EB 虚线、文字 #4E5969；数据标签 #1D2129；折线隐藏数据点；不显示坐标轴名称；系列色用图表色 1–12（有固定含义的系列用业务语义色）。
- 按 `report-spec.md` 第 5 章选择：柱状图分类 ≤ 20、分组 ≤ 10；饼图 ≤ 9 块，超出合并为“其它”；雷达图 3–8 个维度；双轴图柱 ≤ 3 个系列、折线 ≤ 2 条；四象限 20–80 个点。

**图标**
- 只用 `icons.md` 名单中实际存在的图标，按语义选择，不虚构名称、不混用其他图标库。
- 找不到合适图标时说明缺失并给出候选；自绘前先征得同意。
- 同一组图标尺寸和线性 / 填充风格一致；单独的图标按钮要有 `aria-label`。

## 五、执行流程

详细做法见 `references/review-workflow.md`。该文件只管流程和自检，**所有取值仍以本 Skill 规范为准**。

1. 明确页面类型、目标分辨率、受众和用户约束。
2. **扫描**：阅读用户提供的设计稿或已有页面（含源码和构建方式），列出模块清单，确认不变的部分；改动前备份。
3. **诊断**（优化已有页面时）：按审计清单列出问题，能量化的先量化（如逐页统计字号）。
4. 方向不明确的整页优化，先做 2–3 个首屏小样让用户选；方向明确或用户说“直接做”时跳过。
5. 读取需要的参考文件章节（颜色看 `tokens.md`，组件看对应 `components-*.md`）。
6. **修正 / 产出**：栅格 → 颜色 → 字体 → 组件 → 图表 → 图标，在现有技术栈上改，不推倒重写。
7. **截图自检**：按页面类型的分辨率截图（会议大屏 1920×1080，PC 报表 1440×900，移动端 375×812，并加看较小尺寸），检查下拉、弹窗、空状态、长文本等状态；看图修正，再截图，直到没有明显问题。
8. 对照第六节和 `review-workflow.md` 的交付底线检查。
9. 简要说明完成内容、采用的规范来源、偏离之处和用到的补充值。

## 六、交付检查

- [ ] 页面结构、模块、指标、数据与原稿一致，没有擅自增删。
- [ ] 24 栅格、边距、槽宽符合约定，卡片宽度为整数列。
- [ ] 涨跌颜色符合正向 / 反向指标逻辑，反向指标已标注。
- [ ] 状态色、涨跌色、图表系列色没有混用；图例与系列一致，同一指标跨页颜色一致。
- [ ] 组件尺寸、圆角、颜色与 `components-*.md` 参数一致，同类控件尺寸统一。
- [ ] 下拉、弹出、切换类组件能实际操作。
- [ ] 字号不低于最小值，层级清晰，行高 1.5。
- [ ] 单位、口径、统计时间完整；缺失值显示“--”。
- [ ] 数值千分位每 3 位一组（如 4,334,523），数字使用 Nunito Sans 等宽数字。
- [ ] 图标来自 Pangea 3 图标库，或已说明为自绘。
- [ ] 目标分辨率下无遮挡、截断、溢出。
- [ ] 同一类文字在所有页面字号一致，没有非整数字号；没有按页单独缩放；会议大屏每页一屏、无纵向滚动（约定的长页面除外）；明细页没有被拉高的图表和行高。
- [ ] 没有底纹、噪点、光晕等装饰；品牌色只用在最该注意的位置。
- [ ] 并排卡片的标题、数值、图表上沿对齐；图标在底块里视觉居中。
- [ ] 悬停、按下、聚焦、当前位置、加载、空状态、错误状态齐全；状态不只靠颜色表达。
- [ ] 点击区域足够大（桌面 ≥24px，移动 ≥44px），长短内容都不撑破布局。
- [ ] 已按页面类型的分辨率截图自检，不是只看代码。
- [ ] 用到 `assumptions.md` 中的值或未验证的规则，已在说明中注明。

## 七、来源与更新

- 《集团报表规范文档》（含附件：报表上架前注意项及自检重点）
- Pangea Design 3 组件库：https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS
- Pangea 3 图标库：https://www.figma.com/design/RdbGEZDeeMRcWbKbd7ycZr
- 会议大屏样本：https://www.figma.com/design/KqNpaABKE6k6o3kK3SVeLs（见 `dashboard.md`）
- 流程与自检清单参考：UEDMaster https://github.com/ysredcity/ued-master （`skills/ued-master`，其审计正文源自 Leonxlnx/taste-skill，MIT），已按本 Skill 场景改写，见 `review-workflow.md`

参考文件是 2026-11-06 的快照。组件库或图标库更新后，在工作区 `完善/` 下重新构建站点（`ruby _pangea/build.rb`）并重新生成本 Skill（`_skill/gen.rb`）。
