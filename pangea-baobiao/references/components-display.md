# 数据展示组件

每个组件包含：用途、Figma 节点、样式参数（读自 Figma，个别标注为假设）、Figma 变体属性、静态 HTML 实例。

HTML 实例的用法：
- 样式来自 `assets/pangea-components.css`，类名统一 `q-` 前缀；按钮是 `.pb`，颜色和尺寸写在行内 CSS 变量里。
- `<svg data-icon="名称" class="i"/>` 是图标占位，替换成 `assets/icons/名称.svg` 的内容（单色图标用 `currentColor`）。
- 实例里的 `data-*` 属性是站点交互用的钩子，交互逻辑需要自己实现；示例数据只用于演示。

## Avatar 头像

用图标、文字或图片代表用户或事物。分圆形与方形，4 种尺寸，可组合成头像组。

- Figma：[115964:125909](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115964-125909)
- 变体概况：92 个变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 尺寸 | 大 64、中 40、小 32、迷你 24px |
| 底色 | color-fill-4 #C9CDD4 |
| 文字 | 白色 Semibold 600；大号 28px，其余 14px |
| 图标 | user 图标，大 32、中 20、小 16、迷你 12px |
| 圆角 | 圆形 100px；方形 8px（中号读值） |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| avatar | 形状 | 方形 / 圆形 |
| avatar | 类型 | 图标 / 文本 / 图片 |
| avatar | 尺寸 | 大 / 中 / 小 / 迷你 |
| avatar | 交互 | 无 / 遮罩 / 默认 |
| avatar-group | 尺寸 | 中 / 大 / 小 / 迷你 |
| avatar-group | 数量 | 2 / 5 / 4 / 3 |

### 实例：尺寸与类型

大 64 / 中 40 / 小 32 / 迷你 24

```html
<div class="q-vert"><div class="q-row"><span class="q-lab">文字</span><span class="q-av" style="--s:64px;--fs:28px;--is:32px" title="海">海</span><span class="q-av" style="--s:40px;--fs:14px;--is:20px" title="海">海</span><span class="q-av" style="--s:32px;--fs:14px;--is:16px" title="海">海</span><span class="q-av" style="--s:24px;--fs:14px;--is:12px" title="海">海</span></div><div class="q-row"><span class="q-lab">图标</span><span class="q-av" style="--s:64px;--fs:28px;--is:32px" title=""><svg data-icon="user" class="i"/></span><span class="q-av" style="--s:40px;--fs:14px;--is:20px" title=""><svg data-icon="user" class="i"/></span><span class="q-av" style="--s:32px;--fs:14px;--is:16px" title=""><svg data-icon="user" class="i"/></span><span class="q-av" style="--s:24px;--fs:14px;--is:12px" title=""><svg data-icon="user" class="i"/></span></div><div class="q-row"><span class="q-lab">方形</span><span class="q-av sq" style="--s:64px;--fs:28px;--is:32px" title="海">海</span><span class="q-av sq" style="--s:40px;--fs:14px;--is:20px" title="海">海</span><span class="q-av sq" style="--s:32px;--fs:14px;--is:16px" title="海">海</span><span class="q-av sq" style="--s:24px;--fs:14px;--is:12px" title="海">海</span><span class="q-av sq" style="--s:40px;--fs:14px;--is:20px" title=""><svg data-icon="user" class="i"/></span></div></div>
```

### 实例：头像组

相邻头像叠压 8px，外圈 2px 白色描边

```html
<div class="q-vert"><div class="q-row"><span class="q-lab">中</span><span class="q-avg"><span class="q-av" style="--s:40px;--fs:14px;--is:20px;background:#00AAA6" title="李">李</span><span class="q-av" style="--s:40px;--fs:14px;--is:20px;background:#3491FA" title="王">王</span><span class="q-av" style="--s:40px;--fs:14px;--is:20px;background:#FF7D00" title="张">张</span><span class="q-av" style="--s:40px;--fs:14px;--is:20px;background:#C9CDD4" title="赵">赵</span><span class="q-av" style="--s:40px;--fs:14px;--is:20px" title="+3">+3</span></span></div><div class="q-row"><span class="q-lab">小</span><span class="q-avg"><span class="q-av" style="--s:32px;--fs:14px;--is:16px" title="李">李</span><span class="q-av" style="--s:32px;--fs:14px;--is:16px" title="王">王</span><span class="q-av" style="--s:32px;--fs:14px;--is:16px" title="张">张</span></span></div></div>
```

### 实例：交互

```html
<div class="q-row"><span class="q-av hv" style="--s:40px;--fs:14px;--is:20px" title="悬停出现遮罩"><svg data-icon="user" class="i"/></span><span class="q-av hv" style="--s:40px;--fs:14px;--is:20px" title="海">海</span><span class="mut" style="font-size:13px">把鼠标移到头像上，出现半透明遮罩（交互 = 遮罩）</span></div>
```

## Badge 徽标

在头像或图标右上角显示数字、圆点或状态，提示有新内容或当前状态。

- Figma：[115964:125910](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115964-125910)
- 变体概况：30 个变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 数字底色 | danger-6 #F53F3F |
| 数字样式 | 12px / 20px 白色，左右内边距 6px，2px 白色描边，圆角 100px |
| 置灰 | 底色 #E5E6EB，文字 #86909C |
| 状态点与文字间距 | 8px，文字 14 / 22 color-text-1 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| badge/dot | 颜色 | red / orangered / orange / gold / lime / green / cyan / arcoblue / purple / pinkpurple / magenta / gray |
| badge/count | 置灰 | false / true |
| badge/status | 类型 | 默认 / 进行中 / 成功 / 提醒 / 错误 |
| badge-avatar | 字符 | true / false |
| badge-avatar | 圆点 | false / true |
| badge-avatar | 自定义 | false / true |

### 实例：数字徽标

点右侧按钮改变数字，超过 99 显示 99+

```html
<div class="q-row"><span class="q-bdg" id="bdg1"><span class="q-blk"></span><span class="n">8</span></span><span class="q-bdg"><span class="q-blk"></span><span class="n">99+</span></span><span class="q-bdg"><span class="q-blk"></span><span class="n g">16</span></span><span class="q-bdg"><span class="q-av sq" style="--s:40px;--is:20px"><svg data-icon="user" class="i"/></span><span class="dt"></span></span><button data-bd="-1" aria-label="减少" type="button" class="pb io live" style="--h:32px;--px:8px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;"><svg data-icon="minus" class="i"/></button><button data-bd="1" aria-label="增加" type="button" class="pb io live" style="--h:32px;--px:8px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;"><svg data-icon="plus" class="i"/></button></div>
```

### 实例：状态点

```html
<div class="q-row"><span class="q-st" style="--c:#C9CDD4"><i></i>默认</span><span class="q-st" style="--c:#165DFF"><i></i>进行中</span><span class="q-st" style="--c:#00B42A"><i></i>成功</span><span class="q-st" style="--c:#FF7D00"><i></i>提醒</span><span class="q-st" style="--c:#F53F3F"><i></i>错误</span></div>
```

### 实例：圆点颜色

点击复制色值

```html
<div class="q-row"><button type="button" class="cp" data-copy="#F53F3F" title="red #F53F3F" style="margin:0"><span class="q-st" style="--c:#F53F3F"><i></i>red</span></button><button type="button" class="cp" data-copy="#F77234" title="orangered #F77234" style="margin:0"><span class="q-st" style="--c:#F77234"><i></i>orangered</span></button><button type="button" class="cp" data-copy="#FF7D00" title="orange #FF7D00" style="margin:0"><span class="q-st" style="--c:#FF7D00"><i></i>orange</span></button><button type="button" class="cp" data-copy="#F7BA1E" title="gold #F7BA1E" style="margin:0"><span class="q-st" style="--c:#F7BA1E"><i></i>gold</span></button><button type="button" class="cp" data-copy="#9FDB1D" title="lime #9FDB1D" style="margin:0"><span class="q-st" style="--c:#9FDB1D"><i></i>lime</span></button><button type="button" class="cp" data-copy="#00B42A" title="green #00B42A" style="margin:0"><span class="q-st" style="--c:#00B42A"><i></i>green</span></button><button type="button" class="cp" data-copy="#0FC6C2" title="cyan #0FC6C2" style="margin:0"><span class="q-st" style="--c:#0FC6C2"><i></i>cyan</span></button><button type="button" class="cp" data-copy="#00AAA6" title="arcoblue #00AAA6" style="margin:0"><span class="q-st" style="--c:#00AAA6"><i></i>arcoblue</span></button><button type="button" class="cp" data-copy="#722ED1" title="purple #722ED1" style="margin:0"><span class="q-st" style="--c:#722ED1"><i></i>purple</span></button><button type="button" class="cp" data-copy="#D91AD9" title="pinkpurple #D91AD9" style="margin:0"><span class="q-st" style="--c:#D91AD9"><i></i>pinkpurple</span></button><button type="button" class="cp" data-copy="#F5319D" title="magenta #F5319D" style="margin:0"><span class="q-st" style="--c:#F5319D"><i></i>magenta</span></button><button type="button" class="cp" data-copy="#C9CDD4" title="gray #C9CDD4" style="margin:0"><span class="q-st" style="--c:#C9CDD4"><i></i>gray</span></button></div>
```

