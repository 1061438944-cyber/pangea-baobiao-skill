# 通用组件

每个组件包含：用途、Figma 节点、样式参数（读自 Figma，个别标注为假设）、Figma 变体属性、静态 HTML 实例。

HTML 实例的用法：
- 样式来自 `assets/pangea-components.css`，类名统一 `q-` 前缀；按钮是 `.pb`，颜色和尺寸写在行内 CSS 变量里。
- `<svg data-icon="名称" class="i"/>` 是图标占位，替换成 `assets/icons/名称.svg` 的内容（单色图标用 `currentColor`）。
- 实例里的 `data-*` 属性是站点交互用的钩子，交互逻辑需要自己实现；示例数据只用于演示。

## Button 按钮

按钮用来触发一个即时操作。下面的实例、尺寸和颜色全部按 Figma 组件集 button 的 640 个变体还原，悬停和按下效果使用设计稿里对应状态的色值。

- Figma：[115962:128337](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115962-128337)
- 变体概况：640 个变体；5 类型 × 4 种类 × 4 尺寸 × 4 状态 × 有无文字

### 按钮完整变体参数

全部 640 个变体读自 Figma 组件集 button。字段：类型 / 种类 / 尺寸 / 状态 / 仅图标，上下与左右内边距，圆角，背景，描边（虚框为 dashed），文字色，文字样式，图标尺寸。

**尺寸**

| 尺寸 | 高度 | 上下/左右内边距 | 圆角 | 文字样式 | 图标 |
| --- | --- | --- | --- | --- | --- |
| 中 | 32px | 5px / 16px | 4px | 14/CN-Regular | 14px |
| 大 | 36px | 7px / 20px | 4px | 14/CN-Regular | 14px |
| 小 | 28px | 3px / 16px | 4px | 14/CN-Regular | 14px |
| 迷你 | 24px | 2px / 12px | 4px | 12/CN-Regular | 12px |

**颜色（按类型 × 种类 × 状态）**

