# 数据输入组件

每个组件包含：用途、Figma 节点、样式参数（读自 Figma，个别标注为假设）、Figma 变体属性、静态 HTML 实例。

HTML 实例的用法：
- 样式来自 `assets/pangea-components.css`，类名统一 `q-` 前缀；按钮是 `.pb`，颜色和尺寸写在行内 CSS 变量里。
- `<svg data-icon="名称" class="i"/>` 是图标占位，替换成 `assets/icons/名称.svg` 的内容（单色图标用 `currentColor`）。
- 实例里的 `data-*` 属性是站点交互用的钩子，交互逻辑需要自己实现；示例数据只用于演示。

## AutoComplete 自动补全

输入时给出联想建议，可用键盘上下选择、回车确认。

- Figma：[115965:125927](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125927)
- 变体概况：聚焦 / 未聚焦

### 样式参数

| 参数 | 值 |
| --- | --- |
| 输入框 | 同 Input 中号 |
| 候选列表 | dropdown-menu，匹配文字用 primary-6 标出 |
| 键盘 | ↑ ↓ 选择，Enter 确认，Esc 关闭 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| auto-complete | 聚焦 | false / true |

### 实例：自动补全

候选数据为示例

```html
<span class="q-wrap" id="ac1"><span class="q-in" style="--w:260px"><input placeholder="输入“海信”试试" value="" data-ac="" autocomplete="off"></span><div class="q-pop"></div></span>
```

## Cascader 级联选择

逐级选择有层级关系的数据，例如事业部、产品线、品类。

- Figma：[115965:125928](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125928)
- 变体概况：填充 / 未填充

### 样式参数

| 参数 | 值 |
| --- | --- |
| 触发器 | 同 Select |
| 面板 | 每列最小宽 132px，列之间 color-border-2 分隔 |
| 有下级的选项 | 右侧 12px 箭头 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| cascader | 填充 | false / true |
| select | 尺寸 | 中 |
| select | 填充 | false / true |
| select | 多选 | false |
| select | 悬停 | false |
| select | 聚焦 | false |
| select | 禁用 | false |
| select | 无边框模式 | false |

### 实例：级联选择

选到第三级后自动关闭

```html
<span class="q-wrap" id="cas1"><span class="q-in q-sel" style="--w:280px" data-dd="" tabindex="0"><span class="v"><span class="q-ph">请选择品类</span></span><svg data-icon="down" class="i ar"/></span><div class="q-pop q-cas"><div><div class="q-mi" data-cas="0|空气事业部">空气事业部<svg data-icon="right" class="i sub"/></div><div class="q-mi" data-cas="0|冰箱事业部">冰箱事业部<svg data-icon="right" class="i sub"/></div><div class="q-mi" data-cas="0|视像事业部">视像事业部<svg data-icon="right" class="i sub"/></div></div></div></span>
```

## Checkbox 复选框

在一组选项中选择多项，或单独切换某一项。全选框会根据子项显示半选状态。

- Figma：[115965:125929](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125929)
- 变体概况：38 个变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 方框 | 14×14px，描边 2px color-border-2，圆角 2px |
| 选中 | primary-6 #00AAA6 |
| 选中禁用 | primary-3 #79DDD1 |
| 禁用 | color-fill-2 #F2F3F5 |
| 与文字间距 | 8px，文字 14 / 22 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| checkbox | 选中 | false / true |
| checkbox | 半选 | false / true |
| checkbox | 禁用 | false / true |
| checkbox | 悬停 | false / true |
| checkbox | 标签 | true / false |
| checkbox-group | 布局 | 水平 / 垂直 |
| checkbox-group | 数量 | 1 / 2 / 4 / 5 / 6 / 7 / 8 / 9 / 10 / 3 |

### 实例：状态

点击切换，禁用项不可点

```html
<div class="q-row"><span class="q-cb" role="checkbox" aria-checked="false" tabindex="0"><i></i>未选</span><span class="q-cb on" role="checkbox" aria-checked="true" tabindex="0"><i></i>选中</span><span class="q-cb half" role="checkbox" aria-checked="false" tabindex="0"><i></i>半选</span><span class="q-cb d" role="checkbox" aria-checked="false" tabindex="-1"><i></i>禁用</span><span class="q-cb on d" role="checkbox" aria-checked="true" tabindex="-1"><i></i>选中禁用</span></div>
```

### 实例：全选

子项部分选中时，全选框为半选

```html
<div class="q-vert" data-cg=""><span class="q-cb half" data-all="" role="checkbox" aria-checked="false" tabindex="0"><i></i>全部品类</span><div class="q-row" style="padding-left:22px"><span class="q-cb on" role="checkbox" aria-checked="true" tabindex="0"><i></i>家空</span><span class="q-cb on" role="checkbox" aria-checked="true" tabindex="0"><i></i>商空</span><span class="q-cb" role="checkbox" aria-checked="false" tabindex="0"><i></i>冰箱</span><span class="q-cb" role="checkbox" aria-checked="false" tabindex="0"><i></i>洗衣机</span><span class="q-cb d" role="checkbox" aria-checked="false" tabindex="-1"><i></i>厨电（停售）</span></div></div>
```

### 实例：垂直排列

```html
<div class="q-vert" data-cg=""><span class="q-cb on" role="checkbox" aria-checked="true" tabindex="0"><i></i>只看预警指标</span><span class="q-cb" role="checkbox" aria-checked="false" tabindex="0"><i></i>显示同比</span><span class="q-cb" role="checkbox" aria-checked="false" tabindex="0"><i></i>显示环比</span></div>
```

## CodeEditor 代码编辑器

带行号的代码编辑区，用于配置脚本、公式或 SQL。分描边和填充两种外观。

- Figma：[150576:517](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=150576-517)
- 变体概况：填充 / 未填充

### 样式参数

| 参数 | 值 |
| --- | --- |
| 行号栏 | 宽 42px，底色 #EBEBEB，右侧 0.5px #9F9F9F 分隔线 |
| 编辑区 | 白底；填充外观为 color-fill-1 |
| 尺寸 | 示例 415×242px |

> 说明：代码字体与行高在 Figma 中未单独标注，示例使用等宽字体 13 / 20。

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| code-editor | 填充 | false / true |

### 实例：代码编辑器

可直接编辑，Tab 键缩进

```html
<div class="q-vert" style="width:100%"><div class="q-row"><span class="q-lab">外观</span><span class="q-cap s"><button type="button" class="on">描边</button><i></i><button type="button" class="">填充</button></span></div><div class="q-code" id="ce1"><div class="gt">1
2
3
4
5
6
7</div><textarea spellcheck="false" aria-label="代码">// 计算计划完成率
function rate(actual, plan) { if (!plan) return null; return +(actual / plan * 100).toFixed(1);
} rate(43345, 45200); // 95.9</textarea></div></div>
```

## ColorPicker 颜色选择器

选择颜色。面板支持拖动取色、调整色相和透明度、输入 HEX，以及选择最近使用的颜色。

- Figma：[153171:62609](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=153171-62609)
- 变体概况：25 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 触发器 | 内边距 3px，描边 color-border-2，圆角 2px，色块 18×18px |
| 面板 | 宽 276px，圆角 8px，内边距 16px，白底投影 |
| 滑条 | 高 14px，圆角 7px |
| 底部 | 上边框 color-border-1，取消 / 确定按钮为小号 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| color-picker | 填充 | false / true |
| color-picker | 尺寸 | 小 / 中 / 大 / 迷你 |
| color-picker | 形状 | 方形 / 圆形 |
| color-picker-panel | 面板 | 纯色 / 渐变色 |

### 实例：颜色选择器

点色块打开面板

```html
<span class="q-wrap" id="cp1"><span class="q-cp" data-dd="" tabindex="0" role="button" aria-label="选择颜色"><i style="--c:#00AAA6"></i></span><div class="q-cpp"><div class="in"><div class="sv" data-sv=""><i></i></div><input type="range" class="hue" min="0" max="360" aria-label="色相"><input type="range" class="alp" min="0" max="100" data-al="" aria-label="透明度"><div class="row"><span class="q-in" style="--w:140px"><input placeholder="请输入" value="" data-hex="" aria-label="HEX"></span><span class="q-in" style="--w:84px"><input value="100" data-al2="" aria-label="透明度百分比"><span class="q-ph">%</span></span></div><div class="hist"><button type="button" style="--c:#00AAA6" data-hc="#00AAA6" aria-label="#00AAA6"></button><button type="button" style="--c:#3491FA" data-hc="#3491FA" aria-label="#3491FA"></button><button type="button" style="--c:#FF7D00" data-hc="#FF7D00" aria-label="#FF7D00"></button><button type="button" style="--c:#F53F3F" data-hc="#F53F3F" aria-label="#F53F3F"></button><button type="button" style="--c:#00B42A" data-hc="#00B42A" aria-label="#00B42A"></button><button type="button" style="--c:#722ED1" data-hc="#722ED1" aria-label="#722ED1"></button><button type="button" style="--c:#1D2129" data-hc="#1D2129" aria-label="#1D2129"></button><button type="button" style="--c:#C9CDD4" data-hc="#C9CDD4" aria-label="#C9CDD4"></button></div></div><div class="ft"><button data-cpx="" type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="取消">取消</button><button data-cpok="" type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="确定">确定</button></div></div></span><span class="q-out">当前颜色：<b id="cpo">#00AAA6</b></span>
```

## DatePicker 日期选择器

通过日历面板选择日期或日期范围，也可以直接选择“今天”。

- Figma：[115965:125930](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125930)
- 变体概况：98 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 触发器 | 同 Input，宽 240px（示例），右侧 16px 日历图标 |
| 面板 | 宽 280px，头部高 40px，内容区内边距 16px |
| 日期单元 | 32×32px，数字 14 / 22 Semibold |
| 选中 | primary-6 #00AAA6 |
| 范围内 | primary-1 #E8FFFB |
| 非本月 | color-text-4 #C9CDD4 |

> 说明：Figma 中面板还有月、年、周、季度、带时间和预设范围几种类型，本页先还原最常用的日期与范围选择。

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| datepicker | 尺寸 | 中 / 大 / 小 / 迷你 |
| datepicker | 填充 | false / true |
| datepicker | 范围 | false / true |
| datepicker | 聚焦&悬停 | false / true |
| datepicker | 禁用 | false / true |
| datepicker-dropdown | 类型 | 基本 / 月 / 年 / 周 / 季度 / 带时间 |
| datepicker-dropdown | 范围 | false / true |
| datepicker-dropdown | 预设范围 | false / true |

### 实例：选择日期

选中后自动关闭