## Calendar 日历

按月或按年查看日程。点击日期选中，可切换月份和视图。

- Figma：[115967:127095](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115967-127095)
- 变体概况：月 / 年视图

### 样式参数

| 参数 | 值 |
| --- | --- |
| 容器 | 宽 980px（示例），白底，描边 color-border-2，圆角 2px |
| 头部内边距 | 24px |
| 表头 | 上下内边距 18px，左侧 20px |
| 日期单元 | picker-cell：今天 primary-6，选中 primary-6 圆底白字 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| calendar | 视图 | 月 / 年 |
| calendar | 下拉选择 | false / true |

### 实例：日历

示例日程为示例数据

```html
<div class="q-cal" id="cal1"><div class="hd"><b>2026 年 11 月</b><span class="nav"><button data-cm="-1" aria-label="上个月" type="button" class="pb io live" style="--h:28px;--px:6px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;"><svg data-icon="left" class="i"/></button><button data-cm="0" type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="今天">今天</button><button data-cm="1" aria-label="下个月" type="button" class="pb io live" style="--h:28px;--px:6px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;"><svg data-icon="right" class="i"/></button></span><span class="q-cap s"><button type="button" class="on">月</button><i></i><button type="button" class="">年</button></span></div> <div class="th"><span>日</span><span>一</span><span>二</span><span>三</span><span>四</span><span>五</span><span>六</span></div><div class="tb"><div class="cl" data-cd="2026-11-01"><span class="d">1</span></div><div class="cl" data-cd="2026-11-02"><span class="d">2</span></div><div class="cl" data-cd="2026-11-03"><span class="d">3</span><span class="q-st" style="--c:#00B42A"><i></i>月度结账</span></div><div class="cl" data-cd="2026-11-04"><span class="d">4</span></div><div class="cl" data-cd="2026-11-05"><span class="d">5</span></div><div class="cl" data-cd="2026-11-06"><span class="d">6</span></div><div class="cl" data-cd="2026-11-07"><span class="d">7</span></div><div class="cl" data-cd="2026-11-08"><span class="d">8</span></div><div class="cl td on" data-cd="2026-11-09"><span class="d">9</span><span class="q-st" style="--c:#165DFF"><i></i>经营分析会</span></div><div class="cl" data-cd="2026-11-10"><span class="d">10</span></div><div class="cl" data-cd="2026-11-11"><span class="d">11</span></div><div class="cl" data-cd="2026-11-12"><span class="d">12</span></div><div class="cl" data-cd="2026-11-13"><span class="d">13</span></div><div class="cl" data-cd="2026-11-14"><span class="d">14</span></div><div class="cl" data-cd="2026-11-15"><span class="d">15</span></div><div class="cl" data-cd="2026-11-16"><span class="d">16</span></div><div class="cl" data-cd="2026-11-17"><span class="d">17</span></div><div class="cl" data-cd="2026-11-18"><span class="d">18</span><span class="q-st" style="--c:#165DFF"><i></i>预算评审</span></div><div class="cl" data-cd="2026-11-19"><span class="d">19</span></div><div class="cl" data-cd="2026-11-20"><span class="d">20</span></div><div class="cl" data-cd="2026-11-21"><span class="d">21</span></div><div class="cl" data-cd="2026-11-22"><span class="d">22</span></div><div class="cl" data-cd="2026-11-23"><span class="d">23</span></div><div class="cl" data-cd="2026-11-24"><span class="d">24</span></div><div class="cl" data-cd="2026-11-25"><span class="d">25</span><span class="q-st" style="--c:#00B42A"><i></i>报表上线</span></div><div class="cl" data-cd="2026-11-26"><span class="d">26</span></div><div class="cl" data-cd="2026-11-27"><span class="d">27</span></div><div class="cl" data-cd="2026-11-28"><span class="d">28</span></div><div class="cl" data-cd="2026-11-29"><span class="d">29</span></div><div class="cl" data-cd="2026-11-30"><span class="d">30</span></div><div class="cl out" data-cd="2026-12-01"><span class="d">1</span></div><div class="cl out" data-cd="2026-12-02"><span class="d">2</span></div><div class="cl out" data-cd="2026-12-03"><span class="d">3</span></div><div class="cl out" data-cd="2026-12-04"><span class="d">4</span></div><div class="cl out" data-cd="2026-12-05"><span class="d">5</span></div><div class="cl out" data-cd="2026-12-06"><span class="d">6</span></div><div class="cl out" data-cd="2026-12-07"><span class="d">7</span></div><div class="cl out" data-cd="2026-12-08"><span class="d">8</span></div><div class="cl out" data-cd="2026-12-09"><span class="d">9</span></div><div class="cl out" data-cd="2026-12-10"><span class="d">10</span></div><div class="cl out" data-cd="2026-12-11"><span class="d">11</span></div><div class="cl out" data-cd="2026-12-12"><span class="d">12</span></div></div></div>
```

## Card 卡片

承载一组相关信息的容器，可带标题、操作、封面图和底部操作。

- Figma：[115964:125911](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115964-125911)
- 变体概况：简洁 / 边框

### 样式参数

| 参数 | 值 |
| --- | --- |
| 圆角 | 8px |
| 描边 | color-border-2 #E5E6EB |
| 头部 | 内边距 11px 16px，标题 16 / 24 Semibold，下边框 1px |
| 内容区 | 内边距 16px，正文 14 / 22 color-text-2 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| card | 简洁 | false / true |
| card | 边框 | true / false |

### 实例：卡片

```html
<div class="q-card"><h5>经营月报<a href="javascript:void 0">更多</a></h5><div class="bd">7 月主营业务收入 43,345 万元，计划完成率 98.6%，同比增长 4.23%。</div></div> <div class="q-card"><div class="q-media">封面图 16:9</div><div class="bd"><b style="display:block;color:#1D2129;font-weight:600;margin-bottom:4px">海信空调</b>家用与商用空调产品线概览。</div><div class="ft"><button type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="查看">查看</button><button type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="分享">分享</button></div></div>
```

### 实例：简洁卡片

简洁 = true，边框 = false

```html
<div class="q-card nb lite"><h5>无边框</h5><div class="bd">放在灰色背景上，用底色区分层级。</div></div>
```

## Carousel 图片轮播

在同一区域循环展示多张内容。支持自动播放、指示器和左右切换。

- Figma：[115964:125912](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115964-125912)
- 变体概况：点状 / 条状 / 滑动指示器

### 样式参数

| 参数 | 值 |
| --- | --- |
| 点状指示器 | 6×6px 白点，圆角 4px，底板 #E5E6EB 半透明 |
| 条状指示器 | 12×4px |
| 切换 | 横向滑动 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| carousel | 指示器位置 | 底部 / 顶部 / 左侧 / 右侧 / 外部 |
| carousel | 指示器类型 | 点状 / 条状 / 滚动 |
| carousel | 卡片化 | False / True |
| carousel-indicator | 类型 | 点状 / 条状 / 滑动 |

### 实例：轮播

每 3 秒自动切换，悬停时暂停

