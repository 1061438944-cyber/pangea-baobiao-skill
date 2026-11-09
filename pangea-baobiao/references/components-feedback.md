# 反馈组件

每个组件包含：用途、Figma 节点、样式参数（读自 Figma，个别标注为假设）、Figma 变体属性、静态 HTML 实例。

HTML 实例的用法：
- 样式来自 `assets/pangea-components.css`，类名统一 `q-` 前缀；按钮是 `.pb`，颜色和尺寸写在行内 CSS 变量里。
- `<svg data-icon="名称" class="i"/>` 是图标占位，替换成 `assets/icons/名称.svg` 的内容（单色图标用 `currentColor`）。
- 实例里的 `data-*` 属性是站点交互用的钩子，交互逻辑需要自己实现；示例数据只用于演示。

## Alert 警告提示

在页面内显示需要用户注意的信息，不会自动消失。分信息、成功、警告、危险四种。

- Figma：[115965:125947](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125947)
- 变体概况：4 种类型，有无标题

### 样式参数

| 参数 | 值 |
| --- | --- |
| 内边距 | 9px 16px；带标题时 16px |
| 圆角 | 4px |
| 图标 | 16px（带标题时 20px），与文字间距 8px |
| 底色 | 未匹配令牌 #E8F3FF success-1 #E8FFEA warning-1 #FFF7E8 danger-1 #FFECE8 |
| 文字 | 14 / 22 color-text-1；标题 16 / 24 Semibold |

> 说明：信息色只读到了 info-1（#E8F3FF）这个令牌，图标的 #165DFF 来自 Figma 组件中实际使用的色值。

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| alert | 类型 | 信息 / 成功 / 警告 / 危险 |
| alert | 标题 | false / true |

### 实例：类型

```html
<div class="q-vert" style="width:100%"><div class="q-al" role="alert" style="--ab:#E8F3FF;--ac:#165DFF"><svg data-icon="info-circle-fill" class="i"/><div class="m">口径说明：收入为不含税管理口径。</div></div><div class="q-al" role="alert" style="--ab:#E8FFEA;--ac:#00B42A"><svg data-icon="check-circle-fill" class="i"/><div class="m">数据已更新到 2026-07。</div></div><div class="q-al" role="alert" style="--ab:#FFF7E8;--ac:#FF7D00"><svg data-icon="exclamation-circle-fill" class="i"/><div class="m">本月尚未结账，数值可能变化。</div></div><div class="q-al" role="alert" style="--ab:#FFECE8;--ac:#F53F3F"><svg data-icon="close-circle-fill" class="i"/><div class="m">数据加载失败，请稍后重试。</div></div></div>
```

### 实例：带标题、操作与关闭

点 × 关闭

```html
<div class="q-vert" style="width:100%"><div class="q-al tt" role="alert" style="--ab:#FFF7E8;--ac:#FF7D00"><svg data-icon="exclamation-circle-fill" class="i"/><div class="m"><b>指标预警</b>7 月内销商空完成率 87.2%，低于预警线 90%。</div><button type="button" class="x" data-alx="" aria-label="关闭"><svg data-icon="close" class="i"/></button></div><div class="q-al" role="alert" style="--ab:#E8F3FF;--ac:#165DFF"><svg data-icon="info-circle-fill" class="i"/><div class="m">有 3 张报表等待你审批。</div><button type="button" class="pb live" style="--h:24px;--px:11px;--r:4px;--fs:12px;--lh:20px;--is:12px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="去处理">去处理</button><button type="button" class="x" data-alx="" aria-label="关闭"><svg data-icon="close" class="i"/></button></div></div>
```

## Drawer 抽屉

从屏幕边缘滑出的面板，用于查看详情或编辑，不离开当前页面。

- Figma：[115965:125948](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125948)
- 变体概况：可调整宽度

### 样式参数

| 参数 | 值 |
| --- | --- |
| 位置 | 右侧，高度占满 |
| 头部 | 内边距 12px 20px，标题 16 / 24 Semibold |
| 内容区 | 内边距 24px |
| 底部 | 内边距 16px 20px，按钮右对齐 |
| 遮罩 | #1D2129，60% 不透明 |
| 宽度 | Figma 中可拖动调整（adjuster），示例 440 / 640px |

