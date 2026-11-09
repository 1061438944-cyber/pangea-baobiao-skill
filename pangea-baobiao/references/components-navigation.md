# 导航组件

每个组件包含：用途、Figma 节点、样式参数（读自 Figma，个别标注为假设）、Figma 变体属性、静态 HTML 实例。

HTML 实例的用法：
- 样式来自 `assets/pangea-components.css`，类名统一 `q-` 前缀；按钮是 `.pb`，颜色和尺寸写在行内 CSS 变量里。
- `<svg data-icon="名称" class="i"/>` 是图标占位，替换成 `assets/icons/名称.svg` 的内容（单色图标用 `currentColor`）。
- 实例里的 `data-*` 属性是站点交互用的钩子，交互逻辑需要自己实现；示例数据只用于演示。

## Anchor 锚点

固定在页面一侧的目录，点击跳到对应内容，滚动时自动高亮当前位置。

- Figma：[115965:125962](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125962)
- 变体概况：4 级缩进，有无轴线

### 样式参数

| 参数 | 值 |
| --- | --- |
| 链接 | 14 / 22 color-text-2，链接间距 8px，每级缩进 16px |
| 当前项 | 14 / 22 Semibold color-text-1 |
| 轴线 | 2px 宽 color-border-2，当前项指示条 primary-6 |
| 轴线与链接间距 | 12px |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| anchor | 轴线 | true / false |
| .anchor/link | 层级 | 1 / 2 / 3 / 4 |
| .anchor/link | 选中 | false / true |
| .anchor/link | 轴线 | true / false |

### 实例：锚点

滚动左侧内容或点击右侧目录

```html
<div class="q-row" style="align-items:flex-start;width:100%;flex-wrap:nowrap"><div class="q-ancv" id="anv" style="flex:1"><h4 id="anc-0">概述</h4><p>这里是“概述”的说明内容。</p><h4 id="anc-1">指标口径</h4><p>这里是“指标口径”的说明内容。</p><h4 id="anc-2">收入口径</h4><p>这里是“收入口径”的说明内容。</p><h4 id="anc-3">利润口径</h4><p>这里是“利润口径”的说明内容。</p><h4 id="anc-4">数据来源</h4><p>这里是“数据来源”的说明内容。</p><h4 id="anc-5">更新频率</h4><p>这里是“更新频率”的说明内容。</p><h4 id="anc-6">联系人</h4><p>这里是“联系人”的说明内容。</p></div><div class="q-vert"><nav class="q-anc" id="an1"><span class="tk"><i style="top:0"></i></span><div class="bd"><a data-anc="0" class="on" style="padding-left:0px">概述</a><a data-anc="1" class="" style="padding-left:0px">指标口径</a><a data-anc="2" class="" style="padding-left:16px">收入口径</a><a data-anc="3" class="" style="padding-left:16px">利润口径</a><a data-anc="4" class="" style="padding-left:0px">数据来源</a><a data-anc="5" class="" style="padding-left:16px">更新频率</a><a data-anc="6" class="" style="padding-left:0px">联系人</a></div></nav><div class="q-row"><span class="q-lab">轴线</span><button type="button" data-anl="" class="q-sw on sm" role="switch" aria-checked="true" aria-label="轴线"></button></div></div></div>
```

## BackTop 返回顶部

页面滚动较长时出现，点击回到顶部。

- Figma：[115965:125963](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125963)
- 变体概况：矩形 / 圆形，图标 / 文字

### 样式参数

| 参数 | 值 |
| --- | --- |
| 尺寸 | 40×40px，内边距 8px，图标 to-top 24px |
| 底色 | primary-6 #00AAA6 |
| 圆角 | 矩形 4px，圆形 100px |
| 文字 | UP，12 / 20 Semibold 白色 |
| 阴影 | shadow-BackTop：0 4px 10px rgba(0,0,0,.1) |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| backtop | 形状 | 矩形 / 圆形 |
| backtop | 内容 | 图标 / 文本 / 自定义 |

### 实例：样式

```html
<div class="q-row"><button type="button" class="q-bt" aria-label="返回顶部"><svg data-icon="to-top" class="i"/></button><button type="button" class="q-bt rd" aria-label="返回顶部"><svg data-icon="to-top" class="i"/></button><button type="button" class="q-bt">UP</button><button type="button" class="q-bt rd">UP</button></div>
```

### 实例：在滚动区域中

向下滚动后右下角出现按钮