```html
<div class="q-vert" style="width:100%"><div class="q-row"><span class="q-lab">指示器</span><span class="q-cap s"><button type="button" class="on">点状</button><i></i><button type="button" class="">条状</button></span></div><div class="q-car" id="car1" data-i="0"><div class="tr"><div class="sl" style="background:linear-gradient(120deg,#00AAA6,#4ACCC1)">经营分析大屏</div><div class="sl" style="background:linear-gradient(120deg,#3491FA,#7BC0FC)">财务指标</div><div class="sl" style="background:linear-gradient(120deg,#FF7D00,#FFB65D)">供应链看板</div><div class="sl" style="background:linear-gradient(120deg,#722ED1,#A871E3)">人力资源</div></div><button type="button" class="ar" style="left:12px" data-car="-1" aria-label="上一张"><svg data-icon="left" class="i"/></button><button type="button" class="ar" style="right:12px" data-car="1" aria-label="下一张"><svg data-icon="right" class="i"/></button><div class="ind"><button type="button" class="on" data-cari="0" aria-label="第 1 张"></button><button type="button" class="" data-cari="1" aria-label="第 2 张"></button><button type="button" class="" data-cari="2" aria-label="第 3 张"></button><button type="button" class="" data-cari="3" aria-label="第 4 张"></button></div></div></div>
```

## Comment 评论

展示评论与回复。可点赞、回复，回复以缩进形式嵌套。

- Figma：[115964:125914](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115964-125914)
- 变体概况：左对齐 / 右对齐

### 样式参数

| 参数 | 值 |
| --- | --- |
| 头像 | 小号 32px |
| 头像与内容间距 | 12px |
| 正文 | 14 / 22 color-text-1 |
| 操作间距 | 20px，图标与文字 4px |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| comment | 对齐方式 | 左 / 右 |
| comment | 回复框 | false / true |

### 实例：评论

点赞、回复都可以点击

```html
<div class="q-cmt"><span class="q-av" style="--s:32px;--fs:14px;--is:16px;background:#00AAA6" title="李">李</span><div class="m"><div class="tt"><b>李明</b><span>2 小时前</span></div><div>7 月数据已更新，内销家空完成率略低于计划，建议补充原因说明。</div><div class="acts"><button type="button" data-like="3"><svg data-icon="thumb-up" class="i"/><span>3</span></button><button type="button" data-reply=""><svg data-icon="message" class="i"/>回复</button><button type="button" aria-label="更多"><svg data-icon="more" class="i"/></button></div><div class="rep"><div class="q-cmt"><span class="q-av" style="--s:32px;--fs:14px;--is:16px;background:#3491FA" title="王">王</span><div class="m"><div class="tt"><b>王芳</b><span>1 小时前</span></div><div>已补充，主要受渠道库存调整影响。</div><div class="acts"><button type="button" data-like="0"><svg data-icon="thumb-up" class="i"/><span>点赞</span></button><button type="button" data-reply=""><svg data-icon="message" class="i"/>回复</button><button type="button" aria-label="更多"><svg data-icon="more" class="i"/></button></div><div class="rbox"></div></div></div></div><div class="rbox"></div></div></div>
```

### 实例：右对齐

```html
<div class="q-cmt r"><span class="q-av" style="--s:32px;--fs:14px;--is:16px" title="张">张</span><div class="m"><div class="tt"><b>张伟</b><span>刚刚</span></div><div>右对齐用于对话中自己发出的消息。</div><div class="acts"><button type="button" data-like="0"><svg data-icon="thumb-up" class="i"/><span>点赞</span></button><button type="button" data-reply=""><svg data-icon="message" class="i"/>回复</button><button type="button" aria-label="更多"><svg data-icon="more" class="i"/></button></div><div class="rbox"></div></div></div>
```

## Collapse 折叠面板

把内容分组折叠，点击标题展开或收起。可设为手风琴模式，一次只展开一项。

- Figma：[115964:125913](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115964-125913)
- 变体概况：44 个变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 标题 | 内边距 9px 12px，14 / 22 Semibold color-text-1 |
| 展开图标 | caret-right 14px，展开后旋转 90°，与标题间距 6px |
| 内容区 | 内边距 8px 12px 8px 34px，14 / 22 color-text-2 |
| 分隔线 | color-border-2 #E5E6EB |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| collapse-item | 展开 | false / true |
| collapse-item | 禁用 | false / true |
| collapse-item | 简洁 | false / true |
| collapse-item | 展开图标 | 左侧 / 右侧 / 无 |
| collapse | 简洁 | false / true |
| collapse | 数量 | 2 / 3 / 4 / 5 / 6 / 7 / 8 / 9 / 10 |

### 实例：基础

图标在左侧

```html
<div class="q-col"><div class="q-ci open"><button type="button" class="q-ch" aria-expanded="true"><svg data-icon="caret-right" class="i c"/>经营指标口径说明</button><div class="q-cbd">收入为不含税管理口径，按结账月统计。</div></div><div class="q-ci"><button type="button" class="q-ch" aria-expanded="false"><svg data-icon="caret-right" class="i c"/>数据更新时间</button><div class="q-cbd">每日 08:00 更新前一日数据，月初 3 日前为预估数。</div></div><div class="q-ci"><button type="button" class="q-ch" aria-expanded="false"><svg data-icon="caret-right" class="i c"/>权限申请</button><div class="q-cbd">联系数据团队开通事业部级数据权限。</div></div><div class="q-ci d"><button type="button" class="q-ch" aria-expanded="false"><svg data-icon="caret-right" class="i c"/>已停用的指标</button><div class="q-cbd">禁用状态，不能展开。</div></div></div>
```

### 实例：手风琴

一次只展开一项，图标在右侧

```html
<div class="q-col" data-acc=""><div class="q-ci open"><button type="button" class="q-ch" aria-expanded="true">经营指标口径说明<svg data-icon="caret-right" class="i c ex"/></button><div class="q-cbd">收入为不含税管理口径，按结账月统计。</div></div><div class="q-ci"><button type="button" class="q-ch" aria-expanded="false">数据更新时间<svg data-icon="caret-right" class="i c ex"/></button><div class="q-cbd">每日 08:00 更新前一日数据，月初 3 日前为预估数。</div></div><div class="q-ci"><button type="button" class="q-ch" aria-expanded="false">权限申请<svg data-icon="caret-right" class="i c ex"/></button><div class="q-cbd">联系数据团队开通事业部级数据权限。</div></div><div class="q-ci d"><button type="button" class="q-ch" aria-expanded="false">已停用的指标<svg data-icon="caret-right" class="i c ex"/></button><div class="q-cbd">禁用状态，不能展开。</div></div></div>
```

### 实例：简洁

简洁 = true，无边框

```html
<div class="q-col lite"><div class="q-ci open"><button type="button" class="q-ch" aria-expanded="true"><svg data-icon="caret-right" class="i c"/>经营指标口径说明</button><div class="q-cbd">收入为不含税管理口径，按结账月统计。</div></div><div class="q-ci"><button type="button" class="q-ch" aria-expanded="false"><svg data-icon="caret-right" class="i c"/>数据更新时间</button><div class="q-cbd">每日 08:00 更新前一日数据，月初 3 日前为预估数。</div></div><div class="q-ci"><button type="button" class="q-ch" aria-expanded="false"><svg data-icon="caret-right" class="i c"/>权限申请</button><div class="q-cbd">联系数据团队开通事业部级数据权限。</div></div><div class="q-ci d"><button type="button" class="q-ch" aria-expanded="false"><svg data-icon="caret-right" class="i c"/>已停用的指标</button><div class="q-cbd">禁用状态，不能展开。</div></div></div>
```

## Descriptions 描述列表

成组展示只读字段，常用于详情页。分带边框和无边框两种，支持 4 种尺寸。

- Figma：[115964:125915](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115964-125915)
- 变体概况：50 个变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 带边框单元 | 内边距 5px 20px（中），描边 color-border-2 |
| 标签底色 | color-fill-1 #F7F8FA |
| 无边框单元 | 右 20px、下 8px 内边距 |
| 文字 | 14 / 22；标签 color-text-3，内容 color-text-1 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| descriptions | 尺寸 | 中 / 大 / 小 / 迷你 |
| descriptions | 边框 | true / false |
| descriptions-item/border | 尺寸 | 中 / 大 / 小 / 迷你 |
| descriptions-item/border | 布局模式 | horizontal / vertical / inline-horizontal / inline-vertical |
| descriptions-item/border | 标签对齐 | 左 / - / 右 |

### 实例：带边框

标签底色 color-fill-1