| 类型 | 种类 | 状态 | 背景 | 描边 | 文字 |
| --- | --- | --- | --- | --- | --- |
| 主要按钮 | 标准 | 默认 | #00AAA6 | 无 | #FFFFFF |
| 主要按钮 | 标准 | 悬停 | #22BBB3 | 无 | #FFFFFF |
| 主要按钮 | 标准 | 激活 | #009093 | 无 | #FFFFFF |
| 主要按钮 | 标准 | 禁用 | #79DDD1 | 无 | #FFFFFF |
| 次要按钮 | 标准 | 默认 | #F7F8FA | #C9CDD4 | #4E5969 |
| 次要按钮 | 危险 | 默认 | #FFECE8 | 无 | #F53F3F |
| 次要按钮 | 成功 | 默认 | #E8FFEA | 无 | #00B42A |
| 次要按钮 | 警告 | 默认 | #FFF7E8 | 无 | #FF7D00 |
| 次要按钮 | 标准 | 悬停 | #FFFFFF | #86909C | #1D2129 |
| 次要按钮 | 危险 | 悬停 | #FDCDC5 | 无 | #F53F3F |
| 次要按钮 | 成功 | 悬停 | #AFF0B5 | 无 | #00B42A |
| 次要按钮 | 警告 | 悬停 | #FFE4BA | 无 | #FF7D00 |
| 次要按钮 | 标准 | 激活 | #F2F3F5 | #86909C | #1D2129 |
| 次要按钮 | 危险 | 激活 | #FBACA3 | 无 | #F53F3F |
| 次要按钮 | 成功 | 激活 | #7BE188 | 无 | #00B42A |
| 次要按钮 | 警告 | 激活 | #FFCF8B | 无 | #FF7D00 |
| 次要按钮 | 标准 | 禁用 | #F7F8FA | #C9CDD4 | #C9CDD4 |
| 次要按钮 | 危险 | 禁用 | #FFECE8 | 无 | #FBACA3 |
| 次要按钮 | 成功 | 禁用 | #E8FFEA | 无 | #7BE188 |
| 次要按钮 | 警告 | 禁用 | #FFF7E8 | 无 | #FFCF8B |
| 虚框按钮 | 标准 | 默认 | #F7F8FA | #C9CDD4 虚线 | #4E5969 |
| 虚框按钮 | 危险 | 默认 | #FFECE8 | #FDCDC5 虚线 | #F53F3F |
| 虚框按钮 | 警告 | 默认 | #FFF7E8 | #FFE4BA 虚线 | #FF7D00 |
| 虚框按钮 | 成功 | 默认 | #E8FFEA | #AFF0B5 虚线 | #00B42A |
| 虚框按钮 | 标准 | 悬停 | #FFFFFF | #86909C 虚线 | #1D2129 |
| 虚框按钮 | 危险 | 悬停 | #FDCDC5 | #FBACA3 虚线 | #F53F3F |
| 虚框按钮 | 警告 | 悬停 | #FFE4BA | #FFCF8B 虚线 | #FF7D00 |
| 虚框按钮 | 成功 | 悬停 | #AFF0B5 | #7BE188 虚线 | #00B42A |
| 虚框按钮 | 标准 | 激活 | #F2F3F5 | #86909C 虚线 | #1D2129 |
| 虚框按钮 | 危险 | 激活 | #FBACA3 | #F76560 虚线 | #F53F3F |
| 虚框按钮 | 警告 | 激活 | #FFCF8B | #FF9A2E 虚线 | #FF7D00 |
| 虚框按钮 | 成功 | 激活 | #7BE188 | #23C343 虚线 | #00B42A |
| 虚框按钮 | 标准 | 禁用 | #F7F8FA | #C9CDD4 虚线 | #C9CDD4 |
| 虚框按钮 | 危险 | 禁用 | #FFECE8 | #FDCDC5 虚线 | #FBACA3 |
| 虚框按钮 | 警告 | 禁用 | #FFF7E8 | #FFE4BA 虚线 | #FFCF8B |
| 虚框按钮 | 成功 | 禁用 | #E8FFEA | #AFF0B5 虚线 | #7BE188 |
| 线框按钮 | 标准 | 默认 | 透明 | #00AAA6 | #00AAA6 |
| 线框按钮 | 危险 | 默认 | 透明 | #F53F3F | #F53F3F |
| 线框按钮 | 成功 | 默认 | 透明 | #00B42A | #00B42A |
| 线框按钮 | 警告 | 默认 | 透明 | #FF7D00 | #FF7D00 |
| 线框按钮 | 标准 | 悬停 | 透明 | #22BBB3 | #22BBB3 |
| 线框按钮 | 危险 | 悬停 | 透明 | #F76560 | #F76560 |
| 线框按钮 | 成功 | 悬停 | 透明 | #23C343 | #23C343 |
| 线框按钮 | 警告 | 悬停 | 透明 | #FF9A2E | #FF9A2E |
| 线框按钮 | 标准 | 激活 | 透明 | #009093 | #009093 |
| 线框按钮 | 危险 | 激活 | 透明 | #CB2634 | #CB2634 |
| 线框按钮 | 成功 | 激活 | 透明 | #009A29 | #009A29 |
| 线框按钮 | 警告 | 激活 | 透明 | #D25F00 | #D25F00 |
| 线框按钮 | 标准 | 禁用 | 透明 | #79DDD1 | #79DDD1 |
| 线框按钮 | 危险 | 禁用 | 透明 | #FBACA3 | #FBACA3 |
| 线框按钮 | 成功 | 禁用 | 透明 | #7BE188 | #7BE188 |
| 线框按钮 | 警告 | 禁用 | 透明 | #FFCF8B | #FFCF8B |
| 主要按钮 | 危险 | 默认 | #F53F3F | 无 | #FFFFFF |
| 主要按钮 | 成功 | 默认 | #00B42A | 无 | #FFFFFF |
| 主要按钮 | 警告 | 默认 | #FF7D00 | 无 | #FFFFFF |
| 主要按钮 | 危险 | 悬停 | #F76560 | 无 | #FFFFFF |
| 主要按钮 | 成功 | 悬停 | #23C343 | 无 | #FFFFFF |
| 主要按钮 | 警告 | 悬停 | #FF9A2E | 无 | #FFFFFF |
| 主要按钮 | 危险 | 激活 | #CB2634 | 无 | #FFFFFF |
| 主要按钮 | 成功 | 激活 | #009A29 | 无 | #FFFFFF |
| 主要按钮 | 警告 | 激活 | #D25F00 | 无 | #FFFFFF |
| 主要按钮 | 危险 | 禁用 | #FBACA3 | 无 | #FFFFFF |
| 主要按钮 | 成功 | 禁用 | #7BE188 | 无 | #FFFFFF |
| 主要按钮 | 警告 | 禁用 | #FFCF8B | 无 | #FFFFFF |
| 文本按钮 | 标准 | 默认 | 透明 | 无 | #00AAA6 |
| 文本按钮 | 危险 | 默认 | 透明 | 无 | #F53F3F |
| 文本按钮 | 成功 | 默认 | 透明 | 无 | #00B42A |
| 文本按钮 | 警告 | 默认 | 透明 | 无 | #FF7D00 |
| 文本按钮 | 标准 | 悬停 | #F2F3F5 | 无 | #00AAA6 |
| 文本按钮 | 危险 | 悬停 | #F2F3F5 | 无 | #F53F3F |
| 文本按钮 | 成功 | 悬停 | #F2F3F5 | 无 | #00B42A |
| 文本按钮 | 警告 | 悬停 | #F2F3F5 | 无 | #FF7D00 |
| 文本按钮 | 标准 | 激活 | #E5E6EB | 无 | #00AAA6 |
| 文本按钮 | 危险 | 激活 | #E5E6EB | 无 | #F53F3F |
| 文本按钮 | 成功 | 激活 | #E5E6EB | 无 | #00B42A |
| 文本按钮 | 警告 | 激活 | #E5E6EB | 无 | #FF7D00 |
| 文本按钮 | 标准 | 禁用 | 透明 | 无 | #79DDD1 |
| 文本按钮 | 危险 | 禁用 | 透明 | 无 | #FBACA3 |
| 文本按钮 | 成功 | 禁用 | 透明 | 无 | #7BE188 |
| 文本按钮 | 警告 | 禁用 | 透明 | 无 | #FFCF8B |