```html
<span class="q-wrap"><span class="q-in q-sel" style="--w:240px" data-dd="" tabindex="0"><span class="v" data-dpi="dp1"><span class="q-ph">请选择日期</span></span><svg data-icon="calendar" class="i ar"/></span><div class="q-dp pop" id="dp1"><div class="hd"><button type="button" data-dpn="dp1|-12" aria-label="上一年"><svg data-icon="double-left" class="i"/></button><button type="button" data-dpn="dp1|-1" aria-label="上个月"><svg data-icon="left" class="i"/></button><b>2026-11</b><button type="button" data-dpn="dp1|1" aria-label="下个月"><svg data-icon="right" class="i"/></button><button type="button" data-dpn="dp1|12" aria-label="下一年"><svg data-icon="double-right" class="i"/></button></div> <div class="bd"><span class="wk">日</span><span class="wk">一</span><span class="wk">二</span><span class="wk">三</span><span class="wk">四</span><span class="wk">五</span><span class="wk">六</span><button type="button" class="q-dc" data-dc="dp1|2026-11-01"><span>1</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-02"><span>2</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-03"><span>3</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-04"><span>4</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-05"><span>5</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-06"><span>6</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-07"><span>7</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-08"><span>8</span></button><button type="button" class="q-dc td" data-dc="dp1|2026-11-09"><span>9</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-10"><span>10</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-11"><span>11</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-12"><span>12</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-13"><span>13</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-14"><span>14</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-15"><span>15</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-16"><span>16</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-17"><span>17</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-18"><span>18</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-19"><span>19</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-20"><span>20</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-21"><span>21</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-22"><span>22</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-23"><span>23</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-24"><span>24</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-25"><span>25</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-26"><span>26</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-27"><span>27</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-28"><span>28</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-29"><span>29</span></button><button type="button" class="q-dc" data-dc="dp1|2026-11-30"><span>30</span></button><button type="button" class="q-dc out" data-dc="dp1|2026-12-01"><span>1</span></button><button type="button" class="q-dc out" data-dc="dp1|2026-12-02"><span>2</span></button><button type="button" class="q-dc out" data-dc="dp1|2026-12-03"><span>3</span></button><button type="button" class="q-dc out" data-dc="dp1|2026-12-04"><span>4</span></button><button type="button" class="q-dc out" data-dc="dp1|2026-12-05"><span>5</span></button><button type="button" class="q-dc out" data-dc="dp1|2026-12-06"><span>6</span></button><button type="button" class="q-dc out" data-dc="dp1|2026-12-07"><span>7</span></button><button type="button" class="q-dc out" data-dc="dp1|2026-12-08"><span>8</span></button><button type="button" class="q-dc out" data-dc="dp1|2026-12-09"><span>9</span></button><button type="button" class="q-dc out" data-dc="dp1|2026-12-10"><span>10</span></button><button type="button" class="q-dc out" data-dc="dp1|2026-12-11"><span>11</span></button><button type="button" class="q-dc out" data-dc="dp1|2026-12-12"><span>12</span></button></div> <div class="ft"><button type="button" data-dctoday="dp1">今天</button></div></div></span>
```

### 实例：选择范围

先点开始日期，再点结束日期

```html
<span class="q-wrap"><span class="q-in q-sel" style="--w:300px" data-dd="" tabindex="0"><span class="v" data-dpi="dp2"><span class="q-ph">开始日期 — 结束日期</span></span><svg data-icon="calendar" class="i ar"/></span><div class="q-dp pop" id="dp2"><div class="hd"><button type="button" data-dpn="dp2|-12" aria-label="上一年"><svg data-icon="double-left" class="i"/></button><button type="button" data-dpn="dp2|-1" aria-label="上个月"><svg data-icon="left" class="i"/></button><b>2026-11</b><button type="button" data-dpn="dp2|1" aria-label="下个月"><svg data-icon="right" class="i"/></button><button type="button" data-dpn="dp2|12" aria-label="下一年"><svg data-icon="double-right" class="i"/></button></div> <div class="bd"><span class="wk">日</span><span class="wk">一</span><span class="wk">二</span><span class="wk">三</span><span class="wk">四</span><span class="wk">五</span><span class="wk">六</span><button type="button" class="q-dc" data-dc="dp2|2026-11-01"><span>1</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-02"><span>2</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-03"><span>3</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-04"><span>4</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-05"><span>5</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-06"><span>6</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-07"><span>7</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-08"><span>8</span></button><button type="button" class="q-dc td" data-dc="dp2|2026-11-09"><span>9</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-10"><span>10</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-11"><span>11</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-12"><span>12</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-13"><span>13</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-14"><span>14</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-15"><span>15</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-16"><span>16</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-17"><span>17</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-18"><span>18</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-19"><span>19</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-20"><span>20</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-21"><span>21</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-22"><span>22</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-23"><span>23</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-24"><span>24</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-25"><span>25</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-26"><span>26</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-27"><span>27</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-28"><span>28</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-29"><span>29</span></button><button type="button" class="q-dc" data-dc="dp2|2026-11-30"><span>30</span></button><button type="button" class="q-dc out" data-dc="dp2|2026-12-01"><span>1</span></button><button type="button" class="q-dc out" data-dc="dp2|2026-12-02"><span>2</span></button><button type="button" class="q-dc out" data-dc="dp2|2026-12-03"><span>3</span></button><button type="button" class="q-dc out" data-dc="dp2|2026-12-04"><span>4</span></button><button type="button" class="q-dc out" data-dc="dp2|2026-12-05"><span>5</span></button><button type="button" class="q-dc out" data-dc="dp2|2026-12-06"><span>6</span></button><button type="button" class="q-dc out" data-dc="dp2|2026-12-07"><span>7</span></button><button type="button" class="q-dc out" data-dc="dp2|2026-12-08"><span>8</span></button><button type="button" class="q-dc out" data-dc="dp2|2026-12-09"><span>9</span></button><button type="button" class="q-dc out" data-dc="dp2|2026-12-10"><span>10</span></button><button type="button" class="q-dc out" data-dc="dp2|2026-12-11"><span>11</span></button><button type="button" class="q-dc out" data-dc="dp2|2026-12-12"><span>12</span></button></div> </div></span>
```

### 实例：面板

今天下方有 primary-6 小圆点

```html
<div class="q-dp" id="dp3"><div class="hd"><button type="button" data-dpn="dp3|-12" aria-label="上一年"><svg data-icon="double-left" class="i"/></button><button type="button" data-dpn="dp3|-1" aria-label="上个月"><svg data-icon="left" class="i"/></button><b>2026-11</b><button type="button" data-dpn="dp3|1" aria-label="下个月"><svg data-icon="right" class="i"/></button><button type="button" data-dpn="dp3|12" aria-label="下一年"><svg data-icon="double-right" class="i"/></button></div> <div class="bd"><span class="wk">日</span><span class="wk">一</span><span class="wk">二</span><span class="wk">三</span><span class="wk">四</span><span class="wk">五</span><span class="wk">六</span><button type="button" class="q-dc" data-dc="dp3|2026-11-01"><span>1</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-02"><span>2</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-03"><span>3</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-04"><span>4</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-05"><span>5</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-06"><span>6</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-07"><span>7</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-08"><span>8</span></button><button type="button" class="q-dc td on" data-dc="dp3|2026-11-09"><span>9</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-10"><span>10</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-11"><span>11</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-12"><span>12</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-13"><span>13</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-14"><span>14</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-15"><span>15</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-16"><span>16</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-17"><span>17</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-18"><span>18</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-19"><span>19</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-20"><span>20</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-21"><span>21</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-22"><span>22</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-23"><span>23</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-24"><span>24</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-25"><span>25</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-26"><span>26</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-27"><span>27</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-28"><span>28</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-29"><span>29</span></button><button type="button" class="q-dc" data-dc="dp3|2026-11-30"><span>30</span></button><button type="button" class="q-dc out" data-dc="dp3|2026-12-01"><span>1</span></button><button type="button" class="q-dc out" data-dc="dp3|2026-12-02"><span>2</span></button><button type="button" class="q-dc out" data-dc="dp3|2026-12-03"><span>3</span></button><button type="button" class="q-dc out" data-dc="dp3|2026-12-04"><span>4</span></button><button type="button" class="q-dc out" data-dc="dp3|2026-12-05"><span>5</span></button><button type="button" class="q-dc out" data-dc="dp3|2026-12-06"><span>6</span></button><button type="button" class="q-dc out" data-dc="dp3|2026-12-07"><span>7</span></button><button type="button" class="q-dc out" data-dc="dp3|2026-12-08"><span>8</span></button><button type="button" class="q-dc out" data-dc="dp3|2026-12-09"><span>9</span></button><button type="button" class="q-dc out" data-dc="dp3|2026-12-10"><span>10</span></button><button type="button" class="q-dc out" data-dc="dp3|2026-12-11"><span>11</span></button><button type="button" class="q-dc out" data-dc="dp3|2026-12-12"><span>12</span></button></div> <div class="ft"><button type="button" data-dctoday="dp3">今天</button></div></div>
```

## Form 表单

收集和校验用户输入。支持水平与垂直布局、标签左右对齐，字段可附帮助、额外说明和错误提示。

- Figma：[115965:125931](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125931)
- 变体概况：286 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 标签 | 14 / 22 color-text-2，必填星号 danger-6 |
| 字段间距 | 字段项底部 20px |
| 帮助文字 | 12 / 20 color-text-3；错误时为 danger-6 |
| 额外说明 | 12 / 14 color-text-3，上内边距 4px |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| form | 布局 | 水平 / 垂直 |
| form | 尺寸 | 中 / 大 / 小 / 迷你 |
| form | 数量 | 2 / 3 / 9 / 8 / 7 / 6 / 5 / 4 |
| form-item/input | Help | false / true |
| form-item/input | 标签对齐 | 右 / 左 |

另有布尔属性：气泡提示、必填、插槽、展开菜单

### 实例：表单

直接点“提交”查看必填校验

```html
<div class="q-vert" style="width:100%"><div class="q-row"><span class="q-lab">布局</span><span class="q-cap s" id="fml"><button type="button" class="on" data-fl="水平">水平</button><i></i><button type="button" class="" data-fl="垂直">垂直</button></span><span class="q-lab">标签对齐</span><span class="q-cap s" id="fma"><button type="button" class="on" data-fa="右">右</button><i></i><button type="button" class="" data-fa="左">左</button></span></div><div id="fmw" style="width:100%"><form class="q-form" id="fm1" novalidate=""> <div class="q-fit"><label><i>*</i>报表名称</label><div><span class="q-in"><input placeholder="请输入报表名称" value="" data-req="报表名称"></span><div class="q-help">最多 20 个字</div></div></div> <div class="q-fit"><label><i>*</i>负责人</label><div><span class="q-wrap" data-sel="" data-reqsel="负责人"><span class="q-in q-sel" style="--w:220px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v"><span class="q-ph">请选择负责人</span></span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi" data-v="李明">李明</div><div class="q-mi" data-v="王芳">王芳</div><div class="q-mi" data-v="张伟">张伟</div><div class="q-mi" data-v="赵丽">赵丽</div><div class="q-mi" data-v="孙强">孙强</div><div class="q-mi" data-v="周敏">周敏</div><div class="q-mi" data-v="吴磊">吴磊</div><div class="q-mi" data-v="郑洁">郑洁</div></div></span></div></div> <div class="q-fit"><label>数据口径</label><div style="padding-top:5px"><div class="q-row" data-rg=""><span class="q-rd on" role="radio" aria-checked="true" tabindex="0"><i></i>管理口径</span><span class="q-rd" role="radio" aria-checked="false" tabindex="0"><i></i>财务口径</span></div></div></div> <div class="q-fit"><label>推送到飞书</label><div style="padding-top:4px"><button type="button" class="q-sw on" role="switch" aria-checked="true" aria-label="推送到飞书"></button><div class="q-extra">每天 08:30 推送</div></div></div> <div class="q-fit"><label>备注</label><div><span class="q-in ta" style="--w:100%;width:100%"><textarea placeholder="选填" maxlength="200"></textarea></span></div></div> <div class="q-fbt"><button data-fsub="" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="提交">提交</button><button data-frst="" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="重置">重置</button></div></form></div></div>
```

## IconPicker 图标选择器

从 Pangea 图标库中选择一个图标，用于菜单、应用入口等可配置的位置。