```html
<div class="q-vert" style="width:100%"><div class="q-row"><span class="q-lab">尺寸</span><span class="q-cap s"><button type="button" class="">大</button><i></i><button type="button" class="on">中</button><i></i><button type="button" class="">小</button></span></div><div id="ds1" style="width:100%"><table class="q-ds b "><tbody><tr><td class="k">报表名称</td><td>空气事业部经营月报</td><td class="k">负责人</td><td>李明</td><td class="k">统计口径</td><td>管理口径</td></tr><tr><td class="k">更新时间</td><td>2026-07-31 08:00</td><td class="k">订阅人数</td><td>128 人</td><td class="k">状态</td><td><span class="q-st" style="--c:#00B42A"><i></i>已上线</span></td></tr></tbody></table></div></div>
```

### 实例：无边框

```html
<table class="q-ds "><tbody><tr><td class="k">报表名称</td><td>空气事业部经营月报</td><td class="k">负责人</td><td>李明</td><td class="k">统计口径</td><td>管理口径</td></tr><tr><td class="k">更新时间</td><td>2026-07-31 08:00</td><td class="k">订阅人数</td><td>128 人</td><td class="k">状态</td><td><span class="q-st" style="--c:#00B42A"><i></i>已上线</span></td></tr></tbody></table>
```

## Empty 空状态

没有数据时显示的占位，告诉用户这里为什么是空的。

- Figma：[115964:125916](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115964-125916)
- 变体概况：默认 / 自定义图片

### 样式参数

| 参数 | 值 |
| --- | --- |
| 宽度 | 168px |
| 图片 | 48×48px，与文字间距 4px |
| 文字 | 14 / 22 |
| 文字颜色 | gray-5 #A9AEB8 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| empty | 自定义图片 | false / true |

### 实例：空状态

第二个为自定义图片，示例用 Pangea 图标 file-search

```html
<div class="q-emp"><svg data-icon="empty" class="i"/>暂无数据</div><div class="q-emp" style="width:auto"><svg data-icon="file-search" class="i"/>没有符合条件的报表<span style="margin-top:12px"><button type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="清空筛选条件">清空筛选条件</button></span></div>
```

## HPTable 高性能表格

面向大数据量的高性能表格。首列复选框与末列操作固定，中间列可横向滚动。

- Figma：[150286:42514](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=150286-42514)
- 变体概况：中 / 小 / 迷你

### 样式参数

| 参数 | 值 |
| --- | --- |
| 列类型 | 文本、链接、操作、复选、单选，均可左 / 中 / 右对齐，可固定 |
| 尺寸 | 中、小、迷你 |
| 固定列 | 首列与操作列 sticky 固定，分隔线 color-border-2 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| hp-table | 尺寸 | 中 / 小 / 迷你 |
| column/text | 尺寸 | 中 / 小 / 迷你 |
| column/text | 对齐 | 左 / 中 / 右 |
| column/text | 固定 | false / true |
| column/checkbox | 尺寸 | 中 / 小 / 迷你 |
| column/checkbox | 对齐 | 左 / 中 / 右 |
| column/checkbox | 文字 | false / true |
| column/checkbox | 固定 | false / true |

### 实例：高性能表格

左右拖动表格查看被固定的首末列

```html
<div class="q-vert" style="width:100%"><div class="q-row"><span class="q-lab">尺寸</span><span class="q-cap s" id="hpsz"><button type="button" class="on" data-hsz="">中</button><i></i><button type="button" class="" data-hsz="s">小</button><i></i><button type="button" class="" data-hsz="xs">迷你</button></span></div><div id="hp1" style="width:100%"><div class="q-tbw" style="max-width:900px"><table class="q-tb bd"><thead><tr><th class="w fx"><span class="q-cb" data-all="" role="checkbox" aria-checked="false" tabindex="0"><i></i></span></th><th>产品线</th><th>负责人</th><th class="r">收入（万元）<span class="srt" data-sort="" title="排序"><svg data-icon="caret-up" class="i"/><svg data-icon="caret-down" class="i"/></span></th><th class="r">完成率</th><th>状态</th><th>标签</th><th>订阅</th><th>口径</th><th>更新时间</th><th>数据来源</th><th class="fxr">操作</th></tr></thead><tbody> <tr><td class="w fx"><span class="q-cb" data-v="0" role="checkbox" aria-checked="false" tabindex="0"><i></i></span></td><td>内销家空</td><td>李明</td><td class="r num">23,323.32</td><td class="r num">98.6%</td><td><span class="q-st" style="--c:#00B42A"><i></i>正常</span></td><td><span class="q-tag" style="margin-right:4px">家用</span></td><td><button type="button" class="q-sw on sm" role="switch" aria-checked="true" aria-label="订阅"></button></td><td>管理口径</td><td>2026-07-31 08:00</td><td>永洪 BI</td><td class="fxr"><button type="button" class="op">查看</button><button type="button" class="op">导出</button></td></tr><tr><td class="w fx"><span class="q-cb" data-v="1" role="checkbox" aria-checked="false" tabindex="0"><i></i></span></td><td>内销商空</td><td>王芳</td><td class="r num">12,086.15</td><td class="r num">87.2%</td><td><span class="q-st" style="--c:#FF7D00"><i></i>预警</span></td><td><span class="q-tag" style="margin-right:4px">商用</span></td><td><button type="button" class="q-sw on sm" role="switch" aria-checked="true" aria-label="订阅"></button></td><td>管理口径</td><td>2026-07-31 08:00</td><td>永洪 BI</td><td class="fxr"><button type="button" class="op">查看</button><button type="button" class="op">导出</button></td></tr><tr><td class="w fx"><span class="q-cb" data-v="2" role="checkbox" aria-checked="false" tabindex="0"><i></i></span></td><td>出口整体</td><td>张伟</td><td class="r num">18,540.60</td><td class="r num">104.5%</td><td><span class="q-st" style="--c:#00B42A"><i></i>正常</span></td><td><span class="q-tag" style="margin-right:4px">出口</span><span class="q-tag" style="margin-right:4px">重点</span></td><td><button type="button" class="q-sw sm" role="switch" aria-checked="false" aria-label="订阅"></button></td><td>管理口径</td><td>2026-07-31 08:00</td><td>永洪 BI</td><td class="fxr"><button type="button" class="op">查看</button><button type="button" class="op">导出</button></td></tr><tr><td class="w fx"><span class="q-cb" data-v="3" role="checkbox" aria-checked="false" tabindex="0"><i></i></span></td><td>家空分公司</td><td>赵丽</td><td class="r num">9,402.88</td><td class="r num">92.4%</td><td><span class="q-st" style="--c:#00B42A"><i></i>正常</span></td><td><span class="q-tag" style="margin-right:4px">家用</span></td><td><button type="button" class="q-sw on sm" role="switch" aria-checked="true" aria-label="订阅"></button></td><td>管理口径</td><td>2026-07-31 08:00</td><td>永洪 BI</td><td class="fxr"><button type="button" class="op">查看</button><button type="button" class="op">导出</button></td></tr><tr><td class="w fx"><span class="q-cb" data-v="4" role="checkbox" aria-checked="false" tabindex="0"><i></i></span></td><td>商空分公司</td><td>孙强</td><td class="r num">7,720.30</td><td class="r num">81.9%</td><td><span class="q-st" style="--c:#FF7D00"><i></i>预警</span></td><td><span class="q-tag" style="margin-right:4px">商用</span></td><td><button type="button" class="q-sw sm" role="switch" aria-checked="false" aria-label="订阅"></button></td><td>管理口径</td><td>2026-07-31 08:00</td><td>永洪 BI</td><td class="fxr"><button type="button" class="op">查看</button><button type="button" class="op">导出</button></td></tr><tr><td class="w fx"><span class="q-cb" data-v="5" role="checkbox" aria-checked="false" tabindex="0"><i></i></span></td><td>配件业务</td><td>周敏</td><td class="r num">2,210.45</td><td class="r num">110.2%</td><td><span class="q-st" style="--c:#00B42A"><i></i>正常</span></td><td><span class="q-tag" style="margin-right:4px">配件</span></td><td><button type="button" class="q-sw on sm" role="switch" aria-checked="true" aria-label="订阅"></button></td><td>管理口径</td><td>2026-07-31 08:00</td><td>永洪 BI</td><td class="fxr"><button type="button" class="op">查看</button><button type="button" class="op">导出</button></td></tr> </tbody></table></div></div></div>
```

## Image 图片

展示图片，可按比例裁切，并在图片内部或外部附加描述与操作。点击图片可预览。