```html
<div class="q-btbox" id="bt1"><div style="padding:16px 20px;font-size:14px;line-height:2;color:#4E5969">第 1 行：经营分析明细内容<br>第 2 行：经营分析明细内容<br>第 3 行：经营分析明细内容<br>第 4 行：经营分析明细内容<br>第 5 行：经营分析明细内容<br>第 6 行：经营分析明细内容<br>第 7 行：经营分析明细内容<br>第 8 行：经营分析明细内容<br>第 9 行：经营分析明细内容<br>第 10 行：经营分析明细内容<br>第 11 行：经营分析明细内容<br>第 12 行：经营分析明细内容<br>第 13 行：经营分析明细内容<br>第 14 行：经营分析明细内容<br>第 15 行：经营分析明细内容<br>第 16 行：经营分析明细内容<br>第 17 行：经营分析明细内容<br>第 18 行：经营分析明细内容<br>第 19 行：经营分析明细内容<br>第 20 行：经营分析明细内容<br>第 21 行：经营分析明细内容<br>第 22 行：经营分析明细内容<br>第 23 行：经营分析明细内容<br>第 24 行：经营分析明细内容</div><button type="button" class="q-bt" data-bt="" aria-label="返回顶部"><svg data-icon="to-top" class="i"/></button></div>
```

## Breadcrumb 面包屑

显示当前页面在层级中的位置，点击上级可以返回。

- Figma：[115965:125946](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125946)
- 变体概况：41 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 层级项 | 左右内边距 4px，14 / 22 color-text-2 |
| 悬停 | 底色 color-fill-2，文字 primary-6，圆角 2px |
| 当前页 | 14 / 22 Semibold color-text-1 |
| 分隔符 | 12px：oblique-line、right、circular，间距 4px |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| breadcrumb | 分隔符 | 斜杠分隔符 / 圆点分隔符 / 箭头分隔符 |
| breadcrumb | 数量 | 2 / 3 / 4 / 4+ / 1 |
| components/breadcrumb-item | 当前 | false / true |
| components/breadcrumb-item | 文字 | true / false |
| components/breadcrumb-item | 图标 | false / true |
| components/breadcrumb-item | 下拉 | false / true |
| components/breadcrumb-item | 悬停 | false / true |

### 实例：面包屑

点上级层级返回（示例中会截断路径）

```html
<div class="q-vert"><div class="q-row"><span class="q-lab">分隔符</span><span class="q-cap s"><button type="button" class="on">斜杠</button><i></i><button type="button" class="">箭头</button><i></i><button type="button" class="">圆点</button></span><button data-bcr="" type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="恢复路径">恢复路径</button></div><div id="bc1"><nav class="q-bc" aria-label="面包屑"><a class="" data-bc="0"><svg data-icon="home" class="i"/>首页</a><svg data-icon="oblique-line" class="i"/><a class="" data-bc="1">经营分析</a><svg data-icon="oblique-line" class="i"/><a class="" data-bc="2">空气事业部</a><svg data-icon="oblique-line" class="i"/><a class="cur" data-bc="3" aria-current="page">经营月报</a></nav></div></div>
```

## Dropdown 下拉菜单

把多个操作收进一个按钮的下拉菜单里。支持图标、分隔线、多级菜单、多选和禁用项。

- Figma：[115965:125956](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125956)
- 变体概况：169 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 次要触发器 | 内边距 5px 15px，color-fill-1 底，描边 color-border-3，圆角 4px，箭头 14px |
| 菜单 | dropdown-menu：白底，描边 color-border-2，圆角 8px，上下内边距 4px |
| 菜单项 | 内边距 7px 12px，悬停 color-fill-2，选中 primary-6，禁用 color-text-4 |
| 二级菜单 | 在父项右侧 4px 处展开 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| dropdown | 类型 | 文字 / 次要 / 主要 |
| dropdown | 悬停 | false / true |
| dropdown | 禁用 | true / false |
| dropdown | 尺寸 | 迷你 / 小 / 大 / 中 |
| dropdown-button | 尺寸 | 中 / 大 / 小 / 迷你 |
| dropdown-button | 禁用 | false / true |
| dropdown-button | 类型 | 主要 / 次要 / 文字 |
| dropdown-menu/menu-item | 悬停 | false / true |
| dropdown-menu/menu-item | 选中 | false / true |
| dropdown-menu/menu-item | 图标 | false / true |
| dropdown-menu/menu-item | 多级 | false / true |
| dropdown-menu/menu-item | 多选 | false / true |
| dropdown-menu/menu-item | 禁用 | false / true |