仅图标按钮：宽 = 高，左右内边距为 0。按钮组间距 8px，图标与文字间距 8px。

### 实例：按钮

由上表数据生成。`live` 类开启悬停与按下样式；`.pb` 始终带 1px 边框（无描边时透明），所以左右内边距比表中少 1px。

```html
<button type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;">查询</button>
<button type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;">重置</button>
<button type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;--bs:dashed;">添加</button>
<button type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:transparent;--bd:#00AAA6;--tx:#00AAA6;--bg-h:transparent;--bd-h:#22BBB3;--tx-h:#22BBB3;--bg-a:transparent;--bd-a:#009093;--tx-a:#009093;">导出</button>
<button type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:transparent;--bd:transparent;--tx:#00AAA6;--bg-h:#F2F3F5;--bd-h:transparent;--tx-h:#00AAA6;--bg-a:#E5E6EB;--bd-a:transparent;--tx-a:#00AAA6;">查看详情</button>
<button type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F53F3F;--bd:transparent;--tx:#FFFFFF;--bg-h:#F76560;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#CB2634;--bd-a:transparent;--tx-a:#FFFFFF;">删除</button>
<button type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;">小号</button>
<button type="button" class="pb live" style="--h:24px;--px:11px;--r:4px;--fs:12px;--lh:20px;--is:12px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;">迷你</button>
```

> 说明：虚框按钮在 Figma 中的虚线为 4 / 4，网页用 CSS dashed 近似。令牌名按色值与 Figma 颜色变量匹配；同一色值对应多个令牌时，按背景、边框、文字的用途取对应分组。

## Link 链接

文字链接，用于页面跳转或打开外部资源。4 种类型 × 4 种状态共 16 个变体，悬停和按下时出现浅灰底色。

- Figma：[115963:125902](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115963-125902)
- 变体概况：16 个变体

### 链接颜色

| 种类 | 状态 | 背景 | 文字 |
| --- | --- | --- | --- |
| 默认 | 默认 | 透明 | #00AAA6 |
| 默认 | 悬停 | #F2F3F5 | #00AAA6 |
| 默认 | 激活 | #E5E6EB | #00AAA6 |
| 默认 | 禁用 | 透明 | #79DDD1 |
| 错误 | 默认 | 透明 | #F53F3F |
| 错误 | 悬停 | #F2F3F5 | #F53F3F |
| 错误 | 激活 | #E5E6EB | #F53F3F |
| 错误 | 禁用 | 透明 | #FBACA3 |
| 成功 | 默认 | 透明 | #00B42A |
| 成功 | 悬停 | #F2F3F5 | #00B42A |
| 成功 | 激活 | #E5E6EB | #00B42A |
| 成功 | 禁用 | 透明 | #7BE188 |
| 警告 | 默认 | 透明 | #FF7D00 |
| 警告 | 悬停 | #F2F3F5 | #FF7D00 |
| 警告 | 激活 | #E5E6EB | #FF7D00 |
| 警告 | 禁用 | 透明 | #FFCF8B |