- Figma：[115964:125917](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115964-125917)
- 变体概况：55 个变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 比例 | 3:4、2:3、1:1.618、3:1、5:2、2:1 等 |
| 内部描述 | 底部渐变遮罩，白色文字 |
| 外部描述 | 标题 14 / 22，说明 12 / 20 color-text-3 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| image | 比例 | 3:4 / 2:3 / 1:1.618 / 3:1 / 5:2 / 2:1 / 16:9 / 1.618:1 / 16:10 / 3:2 / 4:3 / 1:1 / 自定义 |
| image | 额外内容 | true / false |
| image | ↳位置 | 内部 / 无 / 外部 |
| .image-footer | 位置 | 内部 / 外部 |
| .image-footer | 描述 | true / false |
| .image-footer | 额外操作 | true / false |

### 实例：比例

示例用渐变色代替图片

```html
<div class="q-row"><div class="q-img" style="--w:120px"><div class="q-media" style="--ar:1/1;cursor:zoom-in" data-pv="1:1">1:1</div></div><div class="q-img" style="--w:120px"><div class="q-media" style="--ar:3/4;cursor:zoom-in" data-pv="3:4">3:4</div></div><div class="q-img" style="--w:120px"><div class="q-media" style="--ar:2/3;cursor:zoom-in" data-pv="2:3">2:3</div></div><div class="q-img" style="--w:200px"><div class="q-media" style="--ar:16/9;cursor:zoom-in" data-pv="16:9">16:9</div></div><div class="q-img" style="--w:240px"><div class="q-media" style="--ar:3/1;cursor:zoom-in" data-pv="3:1">3:1</div></div><div class="q-img" style="--w:200px"><div class="q-media" style="--ar:2/1;cursor:zoom-in" data-pv="2:1">2:1</div></div></div>
```

### 实例：描述位置

```html
<div class="q-row"><div class="q-img" style="--w:220px"><div class="q-media" style="--ar:4/3;cursor:zoom-in" data-pv="4:3">4:3<div class="in"><span>内部描述</span><svg data-icon="eye" class="i"/></div></div></div><div class="q-img" style="--w:220px"><div class="q-media" style="--ar:4/3;cursor:zoom-in" data-pv="4:3">4:3</div><div class="out"><span>外部描述<small>2026-07-31 上传</small></span><svg data-icon="more" class="i"/></div></div></div>
```

## List 列表

纵向排列的一组内容。基础列表只放文字；高级列表可放头像、描述和操作项，并支持加载更多。

- Figma：[115965:125918](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125918)
- 变体概况：60 个变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 列表项 | 内边距 13px 20px，14 / 22 color-text-1 |
| 分隔线 | color-border-2 #E5E6EB |
| 操作项 | 图标 + 文字，之间用 12px 高的垂直分割线隔开 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| list | 尺寸 | 中 / 大 / 小 |
| list | 基础列表 | false / true |
| list | ↳操作项 | 无 / 图标 / 文本 |
| list | 加载更多 | true / false |
| list-item/advanced | 操作项 | false / true |
| list-item/advanced | ↳类型 | 无 / 图标 / 文本 |

### 实例：基础列表

```html
<div class="q-ls" style="width:280px"><div class="q-li">海信集团</div><div class="q-li">海信视像</div><div class="q-li">海信家电</div></div>
```

### 实例：高级列表

点“删除”移除一行，点“加载更多”追加

```html
<div class="q-ls" id="ls1"><div class="q-li"><span class="q-av" style="--s:40px;--fs:14px;--is:20px;background:#00AAA6" title="李">李</span><div class="m">空气事业部经营月报<small>更新于 2026-07-31 · 128 人订阅</small></div><div class="acts"><button type="button"><svg data-icon="edit" class="i"/>编辑</button><i></i><button type="button" data-del=""><svg data-icon="delete" class="i"/>删除</button></div></div><div class="q-li"><span class="q-av" style="--s:40px;--fs:14px;--is:20px;background:#3491FA" title="王">王</span><div class="m">财务指标周报<small>更新于 2026-07-30 · 64 人订阅</small></div><div class="acts"><button type="button"><svg data-icon="edit" class="i"/>编辑</button><i></i><button type="button" data-del=""><svg data-icon="delete" class="i"/>删除</button></div></div><div class="q-li"><span class="q-av" style="--s:40px;--fs:14px;--is:20px;background:#FF7D00" title="张">张</span><div class="m">供应链库存日报<small>更新于 2026-07-29 · 32 人订阅</small></div><div class="acts"><button type="button"><svg data-icon="edit" class="i"/>编辑</button><i></i><button type="button" data-del=""><svg data-icon="delete" class="i"/>删除</button></div></div><button type="button" class="q-more" data-more="">加载更多</button></div>
```

## Popover 气泡卡片

鼠标悬停或聚焦时弹出的卡片，可放标题和较多内容。共 12 个弹出位置。

- Figma：[115965:125919](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125919)
- 变体概况：12 个位置

### 样式参数

| 参数 | 值 |
| --- | --- |
| 卡片 | 宽 200px，内边距 12px 16px，圆角 8px，白底投影 |
| 标题 | 16 / 24 Semibold color-text-1，与内容间距 4px |
| 箭头 | 6px，跟随弹出位置 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| popover | 位置 | 上左 / 左上 / 右上 / 左 / 右 / 左下 / 右下 / 下左 / 上 / 下 / 上右 / 下右 |

### 实例：弹出位置

把鼠标移到按钮上

```html
<div class="q-pvg"><span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="上左">上左</button><span class="tp t pv" style="left:0;transform:none"><b>标题</b>气泡卡片内容，位置：上左</span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="上">上</button><span class="tp t pv" style=""><b>标题</b>气泡卡片内容，位置：上</span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="上右">上右</button><span class="tp t pv" style="left:auto;right:0;transform:none"><b>标题</b>气泡卡片内容，位置：上右</span></span><span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="左上">左上</button><span class="tp lt pv" style="top:0;transform:none"><b>标题</b>气泡卡片内容，位置：左上</span></span><span></span><span></span><span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="右上">右上</button><span class="tp rt pv" style="top:0;transform:none"><b>标题</b>气泡卡片内容，位置：右上</span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="左">左</button><span class="tp lt pv" style=""><b>标题</b>气泡卡片内容，位置：左</span></span><span></span><span></span><span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="右">右</button><span class="tp rt pv" style=""><b>标题</b>气泡卡片内容，位置：右</span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="左下">左下</button><span class="tp lt pv" style="top:auto;bottom:0;transform:none"><b>标题</b>气泡卡片内容，位置：左下</span></span><span></span><span></span><span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="右下">右下</button><span class="tp rt pv" style="top:auto;bottom:0;transform:none"><b>标题</b>气泡卡片内容，位置：右下</span></span><span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="下左">下左</button><span class="tp b pv" style="left:0;transform:none"><b>标题</b>气泡卡片内容，位置：下左</span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="下">下</button><span class="tp b pv" style=""><b>标题</b>气泡卡片内容，位置：下</span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="下右">下右</button><span class="tp b pv" style="left:auto;right:0;transform:none"><b>标题</b>气泡卡片内容，位置：下右</span></span><span></span></div>
```

## Statistic 数值显示

突出展示一个数值，可配标题、单位、趋势箭头和倒计时。

- Figma：[115965:125920](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125920)
- 变体概况：数字 / 趋势 / 比率 / 计时

### 样式参数

| 参数 | 值 |
| --- | --- |
| 标题 | 14 / 22 color-text-2，与数值间距 8px |
| 数值 | 24 / 32 Semibold color-text-1 |
| 趋势图标 | 14px，arrow-rise / arrow-fall，位于数值后 |
| 精度 | 0、1、2 位小数，可开关千位分隔符 |

> 说明：Figma 中趋势箭头没有单独设置颜色；在报表中表达涨跌时，按颜色页的涨跌语义色上色。

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| statistic | 标题 | true / false |
| statistic | 数值样式 | 数字 / 趋势 / 比率 / 计时 |
| statistic | 按钮 | false / true |
| components/trend | 增长 | false / true |
| components/trend | 下降 | true / false |
| components/trend | 千位分隔符 | false / true |
| components/trend | 数字精度 | 0 / 1 / 2 |

### 实例：数值