### 实例：触发器类型

“更多格式”悬停展开二级菜单

```html
<div class="q-row"><span class="q-wrap"><button type="button" class="q-ddt pri" data-dd="">主要<svg data-icon="down" class="i"/></button><div class="q-pop" role="menu" style="min-width:160px"><div class="q-mi" data-dm="导出 Excel"><svg data-icon="download" class="i"/>导出 Excel</div><div class="q-mi" data-dm="导出 PDF"><svg data-icon="file-pdf" class="i"/>导出 PDF</div><div class="q-mi" data-dm="分享链接"><svg data-icon="share-alt" class="i"/>分享链接</div><div style="height:1px;margin:4px 0;background:#E5E6EB"></div><div class="q-mi q-sub"><svg data-icon="more" class="i"/>更多格式<svg data-icon="right" class="i sub"/><div class="q-pop" style="min-width:140px"><div class="q-mi" data-dm="CSV">CSV</div><div class="q-mi" data-dm="图片 PNG">图片 PNG</div></div></div><div class="q-mi d" data-dm="打印（无权限）"><svg data-icon="printer" class="i"/>打印（无权限）</div></div></span><span class="q-wrap"><button type="button" class="q-ddt " data-dd="">次要<svg data-icon="down" class="i"/></button><div class="q-pop" role="menu" style="min-width:160px"><div class="q-mi" data-dm="导出 Excel"><svg data-icon="download" class="i"/>导出 Excel</div><div class="q-mi" data-dm="导出 PDF"><svg data-icon="file-pdf" class="i"/>导出 PDF</div><div class="q-mi" data-dm="分享链接"><svg data-icon="share-alt" class="i"/>分享链接</div><div style="height:1px;margin:4px 0;background:#E5E6EB"></div><div class="q-mi q-sub"><svg data-icon="more" class="i"/>更多格式<svg data-icon="right" class="i sub"/><div class="q-pop" style="min-width:140px"><div class="q-mi" data-dm="CSV">CSV</div><div class="q-mi" data-dm="图片 PNG">图片 PNG</div></div></div><div class="q-mi d" data-dm="打印（无权限）"><svg data-icon="printer" class="i"/>打印（无权限）</div></div></span><span class="q-wrap"><button type="button" class="q-ddt txt" data-dd="">文字<svg data-icon="down" class="i"/></button><div class="q-pop" role="menu" style="min-width:160px"><div class="q-mi" data-dm="导出 Excel"><svg data-icon="download" class="i"/>导出 Excel</div><div class="q-mi" data-dm="导出 PDF"><svg data-icon="file-pdf" class="i"/>导出 PDF</div><div class="q-mi" data-dm="分享链接"><svg data-icon="share-alt" class="i"/>分享链接</div><div style="height:1px;margin:4px 0;background:#E5E6EB"></div><div class="q-mi q-sub"><svg data-icon="more" class="i"/>更多格式<svg data-icon="right" class="i sub"/><div class="q-pop" style="min-width:140px"><div class="q-mi" data-dm="CSV">CSV</div><div class="q-mi" data-dm="图片 PNG">图片 PNG</div></div></div><div class="q-mi d" data-dm="打印（无权限）"><svg data-icon="printer" class="i"/>打印（无权限）</div></div></span></div>
```

### 实例：下拉按钮

左侧执行默认操作，右侧打开菜单

```html
<span class="q-wrap q-dbtn"><button data-dexp="" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="导出">导出</button><button data-dd="" aria-label="更多导出方式" type="button" class="pb io live" style="--h:32px;--px:8px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;"><svg data-icon="down" class="i"/></button><div class="q-pop" role="menu" style="min-width:160px"><div class="q-mi" data-dm="导出 Excel"><svg data-icon="download" class="i"/>导出 Excel</div><div class="q-mi" data-dm="导出 PDF"><svg data-icon="file-pdf" class="i"/>导出 PDF</div><div class="q-mi" data-dm="分享链接"><svg data-icon="share-alt" class="i"/>分享链接</div></div></span>
```

### 实例：多选菜单

选择后菜单不关闭