- Figma：[153171:57191](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=153171-57191)
- 变体概况：中 / 大 / 小 / 迷你

### 样式参数

| 参数 | 值 |
| --- | --- |
| 组成 | “更换”次要按钮 + 当前图标与名称，间距 8px |
| 当前图标 | 16px，名称 14 / 22 color-text-2 |
| 面板 | 8 列网格，单元高 32px，选中 primary-1 底 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| icon-picker | 尺寸 | 中 / 大 / 小 / 迷你 |
| icon-picker | 填充 | true / false |

### 实例：图标选择

图标来自本站的 Pangea 图标库

```html
<span class="q-wrap" id="ip1"><button data-dd="" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="更换">更换</button><span class="q-icur" id="ipc"><svg data-icon="dashboard" class="i"/>dashboard</span><div class="q-ipk"><span class="q-in" style="--w:296px"><input placeholder="搜索图标，例如 chart" value="" data-ipq=""></span><div class="g"><button type="button" class="" data-ipk="column-setting" title="column-setting"><svg data-icon="column-setting" class="i"/></button><button type="button" class="" data-ipk="transaction" title="transaction"><svg data-icon="transaction" class="i"/></button><button type="button" class="" data-ipk="trademark" title="trademark"><svg data-icon="trademark" class="i"/></button><button type="button" class="" data-ipk="select" title="select"><svg data-icon="select" class="i"/></button><button type="button" class="" data-ipk="pull-request" title="pull-request"><svg data-icon="pull-request" class="i"/></button><button type="button" class="" data-ipk="pound" title="pound"><svg data-icon="pound" class="i"/></button><button type="button" class="" data-ipk="percentage" title="percentage"><svg data-icon="percentage" class="i"/></button><button type="button" class="" data-ipk="monitor" title="monitor"><svg data-icon="monitor" class="i"/></button><button type="button" class="" data-ipk="key" title="key"><svg data-icon="key" class="i"/></button><button type="button" class="" data-ipk="gold" title="gold"><svg data-icon="gold" class="i"/></button><button type="button" class="" data-ipk="gateway" title="gateway"><svg data-icon="gateway" class="i"/></button><button type="button" class="" data-ipk="euro" title="euro"><svg data-icon="euro" class="i"/></button><button type="button" class="" data-ipk="dollar" title="dollar"><svg data-icon="dollar" class="i"/></button><button type="button" class="" data-ipk="deployment-unit" title="deployment-unit"><svg data-icon="deployment-unit" class="i"/></button><button type="button" class="" data-ipk="coffee" title="coffee"><svg data-icon="coffee" class="i"/></button><button type="button" class="" data-ipk="cluster" title="cluster"><svg data-icon="cluster" class="i"/></button><button type="button" class="" data-ipk="ci" title="ci"><svg data-icon="ci" class="i"/></button><button type="button" class="" data-ipk="barcode" title="barcode"><svg data-icon="barcode" class="i"/></button><button type="button" class="" data-ipk="usb" title="usb"><svg data-icon="usb" class="i"/></button><button type="button" class="" data-ipk="switcher" title="switcher"><svg data-icon="switcher" class="i"/></button><button type="button" class="" data-ipk="shop" title="shop"><svg data-icon="shop" class="i"/></button><button type="button" class="" data-ipk="rocket" title="rocket"><svg data-icon="rocket" class="i"/></button><button type="button" class="" data-ipk="rest" title="rest"><svg data-icon="rest" class="i"/></button><button type="button" class="" data-ipk="reconciliation" title="reconciliation"><svg data-icon="reconciliation" class="i"/></button><button type="button" class="" data-ipk="money-collect" title="money-collect"><svg data-icon="money-collect" class="i"/></button><button type="button" class="" data-ipk="medicine-box" title="medicine-box"><svg data-icon="medicine-box" class="i"/></button><button type="button" class="" data-ipk="hourglass" title="hourglass"><svg data-icon="hourglass" class="i"/></button><button type="button" class="" data-ipk="flag" title="flag"><svg data-icon="flag" class="i"/></button><button type="button" class="" data-ipk="crown" title="crown"><svg data-icon="crown" class="i"/></button><button type="button" class="" data-ipk="contacts" title="contacts"><svg data-icon="contacts" class="i"/></button><button type="button" class="" data-ipk="carry-out" title="carry-out"><svg data-icon="carry-out" class="i"/></button><button type="button" class="" data-ipk="car" title="car"><svg data-icon="car" class="i"/></button><button type="button" class="" data-ipk="build" title="build"><svg data-icon="build" class="i"/></button><button type="button" class="" data-ipk="red-envelope" title="red-envelope"><svg data-icon="red-envelope" class="i"/></button><button type="button" class="" data-ipk="folder-open" title="folder-open"><svg data-icon="folder-open" class="i"/></button><button type="button" class="" data-ipk="shopping" title="shopping"><svg data-icon="shopping" class="i"/></button><button type="button" class="" data-ipk="border" title="border"><svg data-icon="border" class="i"/></button><button type="button" class="" data-ipk="project" title="project"><svg data-icon="project" class="i"/></button><button type="button" class="" data-ipk="control" title="control"><svg data-icon="control" class="i"/></button><button type="button" class="" data-ipk="calculator" title="calculator"><svg data-icon="calculator" class="i"/></button><button type="button" class="" data-ipk="inbox" title="inbox"><svg data-icon="inbox" class="i"/></button><button type="button" class="" data-ipk="security-scan" title="security-scan"><svg data-icon="security-scan" class="i"/></button><button type="button" class="" data-ipk="property-safety" title="property-safety"><svg data-icon="property-safety" class="i"/></button><button type="button" class="" data-ipk="insurance" title="insurance"><svg data-icon="insurance" class="i"/></button><button type="button" class="" data-ipk="block" title="block"><svg data-icon="block" class="i"/></button><button type="button" class="" data-ipk="number" title="number"><svg data-icon="number" class="i"/></button><button type="button" class="" data-ipk="table" title="table"><svg data-icon="table" class="i"/></button><button type="button" class="" data-ipk="shopping-cart" title="shopping-cart"><svg data-icon="shopping-cart" class="i"/></button><button type="button" class="" data-ipk="solution" title="solution"><svg data-icon="solution" class="i"/></button><button type="button" class="" data-ipk="audit" title="audit"><svg data-icon="audit" class="i"/></button><button type="button" class="" data-ipk="container" title="container"><svg data-icon="container" class="i"/></button><button type="button" class="" data-ipk="wallet" title="wallet"><svg data-icon="wallet" class="i"/></button><button type="button" class="" data-ipk="credit-card" title="credit-card"><svg data-icon="credit-card" class="i"/></button><button type="button" class="" data-ipk="laptop" title="laptop"><svg data-icon="laptop" class="i"/></button><button type="button" class="" data-ipk="file-sync" title="file-sync"><svg data-icon="file-sync" class="i"/></button><button type="button" class="" data-ipk="file-protect" title="file-protect"><svg data-icon="file-protect" class="i"/></button><button type="button" class="" data-ipk="file-done" title="file-done"><svg data-icon="file-done" class="i"/></button><button type="button" class="" data-ipk="exception" title="exception"><svg data-icon="exception" class="i"/></button><button type="button" class="" data-ipk="cloud-server" title="cloud-server"><svg data-icon="cloud-server" class="i"/></button><button type="button" class="" data-ipk="account-book" title="account-book"><svg data-icon="account-book" class="i"/></button><button type="button" class="" data-ipk="file-search" title="file-search"><svg data-icon="file-search" class="i"/></button><button type="button" class="" data-ipk="apartment" title="apartment"><svg data-icon="apartment" class="i"/></button><button type="button" class="" data-ipk="alert" title="alert"><svg data-icon="alert" class="i"/></button><button type="button" class="" data-ipk="explore" title="explore"><svg data-icon="explore" class="i"/></button><button type="button" class="" data-ipk="bank" title="bank"><svg data-icon="bank" class="i"/></button><button type="button" class="" data-ipk="heat-map" title="heat-map"><svg data-icon="heat-map" class="i"/></button><button type="button" class="" data-ipk="english-fill" title="english-fill"><svg data-icon="english-fill" class="i"/></button><button type="button" class="" data-ipk="fund" title="fund"><svg data-icon="fund" class="i"/></button><button type="button" class="" data-ipk="chinese-fill" title="chinese-fill"><svg data-icon="chinese-fill" class="i"/></button><button type="button" class="" data-ipk="box-plot" title="box-plot"><svg data-icon="box-plot" class="i"/></button><button type="button" class="" data-ipk="face-smile-fill" title="face-smile-fill"><svg data-icon="face-smile-fill" class="i"/></button><button type="button" class="" data-ipk="face-meh-fill" title="face-meh-fill"><svg data-icon="face-meh-fill" class="i"/></button><button type="button" class="" data-ipk="line-chart" title="line-chart"><svg data-icon="line-chart" class="i"/></button><button type="button" class="" data-ipk="face-frown-fill" title="face-frown-fill"><svg data-icon="face-frown-fill" class="i"/></button><button type="button" class="" data-ipk="dot-chart" title="dot-chart"><svg data-icon="dot-chart" class="i"/></button><button type="button" class="" data-ipk="bar-chart" title="bar-chart"><svg data-icon="bar-chart" class="i"/></button><button type="button" class="" data-ipk="area-chart" title="area-chart"><svg data-icon="area-chart" class="i"/></button><button type="button" class="" data-ipk="bookmark" title="bookmark"><svg data-icon="bookmark" class="i"/></button><button type="button" class="" data-ipk="dash" title="dash"><svg data-icon="dash" class="i"/></button><button type="button" class="" data-ipk="calendar-clock" title="calendar-clock"><svg data-icon="calendar-clock" class="i"/></button><button type="button" class="" data-ipk="computer" title="computer"><svg data-icon="computer" class="i"/></button><button type="button" class="" data-ipk="layers" title="layers"><svg data-icon="layers" class="i"/></button><button type="button" class="" data-ipk="relation" title="relation"><svg data-icon="relation" class="i"/></button><button type="button" class="" data-ipk="palette" title="palette"><svg data-icon="palette" class="i"/></button><button type="button" class="" data-ipk="snippets" title="snippets"><svg data-icon="snippets" class="i"/></button><button type="button" class="" data-ipk="language" title="language"><svg data-icon="language" class="i"/></button><button type="button" class="" data-ipk="diff" title="diff"><svg data-icon="diff" class="i"/></button><button type="button" class="" data-ipk="archive" title="archive"><svg data-icon="archive" class="i"/></button><button type="button" class="" data-ipk="form" title="form"><svg data-icon="form" class="i"/></button><button type="button" class="" data-ipk="old-version" title="old-version"><svg data-icon="old-version" class="i"/></button><button type="button" class="" data-ipk="issues-close" title="issues-close"><svg data-icon="issues-close" class="i"/></button><button type="button" class="" data-ipk="dice" title="dice"><svg data-icon="dice" class="i"/></button><button type="button" class="" data-ipk="moon-fill" title="moon-fill"><svg data-icon="moon-fill" class="i"/></button><button type="button" class="" data-ipk="moon" title="moon"><svg data-icon="moon" class="i"/></button><button type="button" class="" data-ipk="sun-fill" title="sun-fill"><svg data-icon="sun-fill" class="i"/></button><button type="button" class="" data-ipk="sun" title="sun"><svg data-icon="sun" class="i"/></button></div></div></span>
```

## ImageSelect 图片选择

