# 其他组件

每个组件包含：用途、Figma 节点、样式参数（读自 Figma，个别标注为假设）、Figma 变体属性、静态 HTML 实例。

HTML 实例的用法：
- 样式来自 `assets/pangea-components.css`，类名统一 `q-` 前缀；按钮是 `.pb`，颜色和尺寸写在行内 CSS 变量里。
- `<svg data-icon="名称" class="i"/>` 是图标占位，替换成 `assets/icons/名称.svg` 的内容（单色图标用 `currentColor`）。
- 实例里的 `data-*` 属性是站点交互用的钩子，交互逻辑需要自己实现；示例数据只用于演示。

## ActionBar 操作栏

放在列表或表格上方的一行操作：左侧是按钮组，右侧插槽放视图切换、刷新、设置等工具。

- Figma：[150592:26362](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=150592-26362)
- 变体概况：19 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 容器 | 横向排列，按钮组靠左，插槽靠右（Figma 示例宽 1000px / 800px） |
| 按钮组 | 小号按钮，间距 8px，第一个是主要按钮，其余是次要按钮 |
| 插槽 | 间距 8px，放图标单选按钮组和只有图标的小号次要按钮 |
| 图标单选按钮组 | 内边距 3px，圆角 4px color-fill-2 #F2F3F5 |
| 选中项 | 白底，圆角 2px，左右内边距 12px，图标 14px |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| button-group | 数量 | 4 |
| radio-button-group | 尺寸 | 小 |
| radio-button-group | 图标 | true |
| radio-button-group | 数量 | 2 |
| radio-button-group | ↳ 选中 | 1 |

另有布尔属性：插槽

### 实例：有插槽

右侧切换列表 / 卡片视图

```html
<div class="q-vert" style="width:100%;gap:12px"><div class="q-acb"><div class="q-acbg"><button data-abt="" type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="创建">创建</button><button data-abt="" type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="导入">导入</button><button data-abt="" type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="导出">导出</button><button data-abt="" type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="打印">打印</button></div><span class="sp"></span><div class="q-acbs"><span class="q-rbi" role="radiogroup" aria-label="视图"><button type="button" class="on" data-abv="list" role="radio" aria-checked="true" aria-label="列表视图" title="列表视图"><svg data-icon="list" class="i"/></button><button type="button" class="" data-abv="apps" role="radio" aria-checked="false" aria-label="卡片视图" title="卡片视图"><svg data-icon="apps" class="i"/></button></span><button aria-label="刷新" title="刷新" data-abr="" type="button" class="pb io live" style="--h:28px;--px:6px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;"><svg data-icon="refresh" class="i"/></button><button aria-label="列设置" title="列设置" data-abt="" type="button" class="pb io live" style="--h:28px;--px:6px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;"><svg data-icon="settings" class="i"/></button></div></div><div id="abb"><div class="q-tbw"><table class="q-tb s"><thead><tr><th>报表名称</th><th>负责人</th><th>更新日期</th></tr></thead><tbody><tr><td>空气事业部经营月报</td><td>王凡玄</td><td>2026-07-31</td></tr><tr><td>内销家空利润分析</td><td>李书萍</td><td>2026-07-28</td></tr><tr><td>海外库存周转</td><td>赵吾光</td><td>2026-07-25</td></tr><tr><td>商空订单交付</td><td>郑盈</td><td>2026-07-20</td></tr></tbody></table></div></div></div>
```

### 实例：无插槽

```html
<div class="q-acb"><div class="q-acbg"><button data-abt="" type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="创建">创建</button><button data-abt="" type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="导入">导入</button><button data-abt="" type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="导出">导出</button><button data-abt="" type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="打印">打印</button></div></div>
```

## Approval 流程审批专用

流程审批页面专用：流程处理（审批记录与处理表单）、流程图和传阅记录三个页签。

- Figma：[150651:24301](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=150651-24301)
- 变体概况：112 个组件与变体

### 样式参数

| 参数 | 值 |
| --- | --- |
| 容器 | 宽 1200px，白底，圆角 4px；内容区内边距 16px，区块间距 16px |
| 页签 | 线条页签，大号：内边距 11px 0，选中 14 / 22 Semibold primary-6，下划线 2px |
| 审批记录 | 中号带边框表格，表头 color-fill-2；列宽 200 / 140 / 100 / 100 / 200px |
| 处理表单 | 带边框描述列表，标签列宽 100px，单元格内边距 9px 20px color-fill-2 #F2F3F5 |
| 操作 | 单选组：通过、转办、沟通、驳回、不通过、加签，每项对应不同表单项 |
| 以发起人身份操作 | 文字链接 + 下拉菜单：催办、撤回、废弃 |

> 说明：流程图页签在 Figma 中只是“流程图嵌入区域”占位，这里画的节点图是示例，实际由流程引擎渲染。

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| approval-process | 类型 | 流程处理 / 流程图 / 传阅记录 |
| approval-process/processing | 操作 | 通过 / 转办 / 沟通 / 驳回 / 不通过 / 加签 / 同意 / 不同意 |

### 实例：流程审批

切换“操作”会改变下方表单项，提交后追加到审批记录