```html
<span class="q-wrap" id="dm1"><button type="button" class="q-ddt" data-dd="">显示列（<b>3</b>）<svg data-icon="down" class="i"/></button><div class="q-pop" role="menu" style="min-width:160px"><div class="q-mi" data-dm="收入" data-dmm=""><span class="q-cb on" role="checkbox" aria-checked="true" tabindex="0"><i></i></span>收入</div><div class="q-mi" data-dm="完成率" data-dmm=""><span class="q-cb on" role="checkbox" aria-checked="true" tabindex="0"><i></i></span>完成率</div><div class="q-mi" data-dm="同比" data-dmm=""><span class="q-cb on" role="checkbox" aria-checked="true" tabindex="0"><i></i></span>同比</div><div class="q-mi" data-dm="环比" data-dmm=""><span class="q-cb" role="checkbox" aria-checked="false" tabindex="0"><i></i></span>环比</div><div class="q-mi" data-dm="毛利率" data-dmm=""><span class="q-cb" role="checkbox" aria-checked="false" tabindex="0"><i></i></span>毛利率</div></div></span>
```

## Filter 筛选器

表格上方的筛选器：常用条件放在顶部，更多条件收进展开面板，已选条件以标签形式显示。

- Figma：[150592:12920](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=150592-12920)
- 变体概况：收起 / 展开

### 样式参数

| 参数 | 值 |
| --- | --- |
| 容器 | 白底，描边 color-border-2，圆角 8px（示例） |
| 顶部 | 常用条件与快捷切换，内边距 12px 16px |
| 展开面板 | 3 列表单，间距 16px 24px |
| 已选条件 | tag，默认颜色，可删除 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| filter | 筛选 | 收起 / 展开 |

### 实例：筛选器

点“筛选”展开，选择后点“查询”

```html
<div class="q-flt" id="fl1"><div class="tp"><span class="q-in" style="--w:240px"><svg data-icon="search" class="i"/><input placeholder="搜索报表名称" value=""></span><span class="q-cap s"><button type="button" class="on">全部</button><i></i><button type="button" class="">我负责的</button><i></i><button type="button" class="">我订阅的</button></span><span class="sp"></span><span id="flt" class="q-row" style="gap:8px"></span><button data-flo="" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="筛选"><svg data-icon="filter" class="i"/>筛选</button></div><div class="pn"><div><label>统计月份</label><span class="q-wrap" data-sel=""><span class="q-in q-sel" style="--w:220px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v">2026-07</span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi" data-v="2026-05">2026-05</div><div class="q-mi" data-v="2026-06">2026-06</div><div class="q-mi on" data-v="2026-07">2026-07</div></div></span></div><div><label>渠道</label><span class="q-wrap" data-sel="" data-fk="渠道"><span class="q-in q-sel" style="--w:220px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v"><span class="q-ph">全部渠道</span></span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi" data-v="线上">线上</div><div class="q-mi" data-v="线下">线下</div><div class="q-mi" data-v="海外">海外</div></div></span></div><div><label>品类</label><span class="q-wrap" data-sel="" data-multi="" data-fk="品类"><span class="q-in q-sel mul" style="--w:220px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v"><span class="q-ph">全部品类</span></span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi" data-v="家空">家空</div><div class="q-mi" data-v="商空">商空</div><div class="q-mi" data-v="冰箱">冰箱</div><div class="q-mi" data-v="洗衣机">洗衣机</div></div></span></div><div><label>区域</label><span class="q-wrap" data-sel="" data-fk="区域"><span class="q-in q-sel" style="--w:220px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v"><span class="q-ph">全部区域</span></span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi" data-v="华东">华东</div><div class="q-mi" data-v="华南">华南</div><div class="q-mi" data-v="华北">华北</div><div class="q-mi" data-v="西南">西南</div></div></span></div><div><label>负责人</label><span class="q-in"><input placeholder="输入姓名" value=""></span></div><div><label>只看预警</label><div style="padding-top:5px"><button type="button" class="q-sw" role="switch" aria-checked="false" aria-label="只看预警"></button></div></div></div><div class="pf"><button data-flr="" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="重置">重置</button><button data-flq="" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="查询">查询</button></div></div>
```

## ResizeBox 伸缩框

可以拖动边缘伸缩的容器，常用于左右或上下分栏。

- Figma：[115965:125967](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125967)
- 变体概况：水平 / 垂直伸缩杆

### 样式参数