用图片卡片展示可选项，适合选择模板、主题等需要预览的场景。支持单选和多选。

- Figma：[149532:12368](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=149532-12368)
- 变体概况：28 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 卡片 | 宽 200px，内边距 12px，内容间距 12px，圆角 8px |
| 默认描边 | color-border-2 #E5E6EB |
| 选中 | primary-1 #E8FFFB primary-6 #00AAA6 |
| 图片比例 | 3:2 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| image-select-item | 选中 | false / true |
| image-select-item | 悬停 | false / true |
| image-select-item | 禁用 | false / true |
| image-select-item | 复选 | false / true |
| image-select | 数量 | 2 / 3 / 4 / 5 / 6 / 7 |

### 实例：图片选择

多选时右上角显示复选框

```html
<div class="q-vert"><div class="q-row"><span class="q-lab">模式</span><span class="q-cap s"><button type="button" class="on">单选</button><i></i><button type="button" class="">多选</button></span></div><div id="is1"><div class="q-isel" data-mode="0"><button type="button" class="q-isi on" data-isi=""><div class="q-media">经营总览模板</div><span><b>经营总览模板</b><small>3 个指标卡 + 趋势图</small></span></button><button type="button" class="q-isi" data-isi=""><div class="q-media">明细表模板</div><span><b>明细表模板</b><small>筛选栏 + 明细表</small></span></button><button type="button" class="q-isi" data-isi=""><div class="q-media">大屏模板</div><span><b>大屏模板</b><small>1920 × 1080</small></span></button><button type="button" class="q-isi d" data-isi="" disabled=""><div class="q-media">移动端模板</div><span><b>移动端模板</b><small>375 宽，禁用</small></span></button></div></div></div>
```

## Input 输入框

输入单行或多行文字。支持 4 种尺寸、前后缀、前置后置标签、密码、搜索和字数统计。

- Figma：[115965:125932](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125932)
- 变体概况：179 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 高度 | 大 36、中 32、小 28、迷你 24px |
| 内边距 | 左右：大 16、中 12、小 12、迷你 8px |
| 默认 | color-background-white #FFFFFF color-border-3 #C9CDD4 |
| 聚焦描边 | primary-6 #00AAA6 |
| 禁用 | color-fill-2 #F2F3F5 color-text-4 #C9CDD4 |
| 占位文字 | color-text-3 #86909C |
| 圆角 | 4px |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| input | 尺寸 | 大 / 中 / 小 / 迷你 |
| input | 状态 | 默认 / 禁用 / 聚焦 |
| input | 填充 | false / true |
| input | 前置标签 | false / true |
| input | 后置标签 | false / true |
| password | 尺寸 | 大 / 中 / 小 / 迷你 |
| password | 填充 | true / false |
| password | 可见 | false / true |
| search-box | 尺寸 | 中 / 小 / 大 / 迷你 |
| search-box | 类型 | 默认 / 文字按钮 / 图标按钮 |
| search-box | 填充 | false / true |
| textarea | 尺寸 | 中 |
| textarea | 状态 | 默认 / 禁用 / 悬停&聚焦 |
| textarea | 填充 | false / true |
| textarea | 字数统计 | false / true |
| input-group | 分隔符 | false / true |

### 实例：尺寸

```html
<div class="q-vert"><div class="q-row"><span class="q-lab">大</span><span class="q-in l"><input placeholder="请输入指标名称" value=""></span></div><div class="q-row"><span class="q-lab">中</span><span class="q-in"><input placeholder="请输入指标名称" value=""></span></div><div class="q-row"><span class="q-lab">小</span><span class="q-in s"><input placeholder="请输入指标名称" value=""></span></div><div class="q-row"><span class="q-lab">迷你</span><span class="q-in xs"><input placeholder="请输入指标名称" value=""></span></div></div>
```

### 实例：状态

```html
<div class="q-row"><span class="q-in"><input placeholder="默认" value=""></span><span class="q-in f"><input placeholder="请输入" value="聚焦"></span><span class="q-in d"><input placeholder="请输入" value="禁用" disabled=""></span><span class="q-in e"><input placeholder="请输入" value="2026-13"><span style="color:#F53F3F;font-size:12px;white-space:nowrap">格式错误</span></span></div>
```

### 实例：前后缀与标签

带清除按钮的输入框可以点 × 清空

```html
<div class="q-vert"><div class="q-row"><span class="q-in"><svg data-icon="user" class="i"/><input placeholder="工号" value=""></span><span class="q-in"><input placeholder="金额" value=""><span class="q-ph">万元</span></span><span class="q-in" data-clr=""><svg data-icon="search" class="i"/><input placeholder="可清除" value="海信空调"><button type="button" class="ic" data-clear="" aria-label="清除"><svg data-icon="close-circle-fill" class="i"/></button></span></div><div class="q-row"><span class="q-grp"><span class="q-ad">https://</span><span class="q-in"><input placeholder="报表地址" value=""></span><span class="q-ad">.com</span></span></div></div>
```

### 实例：密码与搜索

点眼睛图标切换密码可见

```html
<div class="q-row"><span class="q-in"><input type="password" value="hisense2026" aria-label="密码"><button type="button" class="ic" data-eye="" aria-label="显示密码"><svg data-icon="eye-invisible" class="i"/></button></span><span class="q-grp" style="--w:300px"><span class="q-in"><input placeholder="搜索报表、指标" value=""></span><button data-srch="" aria-label="搜索" type="button" class="pb io live" style="--h:32px;--px:8px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;"><svg data-icon="search" class="i"/></button></span></div>
```

### 实例：多行与字数统计

```html
<span class="q-in ta" style="--w:420px"><textarea maxlength="50" data-cnt="" placeholder="请输入业务点评">7 月内销家空收入同比增长 4.23%。</textarea><span class="cnt">20/50</span></span>
```

## i18n 多语言输入框

为同一字段录入多种语言。点地球图标打开多语言面板，保存后显示已绑定的语言数量。

- Figma：[148484:264510](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=148484-264510)
- 变体概况：85 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 输入框 | 同 Input，右侧显示已绑定标记与地球图标 |
| 面板 | 内边距 12px，行间距 12px，圆角 2px，白底投影 |
| 已绑定 | 主题色标签显示语言数量 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| i18n-input | 尺寸 | 中 / 大 / 小 / 迷你 |
| i18n-input | 状态 | 默认 / 聚焦 |
| i18n-input | 填充 | false / true |
| i18n-input | 禁用 | false / true |
| i18n-input | 已绑定 | false / true |
| i18n-textarea | 尺寸 | 中 |
| i18n-textarea | 状态 | 默认 / 禁用 / 聚焦 |
| i18n-textarea | 填充 | false / true |
| i18n-textarea | 字数统计 | false / true |
| i18n-textarea | 已绑定 | false / true |

### 实例：多语言输入框

修改后点“保存”

```html
<span class="q-wrap" id="i18"><span class="q-in" style="--w:280px"><input value="空气事业部" aria-label="名称" data-i0=""><span class="q-tag" id="i18b" style="--tb:#E8FFFB;--tt:#00AAA6">2 种语言</span><button type="button" class="ic" data-dd="" aria-label="多语言"><svg data-icon="global" class="i"/></button></span><div class="q-i18n"><div class="rw"><span>中文</span><span class="q-in" style="--w:200px"><input placeholder="未填写" value="空气事业部" data-li="0"></span></div><div class="rw"><span>English</span><span class="q-in" style="--w:200px"><input placeholder="未填写" value="Air Conditioning BU" data-li="1"></span></div><div class="rw"><span>日本語</span><span class="q-in" style="--w:200px"><input placeholder="未填写" value="" data-li="2"></span></div><div style="display:flex;justify-content:flex-end;gap:8px;margin-top:4px"><button data-ix="" type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="取消">取消</button><button data-iok="" type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="保存">保存</button></div></div></span>
```

## InputTag 标签输入框

把输入的内容变成标签。回车添加，点 × 或按退格删除。

- Figma：[115965:125934](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125934)
- 变体概况：38 个变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 容器 | 同 Input，高度随标签自动增加 |
| 标签 | selection-item：高 24px，内边距 1px 8px，color-fill-2 底，color-border-2 描边，圆角 4px |
| 标签文字 | 14 / 22 Semibold；禁用 color-text-4 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| inputtag | 尺寸 | 中 / 大 / 小 / 迷你 |
| inputtag | 填充 | false / true |
| inputtag | 悬停 | false |
| inputtag | 聚焦 | false / true |
| inputtag | 禁用 | false / true |

### 实例：标签输入

空输入时按退格删除最后一个标签

```html
<span class="q-wrap"><span class="q-in q-sel mul" style="--w:380px;cursor:text" data-it=""><span class="v"><span class="q-chip" data-v="内销">内销<button type="button" class="x" data-rm="" aria-label="移除 内销"><svg data-icon="close" class="i"/></button></span><span class="q-chip" data-v="出口">出口<button type="button" class="x" data-rm="" aria-label="移除 出口"><svg data-icon="close" class="i"/></button></span><input placeholder="输入后回车" style="flex:1;min-width:80px;height:24px" aria-label="新标签"></span></span></span>
```

### 实例：禁用

```html
<span class="q-in q-sel mul d" style="--w:380px"><span class="v"><span class="q-chip" style="color:#C9CDD4">内销</span></span></span>
```

## InputNumber 数字输入框

输入数值，可用按钮或键盘上下键按步长加减，并限制最大最小值。

- Figma：[115965:125933](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125933)
- 变体概况：61 个变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 宽度 | 160px（示例） |
| 前缀 / 后缀 | 14 / 22 color-text-1，与数值间距 12px |
| 按钮模式 | 两侧按钮 32×32px，color-fill-1 底，描边 color-border-3 |
| 默认 | color-background-white #FFFFFF color-border-3 #C9CDD4 |
| 聚焦描边 | primary-6 #00AAA6 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| input-number | 尺寸 | 中 / 小 / 迷你 / 大 |
| input-number | 状态 | 默认 / 禁用 / 悬停&聚焦 |
| input-number | 按钮模式 | false / true |
| input-number | 填充 | true / false |

### 实例：默认

范围 0 至 100，键盘 ↑ ↓ 也可调整

```html
<div class="q-row"><span class="q-in" style="--w:160px" data-num="0|100|1"><input value="50" inputmode="decimal" aria-label="数值"><span style="display:flex;flex-direction:column;margin-right:-6px"><button type="button" class="ic" data-ns="1" style="height:12px" aria-label="增加"><svg data-icon="up" class="i"/></button><button type="button" class="ic" data-ns="-1" style="height:12px" aria-label="减少"><svg data-icon="down" class="i"/></button></span></span><span class="q-in" style="--w:160px" data-num="0|100000|100"><span>¥</span><input value="1200" aria-label="金额"><span class="q-ph">万元</span></span></div>
```

### 实例：按钮模式

范围 0 至 10

```html
<span class="q-grp" style="--w:160px" data-num="0|10|1"><button type="button" class="q-ab" data-ns="-1" aria-label="减少"><svg data-icon="minus" class="i"/></button><span class="q-in" style="text-align:center"><input value="3" style="text-align:center" aria-label="数量"></span><button type="button" class="q-ab" data-ns="1" aria-label="增加"><svg data-icon="plus" class="i"/></button></span>
```

## VerificationCode 验证码输入框

逐格输入验证码，输入后自动跳到下一格，支持粘贴整串数字。

- Figma：[160777:1779](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=160777-1779)
- 变体概况：4 / 6 / 8 位

### 样式参数