```html
<div class="q-apv"><div class="q-tl l" id="aptab" role="tablist"><button type="button" class="on" role="tab">流程处理</button><button type="button" class="" role="tab">流程图</button><button type="button" class="" role="tab">传阅记录</button></div><div class="q-appn" data-p="0"><div class="q-apbar"><span id="aprc" class="q-cb on" role="checkbox" aria-checked="true" tabindex="0"><i></i>显示审批记录</span><span class="sp"></span><span class="q-wrap"><a class="q-aplk" data-dd="" role="button" tabindex="0">以发起人身份操作<svg data-icon="down" class="i"/></a><div class="q-pop" style="left:auto;right:0;min-width:112px"><div class="q-mi" data-apx="催办">催办</div><div class="q-mi" data-apx="撤回">撤回</div><div class="q-mi" data-apx="废弃">废弃</div></div></span></div> <div class="q-tbw" id="aprec"><table class="q-tb"><thead><tr><th style="width:200px">节点名称</th><th style="width:140px">操作者</th><th style="width:100px">操作</th><th>处理意见</th><th style="width:200px">时间</th></tr></thead><tbody id="aprb"><tr><td>发起节点</td><td>张益达</td><td>提交</td><td class="opn">--</td><td>2024-04-09 11:22:14</td></tr><tr><td>部门长审批</td><td>赵鹃</td><td>同意</td><td class="opn">同意。使用对方提供合同模板，金额和税额描述符合集团规定。</td><td>2024-04-14 04:41:11</td></tr><tr><td>部门副总经理</td><td>何安其</td><td>转办</td><td class="opn">--</td><td>2024-04-14 15:46:43</td></tr><tr><td>部门总经理</td><td>周家福</td><td>同意</td><td class="opn">同意</td><td>2024-04-20 14:48:40</td></tr></tbody></table></div> <table class="q-ds b l q-apds"><tbody><tr><td class="k">当前处理人</td><td>部门长审批：张益达,吴迪</td></tr><tr><td class="k">操作</td><td><div class="q-row" data-rg="" id="apop" style="gap:24px"><span class="q-rd on" role="radio" aria-checked="true" tabindex="0"><i></i>通过</span><span class="q-rd" role="radio" aria-checked="false" tabindex="0"><i></i>转办</span><span class="q-rd" role="radio" aria-checked="false" tabindex="0"><i></i>沟通</span><span class="q-rd" role="radio" aria-checked="false" tabindex="0"><i></i>驳回</span><span class="q-rd" role="radio" aria-checked="false" tabindex="0"><i></i>不通过</span><span class="q-rd" role="radio" aria-checked="false" tabindex="0"><i></i>加签</span></div></td></tr></tbody><tbody id="apdyn"><tr><td class="k">即将流向</td><td>LDAP负责人审批：李敏,孙铭阳</td></tr></tbody> <tbody><tr><td class="k">处理意见<b class="rq">*</b></td><td><div class="q-vert" style="gap:8px;width:100%"><span class="q-wrap" data-sel="" id="apq"><span class="q-in q-sel" style="--w:160px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v"><span class="q-ph">快速审批</span></span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi" data-v="同意">同意</div><div class="q-mi" data-v="不同意">不同意</div></div></span><span class="q-in ta" style="--w:100%"><textarea id="apt" placeholder="请输入" aria-label="处理意见"></textarea></span></div></td></tr> <tr><td class="k">附件</td><td><div class="q-vert" style="gap:8px"><button data-apu="" type="button" class="pb live" style="--h:28px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="点击上传"><svg data-icon="upload" class="i"/>点击上传</button><div class="q-fl" id="apf"><div class="q-fi"><svg data-icon="attachment" class="i"/><span class="nm">此处为附件标题.docx</span><button type="button" class="del" data-apfd="0" aria-label="删除附件"><svg data-icon="delete" class="i"/></button></div></div></div></td></tr></tbody></table> <div class="q-apft"><button data-aps="" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="提交">提交</button><button data-apc="" type="button" class="pb live" style="--h:32px;--px:15px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="取消">取消</button></div></div><div class="q-appn" data-p="1" hidden=""><div class="q-apflow"><span class="cap">流程图嵌入区域</span><div class="fl"><div class="nd d"><b>发起节点</b><small>张益达</small></div><i class="ar d"></i><div class="nd d"><b>部门长审批</b><small>赵鹃</small></div><i class="ar d"></i><div class="nd d"><b>部门副总经理</b><small>何安其</small></div><i class="ar d"></i><div class="nd c"><b>部门长审批</b><small>张益达,吴迪</small></div><i class="ar"></i><div class="nd "><b>LDAP负责人审批</b><small>李敏,孙铭阳</small></div><i class="ar"></i><div class="nd "><b>结束节点</b></div></div><small class="lg"><span class="d">已处理</span><span class="c">当前节点</span><span>未到达</span></small></div></div><div class="q-appn" data-p="2" hidden=""><div class="q-tbw"><table class="q-tb"><thead><tr><th>传阅对象</th><th>传阅发起人</th><th>传阅时间</th></tr></thead><tbody id="apcr"><tr><td>何引琪</td><td>张益达</td><td>2024-07-17 01:52:07</td></tr><tr><td>谢倩</td><td>张益达</td><td>2024-07-16 02:52:07</td></tr><tr><td>李鹏</td><td>张益达</td><td>2024-07-15 03:52:07</td></tr><tr><td>赵天宇</td><td>张益达</td><td>2024-07-14 04:52:07</td></tr><tr><td>郑以轩</td><td>张益达</td><td>2024-07-13 05:52:07</td></tr></tbody></table></div><div id="apcp"><div class="q-pg" style="margin:12px 0 0"><span>共50条</span><button type="button" data-cpg="1" class="on">1</button><button type="button" data-cpg="2" class="">2</button><button type="button" data-cpg="3" class="">3</button><button type="button" data-cpg="4" class="">4</button><button type="button" data-cpg="5" class="">5</button><span style="padding:0 6px;color:#86909C">…</span><button type="button" data-cpg="10">10</button></div></div></div></div>
```

## Condition 条件配置

用“字段 + 运算符 + 值”配置筛选条件，条件之间用“且 / 或”连接，可以加同级条件或嵌套子级条件。

- Figma：[150602:9397](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=150602-9397)
- 变体概况：条件数量：1 / 2 / N

### 样式参数

| 参数 | 值 |
| --- | --- |
| 条件行 | 字段选择器 168px、运算符 100px、值输入框 168px，间距 8px |
| 删除按钮 | 只有图标的次要危险按钮，图标 delete 14px danger-1 #FFECE8 |
| 添加按钮 | 只有图标的次要按钮，菜单：同级条件、子级条件 |
| 连接符 | 选择器 60px，“且 / 或” |
| 连接线 | 1px color-border-2，圆角 4px，上下各留 16px 对齐首末行中线 |
| 行间距 | 16px |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| condition | 条件数量 | N / 1 / 2 |

另有布尔属性：展开添加条件菜单

### 实例：条件配置

右侧 + 号选择“同级条件”或“子级条件”；左侧“且 / 或”可切换