| 参数 | 值 |
| --- | --- |
| 伸缩杆 | 6px 宽 color-fill-3 #E5E6EB |
| 手柄图标 | 12px：drag-dot / drag-dot-vertical |
| 悬停 / 拖动 | primary-2 底，primary-6 图标（示例） |
| 内边距 | 示例容器 4px |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| resize-box | 定制伸缩杆 | false / true |
| resize-trigger | 布局 | 垂直 / 水平 |
| resize-trigger | 定制伸缩杆 | false / true |

### 实例：伸缩框

拖动灰色伸缩杆

```html
<div class="q-rz" id="rz1"><div class="pa">指标目录<br><span class="q-ph" style="font-size:12px">拖动右侧伸缩杆调整宽度</span></div><div class="rh" data-rz="h"><svg data-icon="drag-dot-vertical" class="i"/></div><div class="pb2"><div class="pt">图表区域<br><span class="q-ph" style="font-size:12px">拖动下方伸缩杆调整高度</span></div><div class="rv" data-rz="v"><svg data-icon="drag-dot" class="i"/></div><div>明细表区域</div></div></div>
```

## Header 顶部导航

系统顶部导航，包含应用切换、产品名、应用页签和右侧工具（搜索、待办、账号）。

- Figma：[150639:10198](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=150639-10198)
- 变体概况：198 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 高度 | 48px，示例宽 1440px |
| 应用抽屉触发器 | 内边距 14px，图标 general 20px |
| 产品名 | 14 / 22 color-text-1，与 logo 间距 8px，左内边距 12px |
| 中间区域 | 左右内边距 32px，放应用页签 |
| 右侧工具 | 间距 12px，右内边距 20px |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| header | 状态 | 默认 |
| tools-search | 激活 | false / true |
| tools-search | 填充 | false / true |

另有布尔属性：数量超出、特殊账号标签、展开面板、消息提示、最近搜索、最近访问

### 实例：顶部导航

点搜索图标展开输入框

```html
<div class="q-hd"><button type="button" class="apps" aria-label="应用抽屉" data-hda=""><svg data-icon="general" class="i"/></button><span class="lg"><i></i>经营分析平台</span><div class="ce"><span class="q-trd"><button type="button" class="on">经营总览</button><button type="button" class="">财务</button><button type="button" class="">供应链</button></span></div><div class="rt"><label class="srch" data-hds=""><svg data-icon="search" class="i"/><input placeholder="搜索报表、指标" aria-label="搜索"></label><span class="q-wrap"><button type="button" class="ib" data-dd="" aria-label="待办"><svg data-icon="notification" class="i"/><span class="dt"></span></button><div class="q-pop" style="left:auto;right:0;min-width:240px"><div class="q-mi" data-hdt="">审批：财务月报口径调整</div><div class="q-mi" data-hdt="">提醒：7 月数据已结账</div><div class="q-mi" data-hdt="">评论：李明回复了你</div></div></span><span class="q-wrap"><span data-dd="" style="cursor:pointer"><span class="q-av" style="--s:32px;--fs:14px;--is:16px;background:#00AAA6" title="李">李</span></span><div class="q-pop" style="left:auto;right:0;min-width:160px"><div class="q-mi">个人信息</div><div class="q-mi">国际化设置</div><div class="q-mi">退出登录</div></div></span></div></div>
```

## Menu 菜单

为页面和功能提供导航。分垂直、悬浮和水平三种，垂直菜单可以收起只显示图标。

- Figma：[115965:125957](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125957)
- 变体概况：157 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 一级菜单项 | 内边距 7px 12px，图标 14px，图标与文字间距 16px，圆角 4px |
| 选中 | color-fill-2 底，primary-6 Semibold 文字 |
| 二级菜单项 | 左缩进 32px（含 12px 内边距共 50px 起），悬停 color-fill-2 |
| 菜单容器 | 宽 220px，内边距 4px 8px，项间距 4px |
| 水平菜单项 | 上下 14px，内层 4px 12px，选中下划线 3px primary-6，悬停 color-fill-3 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| menu | 类型 | 垂直 / 悬浮 / 水平 |
| menu | 数量 | 8 / 1 / 2 / 3 / 4 / 5 / 6 / 7 / 9 / 10 |
| menu | 收起 | false / true |
| vertical-item-1st/menu-item | 选中 | false / true |
| vertical-item-1st/menu-item | 悬停 | false / true |
| vertical-item-1st/menu-item | 子菜单 | false / true |
| vertical-item-1st/menu-item | ⬑展开 | false / true |
| vertical-item-1st/menu-item | ⬑数量 | 0 / 1 / 2 / 3 / 4 / 5 / 6 / 7 / 8 / 9 / 10 |
| horizontal-item/1st-level | 选中 | true / false |
| horizontal-item/1st-level | 悬停 | false / true |
| horizontal-item/1st-level | 禁用 | false / true |