| 参数 | 值 |
| --- | --- |
| 单格 | 32×32px，内边距 5px 12px，描边 color-border-3，圆角 4px |
| 格间距 | 8px |
| 只读 | 底色 color-fill-2 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| verification-code | 数量 | 4 / 6 / 8 |
| verification-code | 状态 | 默认 / 只读 |

### 实例：6 位

退格回到上一格

```html
<div class="q-vert"><span class="q-vc" data-vc=""><input maxlength="1" inputmode="numeric" aria-label="第 1 位"><input maxlength="1" inputmode="numeric" aria-label="第 2 位"><input maxlength="1" inputmode="numeric" aria-label="第 3 位"><input maxlength="1" inputmode="numeric" aria-label="第 4 位"><input maxlength="1" inputmode="numeric" aria-label="第 5 位"><input maxlength="1" inputmode="numeric" aria-label="第 6 位"></span><span class="q-out" id="vco">已输入：<b>—</b></span></div>
```

### 实例：4 位与只读

```html
<div class="q-row"><span class="q-vc" data-vc=""><input maxlength="1" inputmode="numeric" aria-label="第 1 位"><input maxlength="1" inputmode="numeric" aria-label="第 2 位"><input maxlength="1" inputmode="numeric" aria-label="第 3 位"><input maxlength="1" inputmode="numeric" aria-label="第 4 位"></span><span class="q-vc ro" data-vc=""><input maxlength="1" inputmode="numeric" aria-label="第 1 位" value="2" readonly=""><input maxlength="1" inputmode="numeric" aria-label="第 2 位" value="0" readonly=""><input maxlength="1" inputmode="numeric" aria-label="第 3 位" value="2" readonly=""><input maxlength="1" inputmode="numeric" aria-label="第 4 位" value="6" readonly=""></span></div>
```

## Jira 任务信息

关联 Jira 任务，展示任务编号与标题。可切换为只读或禁用状态。

- Figma：[149197:26241](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=149197-26241)
- 变体概况：禁用 / 只读

### 样式参数

| 参数 | 值 |
| --- | --- |
| 任务框 | 宽 244px，内边距 5px 12px，描边 color-border-3，圆角 4px |
| 按钮 | 仅图标次要按钮，与任务框间距 4px |
| 只读 | 底色 color-fill-2 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| jira | 禁用 | false / true |
| jira | 只读 | false / true |

另有布尔属性：展开下拉

### 实例：关联任务

点右侧按钮更换任务

```html
<span class="q-wrap"><span class="q-jira" id="jr1"><span class="task"><code>PG-1024</code><span style="overflow:hidden;white-space:nowrap;text-overflow:ellipsis">经营分析大屏改版</span></span><button data-dd="" aria-label="更换任务" type="button" class="pb io live" style="--h:32px;--px:8px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;"><svg data-icon="link" class="i"/></button></span><div class="q-pop"><div class="q-mi on" data-jr="0"><code style="font-size:12px;color:#165DFF">PG-1024</code>经营分析大屏改版</div><div class="q-mi" data-jr="1"><code style="font-size:12px;color:#165DFF">PG-1031</code>财务月报口径调整</div><div class="q-mi" data-jr="2"><code style="font-size:12px;color:#165DFF">PG-1046</code>移动端指标卡优化</div></div></span>
```

### 实例：只读

```html
<span class="q-jira ro"><span class="task"><code>PG-1031</code><span style="overflow:hidden;white-space:nowrap;text-overflow:ellipsis">财务月报口径调整</span></span></span>
```

## Mention 提及

输入 @ 时弹出人员列表，选择后插入到文字中。

- Figma：[115965:125935](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125935)
- 变体概况：标签 / 聚焦

### 样式参数

| 参数 | 值 |
| --- | --- |
| 输入框 | 同 Input，聚焦描边 primary-6 |
| 人员列表 | dropdown-menu，显示头像与姓名 |
| 插入格式 | @姓名 + 空格 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| Mentions | 标签 | false / true |
| Mentions | 聚焦 | false / true |

### 实例：提及

例如输入“请 @王”

```html
<span class="q-wrap" id="mt1"><span class="q-in" style="--w:360px"><input placeholder="输入 @ 提及同事" value="" data-mt="" autocomplete="off"></span><div class="q-pop"></div></span>
```

## Radio 单选框

在一组互斥的选项中选择一项。也可以用按钮样式的单选组。

- Figma：[115965:125936](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125936)
- 变体概况：181 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 圆点 | 14×14px，未选描边 2px color-border-2 |
| 选中 | 描边 4px primary-6 #00AAA6 |
| 悬停 | 外圈 4px color-fill-1 |
| 禁用选中 | primary-3 #79DDD1 |
| 按钮样式 | 容器 color-fill-2 内边距 3px，选中项白底 primary-6 文字 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| components/radio | 选中 | false / true |
| components/radio | 禁用 | false / true |
| components/radio | 插槽 | false / true |
| radio-group | 布局 | 水平 / 垂直 |
| radio-group | 数量 | 3 / 2 / 1 / 4 / 5 / 6 / 7 / 8 / 9 / 10 |
| radio-button-group | 尺寸 | 大 / 中 / 小 / 迷你 |
| radio-button-group | 图标 | false / true |
| radio-button-group | 数量 | 4 / 5 / 3 / 2 |
| radio-button-group | ↳ 选中 | 1 / 2 / 3 / 4 / 5 |

### 实例：单选组

```html
<div class="q-row" data-rg=""><span class="q-rd on" role="radio" aria-checked="true" tabindex="0"><i></i>管理口径</span><span class="q-rd" role="radio" aria-checked="false" tabindex="0"><i></i>财务口径</span><span class="q-rd d" role="radio" aria-checked="false" tabindex="-1"><i></i>税务口径（停用）</span></div>
```

### 实例：垂直

```html
<div class="q-vert" data-rg=""><span class="q-rd on" role="radio" aria-checked="true" tabindex="0"><i></i>按月</span><span class="q-rd" role="radio" aria-checked="false" tabindex="0"><i></i>按季度</span><span class="q-rd" role="radio" aria-checked="false" tabindex="0"><i></i>按年</span></div>
```

### 实例：按钮样式

radio-button-group

```html
<div class="q-vert"><div class="q-row"><span class="q-lab">大</span><span class="q-cap l"><button type="button" class="">日</button><i></i><button type="button" class="">周</button><i></i><button type="button" class="on">月</button><i></i><button type="button" class="">年</button></span></div><div class="q-row"><span class="q-lab">中</span><span class="q-cap"><button type="button" class="">日</button><i></i><button type="button" class="">周</button><i></i><button type="button" class="on">月</button><i></i><button type="button" class="">年</button></span></div><div class="q-row"><span class="q-lab">小</span><span class="q-cap s"><button type="button" class="">日</button><i></i><button type="button" class="">周</button><i></i><button type="button" class="on">月</button><i></i><button type="button" class="">年</button></span></div><div class="q-row"><span class="q-lab">迷你</span><span class="q-cap xs"><button type="button" class="">日</button><i></i><button type="button" class="">周</button><i></i><button type="button" class="on">月</button><i></i><button type="button" class="">年</button></span></div></div>
```

## Rate 评分

用星级或爱心评分。支持半星、悬停预览和只读展示。

- Figma：[115965:125937](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125937)
- 变体概况：68 个变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 单项 | 24×24px，间距 8px |
| 选中 | 未匹配令牌 #F7BA1E |
| 未选 | color-fill-2 #F2F3F5 |
| 悬停 | 放大约 1.1 倍 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| rate | 类型 | 基础 / 爱心 |
| rate | 数量 | 5 / 4 / 3 |
| rate | 值 | 5 / 4.5 / 4 / 3.5 / 3 / 2.5 / 2 / 1.5 / 1 / 0.5 / 0 |

### 实例：基础

悬停预览，点击确定

```html
<div class="q-row"><span class="q-rate" data-rate="3"><button type="button" data-ri="1" aria-label="1 分" class="on"><svg data-icon="star-fill" class="i"/><span class="f"><svg data-icon="star-fill" class="i"/></span></button><button type="button" data-ri="2" aria-label="2 分" class="on"><svg data-icon="star-fill" class="i"/><span class="f"><svg data-icon="star-fill" class="i"/></span></button><button type="button" data-ri="3" aria-label="3 分" class="on"><svg data-icon="star-fill" class="i"/><span class="f"><svg data-icon="star-fill" class="i"/></span></button><button type="button" data-ri="4" aria-label="4 分"><svg data-icon="star-fill" class="i"/><span class="f"><svg data-icon="star-fill" class="i"/></span></button><button type="button" data-ri="5" aria-label="5 分"><svg data-icon="star-fill" class="i"/><span class="f"><svg data-icon="star-fill" class="i"/></span></button></span><span class="q-out" id="rto">3 分</span></div>
```

### 实例：半星

点星星左半边得半分

```html
<span class="q-rate" data-rate="3.5" data-half=""><button type="button" data-ri="1" aria-label="1 分" class="on"><svg data-icon="star-fill" class="i"/><span class="f"><svg data-icon="star-fill" class="i"/></span></button><button type="button" data-ri="2" aria-label="2 分" class="on"><svg data-icon="star-fill" class="i"/><span class="f"><svg data-icon="star-fill" class="i"/></span></button><button type="button" data-ri="3" aria-label="3 分" class="on"><svg data-icon="star-fill" class="i"/><span class="f"><svg data-icon="star-fill" class="i"/></span></button><button type="button" data-ri="4" aria-label="4 分" class="hf"><svg data-icon="star-fill" class="i"/><span class="f"><svg data-icon="star-fill" class="i"/></span></button><button type="button" data-ri="5" aria-label="5 分"><svg data-icon="star-fill" class="i"/><span class="f"><svg data-icon="star-fill" class="i"/></span></button></span>
```

### 实例：爱心与只读

```html
<div class="q-row"><span class="q-rate" data-rate="4"><button type="button" data-ri="1" aria-label="1 分" class="on"><svg data-icon="heart-fill" class="i"/><span class="f"><svg data-icon="heart-fill" class="i"/></span></button><button type="button" data-ri="2" aria-label="2 分" class="on"><svg data-icon="heart-fill" class="i"/><span class="f"><svg data-icon="heart-fill" class="i"/></span></button><button type="button" data-ri="3" aria-label="3 分" class="on"><svg data-icon="heart-fill" class="i"/><span class="f"><svg data-icon="heart-fill" class="i"/></span></button><button type="button" data-ri="4" aria-label="4 分" class="on"><svg data-icon="heart-fill" class="i"/><span class="f"><svg data-icon="heart-fill" class="i"/></span></button><button type="button" data-ri="5" aria-label="5 分"><svg data-icon="heart-fill" class="i"/><span class="f"><svg data-icon="heart-fill" class="i"/></span></button></span><span class="q-rate ro" data-rate="4.5"><button type="button" data-ri="1" aria-label="1 分" class="on"><svg data-icon="star-fill" class="i"/><span class="f"><svg data-icon="star-fill" class="i"/></span></button><button type="button" data-ri="2" aria-label="2 分" class="on"><svg data-icon="star-fill" class="i"/><span class="f"><svg data-icon="star-fill" class="i"/></span></button><button type="button" data-ri="3" aria-label="3 分" class="on"><svg data-icon="star-fill" class="i"/><span class="f"><svg data-icon="star-fill" class="i"/></span></button><button type="button" data-ri="4" aria-label="4 分" class="on"><svg data-icon="star-fill" class="i"/><span class="f"><svg data-icon="star-fill" class="i"/></span></button><button type="button" data-ri="5" aria-label="5 分" class="hf"><svg data-icon="star-fill" class="i"/><span class="f"><svg data-icon="star-fill" class="i"/></span></button></span></div>
```