```html
<div class="q-vert" style="width:100%;gap:16px"><div id="cd1"><div class="q-cdg"><div class="cjn"><span class="cln t"></span><span class="q-wrap" data-sel="" data-cj="5"><span class="q-in q-sel" style="--w:60px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v">且</span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi on" data-v="且">且</div><div class="q-mi" data-v="或">或</div></div></span><span class="cln b"></span></div><div class="cit"><div class="q-cdi"><span class="q-wrap" data-sel="" data-cf="1|f"><span class="q-in q-sel" style="--w:168px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v">收入</span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi on" data-v="收入">收入</div><div class="q-mi" data-v="毛利率">毛利率</div><div class="q-mi" data-v="完成率">完成率</div><div class="q-mi" data-v="区域">区域</div><div class="q-mi" data-v="品类">品类</div></div></span><span class="q-wrap" data-sel="" data-cf="1|o"><span class="q-in q-sel" style="--w:100px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v">大于</span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi" data-v="等于">等于</div><div class="q-mi" data-v="不等于">不等于</div><div class="q-mi on" data-v="大于">大于</div><div class="q-mi" data-v="小于">小于</div><div class="q-mi" data-v="包含">包含</div></div></span><span class="q-in" style="--w:168px"><input placeholder="请输入" value="5000" data-cv="1" aria-label="条件值"></span> <span class="cbt"><button aria-label="删除条件" title="删除条件" data-cdel="1" type="button" class="pb io live" style="--h:32px;--px:8px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#FFECE8;--bd:transparent;--tx:#F53F3F;--bg-h:#FDCDC5;--bd-h:transparent;--tx-h:#F53F3F;--bg-a:#FBACA3;--bd-a:transparent;--tx-a:#F53F3F;"><svg data-icon="delete" class="i"/></button><span class="q-wrap"><button aria-label="添加条件" title="添加条件" data-dd="" type="button" class="pb io live" style="--h:32px;--px:8px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;"><svg data-icon="plus" class="i"/></button><div class="q-pop" role="menu" style="left:auto;right:0;min-width:120px"><div class="q-mi" data-cadd="1|s">同级条件</div><div class="q-mi" data-cadd="1|c">子级条件</div></div></span></span></div><div class="q-cdg"><div class="cjn"><span class="cln t"></span><span class="q-wrap" data-sel="" data-cj="4"><span class="q-in q-sel" style="--w:60px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v">或</span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi" data-v="且">且</div><div class="q-mi on" data-v="或">或</div></div></span><span class="cln b"></span></div><div class="cit"><div class="q-cdi"><span class="q-wrap" data-sel="" data-cf="2|f"><span class="q-in q-sel" style="--w:168px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v">区域</span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi" data-v="收入">收入</div><div class="q-mi" data-v="毛利率">毛利率</div><div class="q-mi" data-v="完成率">完成率</div><div class="q-mi on" data-v="区域">区域</div><div class="q-mi" data-v="品类">品类</div></div></span><span class="q-wrap" data-sel="" data-cf="2|o"><span class="q-in q-sel" style="--w:100px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v">等于</span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi on" data-v="等于">等于</div><div class="q-mi" data-v="不等于">不等于</div><div class="q-mi" data-v="大于">大于</div><div class="q-mi" data-v="小于">小于</div><div class="q-mi" data-v="包含">包含</div></div></span><span class="q-in" style="--w:168px"><input placeholder="请输入" value="华东" data-cv="2" aria-label="条件值"></span> <span class="cbt"><button aria-label="删除条件" title="删除条件" data-cdel="2" type="button" class="pb io live" style="--h:32px;--px:8px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#FFECE8;--bd:transparent;--tx:#F53F3F;--bg-h:#FDCDC5;--bd-h:transparent;--tx-h:#F53F3F;--bg-a:#FBACA3;--bd-a:transparent;--tx-a:#F53F3F;"><svg data-icon="delete" class="i"/></button><span class="q-wrap"><button aria-label="添加条件" title="添加条件" data-dd="" type="button" class="pb io live" style="--h:32px;--px:8px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;"><svg data-icon="plus" class="i"/></button><div class="q-pop" role="menu" style="left:auto;right:0;min-width:120px"><div class="q-mi" data-cadd="2|s">同级条件</div><div class="q-mi" data-cadd="2|c">子级条件</div></div></span></span></div><div class="q-cdi"><span class="q-wrap" data-sel="" data-cf="3|f"><span class="q-in q-sel" style="--w:168px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v">品类</span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi" data-v="收入">收入</div><div class="q-mi" data-v="毛利率">毛利率</div><div class="q-mi" data-v="完成率">完成率</div><div class="q-mi" data-v="区域">区域</div><div class="q-mi on" data-v="品类">品类</div></div></span><span class="q-wrap" data-sel="" data-cf="3|o"><span class="q-in q-sel" style="--w:100px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v">等于</span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi on" data-v="等于">等于</div><div class="q-mi" data-v="不等于">不等于</div><div class="q-mi" data-v="大于">大于</div><div class="q-mi" data-v="小于">小于</div><div class="q-mi" data-v="包含">包含</div></div></span><span class="q-in" style="--w:168px"><input placeholder="请输入" value="家空" data-cv="3" aria-label="条件值"></span> <span class="cbt"><button aria-label="删除条件" title="删除条件" data-cdel="3" type="button" class="pb io live" style="--h:32px;--px:8px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#FFECE8;--bd:transparent;--tx:#F53F3F;--bg-h:#FDCDC5;--bd-h:transparent;--tx-h:#F53F3F;--bg-a:#FBACA3;--bd-a:transparent;--tx-a:#F53F3F;"><svg data-icon="delete" class="i"/></button><span class="q-wrap"><button aria-label="添加条件" title="添加条件" data-dd="" type="button" class="pb io live" style="--h:32px;--px:8px;--r:4px;--fs:14px;--lh:22px;--is:14px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;"><svg data-icon="plus" class="i"/></button><div class="q-pop" role="menu" style="left:auto;right:0;min-width:120px"><div class="q-mi" data-cadd="3|s">同级条件</div><div class="q-mi" data-cadd="3|c">子级条件</div></div></span></span></div></div></div></div></div></div><div class="q-cdo"><span>生成的条件</span><code id="cdx">收入 大于 5000 且 (区域 等于 华东 或 品类 等于 家空)</code></div></div>
```

## FilePreview 预览容器

文件预览页面的外框：顶部是 64px 的品牌栏，下面是灰底预览区，文件放在居中的白色纸面上。

- Figma：[158919:1300](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=158919-1300)
- 变体概况：PC 1440 × 900 / 移动端 402 × 874

### 样式参数

| 参数 | 值 |
| --- | --- |
| 顶栏 | 高 64px，左右内边距 32px，白底，底部描边 1px color-border-2 |
| 标题 | logo 与“预览中心”间距 8px，16 / 24 color-text-1 |
| 预览区 | color-fill-2 #F2F3F5 |
| 纸面 | PC 宽 800px，上下内边距 12px 居中；移动端内边距 12px 铺满；白底，圆角 4px |
| 纸面投影 | 0 2px 8px rgba(0,0,0,.1) |

> 说明：顶栏为海信企业 logo 原图（126 × 20），不要改色、拉伸或用文字代替；纸面里的月报内容是示例。

### 实例：预览容器

PC 端纸面宽 800px，移动端铺满