### 实例：垂直菜单

点分组展开，点底部按钮收起

```html
<div style="display:flex;flex-direction:column;border:1px solid #E5E6EB;border-radius:8px;overflow:hidden"><div class="q-menu" id="mn1" role="menu"><button type="button" class="q-m1" data-mi1="" title="经营总览"><svg data-icon="dashboard" class="i"/><span>经营总览</span></button><div class="q-mg open"><button type="button" class="q-m1" data-mg="" title="财务分析"><svg data-icon="fund" class="i"/><span>财务分析</span><svg data-icon="down" class="i ar"/></button><div class="kids"><button type="button" class="q-m2" data-mi2="">收入分析</button><button type="button" class="q-m2 on" data-mi2="">利润分析</button><button type="button" class="q-m2" data-mi2="">费用分析</button><button type="button" class="q-m2 d" data-mi2="" disabled="">税务分析（无权限）</button></div></div><div class="q-mg"><button type="button" class="q-m1" data-mg="" title="供应链"><svg data-icon="storage" class="i"/><span>供应链</span><svg data-icon="down" class="i ar"/></button><div class="kids"><button type="button" class="q-m2" data-mi2="">库存周转</button><button type="button" class="q-m2" data-mi2="">交付及时率</button></div></div><button type="button" class="q-m1" data-mi1="" title="人力资源"><svg data-icon="user-group" class="i"/><span>人力资源</span></button><button type="button" class="q-m1" data-mi1="" title="系统设置"><svg data-icon="settings" class="i"/><span>系统设置</span></button></div><div class="q-mfold"><button type="button" class="ibtn" data-mfold="" aria-label="收起菜单"><svg data-icon="menu-fold" class="i"/></button></div></div>
```

### 实例：水平菜单

```html
<div class="q-hm" style="width:100%" role="menubar"><button type="button" class="on" data-hm=""><span>经营总览</span></button><button type="button" class="" data-hm=""><span>财务分析</span></button><button type="button" class="" data-hm=""><span>供应链</span></button><button type="button" class="" data-hm=""><span>人力资源</span></button><button type="button" disabled=""><span>研发（未开放）</span></button></div>
```

## MenuPlatform 工作台菜单

工作台的两级菜单：左侧是一级分类，右侧面板列出该分类下的功能。左侧可以收起。

- Figma：[150656:4702](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=150656-4702)
- 变体概况：109 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 一级菜单项 | 宽 170px，内边距 6px 8px，图标与文字间距 8px，圆角 4px |
| 激活 | 白底，primary-6 文字 |
| 子面板 | 分组标题 12 / 20 color-text-3，功能项两列 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| menu-platform | 收起 | false / true |
| menu-platform | 展开子级菜单 | false / true |
| menu-item/menu-item-primary | 悬停 | false / true |
| menu-item/menu-item-primary | 激活 | false / true |
| menu-item/menu-item-primary | 子菜单 | 无 / 展开 / 收起 |

### 实例：工作台菜单

点左侧分类切换右侧面板

```html
<div class="q-mp" id="mp1"><div class="p1"><button type="button" class="" data-mp1="经营总览" title="经营总览"><svg data-icon="dashboard" class="i"/><span>经营总览</span></button><button type="button" class="on" data-mp1="财务分析" title="财务分析"><svg data-icon="fund" class="i"/><span>财务分析</span></button><button type="button" class="" data-mp1="供应链" title="供应链"><svg data-icon="storage" class="i"/><span>供应链</span></button><button type="button" class="" data-mp1="人力资源" title="人力资源"><svg data-icon="user-group" class="i"/><span>人力资源</span></button><button type="button" class="tg2" data-mpf="" title="收起"><svg data-icon="menu-fold" class="i"/><span>收起</span></button></div><div class="p2" id="mp2"><h6>收入</h6><div class="g"><a data-mpx="">收入分析</a><a data-mpx="">收入结构</a></div><h6>利润</h6><div class="g"><a data-mpx="">利润分析</a><a data-mpx="">费用分析</a><a data-mpx="">成本分析</a></div></div></div>
```

## Pagination 分页