链接内边距 1px 4px，圆角 2px，14 / 22。

### 站点页面内容

```text
文字链接，用于页面跳转或打开外部资源。4 种类型 × 4 种状态共 16 个变体，悬停和按下时出现浅灰底色。

16 个变体
链接
默认
可交互：悬停、按下查看状态
查看详情
类型
默认
错误
成功
警告
状态
交互
默认
悬停
激活
禁用
带图标
链接文字
参数	值（点击复制）
内边距	上下 1px，左右 4px

圆角	2px

图标	12×12px，与文字间距 4px

文字样式	14/CN-Regular，14px / 22px
状态色	默认	悬停	激活	禁用
文字 / 图标
primary-6
#00AAA6

primary-6
#00AAA6

primary-6
#00AAA6

primary-3
#79DDD1

背景
无
transparent

color-fill-2
#F2F3F5

color-fill-3
#E5E6EB

无
transparent
CSS
复制代码
/* Pangea Link：默认 */
.pg-link {
  display: inline-flex;
  align-items: center;
  gap: 4px;
  padding: 1px 4px;
  border-radius: 2px;
  color: #00AAA6; /* primary-6 */
  font: 400 14px/22px "PingFang SC", "Microsoft YaHei", sans-serif;
  text-decoration: none;
}
.pg-link:hover { background: #F2F3F5; /* gray-2 */ }
.pg-link:active { background: #E5E6EB; /* gray-3 */ }
.pg-link[aria-disabled="true"] { color: #79DDD1; /* primary-3 */ cursor: not-allowed; }
全部变体
点击单元格载入上方实例
类型	默认	悬停	激活	禁用
默认
Link
#00AAA6

Link
#00AAA6

Link
#00AAA6

Link
#79DDD1

错误
Link
#F53F3F

Link
#F53F3F

Link
#F53F3F

Link
#FBACA3

成功
Link
#00B42A

Link
#00B42A

Link
#00B42A

Link
#7BE188

警告
Link
#FF7D00

Link
#FF7D00

Link
#FF7D00

Link
#FFCF8B
Figma 中链接图标使用 12px 的 icon-wrapper，没有指定具体图标；示例用 Pangea 图标 link。
```

> 说明：Figma 中链接图标使用 12px 的 icon-wrapper，没有指定具体图标；示例用 Pangea 图标 link。

## Typography 排版

Figma 组件 text/text：按层级区分文字颜色，并可附加标记、代码块、复制或编辑。

- Figma：[115963:125903](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115963-125903)
- 变体概况：10 个变体；字号与字重规范

### 站点页面内容

```text
Figma 组件 text/text：按层级区分文字颜色，并可附加标记、代码块、复制或编辑。

10 个变体
字号与字重规范
text/text
主要
无
做有温度的高效体验
层级
主要
次要
品牌色
附加
无
标记
代码块
可复制
可编辑
文字内容
参数	值（点击复制）
文字样式	14/CN-Regular，14px / 22px，PingFang SC Regular 400

颜色
color-text-1
#1D2129

附加样式	纯文本
全部变体
Figma 中实际存在的 10 种组合
层级	附加	样式
主要	无	Pangea Design
主要	标记
◦
Pangea Design

主要	代码块
Pangea Design

主要	可复制
Pangea Design

主要	可编辑
Pangea Design

次要	无	Pangea Design
次要	标记
◦
Pangea Design

次要	可复制
Pangea Design

次要	可编辑
Pangea Design

品牌色	无	Pangea Design
```

## Divider 分割线

区隔内容区块或行内操作。分水平与垂直两种，可用虚线，水平分割线可以带文字。

- Figma：[115964:125905](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115964-125905)
- 变体概况：10 个变体

### 站点页面内容

```text
区隔内容区块或行内操作。分水平与垂直两种，可用虚线，水平分割线可以带文字。

10 个变体
divider
水平
实线

上方内容区域

更多信息

下方内容区域

方向
水平
垂直
虚线
带文字
文字位置
左
中
右
参数	值（点击复制）
线色
color-border-2
#E5E6EB

线宽	1px

虚线	线段 3px，间隔 2px

文字与线间距	16px

短线长度	21px（文字靠左或靠右时）

文字样式	14/CN-Regular，color-text-1 #1D2129

垂直分割线	高 12px，用于行内操作之间
全部变体
水平，实线

水平，虚线

文字居中
Text

文字靠左
Text

文字靠右，虚线
Text

垂直，实线
编辑
复制
删除

垂直，虚线
编辑
复制
删除
```