### 实例：抽屉

点遮罩、× 或按 Esc 关闭

```html
<div class="q-row"><button data-drw="440" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="打开抽屉">打开抽屉</button><button data-drw="640" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="宽抽屉 640">宽抽屉 640</button></div>
```

## Message 全局提示

操作后的轻量反馈，出现在页面顶部中央，几秒后自动消失。

- Figma：[115965:125949](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125949)
- 变体概况：信息 / 成功 / 危险 / 错误 / 基础

### 样式参数

| 参数 | 值 |
| --- | --- |
| 容器 | 内边距 9px 16px，白底，描边 color-border-2，圆角 8px，投影 |
| 图标 | 20px，与文字间距 8px |
| 文字 | 14 / 22 color-text-1 |
| 关闭图标 | 12px |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| message | 类型 | 信息 / 成功 / 危险 / 错误 / 基础 |

### 实例：全局提示

点按钮弹出，3 秒后自动消失

```html
<div class="q-row"><button data-msg="信息|口径已切换为管理口径" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="信息">信息</button><button data-msg="成功|报表已保存" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="成功">成功</button><button data-msg="警告|部分数据尚未结账" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="警告">警告</button><button data-msg="错误|导出失败，请重试" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="错误">错误</button><button data-msg="基础|正在同步数据" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="基础">基础</button></div>
```

## Modal 对话框

在当前页面上打开一个浮层，让用户完成表单或确认操作。分标准对话框和确认框。

- Figma：[115965:125950](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125950)
- 变体概况：23 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 标准对话框 | 宽 520px，圆角 8px |
| 头部 | 内边距 12px 20px，标题 16 / 24 Semibold，关闭图标 16px |
| 内容区 | 内边距 24px |
| 底部 | 内边距 16px 20px，按钮间距 8px |
| 确认框 | 宽 400px，内边距 24px 32px 32px，图标 20px |
| 遮罩 | #1D2129，60% 不透明 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| modal | 简单模式 | false / true |
| modal-confirm | 信息 | false / true |
| modal-confirm | 成功 | false / true |
| modal-confirm | 警告 | true / false |
| modal-confirm | 危险 | false / true |

### 实例：标准对话框

点遮罩、× 或按 Esc 关闭

```html
<button data-md="" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="打开对话框">打开对话框</button>
```

### 实例：确认框

确认框宽 400px

```html
<div class="q-row"><button data-mcf="信息" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="信息">信息</button><button data-mcf="成功" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="成功">成功</button><button data-mcf="警告" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="警告">警告</button><button data-mcf="危险" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="危险">危险</button></div>
```

## Notification 通知提醒框

从右上角弹出的通知，适合内容较多或需要用户操作的消息。可关闭，默认 4.5 秒后消失。

- Figma：[115965:125951](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125951)
- 变体概况：默认 / 信息 / 成功 / 警告 / 危险

### 样式参数

| 参数 | 值 |
| --- | --- |
| 容器 | 宽 340px，内边距 20px，图标与内容间距 16px，圆角 4px，白底投影 |
| 标题 | 16 / 24 Semibold color-text-1，与正文间距 4px |
| 正文 | 14 / 22 color-text-1 |
| 底部按钮 | 上内边距 16px，按钮组右对齐 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| notification | 类型 | 默认 / 信息 / 成功 / 警告 / 危险 |
| notification | 可关闭 | true / false |

### 实例：通知提醒框

点按钮弹出

```html
<div class="q-row"><button data-ntf="默认" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="默认">默认</button><button data-ntf="信息" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="信息">信息</button><button data-ntf="成功" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="成功">成功</button><button data-ntf="警告" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="警告">警告</button><button data-ntf="危险" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="危险">危险</button><button data-ntf="成功|1" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="带操作按钮">带操作按钮</button></div>
```

## Popconfirm 气泡确认框

点击后在旁边弹出气泡，让用户确认一个轻量操作，例如删除一行。

- Figma：[115965:125952](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125952)
- 变体概况：12 个位置

### 样式参数