把长列表分成多页。支持页码省略、每页条数和跳转到指定页。

- Figma：[115965:125959](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125959)
- 变体概况：中 / 小

### 样式参数

| 参数 | 值 |
| --- | --- |
| 页码项 | 中号 32×32px，内边距 4px，14 / 22 Semibold color-text-2 |
| 悬停 | color-fill-2 #F2F3F5 |
| 禁用 | color-text-4 #C9CDD4 |
| 当前页 | primary-1 底、primary-6 文字（Figma 未读到非禁用的选中样式） |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| pagination | 尺寸 | 大 / 中 / 小 / 迷你 |
| pagination | 禁用 | false / true |
| components/pagination-item | 尺寸 | 中 / 大 / 小 / 迷你 |
| components/pagination-item | 选中 | false / true |
| components/pagination-item | 悬停 | false / true |
| components/pagination-item | 禁用 | false / true |

### 实例：分页

输入页码后回车跳转

```html
<div class="q-vert"><div class="q-row"><span class="q-lab">尺寸</span><span class="q-cap s"><button type="button" class="on">中</button><i></i><button type="button" class="">小</button></span></div><div id="pg2"><div class="q-pg" style="justify-content:flex-start;margin:0"><span>共 248 条</span><button type="button" data-pp="2" aria-label="上一页"><svg data-icon="left" class="i"/></button><button type="button" data-pp="1" class="">1</button><button type="button" data-pp="2" class="">2</button><button type="button" data-pp="3" class="on">3</button><button type="button" data-pp="4" class="">4</button><button type="button" data-pp="5" class="">5</button><span style="padding:0 6px;color:#86909C">…</span><button type="button" data-pp="25" class="">25</button><button type="button" data-pp="4" aria-label="下一页"><svg data-icon="right" class="i"/></button><span class="q-wrap" data-sel="" id="pgsz"><span class="q-in q-sel" style="--w:116px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v">10 条/页</span><svg data-icon="down" class="i ar"/></span><div class="q-pop top" role="listbox"><div class="q-mi on" data-v="10 条/页">10 条/页</div><div class="q-mi" data-v="20 条/页">20 条/页</div><div class="q-mi" data-v="50 条/页">50 条/页</div></div></span><span>前往</span><span class="q-in" style="--w:56px"><input placeholder="" value="" data-pj="" aria-label="跳转页码"></span><span>页</span></div></div></div>
```

## Steps 步骤条

引导用户按顺序完成多步流程，显示已完成、进行中和等待的步骤。

- Figma：[115965:125960](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125960)
- 变体概况：默认 / 点状 / 箭头 / 导航

### 样式参数

| 参数 | 值 |
| --- | --- |
| 步骤图标 | 28×28px 圆形，数字 16 / 24 Semibold |
| 进行中 | primary-6 #00AAA6 |
| 已完成 | primary-1 #E8FFFB |
| 等待 | color-fill-2 #F2F3F5 |
| 错误 | danger-6 #F53F3F |
| 标题 / 描述 | 16 / 24；描述 12 / 20 color-text-3，左缩进 40px |
| 连接线 | 1px color-border-2，已完成为 primary-6 |
| 点状 | 8px 圆点，进行中 10px；箭头样式高 72px |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| steps-default | 布局 | 横向 / 竖向 |
| steps-default | 数量 | 2 / 3 / 4 / 5 / 6 |
| steps-default | 小型 | false / true |
| steps-dot | 布局 | 横向 / 竖向 |
| steps-dot | 数量 | 2 / 3 / 4 / 5 / 6 |
| steps-arrow | 数量 | 3 / 4 / 5 / 6 |
| steps-arrow | 小型 | false / true |
| steps-navigation | 数量 | 2 / 3 / 4 / 5 |
| steps-navigation | 小型 | false / true |

### 实例：默认

下方按钮会同步改变本页所有步骤条

```html
<div class="q-vert" style="width:100%"><div id="sd" style="width:100%"><div class="q-stp"><div class="q-st1 done"><div class="hd"><span class="ic"><svg data-icon="check" class="i"/></span><span class="tt">填写信息</span><span class="ln"></span></div><div class="ds">选择报表模板</div></div><div class="q-st1 cur"><div class="hd"><span class="ic">2</span><span class="tt">配置数据</span><span class="ln"></span></div><div class="ds">绑定数据集与口径</div></div><div class="q-st1 "><div class="hd"><span class="ic">3</span><span class="tt">预览发布</span><span class="ln"></span></div><div class="ds">确认后发布上线</div></div></div></div><div class="q-row"><button data-stg="-1" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="上一步">上一步</button><button data-stg="1" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="下一步">下一步</button><span class="q-out" id="stc">当前第 2 步</span></div></div>
```