## Select 选择器

从下拉列表中选择一项或多项。支持 4 种尺寸、多选、禁用选项和无边框模式。

- Figma：[115965:125938](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125938)
- 变体概况：124 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 触发器 | 上下 4px、左右 12px 内边距，与输入框同高 |
| 箭头 | 12px，展开时翻转 |
| 下拉面板 | 白底，描边 color-border-2，圆角 8px，上下内边距 4px |
| 选项 | 内边距 7px 12px，悬停 color-fill-2，选中文字 primary-6，禁用 color-text-4 |
| 多选标签 | selection-item：内边距 1px 8px，color-fill-2 底，color-border-2 描边 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| select | 尺寸 | 大 / 中 / 小 / 迷你 |
| select | 填充 | false / true |
| select | 多选 | false / true |
| select | 悬停 | false |
| select | 聚焦 | false / true |
| select | 禁用 | false / true |
| select | 无边框模式 | false / true |
| selection-item | 尺寸 | 大 / 中 / 小 / 迷你 |
| selection-item | 禁用 | false / true |

### 实例：单选

第一个下拉中有一项禁用

```html
<div class="q-row"><span class="q-wrap" data-sel=""><span class="q-in q-sel" style="--w:220px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v"><span class="q-ph">请选择渠道</span></span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi" data-v="全部渠道">全部渠道</div><div class="q-mi" data-v="线上">线上</div><div class="q-mi" data-v="线下">线下</div><div class="q-mi d" data-v="下沉（未开通）">下沉（未开通）</div><div class="q-mi" data-v="海外">海外</div></div></span><span class="q-wrap" data-sel=""><span class="q-in q-sel" style="--w:220px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v">内销家空</span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi on" data-v="内销家空">内销家空</div><div class="q-mi" data-v="内销商空">内销商空</div><div class="q-mi" data-v="出口整体">出口整体</div></div></span><span class="q-wrap" data-sel=""><span class="q-in q-sel d" style="--w:220px" data-dd="" tabindex="-1" role="combobox" aria-expanded="false"><span class="v">禁用</span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"></div></span></div>
```

### 实例：多选

点标签上的 × 删除

```html
<span class="q-wrap" data-sel="" data-multi=""><span class="q-in q-sel mul" style="--w:320px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v"><span class="q-chip" data-v="家空">家空<button type="button" class="x" data-rm="" aria-label="移除 家空"><svg data-icon="close" class="i"/></button></span><span class="q-chip" data-v="商空">商空<button type="button" class="x" data-rm="" aria-label="移除 商空"><svg data-icon="close" class="i"/></button></span></span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi on" data-v="家空">家空</div><div class="q-mi on" data-v="商空">商空</div><div class="q-mi" data-v="冰箱">冰箱</div><div class="q-mi" data-v="洗衣机">洗衣机</div><div class="q-mi" data-v="厨电">厨电</div><div class="q-mi" data-v="热水器">热水器</div></div></span>
```

### 实例：尺寸

```html
<div class="q-vert"><div class="q-row"><span class="q-lab">大</span><span class="q-wrap" data-sel=""><span class="q-in q-sel l" style="--w:220px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v">2026-07</span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi" data-v="2026-05">2026-05</div><div class="q-mi" data-v="2026-06">2026-06</div><div class="q-mi on" data-v="2026-07">2026-07</div></div></span></div><div class="q-row"><span class="q-lab">中</span><span class="q-wrap" data-sel=""><span class="q-in q-sel" style="--w:220px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v">2026-07</span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi" data-v="2026-05">2026-05</div><div class="q-mi" data-v="2026-06">2026-06</div><div class="q-mi on" data-v="2026-07">2026-07</div></div></span></div><div class="q-row"><span class="q-lab">小</span><span class="q-wrap" data-sel=""><span class="q-in q-sel s" style="--w:220px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v">2026-07</span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi" data-v="2026-05">2026-05</div><div class="q-mi" data-v="2026-06">2026-06</div><div class="q-mi on" data-v="2026-07">2026-07</div></div></span></div><div class="q-row"><span class="q-lab">迷你</span><span class="q-wrap" data-sel=""><span class="q-in q-sel xs" style="--w:220px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v">2026-07</span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi" data-v="2026-05">2026-05</div><div class="q-mi" data-v="2026-06">2026-06</div><div class="q-mi on" data-v="2026-07">2026-07</div></div></span></div></div>
```

### 实例：无边框模式

用在标题栏、表头等空间紧凑处

```html
<div class="q-row"><span class="q-lab">统计月份</span><span class="q-wrap" data-sel=""><span class="q-in q-sel bl" style="--w:120px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v">2026-07</span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi" data-v="2026-06">2026-06</div><div class="q-mi on" data-v="2026-07">2026-07</div><div class="q-mi" data-v="2026-08">2026-08</div></div></span></div>
```

## Signature 手写签名

在画板上手写签名，确认后生成签名图片。

- Figma：[153664:12529](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=153664-12529)
- 变体概况：填充 / 激活

### 样式参数

| 参数 | 值 |
| --- | --- |
| 画板 | 虚线描边 color-border-3，白底，圆角 4px |
| 笔迹 | color-text-1，线宽 2.5px |
| 结果 | 以图片卡片（upload/picture-card）展示 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| upload/picture-card | 状态 | 默认 / 悬停 |

另有布尔属性：填充、激活

### 实例：手写签名

用鼠标或手指书写

```html
<div class="q-vert"><div class="q-sig" id="sg1"><canvas width="396" height="198"></canvas><span>在此处签名</span></div><div class="q-row"><button data-sgc="" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="清除">清除</button><button data-sgok="" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="确认">确认</button></div><div class="q-pcard" id="sgo"><span>签名图片</span></div></div>
```

## Slider 滑动输入条

拖动滑块在一个范围内取值。支持范围选择、步长刻度、与输入框联动和数值提示。

- Figma：[115965:125939](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125939)
- 变体概况：67 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 轨道 | 高 4px color-fill-3 #E5E6EB |
| 已选区间 | primary-6 #00AAA6 |
| 滑块 | 12px 白底，2px primary-6 描边，圆形 |
| 数值提示 | 深色气泡 12 / 20 |
| 禁用 | primary-3 #79DDD1 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| slider | 范围 | false / true |
| slider | 标签 | true / false |
| slider | 步长 | false / true |
| slider | 图标 | false / true |
| slider | 输入框 | false / true |
| slider | 提示 | false / true |

### 实例：基础

拖动或点击轨道

```html
<div class="q-row"><div class="q-sl" style="--w:320px" data-min="0" data-max="100" data-step="1" data-v="40" data-out="slo1" data-unit="%"><span class="tk"></span><span class="br" style="left: 0px; width: 40%;"></span><span class="th" role="slider" tabindex="0" aria-valuemin="0" aria-valuemax="100" aria-valuenow="40" style="left: 40%;"><span class="tp">40%</span></span></div><span class="q-out">当前：<b id="slo1">40%</b></span></div>
```

### 实例：范围

```html
<div class="q-row"><div class="q-sl" style="--w:320px" data-min="0" data-max="100" data-step="1" data-v="20,70" data-out="slo2"><span class="tk"></span><span class="br" style="left: 20%; width: 50%;"></span><span class="th" role="slider" tabindex="0" aria-valuemin="0" aria-valuemax="100" aria-valuenow="20" style="left: 20%;"><span class="tp">20</span></span><span class="th" role="slider" tabindex="0" aria-valuemin="0" aria-valuemax="100" aria-valuenow="70" style="left: 70%;"><span class="tp">70</span></span></div><span class="q-out">区间：<b id="slo2">20 – 70</b></span></div>
```

### 实例：步长刻度

步长 25

```html
<div class="q-sl" style="--w:360px" data-min="0" data-max="100" data-step="25" data-v="50" data-unit="%"><span class="tk"></span><span class="br" style="left: 0px; width: 50%;"></span><i class="mkr in" data-m="0" style="left:0%"></i><span class="ml" style="left:0%">0%</span><i class="mkr in" data-m="25" style="left:25%"></i><span class="ml" style="left:25%">25%</span><i class="mkr in" data-m="50" style="left:50%"></i><span class="ml" style="left:50%">50%</span><i class="mkr" data-m="75" style="left:75%"></i><span class="ml" style="left:75%">75%</span><i class="mkr" data-m="100" style="left:100%"></i><span class="ml" style="left:100%">100%</span><span class="th" role="slider" tabindex="0" aria-valuemin="0" aria-valuemax="100" aria-valuenow="50" style="left: 50%;"><span class="tp">50%</span></span></div>
```

### 实例：联动输入框

```html
<div class="q-row"><div class="q-sl" style="--w:260px" data-min="0" data-max="24" data-step="1" data-v="12" data-out="sli"><span class="tk"></span><span class="br" style="left: 0px; width: 50%;"></span><span class="th" role="slider" tabindex="0" aria-valuemin="0" aria-valuemax="24" aria-valuenow="12" style="left: 50%;"><span class="tp">12</span></span></div><span class="q-in" style="--w:72px"><input id="sli" value="12" aria-label="数值"></span></div>
```

### 实例：禁用

```html
<div class="q-sl d" style="--w:320px" data-min="0" data-max="100" data-step="1" data-v="30"><span class="tk"></span><span class="br" style="left: 0px; width: 30%;"></span><span class="th" role="slider" tabindex="0" aria-valuemin="0" aria-valuemax="100" aria-valuenow="30" style="left: 30%;"><span class="tp">30</span></span></div>
```

## Switch 开关

在开启和关闭两种状态间切换，切换后立即生效。

- Figma：[115965:125940](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125940)
- 变体概况：57 个变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 默认尺寸 | 40×24px，滑块 16px，内边距 4px |
| 小尺寸 | 28×16px，滑块 12px，内边距 2px |
| 开启 | primary-6 #00AAA6 |
| 关闭 | color-fill-4 #C9CDD4 |
| 开启禁用 | primary-3 #79DDD1 |
| 圆角 | 圆形 24px；矩形 2px；线性轨道 36×6px，滑块 20px |

> 说明：Figma 中还有“滑块图标”和“滑轨内容（图标 / 文字）”两种变体，本页暂未还原。

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| switch | 类型 | 圆形 / 矩形 / 线性 |
| switch | 尺寸 | 默认 / 小 |
| switch | 开启 | true / false |
| switch | 禁用 | false / true |
| switch | 滑块图标 | false / true |
| switch | 滑轨内容 | 无 / 图标 / 文字 |

### 实例：类型与尺寸

点击切换

```html
<div class="q-vert"><div class="q-row"><span class="q-lab">圆形</span><button type="button" class="q-sw on" role="switch" aria-checked="true" aria-label="开关"></button><button type="button" class="q-sw" role="switch" aria-checked="false" aria-label="开关"></button><button type="button" class="q-sw on sm" role="switch" aria-checked="true" aria-label="开关"></button><button type="button" class="q-sw sm" role="switch" aria-checked="false" aria-label="开关"></button></div><div class="q-row"><span class="q-lab">矩形</span><button type="button" class="q-sw on rect" role="switch" aria-checked="true" aria-label="开关"></button><button type="button" class="q-sw rect" role="switch" aria-checked="false" aria-label="开关"></button><button type="button" class="q-sw on rect sm" role="switch" aria-checked="true" aria-label="开关"></button><button type="button" class="q-sw rect sm" role="switch" aria-checked="false" aria-label="开关"></button></div><div class="q-row"><span class="q-lab">线性</span><button type="button" class="q-sw on line" role="switch" aria-checked="true" aria-label="开关"></button><button type="button" class="q-sw line" role="switch" aria-checked="false" aria-label="开关"></button></div></div>
```