| 参数 | 值 |
| --- | --- |
| 容器 | 内边距 16px，圆角 4px，白底投影 |
| 标题 | 20px 警示图标 + 14 / 22 文字，间距 8px |
| 按钮组 | 右对齐，间距 8px，与标题间距 16px |
| 箭头 | 6px |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| popconfirm | 位置 | 上 / 下 / 上左 / 左 / 右 / 左上 / 右上 / 左下 / 右下 / 下左 / 上右 / 下右 |

### 实例：气泡确认框

点“删除”后确认

```html
<div class="q-row" style="padding-top:110px"><span class="q-row" style="gap:8px;padding:8px 12px;border:1px solid #E5E6EB;border-radius:4px;font-size:14px;color:#1D2129" data-row="">空气事业部经营月报<span class="q-wrap"><button data-dd="" type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:transparent;--bd:transparent;--tx:#F53F3F;--bg-h:#F2F3F5;--bd-h:transparent;--tx-h:#F53F3F;--bg-a:#E5E6EB;--bd-a:transparent;--tx-a:#F53F3F;" aria-label="删除">删除</button><div class="q-pcf" role="dialog"><div class="t"><svg data-icon="exclamation-circle-fill" class="i"/><span>确定删除“空气事业部经营月报”吗？删除后订阅用户将无法查看。</span></div><div class="ft"><button data-pcx="" type="button" class="pb live" style="--h:24px;--px:11px;--r:4px;--fs:12px;--lh:20px;--is:12px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="取消">取消</button><button data-pcok="" type="button" class="pb live" style="--h:24px;--px:11px;--r:4px;--fs:12px;--lh:20px;--is:12px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="确定">确定</button></div></div></span></span><span class="q-row" style="gap:8px;padding:8px 12px;border:1px solid #E5E6EB;border-radius:4px;font-size:14px;color:#1D2129" data-row="">财务指标周报<span class="q-wrap"><button data-dd="" type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:transparent;--bd:transparent;--tx:#F53F3F;--bg-h:#F2F3F5;--bd-h:transparent;--tx-h:#F53F3F;--bg-a:#E5E6EB;--bd-a:transparent;--tx-a:#F53F3F;" aria-label="删除">删除</button><div class="q-pcf" role="dialog"><div class="t"><svg data-icon="exclamation-circle-fill" class="i"/><span>确定删除“财务指标周报”吗？删除后订阅用户将无法查看。</span></div><div class="ft"><button data-pcx="" type="button" class="pb live" style="--h:24px;--px:11px;--r:4px;--fs:12px;--lh:20px;--is:12px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="取消">取消</button><button data-pcok="" type="button" class="pb live" style="--h:24px;--px:11px;--r:4px;--fs:12px;--lh:20px;--is:12px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="确定">确定</button></div></div></span></span></div>
```

## Progress 进度条

展示操作进度。分条形、环形和迷你三种，可显示成功、错误和未开始状态。

- Figma：[115965:125953](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125953)
- 变体概况：61 个变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 条形轨道 | 高 4px，圆角 10px color-fill-3 #E5E6EB |
| 进度色 | primary-6 #00AAA6 success-6 #00B42A danger-6 #F53F3F |
| 百分比 | 14 / 22 color-text-2，与轨道间距 8px |
| 环形 | 中号 64px，百分比 14 / 22 Semibold color-text-3 |
| 迷你 | 16px，轨道 primary-3，进度 primary-6 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| progress-line | 尺寸 | 中 / 大 / 小 |
| progress-line | 状态 | 默认 / 成功 / 错误 / 未开始 |
| progress-line | 文本 | false / true |
| progress-circle | 尺寸 | 中 / 大 / 小 |
| progress-circle | 状态 | 默认 / 成功 / 错误 / 未开始 |
| progress-circle | 文本 | false / true |
| progress-mini | 状态 | 默认 / 未开始 / 错误 / 成功 |
| progress-mini | 饼状 | false / true |

### 实例：条形