```html
<div class="q-vert" style="width:100%;gap:16px"><div class="q-row"><span class="q-lab">设备</span><span class="q-cap s"><button type="button" class="on">PC</button><i></i><button type="button" class="">移动端</button></span></div><div id="fp1" class="q-fpw"><div class="q-fp"><div class="hd"><span class="lg"><svg role="img" aria-label="Hisense" width="126" height="20" viewBox="0 0 126 20" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M44.0541 11.1965L41.8991 10.2875C40.3949 9.67852 39.2549 9.22852 39.4534 8.60052C39.5665 8.25052 40.256 8.01652 42.3218 8.01352C45.5623 8.00952 48.7918 8.72052 48.7918 8.72052L49.0796 5.74852C49.0796 5.74852 46.0455 5.09152 42.422 5.04952C40.7789 5.02952 39.5972 5.09152 38.4641 5.25452C36.5443 5.53052 33.2968 6.37352 33.1361 9.07252C32.9694 11.8355 36.2516 13.0435 38.2558 13.8815L39.9177 14.5475C41.8128 15.3105 42.7038 15.5915 42.672 16.1555C42.6423 16.7735 41.3276 16.8755 39.5427 16.8185C36.3915 16.7185 33.0676 16.0985 33.0676 16.0985L32.8652 19.2975C32.8652 19.2975 35.2713 19.6805 40.0874 19.8135C40.3701 19.8205 40.6549 19.8235 40.9367 19.8235C44.4431 19.8235 48.7164 19.2725 49.1847 16.3325C49.6144 13.6355 46.7985 12.4345 44.0541 11.1965Z" fill-rule="evenodd" clip-rule="evenodd" fill="#00AAA6"></path><path d="M56.6015 10.9839C56.8694 9.47086 58.0273 7.93886 60.484 7.92286C64.0638 7.95586 63.8286 10.9839 63.8286 10.9839H56.6015ZM68.61 13.6929C69.8175 6.78486 63.7354 5.43786 62.3086 5.21986C61.7827 5.14986 61.2182 5.09886 60.602 5.09186C54.2143 5.03686 51.0195 9.09286 50.7516 12.4529C50.5055 15.4999 51.6545 19.9999 61.0386 19.9999C64.4874 19.9999 66.703 19.4879 67.6456 19.2149C67.7468 18.5749 67.9512 17.2649 68.1089 16.2569C67.6446 16.3609 64.8327 16.9649 61.7698 16.9649C61.6716 16.9649 61.5823 16.9609 61.4871 16.9599C57.2246 16.8119 56.3743 14.7049 56.3684 13.7399C56.3684 13.7399 56.3664 13.7189 56.3634 13.6929H68.61Z" fill-rule="evenodd" clip-rule="evenodd" fill="#00AAA6"></path><mask id="mask0_150_1987" style="mask-type:luminance" maskUnits="userSpaceOnUse" x="107" y="5" width="19" height="15"><path d="M107.443 5.09119H125.489V19.9997H107.443V5.09119Z" fill="white"></path></mask><g mask="url(#mask0_150_1987)"><path d="M113.323 10.9837C113.592 9.47074 114.749 7.93874 117.206 7.92274C120.784 7.95574 120.548 10.9837 120.548 10.9837H113.323ZM125.331 13.6927C126.538 6.78474 120.455 5.43774 119.031 5.21974C118.506 5.14974 117.939 5.09874 117.325 5.09174C110.935 5.03674 107.742 9.09274 107.472 12.4527C107.227 15.4997 108.376 19.9997 117.76 19.9997C121.21 19.9997 123.424 19.4877 124.37 19.2147C124.468 18.5747 124.673 17.2647 124.831 16.2567C124.366 16.3607 121.555 16.9647 118.491 16.9647C118.393 16.9647 118.303 16.9607 118.209 16.9597C113.946 16.8117 113.097 14.7047 113.091 13.7397C113.091 13.7397 113.091 13.7187 113.086 13.6927H125.331Z" fill-rule="evenodd" clip-rule="evenodd" fill="#00AAA6"></path></g><path d="M82.2933 10.2899C82.1346 12.8339 81.696 19.6939 81.696 19.6939H87.3148L87.918 10.1419C88.1859 5.80292 85.1389 5.48292 83.1228 5.27192C82.9888 5.25592 81.9183 5.16992 80.4528 5.16992C80.0708 5.16992 79.667 5.17592 79.2443 5.19192C75.7488 5.30992 71.3098 5.83292 71.3098 5.83292L70.4277 19.6939H76.0683L76.7539 8.44292C76.7539 8.44292 78.7542 8.15292 80.3317 8.22192C80.8675 8.24592 82.4213 8.21892 82.2933 10.2899Z" fill-rule="evenodd" clip-rule="evenodd" fill="#00AAA6"></path><mask id="mask1_150_1987" style="mask-type:luminance" maskUnits="userSpaceOnUse" x="25" y="0" width="7" height="4"><path d="M25.2441 0H31.4464V3.7619H25.2441V0Z" fill="white"></path></mask><g mask="url(#mask1_150_1987)"><path d="M30.1902 0H25.5259L25.2441 3.762H31.2647C31.2647 3.762 31.4195 1.617 31.4413 1.257C31.4929 0.414 31.1586 0 30.1902 0Z" fill-rule="evenodd" clip-rule="evenodd" fill="#00AAA6"></path></g><path d="M100.842 11.1953L98.6892 10.2853C97.1821 9.67727 96.043 9.22827 96.2395 8.60127C96.3526 8.25027 97.0451 8.01627 99.1109 8.01227C102.351 8.00827 105.578 8.72027 105.578 8.72027L105.868 5.74727C105.868 5.74727 102.834 5.09027 99.2091 5.04827C97.567 5.02927 96.3853 5.09027 95.2532 5.25327C93.3344 5.52927 90.0849 6.37327 89.9232 9.07127C89.7575 11.8353 93.0387 13.0423 95.0429 13.8813L96.7068 14.5453C98.6009 15.3103 99.4909 15.5893 99.4611 16.1533C99.4274 16.7743 98.1167 16.8733 96.3317 16.8163C93.1776 16.7183 89.8548 16.0993 89.8548 16.0993L89.6523 19.2963C89.6523 19.2963 92.0584 19.6783 96.8755 19.8113C97.1592 19.8183 97.442 19.8213 97.7238 19.8213C101.231 19.8213 105.504 19.2723 105.974 16.3313C106.402 13.6343 103.587 12.4333 100.842 11.1953Z" fill-rule="evenodd" clip-rule="evenodd" fill="#00AAA6"></path><path d="M16.4921 0L15.9623 6.893H7.14772L7.5823 1.257C7.59619 0.046 6.57721 0 6.0702 0H1.52499L0 19.722H6.15752L6.83121 11.005H15.6448L14.9701 19.722H21.1078L22.6278 0H16.4921Z" fill-rule="evenodd" clip-rule="evenodd" fill="#00AAA6"></path><path d="M25.0915 5.37061L23.9961 19.7216H30.0127L31.114 5.37061H25.0915Z" fill-rule="evenodd" clip-rule="evenodd" fill="#00AAA6"></path></svg></span><span class="t">预览中心</span></div><div class="bd"><div class="pg"><div class="q-fpd"><h3>空气事业部 2026 年 7 月经营月报</h3><p class="mt">经营管理部 · 2026-08-05 发布</p><h4>一、经营概况</h4><p>7 月实现收入 52.8 亿元，同比增长 6.3%；毛利率 21.4%，同比提高 0.8 个百分点。内销商空完成率 87.2%，低于预警线。</p> <table class="q-tb s"><thead><tr><th>指标</th><th style="text-align:right">本月</th><th style="text-align:right">同比</th></tr></thead><tbody><tr><td>收入（亿元）</td><td style="text-align:right">52.8</td><td style="text-align:right;color:#F53F3F">+6.3%</td></tr><tr><td>毛利率</td><td style="text-align:right">21.4%</td><td style="text-align:right;color:#F53F3F">+0.8pp</td></tr><tr><td>库存周转（天）</td><td style="text-align:right">38</td><td style="text-align:right;color:#00B42A">+3</td></tr></tbody></table> <h4>二、重点事项</h4><p>海外渠道补库完成；商空项目回款节奏偏慢，需在 8 月重点跟进。</p><div class="sk"><i></i><i></i><i style="width:60%"></i></div></div></div></div></div></div></div>
```