### 实例：禁用

```html
<div class="q-row"><button type="button" class="q-sw on" role="switch" aria-checked="true" aria-label="开关" disabled=""></button><button type="button" class="q-sw" role="switch" aria-checked="false" aria-label="开关" disabled=""></button><button type="button" class="q-sw on rect" role="switch" aria-checked="true" aria-label="开关" disabled=""></button></div>
```

### 实例：在设置项中使用

```html
<div class="q-vert" style="width:min(420px,100%)"><div style="display:flex;justify-content:space-between;align-items:center;width:100%;font-size:14px;color:#1D2129">数据更新提醒<button type="button" class="q-sw on" role="switch" aria-checked="true" aria-label="数据更新提醒"></button></div><div style="display:flex;justify-content:space-between;align-items:center;width:100%;font-size:14px;color:#1D2129">订阅推送到飞书<button type="button" class="q-sw" role="switch" aria-checked="false" aria-label="订阅推送到飞书"></button></div><div style="display:flex;justify-content:space-between;align-items:center;width:100%;font-size:14px;color:#1D2129">只看预警指标<button type="button" class="q-sw" role="switch" aria-checked="false" aria-label="只看预警指标"></button></div></div>
```

## RichTextEditor 富文本编辑器

编辑带格式的文字，工具栏提供加粗、列表、对齐、撤销等操作。

- Figma：[149240:23743](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=149240-23743)
- 变体概况：35 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 容器 | 2px #EEEEEE 描边，圆角 10px |
| 工具栏 | 上下内边距 4px，按钮有图标、下拉、文字三种，含悬停与禁用状态 |
| 编辑区 | 内边距 16px，14 / 22 color-text-1 |
| 状态栏 | 上边框 #E3E3E3，左内边距 8px |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| rich-text-editor | 填充 | false / true |
| .components/button | 类型 | 图标 / 下拉 / 文字 |
| .components/button | 悬停 | false / true |
| .components/button | 禁用 | false / true |

### 实例：富文本编辑器

选中文字后点工具栏按钮

```html
<div class="q-rte" id="rte1"><div class="tb"><button type="button" data-cmd="bold" title="加粗" aria-label="加粗"><svg data-icon="bold" class="i"/></button><button type="button" data-cmd="italic" title="斜体" aria-label="斜体"><svg data-icon="italic" class="i"/></button><button type="button" data-cmd="underline" title="下划线" aria-label="下划线"><svg data-icon="underline" class="i"/></button><button type="button" data-cmd="strikeThrough" title="删除线" aria-label="删除线"><svg data-icon="strikethrough" class="i"/></button><i></i><button type="button" data-cmd="insertOrderedList" title="有序列表" aria-label="有序列表"><svg data-icon="ordered-list" class="i"/></button><button type="button" data-cmd="insertUnorderedList" title="无序列表" aria-label="无序列表"><svg data-icon="unordered-list" class="i"/></button><i></i><button type="button" data-cmd="justifyLeft" title="左对齐" aria-label="左对齐"><svg data-icon="align-left" class="i"/></button><button type="button" data-cmd="justifyCenter" title="居中" aria-label="居中"><svg data-icon="align-center" class="i"/></button><button type="button" data-cmd="justifyRight" title="右对齐" aria-label="右对齐"><svg data-icon="align-right" class="i"/></button><i></i><button type="button" data-cmd="undo" title="撤销" aria-label="撤销"><svg data-icon="undo" class="i"/></button><button type="button" data-cmd="redo" title="重做" aria-label="重做"><svg data-icon="redo" class="i"/></button></div><div class="ed" contenteditable="true" spellcheck="false"><p><b>7 月经营点评</b></p><p>内销家空收入同比增长 4.23%，主要来自线上渠道；出口整体完成率 104.5%。</p></div><div class="sb">45 字</div></div>
```

## TimePicker 时间选择器

从时、分、秒三列中选择时间。

- Figma：[115965:125942](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125942)
- 变体概况：HH:mm:ss / HH:mm / HH，12 / 24 小时制

### 样式参数

| 参数 | 值 |
| --- | --- |
| 列 | 宽 64px，列间 color-border-2 分隔 |
| 时间项 | 高 24px，14 / 22 Semibold，悬停 color-fill-2 |
| 禁用项 | color-text-4 #C9CDD4 |

> 说明：Figma 中未给出时间项的选中样式，这里用 primary-1 底和 primary-6 文字表示选中。

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| timepicker | 尺寸 | 中 / 大 / 小 / 迷你 |
| timepicker | 填充 | false / true |
| timepicker | 范围 | false / true |
| timepicker | 悬停&聚焦 | false / true |
| timepicker | 禁用 | false / true |
| timepicker-dropdown | 时间格式 | HH:mm:ss / HH:mm / HH |
| timepicker-dropdown | 额外内容 | false / true |
| timepicker-dropdown | 时制 | 24小时制 / 12小时制 |

### 实例：选择时间

选好后点“确定”

```html
<span class="q-wrap" id="tp1"><span class="q-in q-sel" style="--w:200px" data-dd="" tabindex="0"><span class="v" id="tpv">09:30:00</span><svg data-icon="clock-circle" class="i ar"/></span><div class="q-tpk"><div class="tcs"><div data-tk="h"><button type="button" class="q-ti2" data-tv="h|0">00</button><button type="button" class="q-ti2" data-tv="h|1">01</button><button type="button" class="q-ti2" data-tv="h|2">02</button><button type="button" class="q-ti2" data-tv="h|3">03</button><button type="button" class="q-ti2" data-tv="h|4">04</button><button type="button" class="q-ti2" data-tv="h|5">05</button><button type="button" class="q-ti2" data-tv="h|6">06</button><button type="button" class="q-ti2" data-tv="h|7">07</button><button type="button" class="q-ti2" data-tv="h|8">08</button><button type="button" class="q-ti2 on" data-tv="h|9">09</button><button type="button" class="q-ti2" data-tv="h|10">10</button><button type="button" class="q-ti2" data-tv="h|11">11</button><button type="button" class="q-ti2" data-tv="h|12">12</button><button type="button" class="q-ti2" data-tv="h|13">13</button><button type="button" class="q-ti2" data-tv="h|14">14</button><button type="button" class="q-ti2" data-tv="h|15">15</button><button type="button" class="q-ti2" data-tv="h|16">16</button><button type="button" class="q-ti2" data-tv="h|17">17</button><button type="button" class="q-ti2" data-tv="h|18">18</button><button type="button" class="q-ti2" data-tv="h|19">19</button><button type="button" class="q-ti2" data-tv="h|20">20</button><button type="button" class="q-ti2" data-tv="h|21">21</button><button type="button" class="q-ti2" data-tv="h|22">22</button><button type="button" class="q-ti2" data-tv="h|23">23</button></div><div data-tk="m"><button type="button" class="q-ti2" data-tv="m|0">00</button><button type="button" class="q-ti2" data-tv="m|1">01</button><button type="button" class="q-ti2" data-tv="m|2">02</button><button type="button" class="q-ti2" data-tv="m|3">03</button><button type="button" class="q-ti2" data-tv="m|4">04</button><button type="button" class="q-ti2" data-tv="m|5">05</button><button type="button" class="q-ti2" data-tv="m|6">06</button><button type="button" class="q-ti2" data-tv="m|7">07</button><button type="button" class="q-ti2" data-tv="m|8">08</button><button type="button" class="q-ti2" data-tv="m|9">09</button><button type="button" class="q-ti2" data-tv="m|10">10</button><button type="button" class="q-ti2" data-tv="m|11">11</button><button type="button" class="q-ti2" data-tv="m|12">12</button><button type="button" class="q-ti2" data-tv="m|13">13</button><button type="button" class="q-ti2" data-tv="m|14">14</button><button type="button" class="q-ti2" data-tv="m|15">15</button><button type="button" class="q-ti2" data-tv="m|16">16</button><button type="button" class="q-ti2" data-tv="m|17">17</button><button type="button" class="q-ti2" data-tv="m|18">18</button><button type="button" class="q-ti2" data-tv="m|19">19</button><button type="button" class="q-ti2" data-tv="m|20">20</button><button type="button" class="q-ti2" data-tv="m|21">21</button><button type="button" class="q-ti2" data-tv="m|22">22</button><button type="button" class="q-ti2" data-tv="m|23">23</button><button type="button" class="q-ti2" data-tv="m|24">24</button><button type="button" class="q-ti2" data-tv="m|25">25</button><button type="button" class="q-ti2" data-tv="m|26">26</button><button type="button" class="q-ti2" data-tv="m|27">27</button><button type="button" class="q-ti2" data-tv="m|28">28</button><button type="button" class="q-ti2" data-tv="m|29">29</button><button type="button" class="q-ti2 on" data-tv="m|30">30</button><button type="button" class="q-ti2" data-tv="m|31">31</button><button type="button" class="q-ti2" data-tv="m|32">32</button><button type="button" class="q-ti2" data-tv="m|33">33</button><button type="button" class="q-ti2" data-tv="m|34">34</button><button type="button" class="q-ti2" data-tv="m|35">35</button><button type="button" class="q-ti2" data-tv="m|36">36</button><button type="button" class="q-ti2" data-tv="m|37">37</button><button type="button" class="q-ti2" data-tv="m|38">38</button><button type="button" class="q-ti2" data-tv="m|39">39</button><button type="button" class="q-ti2" data-tv="m|40">40</button><button type="button" class="q-ti2" data-tv="m|41">41</button><button type="button" class="q-ti2" data-tv="m|42">42</button><button type="button" class="q-ti2" data-tv="m|43">43</button><button type="button" class="q-ti2" data-tv="m|44">44</button><button type="button" class="q-ti2" data-tv="m|45">45</button><button type="button" class="q-ti2" data-tv="m|46">46</button><button type="button" class="q-ti2" data-tv="m|47">47</button><button type="button" class="q-ti2" data-tv="m|48">48</button><button type="button" class="q-ti2" data-tv="m|49">49</button><button type="button" class="q-ti2" data-tv="m|50">50</button><button type="button" class="q-ti2" data-tv="m|51">51</button><button type="button" class="q-ti2" data-tv="m|52">52</button><button type="button" class="q-ti2" data-tv="m|53">53</button><button type="button" class="q-ti2" data-tv="m|54">54</button><button type="button" class="q-ti2" data-tv="m|55">55</button><button type="button" class="q-ti2" data-tv="m|56">56</button><button type="button" class="q-ti2" data-tv="m|57">57</button><button type="button" class="q-ti2" data-tv="m|58">58</button><button type="button" class="q-ti2" data-tv="m|59">59</button></div><div data-tk="s"><button type="button" class="q-ti2 on" data-tv="s|0">00</button><button type="button" class="q-ti2" data-tv="s|1">01</button><button type="button" class="q-ti2" data-tv="s|2">02</button><button type="button" class="q-ti2" data-tv="s|3">03</button><button type="button" class="q-ti2" data-tv="s|4">04</button><button type="button" class="q-ti2" data-tv="s|5">05</button><button type="button" class="q-ti2" data-tv="s|6">06</button><button type="button" class="q-ti2" data-tv="s|7">07</button><button type="button" class="q-ti2" data-tv="s|8">08</button><button type="button" class="q-ti2" data-tv="s|9">09</button><button type="button" class="q-ti2" data-tv="s|10">10</button><button type="button" class="q-ti2" data-tv="s|11">11</button><button type="button" class="q-ti2" data-tv="s|12">12</button><button type="button" class="q-ti2" data-tv="s|13">13</button><button type="button" class="q-ti2" data-tv="s|14">14</button><button type="button" class="q-ti2" data-tv="s|15">15</button><button type="button" class="q-ti2" data-tv="s|16">16</button><button type="button" class="q-ti2" data-tv="s|17">17</button><button type="button" class="q-ti2" data-tv="s|18">18</button><button type="button" class="q-ti2" data-tv="s|19">19</button><button type="button" class="q-ti2" data-tv="s|20">20</button><button type="button" class="q-ti2" data-tv="s|21">21</button><button type="button" class="q-ti2" data-tv="s|22">22</button><button type="button" class="q-ti2" data-tv="s|23">23</button><button type="button" class="q-ti2" data-tv="s|24">24</button><button type="button" class="q-ti2" data-tv="s|25">25</button><button type="button" class="q-ti2" data-tv="s|26">26</button><button type="button" class="q-ti2" data-tv="s|27">27</button><button type="button" class="q-ti2" data-tv="s|28">28</button><button type="button" class="q-ti2" data-tv="s|29">29</button><button type="button" class="q-ti2" data-tv="s|30">30</button><button type="button" class="q-ti2" data-tv="s|31">31</button><button type="button" class="q-ti2" data-tv="s|32">32</button><button type="button" class="q-ti2" data-tv="s|33">33</button><button type="button" class="q-ti2" data-tv="s|34">34</button><button type="button" class="q-ti2" data-tv="s|35">35</button><button type="button" class="q-ti2" data-tv="s|36">36</button><button type="button" class="q-ti2" data-tv="s|37">37</button><button type="button" class="q-ti2" data-tv="s|38">38</button><button type="button" class="q-ti2" data-tv="s|39">39</button><button type="button" class="q-ti2" data-tv="s|40">40</button><button type="button" class="q-ti2" data-tv="s|41">41</button><button type="button" class="q-ti2" data-tv="s|42">42</button><button type="button" class="q-ti2" data-tv="s|43">43</button><button type="button" class="q-ti2" data-tv="s|44">44</button><button type="button" class="q-ti2" data-tv="s|45">45</button><button type="button" class="q-ti2" data-tv="s|46">46</button><button type="button" class="q-ti2" data-tv="s|47">47</button><button type="button" class="q-ti2" data-tv="s|48">48</button><button type="button" class="q-ti2" data-tv="s|49">49</button><button type="button" class="q-ti2" data-tv="s|50">50</button><button type="button" class="q-ti2" data-tv="s|51">51</button><button type="button" class="q-ti2" data-tv="s|52">52</button><button type="button" class="q-ti2" data-tv="s|53">53</button><button type="button" class="q-ti2" data-tv="s|54">54</button><button type="button" class="q-ti2" data-tv="s|55">55</button><button type="button" class="q-ti2" data-tv="s|56">56</button><button type="button" class="q-ti2" data-tv="s|57">57</button><button type="button" class="q-ti2" data-tv="s|58">58</button><button type="button" class="q-ti2" data-tv="s|59">59</button></div></div><div class="ft"><button type="button" class="pl live" style="--tx:#00AAA6;--bg:transparent;--bg-h:#F2F3F5;--bg-a:#E5E6EB" data-now="">此刻</button><button data-tok="" type="button" class="pb live" style="--h:24px;--px:11px;--r:4px;--fs:12px;--lh:20px;--is:12px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="确定">确定</button></div></div></span>
```