```html
<div class="q-vert"><div class="q-row"><span class="q-lab">精度</span><span class="q-cap s" id="stp"><button type="button" class="" data-stp="0">0 位</button><i></i><button type="button" class="" data-stp="1">1 位</button><i></i><button type="button" class="on" data-stp="2">2 位</button></span><span class="q-lab">千位分隔</span><button type="button" data-sep="" class="q-sw on sm" role="switch" aria-checked="true" aria-label="千位分隔"></button></div><div id="st1"><div class="q-row"><div class="q-stat"><span class="t">主营业务收入（万元）</span><span class="v">192,393.00</span></div><div class="q-stat"><span class="t">较上月</span><span class="v">1,293.50<svg data-icon="arrow-rise" class="i"/></span></div><div class="q-stat"><span class="t">完成率</span><span class="v">98.6<small>%</small></span></div></div></div></div>
```

### 实例：倒计时

时 / 分 / 秒，每秒刷新

```html
<div class="q-stat"><span class="t">距离月度结账</span><span class="v num" id="cd1">512:31:37</span></div>
```

## Table 表格

以行列展示明细数据，支持选择、排序、分页，单元格可放状态、标签、开关和操作。

- Figma：[115965:125921](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125921)
- 变体概况：561 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 表头 | 底色 color-fill-2，左内边距 16px，下边框 color-border-2 |
| 行高 | 大 40、中 36、小 32、迷你 24px |
| 单元格 | 左右内边距 16px，14 / 22 color-text-1 |
| 分页项 | 32×32px，悬停底色 color-fill-2，数字 14 / 22 Semibold |

> 说明：分页“选中”状态在已读取的变体里只有禁用样式，这里用 primary-1 底色和 primary-6 文字表示当前页。

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| table | 尺寸 | 大 / 中 / 小 / 迷你 |
| table | 边框 | false / true |
| table-cell/header | 尺寸 | 大 / 中 / 小 / 迷你 |
| table-cell/header | 筛选 | false / true |
| table-cell/header | 搜索 | false / true |
| table-column/text | 尺寸 | 大 / 中 / 小 / 迷你 |
| table-column/text | 对齐 | 左 / 右 / 中 |
| table-column/text | 固定 | false / true |

### 实例：表格

表头复选框可全选；点“收入”旁的箭头排序

```html
<div class="q-vert" style="width:100%"><div class="q-row"><span class="q-lab">尺寸</span><span class="q-cap s" id="tbsz"><button type="button" class="" data-tsz="l">大</button><i></i><button type="button" class="on" data-tsz="">中</button><i></i><button type="button" class="" data-tsz="s">小</button><i></i><button type="button" class="" data-tsz="xs">迷你</button></span><span class="q-lab">边框</span><button type="button" data-tbd="" class="q-sw sm" role="switch" aria-checked="false" aria-label="边框"></button></div><div id="tb1" style="width:100%"><div class="q-tbw"><table class="q-tb "><thead><tr><th class="w fx"><span class="q-cb half" data-all="" role="checkbox" aria-checked="false" tabindex="0"><i></i></span></th><th>产品线</th><th>负责人</th><th class="r">收入（万元）<span class="srt" data-sort="" title="排序"><svg data-icon="caret-up" class="i"/><svg data-icon="caret-down" class="i"/></span></th><th class="r">完成率</th><th>状态</th><th>标签</th><th>订阅</th><th class="">操作</th></tr></thead><tbody> <tr><td class="w fx"><span class="q-cb" data-v="0" role="checkbox" aria-checked="false" tabindex="0"><i></i></span></td><td>内销家空</td><td>李明</td><td class="r num">23,323.32</td><td class="r num">98.6%</td><td><span class="q-st" style="--c:#00B42A"><i></i>正常</span></td><td><span class="q-tag" style="margin-right:4px">家用</span></td><td><button type="button" class="q-sw on sm" role="switch" aria-checked="true" aria-label="订阅"></button></td><td class=""><button type="button" class="op">查看</button><button type="button" class="op">导出</button></td></tr><tr><td class="w fx"><span class="q-cb on" data-v="1" role="checkbox" aria-checked="true" tabindex="0"><i></i></span></td><td>内销商空</td><td>王芳</td><td class="r num">12,086.15</td><td class="r num">87.2%</td><td><span class="q-st" style="--c:#FF7D00"><i></i>预警</span></td><td><span class="q-tag" style="margin-right:4px">商用</span></td><td><button type="button" class="q-sw on sm" role="switch" aria-checked="true" aria-label="订阅"></button></td><td class=""><button type="button" class="op">查看</button><button type="button" class="op">导出</button></td></tr><tr><td class="w fx"><span class="q-cb" data-v="2" role="checkbox" aria-checked="false" tabindex="0"><i></i></span></td><td>出口整体</td><td>张伟</td><td class="r num">18,540.60</td><td class="r num">104.5%</td><td><span class="q-st" style="--c:#00B42A"><i></i>正常</span></td><td><span class="q-tag" style="margin-right:4px">出口</span><span class="q-tag" style="margin-right:4px">重点</span></td><td><button type="button" class="q-sw sm" role="switch" aria-checked="false" aria-label="订阅"></button></td><td class=""><button type="button" class="op">查看</button><button type="button" class="op">导出</button></td></tr><tr><td class="w fx"><span class="q-cb" data-v="3" role="checkbox" aria-checked="false" tabindex="0"><i></i></span></td><td>家空分公司</td><td>赵丽</td><td class="r num">9,402.88</td><td class="r num">92.4%</td><td><span class="q-st" style="--c:#00B42A"><i></i>正常</span></td><td><span class="q-tag" style="margin-right:4px">家用</span></td><td><button type="button" class="q-sw on sm" role="switch" aria-checked="true" aria-label="订阅"></button></td><td class=""><button type="button" class="op">查看</button><button type="button" class="op">导出</button></td></tr> </tbody></table></div><div class="q-pg"><span>共 6 条，已选 1 条</span><button type="button" data-pg="0" disabled="" aria-label="上一页"><svg data-icon="left" class="i"/></button><button type="button" data-pg="1" class="on">1</button><button type="button" data-pg="2" class="">2</button><button type="button" data-pg="2" aria-label="下一页"><svg data-icon="right" class="i"/></button></div></div></div>
```

## Tag 标签

给内容打上分类或状态的小标签。11 种颜色，可填充、带边框、可删除，也可以动态新增。

- Figma：[115965:125923](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125923)
- 变体概况：139 个变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 尺寸 | 大 32、中 24、小 20px；左右内边距 8px，图标间距 4px |
| 文字 | 中、小 12 / 20；大 14 / 22 |
| 圆角 | 4px |
| 默认颜色 | color-fill-2 #F2F3F5 color-text-1 #1D2129 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| tag | 尺寸 | 中 / 大 / 小 |
| tag | 颜色 | 默认 / 浪漫红 / 仙野绿 / 碧涛青 / 活力橙 / 晚秋红 / 黄昏 / 青春紫 / 品红 / 主题色 / 海蔚蓝 |
| tag | 填充 | true / false |
| tag | 边框 | false / true |
| tag | 动态删减 | false / true |

### 实例：颜色

切换外观查看三种组合

```html
<div class="q-vert"><div class="q-row"><span class="q-lab">外观</span><span class="q-cap s"><button type="button" class="on">填充</button><i></i><button type="button" class="">描边</button><i></i><button type="button" class="">填充 + 描边</button></span></div><div class="q-row" id="tgc"><span class="q-tag" style="--tb:#F2F3F5;--tt:#1D2129;--tbd:#E5E6EB">默认</span><span class="q-tag" style="--tb:#E8FFFB;--tt:#00AAA6;--tbd:#00AAA655">主题色</span><span class="q-tag" style="--tb:#FFECE8;--tt:#F53F3F;--tbd:#F53F3F55">浪漫红</span><span class="q-tag" style="--tb:#FFF3E8;--tt:#F77234;--tbd:#F7723455">晚秋红</span><span class="q-tag" style="--tb:#FFF7E8;--tt:#FF7D00;--tbd:#FF7D0055">活力橙</span><span class="q-tag" style="--tb:#FFFCE8;--tt:#F7BA1E;--tbd:#F7BA1E55">黄昏</span><span class="q-tag" style="--tb:#E8FFEA;--tt:#009A29;--tbd:#009A2955">仙野绿</span><span class="q-tag" style="--tb:#E8FFFB;--tt:#0FC6C2;--tbd:#0FC6C255">碧涛青</span><span class="q-tag" style="--tb:#E8F3FF;--tt:#165DFF;--tbd:#165DFF55">海蔚蓝</span><span class="q-tag" style="--tb:#F5E8FF;--tt:#722ED1;--tbd:#722ED155">青春紫</span><span class="q-tag" style="--tb:#FFE8F1;--tt:#F5319D;--tbd:#F5319D55">品红</span></div></div>
```