## PTContainer 门户卡片容器

门户首页的卡片容器：标题栏可放图标、标签、页签或选择器，右侧是更多操作。切到“调整”模式后可以拖动排序、拖右下角改变大小。

- Figma：[154299:30746](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=154299-30746)
- 变体概况：模式：默认 / 调整

### 样式参数

| 参数 | 值 |
| --- | --- |
| 容器 | 内边距 20px，内容间距 12px，白底，圆角 8px（Figma 360 × 244） |
| 默认投影 | 0 2px 6px rgba(0,0,0,.05) |
| 悬停投影 | 0 4px 12px rgba(0,0,0,.1) |
| 标题 | 16 / 20 Semibold color-text-1，图标 / 标题 / 插槽间距 8px |
| 标签插槽 | 12 / 20，圆角 4px 未匹配令牌 #E8F3FF |
| 更多操作 | 图标 14px，悬停出现 20px 圆形 color-fill-2 底，下拉菜单 |
| 调整模式 | 悬停描边 2px，右下角 16px 圆形手柄，白色 2px 描边 primary-7 #009093 |
| 卡片间距 | 示例 12px（Figma 门户示例卡片宽 449 / 450px，通栏 1372px） |

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| pt-container | 模式 | 默认 / 调整 |
| pt-container | 悬停&聚焦 | false / true |
| pt-container | 聚焦 | false |

另有布尔属性：插槽、操作、图标

### 实例：门户卡片

调整模式：拖动标题栏交换位置，拖动右下角圆点改变宽高

```html
<div class="q-vert" style="width:100%;gap:16px"><div class="q-row"><span class="q-lab">模式</span><span class="q-cap s"><button type="button" class="on">默认</button><i></i><button type="button" class="">调整</button></span><span class="q-out" id="pto">悬停卡片查看投影变化</span></div><div class="q-ptg" id="pt1"><div class="q-ptc" data-ptc="todo" style="grid-column:span 1;grid-row:span 2"><div class="hd"><div class="l"><svg data-icon="check-square" class="i"/><b>待办事项</b><span class="q-pttag">智能财务</span></div><span class="q-wrap"><button type="button" class="q-pti" data-dd="" aria-label="更多操作"><svg data-icon="more" class="i"/></button><div class="q-pop" role="menu" style="left:auto;right:0;min-width:112px"><div class="q-mi" data-ptm="操作1">操作1</div><div class="q-mi" data-ptm="操作2">操作2</div><div class="q-mi" data-ptm="操作3">操作3</div></div></span></div><div class="ct"><div class="q-ptl"><div><span>经营月报待审批</span><small>张益达</small></div><div><span>7 月预算调整确认</span><small>李书萍</small></div><div><span>库存呆滞专项复盘</span><small>赵吾光</small></div></div></div><span class="rs" data-ptr="todo" aria-hidden="true"></span></div><div class="q-ptc" data-ptc="kpi" style="grid-column:span 1;grid-row:span 2"><div class="hd"><div class="l"><b>经营指标</b><span class="q-trd q-pttb" id="ptkt"><button type="button" class="on">本月</button><button type="button" class="">本季</button><button type="button" class="">本年</button></span></div><span class="q-wrap"><button type="button" class="q-pti" data-dd="" aria-label="更多操作"><svg data-icon="more" class="i"/></button><div class="q-pop" role="menu" style="left:auto;right:0;min-width:112px"><div class="q-mi" data-ptm="操作1">操作1</div><div class="q-mi" data-ptm="操作2">操作2</div><div class="q-mi" data-ptm="操作3">操作3</div></div></span></div><div class="ct"><div class="q-ptk"><div><small>收入（亿元）</small><b>52.8</b></div><div><small>毛利率</small><b>21.4%</b></div><div><small>完成率</small><b>87.2%</b></div></div></div><span class="rs" data-ptr="kpi" aria-hidden="true"></span></div><div class="q-ptc" data-ptc="app" style="grid-column:span 1;grid-row:span 2"><div class="hd"><div class="l"><b>常用应用</b></div><span class="q-wrap"><button type="button" class="q-pti" data-dd="" aria-label="更多操作"><svg data-icon="more" class="i"/></button><div class="q-pop" role="menu" style="left:auto;right:0;min-width:112px"><div class="q-mi" data-ptm="操作1">操作1</div><div class="q-mi" data-ptm="操作2">操作2</div><div class="q-mi" data-ptm="操作3">操作3</div></div></span></div><div class="ct"><div class="q-pta"><button type="button" data-pta="经营看板"><svg data-icon="bar-chart" class="i"/><span>经营看板</span></button><button type="button" data-pta="明细报表"><svg data-icon="table" class="i"/><span>明细报表</span></button><button type="button" data-pta="指标查询"><svg data-icon="file-search" class="i"/><span>指标查询</span></button><button type="button" data-pta="订阅管理"><svg data-icon="calendar-clock" class="i"/><span>订阅管理</span></button><button type="button" data-pta="组织人员"><svg data-icon="user-group" class="i"/><span>组织人员</span></button><button type="button" data-pta="设置"><svg data-icon="settings" class="i"/><span>设置</span></button></div></div><span class="rs" data-ptr="app" aria-hidden="true"></span></div><div class="q-ptc" data-ptc="trend" style="grid-column:span 3;grid-row:span 3"><div class="hd"><div class="l"><b>收入趋势</b><span class="q-wrap" data-sel=""><span class="q-in q-sel bl" style="--w:120px" data-dd="" tabindex="0" role="combobox" aria-expanded="false"><span class="v">空气事业部</span><svg data-icon="down" class="i ar"/></span><div class="q-pop" role="listbox"><div class="q-mi on" data-v="空气事业部">空气事业部</div><div class="q-mi" data-v="冰箱事业部">冰箱事业部</div><div class="q-mi" data-v="视像事业部">视像事业部</div></div></span></div><span class="q-wrap"><button type="button" class="q-pti" data-dd="" aria-label="更多操作"><svg data-icon="more" class="i"/></button><div class="q-pop" role="menu" style="left:auto;right:0;min-width:112px"><div class="q-mi" data-ptm="操作1">操作1</div><div class="q-mi" data-ptm="操作2">操作2</div><div class="q-mi" data-ptm="操作3">操作3</div></div></span></div><div class="ct"><div class="q-ptt"><div><i style="height:62.295081967213115%"></i><span>1月</span></div><div><i style="height:68.85245901639344%"></i><span>2月</span></div><div><i style="height:65.57377049180327%"></i><span>3月</span></div><div><i style="height:77.04918032786885%"></i><span>4月</span></div><div><i style="height:73.77049180327869%"></i><span>5月</span></div><div><i style="height:83.60655737704919%"></i><span>6月</span></div><div><i style="height:86.88524590163934%"></i><span>7月</span></div><div><i style="height:80.32786885245902%"></i><span>8月</span></div><div><i style="height:90.1639344262295%"></i><span>9月</span></div><div><i style="height:95.08196721311475%"></i><span>10月</span></div><div><i style="height:88.52459016393442%"></i><span>11月</span></div><div><i style="height:100%"></i><span>12月</span></div></div></div><span class="rs" data-ptr="trend" aria-hidden="true"></span></div></div></div>
```