## Transfer 数据穿梭框

在两栏之间移动选项。勾选后点中间按钮移动，表头复选框可全选。

- Figma：[115965:125943](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125943)
- 变体概况：89 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 面板 | 描边 color-border-2，圆角 4px |
| 表头 | 内边距 9px 12px 9px 16px，color-fill-1 底，右侧显示已选数量 |
| 移动按钮 | 32×32px 圆形，color-fill-1 底，描边 color-border-3，间距 12px |
| 两栏间距 | 20px |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| transfer | 搜索 | false / true |
| transfer | 单向 | false / true |
| transfer | 操作 | false / true |
| transfer | 分页 | false / true |
| transfer | 拖拽 | false / true |

### 实例：数据穿梭框

```html
<div class="q-tf" id="tf1"><div class="q-tfp" data-cg=""><div class="hd"><span class="q-cb" data-all="" role="checkbox" aria-checked="false" tabindex="0"><i></i>待选品类</span><small>0 / 7</small></div><div class="ls"><span class="q-cb" data-v="家用空调" role="checkbox" aria-checked="false" tabindex="0"><i></i>家用空调</span><span class="q-cb" data-v="商用空调" role="checkbox" aria-checked="false" tabindex="0"><i></i>商用空调</span><span class="q-cb" data-v="冰箱" role="checkbox" aria-checked="false" tabindex="0"><i></i>冰箱</span><span class="q-cb" data-v="冷柜" role="checkbox" aria-checked="false" tabindex="0"><i></i>冷柜</span><span class="q-cb" data-v="洗衣机" role="checkbox" aria-checked="false" tabindex="0"><i></i>洗衣机</span><span class="q-cb" data-v="厨电" role="checkbox" aria-checked="false" tabindex="0"><i></i>厨电</span><span class="q-cb" data-v="热水器" role="checkbox" aria-checked="false" tabindex="0"><i></i>热水器</span></div></div><div class="q-tfo"><button type="button" class="q-rb" data-tf="R" disabled="" aria-label="移到右侧"><svg data-icon="right" class="i"/></button><button type="button" class="q-rb" data-tf="L" disabled="" aria-label="移到左侧"><svg data-icon="left" class="i"/></button></div><div class="q-tfp" data-cg=""><div class="hd"><span class="q-cb" data-all="" role="checkbox" aria-checked="false" tabindex="0"><i></i>已选品类</span><small>0 / 2</small></div><div class="ls"><span class="q-cb" data-v="电视" role="checkbox" aria-checked="false" tabindex="0"><i></i>电视</span><span class="q-cb" data-v="激光显示" role="checkbox" aria-checked="false" tabindex="0"><i></i>激光显示</span></div></div></div>
```

## TreeSelect 树选择

在下拉面板中以树的形式选择节点。

- Figma：[115965:125944](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125944)
- 变体概况：中 / 大 / 小 / 迷你

### 样式参数

| 参数 | 值 |
| --- | --- |
| 触发器 | 同 Select |
| 下拉面板 | dropdown 样式，内放 tree，节点高 32px |
| 选中节点 | primary-7 #009093 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| treeselect | 尺寸 | 中 / 大 / 小 / 迷你 |
| treeselect | 聚焦 | false / true |

### 实例：树选择

点三角展开，点名称选中

```html
<span class="q-wrap" id="ts1"><span class="q-in q-sel" style="--w:280px" data-dd="" tabindex="0"><span class="v"><span class="q-ph">请选择产品线</span></span><svg data-icon="down" class="i ar"/></span><div class="q-pop" style="width:280px;padding:4px"><div class="q-tree" style="width:auto"><div class="q-tn open" style="padding-left:0px" data-t="空气事业部"><span class="swt"><svg data-icon="caret-right" class="i"/></span><span class="t">空气事业部</span></div><div class="q-tkid open"><div class="q-tn open" style="padding-left:24px" data-t="家用空调"><span class="swt"><svg data-icon="caret-right" class="i"/></span><span class="t">家用空调</span></div><div class="q-tkid open"><div class="q-tn" style="padding-left:48px" data-t="挂机"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="t">挂机</span></div><div class="q-tn" style="padding-left:48px" data-t="柜机"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="t">柜机</span></div><div class="q-tn d" style="padding-left:48px" data-t="新风机"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="t">新风机</span></div></div><div class="q-tn" style="padding-left:24px" data-t="商用空调"><span class="swt"><svg data-icon="caret-right" class="i"/></span><span class="t">商用空调</span></div><div class="q-tkid"><div class="q-tn" style="padding-left:48px" data-t="多联机"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="t">多联机</span></div><div class="q-tn" style="padding-left:48px" data-t="冷水机组"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="t">冷水机组</span></div></div></div><div class="q-tn" style="padding-left:0px" data-t="冰箱事业部"><span class="swt"><svg data-icon="caret-right" class="i"/></span><span class="t">冰箱事业部</span></div><div class="q-tkid"><div class="q-tn" style="padding-left:24px" data-t="冰箱"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="t">冰箱</span></div><div class="q-tn" style="padding-left:24px" data-t="冷柜"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="t">冷柜</span></div></div><div class="q-tn" style="padding-left:0px" data-t="视像事业部"><span class="swt"><svg data-icon="caret-right" class="i"/></span><span class="t">视像事业部</span></div><div class="q-tkid"><div class="q-tn" style="padding-left:24px" data-t="电视"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="t">电视</span></div><div class="q-tn" style="padding-left:24px" data-t="激光显示"><span class="swt no"><svg data-icon="caret-right" class="i"/></span><span class="t">激光显示</span></div></div></div></div></span>
```

## Upload 上传

选择或拖拽文件上传，显示上传进度、成功和失败状态，失败后可以重试。

- Figma：[115965:125945](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=115965-125945)
- 变体概况：62 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 文件项 | 宽 360px，内边距 7px 12px，color-fill-1 底，圆角 2px，图标与文字间距 12px |
| 失败 | 文件名 danger-6，“点击重试”12 / 20 primary-6 |
| 拖拽区 | 宽 400px，内边距 50px 16px，color-fill-2 底，color-border-2 描边，圆角 2px |
| 拖拽区文字 | 14 / 22 color-text-1，说明 12 / 20 color-text-3 |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| upload | 类型 | 文件列表 / 图片列表 |
| upload | 触发器 | 按钮 / 拖拽 |
| upload-trigger | 拖拽 | false / true |
| upload-trigger | 悬停 | false / true |
| upload/list | 类型 | 文件列表 / 图片列表 |
| upload/list | 数量 | 2 / 3 / 4 / 5 |

### 实例：点击上传

选择真实文件，上传为模拟过程

```html
<div class="q-vert"><span><button data-ufb="" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="点击上传"><svg data-icon="upload" class="i"/>点击上传</button><input type="file" multiple="" hidden="" data-uf=""></span><div class="q-fl" id="ul1"><div class="q-fi" data-fid="1"><svg data-icon="file" class="i"/><span class="nm">2026-07 经营月报.xlsx</span><svg data-icon="check-circle-fill" class="i ok"/><button type="button" class="del" data-fdel="" aria-label="删除"><svg data-icon="delete" class="i"/></button></div><div class="q-fi err" data-fid="2"><svg data-icon="file" class="i"/><span class="nm">employeelist.doc</span><button type="button" class="rt" data-retry="">点击重试</button><button type="button" class="del" data-fdel="" aria-label="删除"><svg data-icon="delete" class="i"/></button></div></div></div>
```

### 实例：拖拽上传

```html
<div class="q-drag" data-drop="" tabindex="0"><svg data-icon="plus" class="i"/><span><b>点击或拖拽文件到此处上传</b><small>支持 pdf、png、jpg</small></span></div>
```