```html
<div class="q-vert"><div class="q-pl" style="--pc:#00AAA6"><span class="tr"><i style="width:66%"></i></span><span>66%</span></div><div class="q-pl" style="--pc:#00B42A"><span class="tr"><i style="width:100%"></i></span><svg data-icon="check-circle-fill" class="i"/></div><div class="q-pl" style="--pc:#F53F3F"><span class="tr"><i style="width:45%"></i></span><svg data-icon="close-circle-fill" class="i"/></div><div class="q-pl" style="--pc:#E5E6EB"><span class="tr"><i style="width:0%"></i></span><span>0%</span></div></div>
```

### 实例：环形与迷你

```html
<div class="q-row"><span class="q-pc" style="--s:64px;--pc:#00AAA6"><svg viewBox="0 0 64 64"><circle class="bg" cx="32" cy="32" r="30"></circle><circle class="fg" cx="32" cy="32" r="30" stroke-dasharray="188.49555921538757" stroke-dashoffset="131.9468914507713"></circle></svg>30%</span><span class="q-pc" style="--s:64px;--pc:#00B42A"><svg viewBox="0 0 64 64"><circle class="bg" cx="32" cy="32" r="30"></circle><circle class="fg" cx="32" cy="32" r="30" stroke-dasharray="188.49555921538757" stroke-dashoffset="0"></circle></svg><span style="color:#00B42A"><svg data-icon="check" class="i"/></span></span><span class="q-pc" style="--s:64px;--pc:#F53F3F"><svg viewBox="0 0 64 64"><circle class="bg" cx="32" cy="32" r="30"></circle><circle class="fg" cx="32" cy="32" r="30" stroke-dasharray="188.49555921538757" stroke-dashoffset="103.67255756846318"></circle></svg><span style="color:#F53F3F"><svg data-icon="close" class="i"/></span></span><span class="q-pc" style="--s:16px;--sw:4px"><svg viewBox="0 0 16 16"><circle cx="8" cy="8" r="6" style="stroke:#79DDD1"></circle><circle class="fg" cx="8" cy="8" r="6" stroke-dasharray="37.69911184307752" stroke-dashoffset="15.079644737231007"></circle></svg></span><span class="q-out">迷你 16px</span></div>
```

### 实例：模拟进度

点“开始”

```html
<div class="q-vert"><div id="pg1"><div class="q-pl" style="--pc:#00AAA6"><span class="tr"><i style="width:0%"></i></span><span>0%</span></div></div><div class="q-row"><button data-pgo="" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="开始">开始</button><button data-prs="" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="重置">重置</button></div></div>
```

## Result 结果页

告诉用户一个流程的处理结果，并给出下一步操作。

- Figma：[115965:125954](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125954)
- 变体概况：成功 / 信息 / 警告 / 错误

### 样式参数

| 参数 | 值 |
| --- | --- |
| 容器 | 宽 620px，内边距 24px，各部分间距 16px |
| 图标 | 48px，取对应功能色 |
| 标题 | 14 / 22 Semibold color-text-1 |
| 说明 | 14 / 22 color-text-3 |
| 操作 | 按钮组，间距 8px |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| result | 成功提示 | true / false |
| result | 信息提示 | false / true |
| result | 警告提示 | false / true |
| result | 错误提示 | false / true |

### 实例：结果页

切换结果类型

```html
<div class="q-vert" style="width:100%;align-items:center"><span class="q-cap s"><button type="button" class="on">成功</button><i></i><button type="button" class="">信息</button><i></i><button type="button" class="">警告</button><i></i><button type="button" class="">错误</button></span><div id="rs1" style="width:100%;display:flex;justify-content:center"><div class="q-res" style="--ab:#E8FFEA;--ac:#00B42A"><svg data-icon="check-circle-fill" class="i"/><div><b>报表已发布</b><span>订阅用户会在明天 08:30 收到第一次推送。</span></div><div class="ex"><button type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="查看报表">查看报表</button><button type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="返回列表">返回列表</button></div></div></div></div>
```

## Spin 加载中

数据加载时显示的旋转图标，可单独使用，也可以盖在内容区上。

- Figma：[148163:263583](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=148163-263583)
- 变体概况：图标 / 点状

### 样式参数

| 参数 | 值 |
| --- | --- |
| 图标 | 20px，primary-6 |
| 点状 | 3 个 8px 圆点 |
| 文字 | 14 / 22 primary-6，与图标间距 6px |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| spin | 点类型 | false / true |