## UserPicker 人员选择器

选择人员的面板：可以从最近、流程相关人、组织架构中勾选，或按姓名、账号搜索；已选人员显示在底部。

- Figma：[151186:197](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=151186-197)
- 变体概况：最近 / 流程相关 / 组织架构 / 搜索结果

### 样式参数

| 参数 | 值 |
| --- | --- |
| 容器 | 800 × 448px，白底；顶部内边距 16px，间距 12px |
| 页签 | 胶囊页签，外框内边距 3px，圆角 2px，选中项白底 primary-6 文字 color-fill-2 #F2F3F5 |
| 搜索框 | 宽 280px，后缀 search 图标 14px |
| 列表区 | 768 × 320px，描边 color-border-2，圆角 4px，人员两列各 384px |
| 人员项 | 内边距 8px 12px，间距 8px，头像 32px；姓名 12 / 18 Semibold，部门 12 / 18 color-text-3 |
| 已选区 | “已选 N”胶囊按钮居中压在分割线上，可收起 color-fill-1 #F7F8FA |
| 已选项 | 内边距 4px 8px，圆角 40px，头像 16px，12 / 20，悬停出现 close-circle-fill 14px |
| 清空 | 12 / 20 danger-6 文字按钮，气泡确认“确定要清空已选列表吗？” |

> 说明：Figma 里头像是照片，这里用姓氏首字代替；人员和部门是示例数据。组织架构左侧在 Figma 中是带连接线的树，这里简化为缩进列表。

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| user-picker | 类型 | 最近 / 流程相关 / 组织架构 / 搜索结果 |
| user-picker/selected-item | 悬停 | false / true |
| user-picker/selected-item | 删除 | false / true |

另有布尔属性：流程相关人

### 实例：人员选择器

勾选人员、输入“李”或“zh”搜索、在组织架构里切换部门