### 实例：竖向

```html
<div id="sv"><div class="q-stp v"><div class="q-st1 done"><div class="hd"><span class="ic"><svg data-icon="check" class="i"/></span><span class="tt">填写信息</span><span class="ln"></span></div><div class="ds">选择报表模板</div></div><div class="q-st1 cur"><div class="hd"><span class="ic">2</span><span class="tt">配置数据</span><span class="ln"></span></div><div class="ds">绑定数据集与口径</div></div><div class="q-st1 "><div class="hd"><span class="ic">3</span><span class="tt">预览发布</span><span class="ln"></span></div><div class="ds">确认后发布上线</div></div></div></div>
```

### 实例：点状

```html
<div id="sdot" style="width:100%"><div class="q-std"><div class="done"><span class="dl"><i></i></span><span class="tt">填写信息</span><small>选择报表模板</small></div><div class="cur"><span class="dl"><i></i></span><span class="tt">配置数据</span><small>绑定数据集与口径</small></div><div class=""><span class="dl"><i></i></span><span class="tt">预览发布</span><small>确认后发布上线</small></div></div></div>
```

### 实例：箭头

```html
<div id="sar" style="width:100%"><div class="q-sta"><div class="done"><b>填写信息</b><small>选择报表模板</small></div><div class="cur"><b>配置数据</b><small>绑定数据集与口径</small></div><div class=""><b>预览发布</b><small>确认后发布上线</small></div></div></div>
```

### 实例：导航

点击步骤直接跳转

```html
<div id="snv" style="width:100%"><div class="q-stn"><button type="button" class="done" data-sti="0"><span class="ic"><svg data-icon="check" class="i"/></span><span><b>填写信息</b><small>选择报表模板</small></span></button><button type="button" class=" on" data-sti="1"><span class="ic">2</span><span><b>配置数据</b><small>绑定数据集与口径</small></span></button><button type="button" class="" data-sti="2"><span class="ic">3</span><span><b>预览发布</b><small>确认后发布上线</small></span></button></div></div>
```

## TabBar 页签栏

多页签的工作区导航，记录已打开的页面，可切换、关闭和新建。

- Figma：[150639:13286](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=150639-13286)
- 变体概况：页签栏 / 面包屑模式

### 样式参数

| 参数 | 值 |
| --- | --- |
| 容器 | 高 32px，左右内边距 16px |
| 页签 | tag：内边距 2px 8px，圆角 4px，间距 4px，12 / 20 |
| 当前页签 | 白底，primary-6 文字 |
| 关闭图标 | 12px |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| tab-bar | 模式 | 页签栏 / 面包屑 |
| tab-bar | 滚动 | false / true |

### 实例：页签栏

点 × 关闭，点 + 新建

```html
<div id="tbr" style="width:100%"><div class="q-tb2" role="tablist"><span class="tbi" data-tbi="0" role="tab" aria-selected="false"><svg data-icon="home" class="i"/>工作台</span><span class="tbi on" data-tbi="1" role="tab" aria-selected="true">经营月报<button type="button" class="x" data-tbx="1" aria-label="关闭 经营月报"><svg data-icon="close" class="i"/></button></span><span class="tbi" data-tbi="2" role="tab" aria-selected="false">财务周报<button type="button" class="x" data-tbx="2" aria-label="关闭 财务周报"><svg data-icon="close" class="i"/></button></span><span class="tbi" data-tbi="3" role="tab" aria-selected="false">库存日报<button type="button" class="x" data-tbx="3" aria-label="关闭 库存日报"><svg data-icon="close" class="i"/></button></span><span class="tbi" data-tba=""><svg data-icon="plus" class="i"/></span></div></div>
```

### 实例：面包屑模式

```html
<div class="q-tb2" style="background:#fff;border:1px solid #E5E6EB"><nav class="q-bc"><a class="">首页</a><svg data-icon="oblique-line" class="i"/><a class="">经营分析</a><svg data-icon="oblique-line" class="i"/><a class="">空气事业部</a><svg data-icon="oblique-line" class="i"/><a class="cur">经营月报</a></nav></div>
```