### 实例：类型

```html
<div class="q-row"><span class="q-spin"><svg data-icon="loading" class="i"/><span>正在加载数据</span></span><span class="q-spin"><span class="q-dots"><i></i><i></i><i></i></span><span>正在加载数据</span></span></div>
```

### 实例：盖在内容上

用开关控制加载状态

```html
<div class="q-vert"><div class="q-row"><span class="q-lab">加载中</span><button type="button" data-spn="" class="q-sw on sm" role="switch" aria-checked="true" aria-label="加载中"></button></div><div class="q-spinbox"><div class="q-card" style="width:100%"><h5>经营月报</h5><div class="bd">7 月主营业务收入 43,345 万元，计划完成率 98.6%，同比增长 4.23%。</div></div><div class="ov" id="spo"><span class="q-spin"><svg data-icon="loading" class="i"/><span>加载中</span></span></div></div></div>
```

## Skeleton 骨架屏

内容加载出来之前显示的占位图形，让用户预知页面结构。

- Figma：[115965:125955](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125955)
- 变体概况：头像 / 操作按钮可选

### 样式参数

| 参数 | 值 |
| --- | --- |
| 占位色 | color-fill-2 #F2F3F5 |
| 头像 | 圆形 |
| 文字行 | 行高 16px，行间距 16px，末行缩短 |
| 操作按钮占位 | primary-1 #E8FFFB |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| skeleton | 操作按钮 | false / true |
| skeleton | 头像 | false / true |

### 实例：骨架屏

打开开关显示真实内容

```html
<div class="q-vert" style="width:100%"><div class="q-row"><span class="q-lab">加载完成</span><button type="button" data-skn="" class="q-sw sm" role="switch" aria-checked="false" aria-label="加载完成"></button></div><div id="sk1"><div class="q-sk"><span class="av"></span><div class="bd"><span class="ln"></span><span class="ln"></span><span class="ln" style="width:62%"></span><span class="ln btn"></span></div></div></div></div>
```

## Watermark 水印

在页面上叠加半透明文字，标明查看人和用途，防止截图外传。

- Figma：[158317:66744](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=158317-66744)
- 变体概况：PC / 移动端

### 样式参数

| 参数 | 值 |
| --- | --- |
| 文字 | 14px，#1D2129 12% 不透明（示例） |
| 角度 | -22°（示例） |
| 平铺间距 | 240 × 160px（示例） |

> 说明：Figma 的 Watermark 页面给的是整页示例，没有单独标注水印的字号、透明度和间距，这里的取值为示例。

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| watermark | 终端 | PC / Mobile |

### 实例：水印

修改文字后水印实时更新

```html
<div class="q-vert" style="width:100%"><div class="q-row"><span class="q-lab">终端</span><span class="q-cap s"><button type="button" class="on">PC</button><i></i><button type="button" class="">移动端</button></span><span class="q-lab">水印文字</span><span class="q-in" style="--w:220px"><input placeholder="请输入" value="海信集团 李明 1024" data-wmt=""></span></div><div id="wm1" style="width:100%;display:flex;justify-content:center"><div class="q-wm"><div class="ct"><b style="display:block;margin-bottom:8px;color:#1D2129;font-size:16px;line-height:24px">空气事业部经营月报</b>主营业务收入 43,345 万元，计划完成率 98.6%，同比增长 4.23%。利润总额 5,812 万元，计划完成率 104.5%。<br><br>本页内容仅限内部使用。</div><div class="ly" style="background-image:url('data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22240%22%20height%3D%22160%22%3E%3Ctext%20x%3D%2220%22%20y%3D%22100%22%20transform%3D%22rotate(-22%20120%2080)%22%20font-size%3D%2214%22%20font-family%3D%22PingFang%20SC%2C%20sans-serif%22%20fill%3D%22rgba(29%2C33%2C41%2C0.12)%22%3E%E6%B5%B7%E4%BF%A1%E9%9B%86%E5%9B%A2%20%E6%9D%8E%E6%98%8E%201024%3C%2Ftext%3E%3C%2Fsvg%3E')"></div></div></div></div>
```