```html
<div class="q-up" id="up1"><div class="tp"><div class="bar"><span class="q-upt" role="tablist"><button type="button" class="on" data-upt="最近" role="tab">最近</button><button type="button" class="" data-upt="流程相关人" role="tab">流程相关人</button><button type="button" class="" data-upt="组织架构" role="tab">组织架构</button></span><span class="q-in" style="--w:280px"><input placeholder="查询姓名/账号" value="" data-ups="" aria-label="查询姓名或账号"><svg data-icon="search" class="i"/></span></div><div class="ct" id="upc"><div class="q-upc1"><div class="q-upall" data-upall=""><span class="q-cb half" role="checkbox" aria-checked="false" tabindex="0"><i></i>全选</span></div><div class="q-upl"><div class="q-upu" data-upu="zhangyida3" role="checkbox" aria-checked="false" tabindex="0"><span class="q-cb"><i></i></span><span class="q-av" style="--s:32px;--fs:13px;background:#00AAA6">张</span><div class="nm"><b>张益达<span>(zhangyida3)</span></b><small title="海信集团/集团公司/流程IT与数据管理部/业务一室">海信集团/集团公司/流程IT与数据管理部/业务一室</small></div></div><div class="q-upu on" data-upu="lishuping" role="checkbox" aria-checked="true" tabindex="0"><span class="q-cb on"><i></i></span><span class="q-av" style="--s:32px;--fs:13px;background:#165DFF">李</span><div class="nm"><b>李书萍<span>(lishuping)</span></b><small title="海信集团/集团公司/流程IT与数据管理部/业务一室">海信集团/集团公司/流程IT与数据管理部/业务一室</small></div></div><div class="q-upu on" data-upu="wuxuanxuan" role="checkbox" aria-checked="true" tabindex="0"><span class="q-cb on"><i></i></span><span class="q-av" style="--s:32px;--fs:13px;background:#722ED1">吴</span><div class="nm"><b>吴萱萱<span>(wuxuanxuan)</span></b><small title="海信集团/集团公司/流程IT与数据管理部/业务二室">海信集团/集团公司/流程IT与数据管理部/业务二室</small></div></div><div class="q-upu on" data-upu="zhaowuguang" role="checkbox" aria-checked="true" tabindex="0"><span class="q-cb on"><i></i></span><span class="q-av" style="--s:32px;--fs:13px;background:#F77234">赵</span><div class="nm"><b>赵吾光<span>(zhaowuguang)</span></b><small title="海信集团/集团公司/流程IT与数据管理部/国内营销解决方案部">海信集团/集团公司/流程IT与数据管理部/国内营销解决方案部</small></div></div><div class="q-upu" data-upu="wangfanxuan" role="checkbox" aria-checked="false" tabindex="0"><span class="q-cb"><i></i></span><span class="q-av" style="--s:32px;--fs:13px;background:#0FC6C2">王</span><div class="nm"><b>王凡玄<span>(wangfanxuan)</span></b><small title="海信集团/集团公司/流程IT与数据管理部/人资解决方案部">海信集团/集团公司/流程IT与数据管理部/人资解决方案部</small></div></div><div class="q-upu" data-upu="zhengying" role="checkbox" aria-checked="false" tabindex="0"><span class="q-cb"><i></i></span><span class="q-av" style="--s:32px;--fs:13px;background:#3491FA">郑</span><div class="nm"><b>郑盈<span>(zhengying)</span></b><small title="海信集团/集团公司/流程IT与数据管理部/技术平台部">海信集团/集团公司/流程IT与数据管理部/技术平台部</small></div></div><div class="q-upu" data-upu="qianmengmeng" role="checkbox" aria-checked="false" tabindex="0"><span class="q-cb"><i></i></span><span class="q-av" style="--s:32px;--fs:13px;background:#9FDB1D">钱</span><div class="nm"><b>钱萌萌<span>(qianmengmeng)</span></b><small title="海信集团/集团公司/流程IT与数据管理部/业务二室">海信集团/集团公司/流程IT与数据管理部/业务二室</small></div></div></div></div></div></div><div class="q-upck" id="upk"><div class="q-updv"><button type="button" class="q-upn" data-uptg="" aria-expanded="true"><svg data-icon="down" class="i"/>已选 3</button></div><div class="q-upk"><div class="ls"><span class="q-upi"><span class="q-av" style="--s:16px;--fs:7px;background:#165DFF">李</span>李书萍<button type="button" data-uprm="lishuping" aria-label="移除 李书萍"><svg data-icon="close-circle-fill" class="i"/></button></span><span class="q-upi"><span class="q-av" style="--s:16px;--fs:7px;background:#722ED1">吴</span>吴萱萱<button type="button" data-uprm="wuxuanxuan" aria-label="移除 吴萱萱"><svg data-icon="close-circle-fill" class="i"/></button></span><span class="q-upi"><span class="q-av" style="--s:16px;--fs:7px;background:#F77234">赵</span>赵吾光<button type="button" data-uprm="zhaowuguang" aria-label="移除 赵吾光"><svg data-icon="close-circle-fill" class="i"/></button></span></div><span class="q-wrap"><button data-dd="" type="button" class="pb live" style="--h:24px;--px:11px;--r:4px;--fs:12px;--lh:20px;--is:12px;--bg:transparent;--bd:transparent;--tx:#F53F3F;--bg-h:#F2F3F5;--bd-h:transparent;--tx-h:#F53F3F;--bg-a:#E5E6EB;--bd-a:transparent;--tx-a:#F53F3F;" aria-label="清空">清空</button><div class="q-pcf" role="dialog" style="left:auto;right:-8px;transform:none"><div class="t"><svg data-icon="exclamation-circle-fill" class="i"/><span>确定要清空已选列表吗？</span></div><div class="ft"><button data-upcx="" type="button" class="pb live" style="--h:24px;--px:11px;--r:4px;--fs:12px;--lh:20px;--is:12px;--bg:#F7F8FA;--bd:#C9CDD4;--tx:#4E5969;--bg-h:#FFFFFF;--bd-h:#86909C;--tx-h:#1D2129;--bg-a:#F2F3F5;--bd-a:#86909C;--tx-a:#1D2129;" aria-label="取消">取消</button><button data-upclr="" type="button" class="pb live" style="--h:24px;--px:11px;--r:4px;--fs:12px;--lh:20px;--is:12px;--bg:#00AAA6;--bd:transparent;--tx:#FFFFFF;--bg-h:#22BBB3;--bd-h:transparent;--tx-h:#FFFFFF;--bg-a:#009093;--bd-a:transparent;--tx-a:#FFFFFF;" aria-label="确定">确定</button></div></div></span></div></div></div>
```

## SliderVerify 滑动验证

拖动滑块把拼图块移到缺口位置，用于登录、提交等需要人机验证的场景。