### 实例：尺寸

```html
<div class="q-row"><span class="q-tag l" style="--tb:#F2F3F5;--tt:#1D2129;--tbd:#E5E6EB">大 32</span><span class="q-tag" style="--tb:#F2F3F5;--tt:#1D2129;--tbd:#E5E6EB">中 24</span><span class="q-tag s" style="--tb:#F2F3F5;--tt:#1D2129;--tbd:#E5E6EB">小 20</span></div>
```

### 实例：可删除与新增

点 × 删除，点“新标签”后输入并回车

```html
<div class="q-row" id="tgd"><span class="q-tag" style="--tb:#E8FFFB;--tt:#00AAA6;--tbd:#00AAA655">家用<button type="button" class="x" aria-label="删除"><svg data-icon="close" class="i"/></button></span><span class="q-tag" style="--tb:#E8FFFB;--tt:#00AAA6;--tbd:#00AAA655">商用<button type="button" class="x" aria-label="删除"><svg data-icon="close" class="i"/></button></span><span class="q-tag" style="--tb:#E8FFFB;--tt:#00AAA6;--tbd:#00AAA655">出口<button type="button" class="x" aria-label="删除"><svg data-icon="close" class="i"/></button></span><span class="q-tag add" data-add=""><svg data-icon="plus" class="i"/>新标签</span></div>
```

## Tabs 标签页

在同一区域切换多组内容。线条标签页用于页面级切换，胶囊、圆角和文字标签页用于模块内切换。

- Figma：[115965:125922](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125922)
- 变体概况：639 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 线条标签 | 上下内边距 9px（大 11px），标签间距 32px，容器左右 16px |
| 选中 | primary-6 #00AAA6 |
| 未选中 | color-text-2 #4E5969 |
| 胶囊 | 容器 color-fill-2，内边距 3px；标签内边距 2px 12px，圆角 4px |
| 圆角标签 | 内边距 5px 16px，圆角 100px，选中底色 color-fill-2，间距 12px |
| 文字标签 | 左右 8px，2px 宽 12px 高的分隔线 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| tabs-line | 布局 | 水平 / 垂直 |
| tabs-line | 滚动 | false / true |
| tabs-line | 位置 | 上&下 / 左 / 右 |
| tabs-capsule | 尺寸 | 大 / 中 / 小 / 迷你 |
| tabs-capsule | 数量 | 4 / 5 / 6 / 7 / 8 / 9 / 10 / 3 / 2 |
| tabs-rounded | 数量 | 3 / 2 / 4 / 5 / 6 / 7 / 8 / 9 / 10 |
| tabs-text | 数量 | 3 / 2 / 4 / 5 / 6 / 7 / 8 / 9 / 10 |
| tabs-card-gutter | 位置 | 上 / 左 / 右 / 下 |
| tabs-card-gutter | 动态删减 | false / true |

### 实例：线条标签页

选中项 primary-6 Semibold，下划线 2px

```html
<div data-tabs="" style="width:100%"><div class="q-tl"><button type="button" class="on">经营总览</button><button type="button" class="">收入</button><button type="button" class="">利润</button><button type="button" class="">费用</button></div><div class="q-tp">这里是「经营总览」的内容区域。</div></div>
```

### 实例：胶囊标签页

容器内边距 3px，选中项白底

```html
<div class="q-vert"><div class="q-row"><span class="q-lab">大</span><span class="q-cap l"><button type="button" class="on">当月</button><i></i><button type="button" class="">累计</button><i></i><button type="button" class="">同比</button><i></i><button type="button" class="">环比</button></span></div><div class="q-row"><span class="q-lab">中</span><span class="q-cap"><button type="button" class="on">当月</button><i></i><button type="button" class="">累计</button><i></i><button type="button" class="">同比</button><i></i><button type="button" class="">环比</button></span></div><div class="q-row"><span class="q-lab">小</span><span class="q-cap s"><button type="button" class="on">当月</button><i></i><button type="button" class="">累计</button><i></i><button type="button" class="">同比</button><i></i><button type="button" class="">环比</button></span></div><div class="q-row"><span class="q-lab">迷你</span><span class="q-cap xs"><button type="button" class="on">当月</button><i></i><button type="button" class="">累计</button><i></i><button type="button" class="">同比</button><i></i><button type="button" class="">环比</button></span></div></div>
```

### 实例：圆角与文字标签页

```html
<div class="q-vert"><div class="q-row"><span class="q-lab">圆角</span><span class="q-trd"><button type="button" class="on">全部</button><button type="button" class="">进行中</button><button type="button" class="">已完成</button></span></div><div class="q-row"><span class="q-lab">文字</span><span class="q-ttx"><button type="button" class="on">图表</button><i></i><button type="button" class="">表格</button><i></i><button type="button" class="">明细</button></span></div></div>
```

## Timeline 时间轴

按时间顺序展示事件。分纵向与横向，节点可以是圆点或图标。

- Figma：[115965:125924](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125924)
- 变体概况：45 个变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 节点 | 16×16px 区域内放 badge/dot 圆点 |
| 节点颜色 | primary-6 #00AAA6 |
| 轴线 | 1px color-border-2 #E5E6EB |
| 标题 / 时间 | 14 / 22 color-text-1；12 / 20 color-text-3 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| timeline-vertical/dot | 类型 | 点 / 图标 |
| timeline-vertical/dot | 轴线↑ | true / false |
| timeline-vertical/dot | 轴线↓ | true / false |
| timeline-horizontal/dot | 类型 | 点 / 图标 |
| timeline-horizontal/dot | 轴线← | true / false |
| timeline-horizontal/dot | 轴线→ | true / false |

### 实例：纵向

第三个节点为图标节点

```html
<div class="q-vert"><div class="q-row"><span class="q-lab">排序</span><span class="q-cap s"><button type="button" class="on">正序</button><i></i><button type="button" class="">倒序</button></span></div><div id="tm1"><div class="q-tml"><div class="q-ti" style="--c:#00AAA6"><i></i><div><b>方案评审</b><small>2026-07-01</small></div></div><div class="q-ti" style="--c:#00AAA6"><i></i><div><b>数据接入</b><small>2026-07-08</small></div></div><div class="q-ti" style="--c:#165DFF"><i class="ic"><svg data-icon="clock-circle" class="i"/></i><div><b>开发测试</b><small>2026-07-20</small></div></div><div class="q-ti" style="--c:#C9CDD4"><i></i><div><b>报表上线</b><small>2026-07-31</small></div></div></div></div></div>
```

### 实例：横向

```html
<div class="q-tmh"><div style="--c:#00AAA6"><i></i><b style="display:block;font:400 14px/22px var(--sans);color:#1D2129">方案评审</b><small style="font-size:12px;color:#86909C">2026-07-01</small></div><div style="--c:#00AAA6"><i></i><b style="display:block;font:400 14px/22px var(--sans);color:#1D2129">数据接入</b><small style="font-size:12px;color:#86909C">2026-07-08</small></div><div style="--c:#165DFF"><i></i><b style="display:block;font:400 14px/22px var(--sans);color:#1D2129">开发测试</b><small style="font-size:12px;color:#86909C">2026-07-20</small></div><div style="--c:#C9CDD4"><i></i><b style="display:block;font:400 14px/22px var(--sans);color:#1D2129">报表上线</b><small style="font-size:12px;color:#86909C">2026-07-31</small></div></div>
```

## Tooltip 文字气泡

鼠标悬停时出现的简短文字说明。深色底，可选迷你尺寸。

- Figma：[115965:125925](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125925)
- 变体概况：12 个位置，含迷你

### 样式参数

| 参数 | 值 |
| --- | --- |
| 底色 | color-tooltip-bg：#1D2129，90% 不透明 |
| 内边距 | 8px 12px；迷你 2px 8px |
| 文字 | 白色 14 / 22；迷你 12 / 20 |
| 圆角 / 箭头 | 2px / 10×4px |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| tooltip | 位置 | 上↑ / 下↓ / 下右↘ / 下左↙ / 上左↖︎ / 左← / 右→ / 上右↗︎ |
| tooltip | 迷你 | false / true |

### 实例：弹出位置

把鼠标移到按钮上