- Figma：[160491:2036](https://www.figma.com/design/9Vwl2qVz65nnrY6CgR4HpS?node-id=160491-2036)
- 变体概况：默认 / 滑动中 / 失败 / 成功

### 样式参数

| 参数 | 值 |
| --- | --- |
| 容器 | 宽 360px，白底，圆角 8px |
| 标题栏 | 内边距 12px 20px，标题 16 / 24 Semibold color-text-1，右侧换一张 / 关闭图标 16px，间距 16px，底部内阴影 1px #E5E6E8 |
| 内容区 | 内边距 20px，间距 16px；图片区 320 × 192px，圆角 8px，拼图块 56 × 56px |
| 滑轨 | 高 40px，圆角 8px color-fill-2 #F2F3F5 |
| 滑块 | 内边距 6px 16px，图标 28px，圆角 8px，投影 0 2px 8px rgba(0,0,0,.25) primary-7 #009093 |
| 已滑过区域 | 滑动中 #ADEEE4，失败 #FDCDC5，成功 #AFF0B5 |
| 结果遮罩 | rgba(255,255,255,.8)，图标 16px + 14 / 22 Semibold，失败 #F53F3F，成功 #00B42A |

> 说明：Figma 中图片区是一张照片，这里用矢量风景图代替；缺口位置每次随机生成。

### Figma 变体属性

| 组件集 | 属性 | 取值 |
| --- | --- | --- |
| slider-verify | 状态 | 默认 / 滑动中 / 失败 / 成功 |

### 实例：滑动验证

拖动滑块，让拼图块对准缺口后松开（误差 5px 内算成功）

```html
<div id="sv1"><div class="q-sv"><div class="hd"><b>拖动滑块完成拼图验证</b><span class="ac"><button type="button" data-svr="" aria-label="换一张" title="换一张"><svg data-icon="refresh" class="i"/></button><button type="button" data-svx="" aria-label="关闭" title="关闭"><svg data-icon="close" class="i"/></button></span></div><div class="bd"><div class="ar" style="background-image:url('data:image/svg+xml,%3Csvg%20xmlns%3D%27http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%27%20width%3D%27320%27%20height%3D%27192%27%20viewBox%3D%270%200%20320%20192%27%3E%3Cdefs%3E%3ClinearGradient%20id%3D%27s%27%20x1%3D%270%27%20y1%3D%270%27%20x2%3D%270%27%20y2%3D%271%27%3E%3Cstop%20offset%3D%270%27%20stop-color%3D%27%239BE3DC%27%2F%3E%3Cstop%20offset%3D%271%27%20stop-color%3D%27%23E8FFFB%27%2F%3E%3C%2FlinearGradient%3E%3C%2Fdefs%3E%3Crect%20width%3D%27320%27%20height%3D%27192%27%20fill%3D%27url(%23s)%27%2F%3E%3Ccircle%20cx%3D%27252%27%20cy%3D%2746%27%20r%3D%2722%27%20fill%3D%27%23FFF7E8%27%2F%3E%3Cpath%20d%3D%27M0%20132L52%2092L104%20124L168%2070L232%20118L276%2090L320%20112V192H0Z%27%20fill%3D%27%234DCBC0%27%2F%3E%3Cpath%20d%3D%27M0%20160L64%20126L132%20154L204%20118L272%20150L320%20132V192H0Z%27%20fill%3D%27%2300AAA6%27%2F%3E%3Cpath%20d%3D%27M0%20192V176L80%20158L160%20178L240%20160L320%20174V192Z%27%20fill%3D%27%23008685%27%2F%3E%3Cg%20fill%3D%27%23fff%27%20opacity%3D%27.85%27%3E%3Cellipse%20cx%3D%2770%27%20cy%3D%2740%27%20rx%3D%2726%27%20ry%3D%279%27%2F%3E%3Cellipse%20cx%3D%27150%27%20cy%3D%2730%27%20rx%3D%2718%27%20ry%3D%276%27%2F%3E%3C%2Fg%3E%3C%2Fsvg%3E')"><span class="hole" style="left:206px;top:64px"><svg viewBox="0 0 56 56"><path d="M4 12H18A6 6 0 1 1 30 12H44V26A6 6 0 1 1 44 38V52H4Z"></path></svg></span><span class="pc" style="left:0px;top:64px"><i style="background-image:url('data:image/svg+xml,%3Csvg%20xmlns%3D%27http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%27%20width%3D%27320%27%20height%3D%27192%27%20viewBox%3D%270%200%20320%20192%27%3E%3Cdefs%3E%3ClinearGradient%20id%3D%27s%27%20x1%3D%270%27%20y1%3D%270%27%20x2%3D%270%27%20y2%3D%271%27%3E%3Cstop%20offset%3D%270%27%20stop-color%3D%27%239BE3DC%27%2F%3E%3Cstop%20offset%3D%271%27%20stop-color%3D%27%23E8FFFB%27%2F%3E%3C%2FlinearGradient%3E%3C%2Fdefs%3E%3Crect%20width%3D%27320%27%20height%3D%27192%27%20fill%3D%27url(%23s)%27%2F%3E%3Ccircle%20cx%3D%27252%27%20cy%3D%2746%27%20r%3D%2722%27%20fill%3D%27%23FFF7E8%27%2F%3E%3Cpath%20d%3D%27M0%20132L52%2092L104%20124L168%2070L232%20118L276%2090L320%20112V192H0Z%27%20fill%3D%27%234DCBC0%27%2F%3E%3Cpath%20d%3D%27M0%20160L64%20126L132%20154L204%20118L272%20150L320%20132V192H0Z%27%20fill%3D%27%2300AAA6%27%2F%3E%3Cpath%20d%3D%27M0%20192V176L80%20158L160%20178L240%20160L320%20174V192Z%27%20fill%3D%27%23008685%27%2F%3E%3Cg%20fill%3D%27%23fff%27%20opacity%3D%27.85%27%3E%3Cellipse%20cx%3D%2770%27%20cy%3D%2740%27%20rx%3D%2726%27%20ry%3D%279%27%2F%3E%3Cellipse%20cx%3D%27150%27%20cy%3D%2730%27%20rx%3D%2718%27%20ry%3D%276%27%2F%3E%3C%2Fg%3E%3C%2Fsvg%3E');background-position:-206px -64px"></i><svg viewBox="0 0 56 56"><path d="M4 12H18A6 6 0 1 1 30 12H44V26A6 6 0 1 1 44 38V52H4Z"></path></svg></span></div><div id="svt"><div class="q-svt" style="--bc:#009093;--fc:transparent"><span class="fl" style="width:60px"></span><span class="bk" style="left:0px" data-svb="" role="slider" tabindex="0" aria-label="拖动滑块" aria-valuemin="0" aria-valuemax="260" aria-valuenow="0"><svg data-icon="arrow-right" class="i"/></span><span class="hint">向右拖动滑块</span></div></div></div></div></div>
```

### 实例：滑块四种状态

静态展示，不可拖动

```html
<div class="q-vert" style="gap:12px;width:320px"><div class="q-row" style="gap:12px;flex-wrap:nowrap;width:100%"><span class="q-lab" style="width:48px;flex:none">默认</span><div style="flex:1;pointer-events:none"><div class="q-svt" style="--bc:#009093;--fc:transparent"><span class="fl" style="width:60px"></span><span class="bk" style="left:0px"><svg data-icon="arrow-right" class="i"/></span></div></div></div><div class="q-row" style="gap:12px;flex-wrap:nowrap;width:100%"><span class="q-lab" style="width:48px;flex:none">滑动中</span><div style="flex:1;pointer-events:none"><div class="q-svt" style="--bc:#009093;--fc:#ADEEE4"><span class="fl" style="width:140px"></span><span class="bk" style="left:80px"><svg data-icon="arrow-right" class="i"/></span></div></div></div><div class="q-row" style="gap:12px;flex-wrap:nowrap;width:100%"><span class="q-lab" style="width:48px;flex:none">失败</span><div style="flex:1;pointer-events:none"><div class="q-svt" style="--bc:#F53F3F;--fc:#FDCDC5"><span class="fl" style="width:140px"></span><span class="bk" style="left:80px"><svg data-icon="close" class="i"/></span></div></div></div><div class="q-row" style="gap:12px;flex-wrap:nowrap;width:100%"><span class="q-lab" style="width:48px;flex:none">成功</span><div style="flex:1;pointer-events:none"><div class="q-svt" style="--bc:#00B42A;--fc:#AFF0B5"><span class="fl" style="width:224px"></span><span class="bk" style="left:164px"><svg data-icon="check" class="i"/></span></div></div></div></div>
```