```html
<div class="q-pvg"><span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="上左">上左</button><span class="tp t" style="left:0;transform:none">上左</span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="上">上</button><span class="tp t" style="">上</span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="上右">上右</button><span class="tp t" style="left:auto;right:0;transform:none">上右</span></span><span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="左上">左上</button><span class="tp lt" style="top:0;transform:none">左上</span></span><span></span><span></span><span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="右上">右上</button><span class="tp rt" style="top:0;transform:none">右上</span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="左">左</button><span class="tp lt" style="">左</span></span><span></span><span></span><span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="右">右</button><span class="tp rt" style="">右</span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="左下">左下</button><span class="tp lt" style="top:auto;bottom:0;transform:none">左下</span></span><span></span><span></span><span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="右下">右下</button><span class="tp rt" style="top:auto;bottom:0;transform:none">右下</span></span><span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="下左">下左</button><span class="tp b" style="left:0;transform:none">下左</span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="下">下</button><span class="tp b" style="">下</span></span><span class="q-tip"><button type="button" class="pb live" style="width:72px;padding:0;--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="下右">下右</button><span class="tp b" style="left:auto;right:0;transform:none">下右</span></span><span></span></div>
```

### 实例：用在文字和图标上

```html
<div class="q-row"><span class="q-tip" tabindex="0" style="font-size:14px;color:#1D2129">核心利润<svg data-icon="question-circle" class="i"/><span class="tp">不含投资收益的经营利润</span></span><span class="q-tip" tabindex="0" style="font-size:14px;color:#00AAA6">迷你气泡<span class="tp mini">12 / 20 迷你尺寸</span></span></div>
```

## Tour 漫游式引导

分步骤高亮界面元素，引导用户了解新功能。

- Figma：[157835:2752](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=157835-2752)
- 变体概况：步骤卡片 + 遮罩

### 样式参数

| 参数 | 值 |
| --- | --- |
| 卡片 | 宽 260px，内边距 16px，圆角 8px，shadow-3 |
| 标题 | 16 / 24 Semibold |
| 遮罩 | color-mask-bg：#1D2129 45%（示例） |
| 操作 | 上一步 / 下一步，最后一步为“完成” |

### 实例：引导

点“开始引导”

```html
<div class="q-tour-wrap" style="width:100%"><div class="q-tour" id="tour1"><div class="tbar"><span class="tgt" data-step="0"><button type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="新建报表"><svg data-icon="plus" class="i"/>新建报表</button></span><span class="tgt" data-step="1"><span class="q-wrap" data-sel=""><span class="q-in q-sel" style="--w:160px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v">2026-07</span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"></div></span></span><span class="tgt" data-step="2" style="margin-left:auto"><button type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="导出">导出</button></span></div><div style="height:140px;margin-top:16px;border-radius:8px;background:#fff;display:grid;place-items:center;color:#86909C;font-size:13px">报表内容区域</div><div class="cardw" hidden=""></div></div></div><div><button data-tour="0" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="开始引导">开始引导</button></div>
```

## Tree 树

展示层级结构，节点可展开收起、选中或勾选。勾选父节点时子节点同步，部分勾选显示半选。

- Figma：[115965:125926](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125926)
- 变体概况：897 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 节点高度 | 32px（上下内边距 4px），悬停底色 color-fill-2，圆角 2px |
| 选中文字 | primary-7 #009093 |
| 展开图标 | 24×24px 区域，图标与文字间距 4px |
| 缩进 | 每级 24px |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| item/final-level | 尺寸 | 中 / 大 / 小 / 迷你 |
| item/final-level | 悬停 | false / true |
| item/final-level | 选中 | false / true |
| item/final-level | 禁用 | false / true |
| item/final-level | 复选 | false / true |
| components/tree-switcher | 类型 | 按钮 / V型 / 角标 |
| components/tree-switcher | 展开 | false / true |

### 实例：基础树

点三角展开，点文字选中

```html
<div class="q-tree" id="tr1"><div class="q-tn open" style="padding-left:0px" data-t="空气事业部"><span class="swt"><svg data-icon="caret-right" class="i"/></span><span class="t">空气事业部</span></div><div class="q-tkid open"><div class="q-tn open" style="padding-left:24px" data-t="家用空调"><span class="swt"><svg data-icon="caret-right" class="i"/></span><span class="t">家用空调</span></div><div class="q-tkid open"><div class="q-tn" style="padding-left:48px" data-t="挂机"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="t">挂机</span></div><div class="q-tn" style="padding-left:48px" data-t="柜机"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="t">柜机</span></div><div class="q-tn d" style="padding-left:48px" data-t="新风机"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="t">新风机</span></div></div><div class="q-tn" style="padding-left:24px" data-t="商用空调"><span class="swt"><svg data-icon="caret-right" class="i"/></span><span class="t">商用空调</span></div><div class="q-tkid"><div class="q-tn" style="padding-left:48px" data-t="多联机"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="t">多联机</span></div><div class="q-tn" style="padding-left:48px" data-t="冷水机组"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="t">冷水机组</span></div></div></div><div class="q-tn" style="padding-left:0px" data-t="冰箱事业部"><span class="swt"><svg data-icon="caret-right" class="i"/></span><span class="t">冰箱事业部</span></div><div class="q-tkid"><div class="q-tn" style="padding-left:24px" data-t="冰箱"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="t">冰箱</span></div><div class="q-tn" style="padding-left:24px" data-t="冷柜"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="t">冷柜</span></div></div><div class="q-tn" style="padding-left:0px" data-t="视像事业部"><span class="swt"><svg data-icon="caret-right" class="i"/></span><span class="t">视像事业部</span></div><div class="q-tkid"><div class="q-tn" style="padding-left:24px" data-t="电视"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="t">电视</span></div><div class="q-tn" style="padding-left:24px" data-t="激光显示"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="t">激光显示</span></div></div></div><span class="q-out" id="tr1o">选中：<b>无</b></span>
```

### 实例：可勾选

“新风机”为禁用节点

```html
<div class="q-tree" data-check=""><div class="q-tn open" style="padding-left:0px" data-t="空气事业部"><span class="swt"><svg data-icon="caret-right" class="i"/></span><span class="q-cb"><i></i></span><span class="t">空气事业部</span></div><div class="q-tkid open"><div class="q-tn open" style="padding-left:24px" data-t="家用空调"><span class="swt"><svg data-icon="caret-right" class="i"/></span><span class="q-cb"><i></i></span><span class="t">家用空调</span></div><div class="q-tkid open"><div class="q-tn" style="padding-left:48px" data-t="挂机"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="q-cb"><i></i></span><span class="t">挂机</span></div><div class="q-tn" style="padding-left:48px" data-t="柜机"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="q-cb"><i></i></span><span class="t">柜机</span></div><div class="q-tn d" style="padding-left:48px" data-t="新风机"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="q-cb d"><i></i></span><span class="t">新风机</span></div></div><div class="q-tn" style="padding-left:24px" data-t="商用空调"><span class="swt"><svg data-icon="caret-right" class="i"/></span><span class="q-cb"><i></i></span><span class="t">商用空调</span></div><div class="q-tkid"><div class="q-tn" style="padding-left:48px" data-t="多联机"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="q-cb"><i></i></span><span class="t">多联机</span></div><div class="q-tn" style="padding-left:48px" data-t="冷水机组"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="q-cb"><i></i></span><span class="t">冷水机组</span></div></div></div><div class="q-tn" style="padding-left:0px" data-t="冰箱事业部"><span class="swt"><svg data-icon="caret-right" class="i"/></span><span class="q-cb"><i></i></span><span class="t">冰箱事业部</span></div><div class="q-tkid"><div class="q-tn" style="padding-left:24px" data-t="冰箱"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="q-cb"><i></i></span><span class="t">冰箱</span></div><div class="q-tn" style="padding-left:24px" data-t="冷柜"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="q-cb"><i></i></span><span class="t">冷柜</span></div></div><div class="q-tn" style="padding-left:0px" data-t="视像事业部"><span class="swt"><svg data-icon="caret-right" class="i"/></span><span class="q-cb"><i></i></span><span class="t">视像事业部</span></div><div class="q-tkid"><div class="q-tn" style="padding-left:24px" data-t="电视"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="q-cb"><i></i></span><span class="t">电视</span></div><div class="q-tn" style="padding-left:24px" data-t="激光显示"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="q-cb"><i></i></span><span class="t">激光显示</span></div></div></div>
```

