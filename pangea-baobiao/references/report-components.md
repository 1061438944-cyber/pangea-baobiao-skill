# 报表组件、图表与资源（站点实例）

规范原文见 `report-spec.md`；本文件是站点中按规范绘制的实例，HTML 依赖 `assets/pangea-components.css`（旧站报表样例部分）。

## 筛选栏（r/filter）

基础用法：由时间选择器、选择器、选择按钮、展开收起按钮和常规按钮构成；宽度 100%，下拉框高 32px
展开状态：一行放不下时展开全部选项，按钮切换为“收起”
带标签文字：字段名放在下拉框前，适合维度较多、容易混淆的场景
筛选栏宽度为父容器的100%，单个筛选下拉框高度参考32px。

### 实例 1

```html
<div class="demo-cap">基础用法：由时间选择器、选择器、选择按钮、展开收起按钮和常规按钮构成；宽度 100%，下拉框高 32px</div><div class="xfb"><span class="xff"><span class="xseg " data-tog=""><button class="">日</button><button class="">周</button><button class="on">月</button><button class="">年</button></span></span><span class="xff"><span class="xi xsel" style="width:196px"><svg data-icon="calendar" class="ico mut"/><span class="v">2026-07&nbsp;&nbsp;–&nbsp;&nbsp;2026-07</span></span></span><span class="xff"><span class="xi xsel" style="width:128px"><span class="v">全部渠道</span><svg data-icon="down" class="ico sm"/></span></span><span class="xff"><span class="xi xsel" style="width:128px"><span class="v">全部品类</span><svg data-icon="down" class="ico sm"/></span></span><span class="xff"><span class="xi xsel" style="width:128px"><span class="v">全部区域</span><svg data-icon="down" class="ico sm"/></span></span><span class="xff"><span class="xchk on"><i></i>仅看预警</span></span><span class="xfb-r"><span style="position:relative"><button class="xb txt">展开 <svg data-icon="down" class="ico sm"/></button></span><span style="position:relative;display:flex;gap:8px"><button class="xb sec"><svg data-icon="refresh" class="ico "/>重置</button><button class="xb sec"><svg data-icon="file" class="ico "/>毛利率日报</button></span></span></div><div class="demo-cap">展开状态：一行放不下时展开全部选项，按钮切换为“收起”</div><div class="xfb"><span class="xff"><span class="xseg " data-tog=""><button class="">日</button><button class="">周</button><button class="on">月</button><button class="">年</button></span></span><span class="xff"><span class="xi xsel" style="width:196px"><svg data-icon="calendar" class="ico mut"/><span class="v">2026-07&nbsp;&nbsp;–&nbsp;&nbsp;2026-07</span></span></span><span class="xff"><span class="xi xsel" style="width:128px"><span class="v">全部渠道</span><svg data-icon="down" class="ico sm"/></span></span><span class="xff"><span class="xi xsel" style="width:128px"><span class="v">全部品类</span><svg data-icon="down" class="ico sm"/></span></span><span class="xff"><span class="xi xsel" style="width:128px"><span class="v">全部区域</span><svg data-icon="down" class="ico sm"/></span></span><span class="xff"><span class="xi xsel" style="width:128px"><span class="v">全部品牌</span><svg data-icon="down" class="ico sm"/></span></span><span class="xfb-r"><button class="xb txt">收起 <svg data-icon="up" class="ico sm"/></button><button class="xb sec"><svg data-icon="refresh" class="ico "/>重置</button></span><span class="xfb-2"><span class="xff"><span class="xi xsel" style="width:128px"><span class="v">营销中心</span><svg data-icon="down" class="ico sm"/></span></span><span class="xff"><span class="xi xsel" style="width:128px"><span class="v">分办事处</span><svg data-icon="down" class="ico sm"/></span></span><span class="xff"><span class="xi xsel" style="width:128px"><span class="v">产品档次</span><svg data-icon="down" class="ico sm"/></span></span><span class="xff"><span class="xi xsel" style="width:128px"><span class="v">门店级别</span><svg data-icon="down" class="ico sm"/></span></span></span></div><div class="demo-cap">带标签文字：字段名放在下拉框前，适合维度较多、容易混淆的场景</div><div class="xfb"><span class="xff"><span>统计日期</span><span class="xi xsel" style="width:112px"><span class="v">本月</span><svg data-icon="down" class="ico sm"/></span></span><span class="xff"><span class="xi xsel" style="width:196px"><svg data-icon="calendar" class="ico mut"/><span class="v">2026-07&nbsp;&nbsp;–&nbsp;&nbsp;2026-07</span></span></span><span class="xff"><span>渠道</span><span class="xi xsel" style="width:120px"><span class="v">请选择</span><svg data-icon="down" class="ico sm"/></span></span><span class="xff"><span>品类大类</span><span class="xi xsel" style="width:120px"><span class="v">请选择</span><svg data-icon="down" class="ico sm"/></span></span><span class="xfb-r"><button class="xb txt">展开 <svg data-icon="down" class="ico sm"/></button><button class="xb sec"><svg data-icon="refresh" class="ico "/>重置</button></span></div>
```

## 标题栏（r/title）

大标题直观告知用户当前页面核心内容，帮助快速定位页面主题；指标更新时间让用户明确数据的新鲜度，也增强了用户对数据可靠性的感知。
数据更新时间：2026-07-31 08:00
数据更新时间：2026-07-31 08:00
大标题 16px Semibold #1D2129；业务说明图标（没有说明时不显示）；更新时间 12px Regular #4E5969

| 1 | 大标题 | 位于标题栏左侧，字号为16px，字重Semibold，颜色为【强调/正文标题#1D2129】 |
| --- | --- | --- |
| 3 | 更新时间 | 位于标题栏右侧，字号为12px，字重Regular，颜色为【次强调/辅助文本#4E5969】 |

### 实例 1：大标题 16px Semibold #1D2129；业务说明图标（没有说明时不显示）；更新时间 12px Regular #4E5969

```html
<div class="xtb"><span class="xtb-t">空气事业部经营分析</span><span class="xtb-i" title="业务说明：数据口径为管理口径，含税"><svg data-icon="question-circle" class="ico "/></span><span class="xtb-u">数据更新时间：2026-07-31 08:00</span></div>
<div class="xtb"><span class="xtb-t">人力资源指标总览</span><span class="xtb-u">数据更新时间：2026-07-31 08:00</span></div>
```

## 标签页（r/tabs）

### 实例 1：一级用实底按钮，二级用下划线文字，三级用小号切换，层级主次分明

```html
<span class="xlv">一级 Tab · 第一层级</span><div class="xt2" data-tog=""><button class="on">集团整体</button><button class="">财务</button><button class="">人资</button><button class="">制造</button><button class="">供应链</button><button class="">研发</button><button class="">质量</button></div>
<div style="margin-top:18px"><span class="xlv">二级 Tab · 第一层级下</span></div><div class="xt1" data-tog=""><button class="on">指标总览</button><button class="">收入</button><button class="">利润</button><button class="">费用</button><button class="">周转</button></div>
<div class="xcard"><div class="xcard-h">主营业务收入趋势<span class="xlv" style="margin:0 0 0 8px">三级 Tab · 图表 / 表格切换</span><span class="xt3" data-tog=""><button class="on">图表</button><button>表格</button></span></div><svg viewBox="0 0 560 160" role="img"><line class="gl" x1="44" x2="546" y1="136.0" y2="136.0"></line><text x="38" y="140.0" text-anchor="end">0%</text><line class="gl" x1="44" x2="546" y1="110.8" y2="110.8"></line><text x="38" y="114.8" text-anchor="end">10%</text><line class="gl" x1="44" x2="546" y1="85.6" y2="85.6"></line><text x="38" y="89.6" text-anchor="end">20%</text><line class="gl" x1="44" x2="546" y1="60.4" y2="60.4"></line><text x="38" y="64.4" text-anchor="end">30%</text><line class="gl" x1="44" x2="546" y1="35.2" y2="35.2"></line><text x="38" y="39.2" text-anchor="end">40%</text><line class="gl" x1="44" x2="546" y1="10.0" y2="10.0"></line><text x="38" y="14.0" text-anchor="end">50%</text><text x="44.0" y="154" text-anchor="middle">1月</text><text x="89.6" y="154" text-anchor="middle">2月</text><text x="135.3" y="154" text-anchor="middle">3月</text><text x="180.9" y="154" text-anchor="middle">4月</text><text x="226.5" y="154" text-anchor="middle">5月</text><text x="272.2" y="154" text-anchor="middle">6月</text><text x="317.8" y="154" text-anchor="middle">7月</text><text x="363.5" y="154" text-anchor="middle">8月</text><text x="409.1" y="154" text-anchor="middle">9月</text><text x="454.7" y="154" text-anchor="middle">10月</text><text x="500.4" y="154" text-anchor="middle">11月</text><text x="546.0" y="154" text-anchor="middle">12月</text><path class="ln" data-s="0" d="M44.0,52.8 C51.6,55.8 74.4,65.0 89.6,70.5 C104.8,75.9 120.1,82.7 135.3,85.6 C150.5,88.5 165.7,89.0 180.9,88.1 C196.1,87.3 211.3,85.6 226.5,80.6 C241.8,75.5 257.0,62.5 272.2,57.9 C287.4,53.3 302.6,51.6 317.8,52.8 C333.0,54.1 348.2,60.8 363.5,65.4 C378.7,70.1 393.9,81.4 409.1,80.6 C424.3,79.7 439.5,68.8 454.7,60.4 C469.9,52.0 485.2,34.4 500.4,30.2 C515.6,26.0 538.4,34.4 546.0,35.2" fill="none" stroke="#FF4F31" stroke-width="2" stroke-linecap="round"></path><path d="M44.0,42.8 C51.6,41.1 74.4,30.6 89.6,32.7 C104.8,34.8 120.1,54.1 135.3,55.4 C150.5,56.6 165.7,41.1 180.9,40.2 C196.1,39.4 211.3,52.4 226.5,50.3 C241.8,48.2 257.0,25.5 272.2,27.6 C287.4,29.7 310.2,57.0 317.8,62.9 L317.8,136.0 L44.0,136.0Z" fill="#00BBB3" opacity=".1"></path><path class="ln" data-s="1" d="M44.0,42.8 C51.6,41.1 74.4,30.6 89.6,32.7 C104.8,34.8 120.1,54.1 135.3,55.4 C150.5,56.6 165.7,41.1 180.9,40.2 C196.1,39.4 211.3,52.4 226.5,50.3 C241.8,48.2 257.0,25.5 272.2,27.6 C287.4,29.7 310.2,57.0 317.8,62.9" fill="none" stroke="#00BBB3" stroke-width="2" stroke-linecap="round"></path><circle cx="317.8" cy="62.9" r="3.5" fill="#fff" stroke="#00BBB3" stroke-width="2"></circle><path class="ln" data-s="2" d="M44.0,65.4 C51.6,64.2 74.4,60.0 89.6,57.9 C104.8,55.8 120.1,53.3 135.3,52.8 C150.5,52.4 165.7,53.7 180.9,55.4 C196.1,57.0 211.3,59.6 226.5,62.9 C241.8,66.3 257.0,73.0 272.2,75.5 C287.4,78.0 302.6,78.5 317.8,78.0 C333.0,77.6 348.2,75.9 363.5,73.0 C378.7,70.1 393.9,57.0 409.1,60.4 C424.3,63.8 439.5,85.6 454.7,93.2 C469.9,100.7 485.2,104.9 500.4,105.8 C515.6,106.6 538.4,99.5 546.0,98.2" fill="none" stroke="#ECB500" stroke-width="2" stroke-linecap="round"></path></svg></div>
```

## 指标卡（r/kpi）

只读指标卡：仅展示，背景 #F5F7FB，边距 12px；主指标 14px/600，数值 24px/600 D-DIN-PRO
联动指标卡：默认灰底；选中后背景取对应图表系列色，与下方折线图图例一致（点击切换）
主指标卡 / 突出分类：加图标，可按分类调整背景
联动指标卡：选中指标卡背景色运用图表色，与联动折线图图例色值一致，默认指标卡为背景色为灰色
只读指标卡：仅读，无交互，背景色，色值#F5F7FB；
主指标卡/突出分类：主指标卡或突出分类类型指标卡需要加图标，也可根据实际图标颜色修改背景色突出分类
指标卡宽度根据栅格化布局每排指标的个数等分自适应宽度，高度根据文字与间距自适应，边距为12px，其他间距标注如下：

| 14px | Semibold/font - weight：600 | 强调/正文标题 #1D2129 |
| --- | --- | --- |
| 数值 | 参考2.4文本相应内容 | 24/26px | Semibold/font - weight：600 | 强调/正文标题 #1D2129 |
| 12/14px | Regular | 强调/正文标题 #4E5969 |
| 数值 | 参考2.4文本相应内容 | 12/14px | Semibold/font - weight：600 | 强调/正文标题 #1D2129 |

### 实例 1

```html
<div class="demo-cap">只读指标卡：仅展示，背景 #F5F7FB，边距 12px；主指标 14px/600，数值 24px/600 D-DIN-PRO</div><div class="xgrid" style="--w:200px"><div class="xk "><div class="xk-c"><div class="xk-n">主营业务收入</div><div class="xk-r"><div class="xk-v num">43,345<small>万元</small></div><div class="xk-s"><span>完成率<b class="num dn">98.6%</b></span><span>同比<b class="num up tg">+4.23%</b></span></div></div></div></div><div class="xk "><div class="xk-c"><div class="xk-n">利润总额</div><div class="xk-r"><div class="xk-v num">5,812<small>万元</small></div><div class="xk-s"><span>完成率<b class="num up">104.5%</b></span><span>同比<b class="num dn tg">-2.15%</b></span></div></div></div></div><div class="xk "><div class="xk-c"><div class="xk-n">制造费用率 · 反向</div><div class="xk-r"><div class="xk-v num">3.42<small>%</small></div><div class="xk-s"><span>目标<b class="num ">3.60%</b></span><span>同比<b class="num up tg">-0.65 点</b></span></div></div></div></div></div><div class="demo-cap">联动指标卡：默认灰底；选中后背景取对应图表系列色，与下方折线图图例一致（点击切换）</div><div class="xlink" data-sel="1"><div class="xgrid" style="--w:200px"><div class="xk lk" style="--sc:#FF4F31" data-k="0"><div class="xk-c"><div class="xk-n">计划收入</div><div class="xk-r"><div class="xk-v num">45,200<small>万元</small></div><div class="xk-s"><span>完成率<b class="num dn">95.9%</b></span><span>环比<b class="num up tg">+1.82%</b></span></div></div></div></div><div class="xk lk on" style="--sc:#00BBB3" data-k="1"><div class="xk-c"><div class="xk-n">实际收入</div><div class="xk-r"><div class="xk-v num">43,345<small>万元</small></div><div class="xk-s"><span>完成率<b class="num dn">95.9%</b></span><span>环比<b class="num up tg">+1.82%</b></span></div></div></div></div><div class="xk lk" style="--sc:#ECB500" data-k="2"><div class="xk-c"><div class="xk-n">同期收入</div><div class="xk-r"><div class="xk-v num">41,580<small>万元</small></div><div class="xk-s"><span>完成率<b class="num dn">95.9%</b></span><span>环比<b class="num up tg">+1.82%</b></span></div></div></div></div></div><div class="xch" style="margin-top:12px"><svg viewBox="0 0 560 150" role="img"><line class="gl" x1="44" x2="546" y1="126.0" y2="126.0"></line><text x="38" y="130.0" text-anchor="end">0%</text><line class="gl" x1="44" x2="546" y1="102.8" y2="102.8"></line><text x="38" y="106.8" text-anchor="end">10%</text><line class="gl" x1="44" x2="546" y1="79.6" y2="79.6"></line><text x="38" y="83.6" text-anchor="end">20%</text><line class="gl" x1="44" x2="546" y1="56.4" y2="56.4"></line><text x="38" y="60.4" text-anchor="end">30%</text><line class="gl" x1="44" x2="546" y1="33.2" y2="33.2"></line><text x="38" y="37.2" text-anchor="end">40%</text><line class="gl" x1="44" x2="546" y1="10.0" y2="10.0"></line><text x="38" y="14.0" text-anchor="end">50%</text><text x="44.0" y="144" text-anchor="middle">1月</text><text x="89.6" y="144" text-anchor="middle">2月</text><text x="135.3" y="144" text-anchor="middle">3月</text><text x="180.9" y="144" text-anchor="middle">4月</text><text x="226.5" y="144" text-anchor="middle">5月</text><text x="272.2" y="144" text-anchor="middle">6月</text><text x="317.8" y="144" text-anchor="middle">7月</text><text x="363.5" y="144" text-anchor="middle">8月</text><text x="409.1" y="144" text-anchor="middle">9月</text><text x="454.7" y="144" text-anchor="middle">10月</text><text x="500.4" y="144" text-anchor="middle">11月</text><text x="546.0" y="144" text-anchor="middle">12月</text><path class="ln" data-s="0" d="M44.0,49.4 C51.6,52.1 74.4,60.7 89.6,65.7 C104.8,70.7 120.1,76.9 135.3,79.6 C150.5,82.3 165.7,82.7 180.9,81.9 C196.1,81.1 211.3,79.6 226.5,75.0 C241.8,70.3 257.0,58.3 272.2,54.1 C287.4,49.8 302.6,48.3 317.8,49.4 C333.0,50.6 348.2,56.8 363.5,61.0 C378.7,65.3 393.9,75.7 409.1,75.0 C424.3,74.2 439.5,64.1 454.7,56.4 C469.9,48.7 485.2,32.4 500.4,28.6 C515.6,24.7 538.4,32.4 546.0,33.2" fill="none" stroke="#FF4F31" stroke-width="2" stroke-linecap="round"></path><path class="ln" data-s="1" d="M44.0,40.2 C51.6,38.6 74.4,28.9 89.6,30.9 C104.8,32.8 120.1,50.6 135.3,51.8 C150.5,52.9 165.7,38.6 180.9,37.8 C196.1,37.1 211.3,49.1 226.5,47.1 C241.8,45.2 257.0,24.3 272.2,26.2 C287.4,28.2 310.2,53.3 317.8,58.7" fill="none" stroke="#00BBB3" stroke-width="2" stroke-linecap="round"></path><path class="ln" data-s="2" d="M44.0,61.0 C51.6,59.9 74.4,56.0 89.6,54.1 C104.8,52.1 120.1,49.8 135.3,49.4 C150.5,49.1 165.7,50.2 180.9,51.8 C196.1,53.3 211.3,55.6 226.5,58.7 C241.8,61.8 257.0,68.0 272.2,70.3 C287.4,72.6 302.6,73.0 317.8,72.6 C333.0,72.3 348.2,70.7 363.5,68.0 C378.7,65.3 393.9,53.3 409.1,56.4 C424.3,59.5 439.5,79.6 454.7,86.6 C469.9,93.5 485.2,97.4 500.4,98.2 C515.6,98.9 538.4,92.4 546.0,91.2" fill="none" stroke="#ECB500" stroke-width="2" stroke-linecap="round"></path></svg></div></div><div class="demo-cap">主指标卡 / 突出分类：加图标，可按分类调整背景</div><div class="xgrid" style="--w:260px"><div class="xk main"><span class="xk-ic"><svg data-icon="user" class="ico "/></span><div class="xk-c"><div class="xk-n">整体月末人数</div><div class="xk-r"><div class="xk-v num">82,849<small>人</small></div><div class="xk-s"><span>同比<b class="num dn tg">-865 人</b></span><span>环比<b class="num up tg">+234 人</b></span></div></div></div></div><div class="xk main tint"><span class="xk-ic"><svg data-icon="check-circle" class="ico "/></span><div class="xk-c"><div class="xk-n">质量成本率 · 反向</div><div class="xk-r"><div class="xk-v num">1.86<small>%</small></div><div class="xk-s"><span>目标<b class="num ">2.00%</b></span><span>同比<b class="num up tg">-0.12 点</b></span></div></div></div></div></div>
```

## 筛选栏（r/m-filter）

值型下拉：高 48px，只展示选中结果
标签值下拉：高 48px，内置“字段：值”
选择中：显示已选标签，数字为已选数量
已选择：显示所选时间、数量与标签
值型下拉：高 48px，无前置标签，展示选中结果；用于快捷时间筛选、聚合筛选入口
标签值下拉：高 48px，内置「字段：值」文案；用于平铺多维度筛选，自解释条件

### 实例 1

```html
<div class="phones"><div class="phone-w"><div class="phone"><div class="ph-bar"><span>9:41</span><span class="ph-t">经营分析</span><span>●●●</span></div><div class="mfb"><span>本月 <svg data-icon="down" class="ico sm"/></span><span>筛选 <svg data-icon="down" class="ico sm"/></span></div><div class="mbody"><div class="mmod"><h6>核心指标</h6><div class="mk2"><div class="mkpi"><div class="n">主营业务收入</div><div class="v num">43,345<small>万元</small></div><div class="s">同比<b class="num up">+4.23%</b></div></div><div class="mkpi"><div class="n">利润总额</div><div class="v num">5,812<small>万元</small></div><div class="s">同比<b class="num dn">-2.15%</b></div></div><div class="mkpi"><div class="n">毛利率</div><div class="v num">21.3<small>%</small></div><div class="s">同比<b class="num up">+0.8 点</b></div></div><div class="mkpi"><div class="n">费用率 · 反向</div><div class="v num">12.6<small>%</small></div><div class="s">同比<b class="num up">-0.4 点</b></div></div></div></div></div></div><div class="demo-cap c">值型下拉：高 48px，只展示选中结果</div></div>
<div class="phone-w"><div class="phone"><div class="ph-bar"><span>9:41</span><span class="ph-t">经营分析</span><span>●●●</span></div><div class="mfb lab"><span><em>日期：</em>2026-07 <svg data-icon="down" class="ico sm"/></span><span><em>预警状态：</em>全部 <svg data-icon="down" class="ico sm"/></span></div><div class="mbody"><div class="mmod"><h6>核心指标</h6><div class="mk2"><div class="mkpi"><div class="n">主营业务收入</div><div class="v num">43,345<small>万元</small></div><div class="s">同比<b class="num up">+4.23%</b></div></div><div class="mkpi"><div class="n">利润总额</div><div class="v num">5,812<small>万元</small></div><div class="s">同比<b class="num dn">-2.15%</b></div></div><div class="mkpi"><div class="n">毛利率</div><div class="v num">21.3<small>%</small></div><div class="s">同比<b class="num up">+0.8 点</b></div></div><div class="mkpi"><div class="n">费用率 · 反向</div><div class="v num">12.6<small>%</small></div><div class="s">同比<b class="num up">-0.4 点</b></div></div></div></div></div></div><div class="demo-cap c">标签值下拉：高 48px，内置“字段：值”</div></div>
<div class="phone-w"><div class="phone"><div class="ph-bar"><span>9:41</span><span class="ph-t">经营分析</span><span>●●●</span></div><div class="mfb"><span class="on">本月 <svg data-icon="up" class="ico sm"/></span><span>筛选 <svg data-icon="down" class="ico sm"/></span></div><div class="mbody"><div class="mmod"><h6>核心指标</h6><div class="mk2"><div class="mkpi"><div class="n">主营业务收入</div><div class="v num">43,345<small>万元</small></div><div class="s">同比<b class="num up">+4.23%</b></div></div><div class="mkpi"><div class="n">利润总额</div><div class="v num">5,812<small>万元</small></div><div class="s">同比<b class="num dn">-2.15%</b></div></div><div class="mkpi"><div class="n">毛利率</div><div class="v num">21.3<small>%</small></div><div class="s">同比<b class="num up">+0.8 点</b></div></div><div class="mkpi"><div class="n">费用率 · 反向</div><div class="v num">12.6<small>%</small></div><div class="s">同比<b class="num up">-0.4 点</b></div></div></div></div></div><div class="mmask"></div><div class="msheet"><div class="msh-h"><span class="mst" data-tog=""><button class="on">月份选择</button><button class="">自定义时间</button></span><svg data-icon="close" class="ico "/></div><div class="mwheel"><div><span class="" style="opacity:0.43999999999999995">2024年</span><span class="" style="opacity:0.72">2025年</span><span class="on" style="opacity:1">2026年</span><span class="" style="opacity:0.72">2027年</span><span class="" style="opacity:0.43999999999999995">2028年</span></div><div><span class="" style="opacity:0.43999999999999995">5月</span><span class="" style="opacity:0.72">6月</span><span class="on" style="opacity:1">7月</span><span class="" style="opacity:0.72">8月</span><span class="" style="opacity:0.43999999999999995">9月</span></div><i></i></div><button class="xb pri l" style="width:100%;margin-top:14px">确定</button></div></div><div class="demo-cap c">月份选择：底部弹出层</div></div>
<div class="phone-w"><div class="phone"><div class="ph-bar"><span>9:41</span><span class="ph-t">经营分析</span><span>●●●</span></div><div class="mfb"><span class="on">自定义 <svg data-icon="up" class="ico sm"/></span><span>筛选 <svg data-icon="down" class="ico sm"/></span></div><div class="mbody"><div class="mmod"><h6>核心指标</h6><div class="mk2"><div class="mkpi"><div class="n">主营业务收入</div><div class="v num">43,345<small>万元</small></div><div class="s">同比<b class="num up">+4.23%</b></div></div><div class="mkpi"><div class="n">利润总额</div><div class="v num">5,812<small>万元</small></div><div class="s">同比<b class="num dn">-2.15%</b></div></div><div class="mkpi"><div class="n">毛利率</div><div class="v num">21.3<small>%</small></div><div class="s">同比<b class="num up">+0.8 点</b></div></div><div class="mkpi"><div class="n">费用率 · 反向</div><div class="v num">12.6<small>%</small></div><div class="s">同比<b class="num up">-0.4 点</b></div></div></div></div></div><div class="mmask"></div><div class="msheet"><div class="msh-h"><span class="mst" data-tog=""><button class="">月份选择</button><button class="on">自定义时间</button></span><svg data-icon="close" class="ico "/></div><div class="msh-l">时间选择</div><div class="mgran" data-tog=""><button class="on">日</button><button class="">周</button><button class="">月</button><button class="">年</button></div><div class="msh-l">自定义<span>重置</span></div><div class="mrange"><span>2026/07/01</span>至<span class="on">2026/07/31</span></div><div class="mwheel"><div><span class="" style="opacity:0.72">2025年</span><span class="on" style="opacity:1">2026年</span><span class="" style="opacity:0.72">2027年</span></div><div><span class="" style="opacity:0.72">6月</span><span class="on" style="opacity:1">7月</span><span class="" style="opacity:0.72">8月</span></div><div><span class="" style="opacity:0.72">30日</span><span class="on" style="opacity:1">31日</span><span class="" style="opacity:0.72">1日</span></div><i></i></div><button class="xb pri l" style="width:100%;margin-top:14px">确定</button></div></div><div class="demo-cap c">自定义时间选择</div></div>
<div class="phone-w"><div class="phone"><div class="ph-bar"><span>9:41</span><span class="ph-t">经营分析</span><span>●●●</span></div><div class="mfb"><span>本月 <svg data-icon="down" class="ico sm"/></span><span class="on">筛选 <b class="mcnt">2</b> <svg data-icon="up" class="ico sm"/></span></div><div class="mtags"><span>家空 <svg data-icon="close" class="ico sm"/></span><span>线上 <svg data-icon="close" class="ico sm"/></span></div><div class="mpanel"><div class="mnav" data-tog=""><button class="on">全部渠道</button><button class="">全部品类</button><button class="">全部区域</button><button class="">拓展维度</button></div><div class="mopts"><div class="mopt" data-multi=""><button class="">线下</button><button class="on">线上</button><button class="">下沉</button><button class="on">家空</button><button class="">央空</button><button class="">厨电</button></div></div></div><div class="mpfoot"><button class="xb line l">重置</button><button class="xb pri l">确认</button></div><div class="mmask" style="top:auto;bottom:0;height:120px"></div></div><div class="demo-cap c">选择中：显示已选标签，数字为已选数量</div></div>
<div class="phone-w"><div class="phone"><div class="ph-bar"><span>9:41</span><span class="ph-t">经营分析</span><span>●●●</span></div><div class="mfb"><span class="on">2026/07/01–07/31 <svg data-icon="down" class="ico sm"/></span><span class="on">筛选 <b class="mcnt">2</b> <svg data-icon="down" class="ico sm"/></span></div><div class="mtags"><span>家空 <svg data-icon="close" class="ico sm"/></span><span>线上 <svg data-icon="close" class="ico sm"/></span></div><div class="mbody"><div class="mmod"><h6>核心指标</h6><div class="mk2"><div class="mkpi"><div class="n">主营业务收入</div><div class="v num">43,345<small>万元</small></div><div class="s">同比<b class="num up">+4.23%</b></div></div><div class="mkpi"><div class="n">利润总额</div><div class="v num">5,812<small>万元</small></div><div class="s">同比<b class="num dn">-2.15%</b></div></div><div class="mkpi"><div class="n">毛利率</div><div class="v num">21.3<small>%</small></div><div class="s">同比<b class="num up">+0.8 点</b></div></div><div class="mkpi"><div class="n">费用率 · 反向</div><div class="v num">12.6<small>%</small></div><div class="s">同比<b class="num up">-0.4 点</b></div></div></div></div></div></div><div class="demo-cap c">已选择：显示所选时间、数量与标签</div></div></div>
```

## 标签页（r/m-tabs）

基础用法：等分父容器，高 44px
标签栏滚动：超出时自适应宽度，左右间距 12px，左边距 4px
Tabs宽度为父容器的100%，高度固定 44px。
所有Tabs总宽度超出父容器宽度时，每个筛选项宽度自适应，左右间距12px，Tabs左边距4px,靠左对齐，可横向滑动。

### 实例 1

```html
<div class="phones"><div class="phone-w"><div class="phone"><div class="ph-bar"><span>9:41</span><span class="ph-t">经营分析</span><span>●●●</span></div><div class="mtabs " data-tog=""><button class="on">财务</button><button class="">人力</button><button class="">供应链</button><button class="">质量</button></div><div class="mbody"><div class="mmod"><h6>核心指标</h6><div class="mk2"><div class="mkpi"><div class="n">主营业务收入</div><div class="v num">43,345<small>万元</small></div><div class="s">同比<b class="num up">+4.23%</b></div></div><div class="mkpi"><div class="n">利润总额</div><div class="v num">5,812<small>万元</small></div><div class="s">同比<b class="num dn">-2.15%</b></div></div><div class="mkpi"><div class="n">毛利率</div><div class="v num">21.3<small>%</small></div><div class="s">同比<b class="num up">+0.8 点</b></div></div><div class="mkpi"><div class="n">费用率 · 反向</div><div class="v num">12.6<small>%</small></div><div class="s">同比<b class="num up">-0.4 点</b></div></div></div></div></div></div><div class="demo-cap c">基础用法：等分父容器，高 44px</div></div>
<div class="phone-w"><div class="phone"><div class="ph-bar"><span>9:41</span><span class="ph-t">经营分析</span><span>●●●</span></div><div class="mtabs scroll" data-tog=""><button class="on">事业部整体</button><button class="">内销家空</button><button class="">内销商空</button><button class="">出口整体</button><button class="">家空分公司</button><button class="">商空分公司</button><button class="">成本</button></div><div class="mbody"><div class="mmod"><h6>核心指标</h6><div class="mk2"><div class="mkpi"><div class="n">主营业务收入</div><div class="v num">43,345<small>万元</small></div><div class="s">同比<b class="num up">+4.23%</b></div></div><div class="mkpi"><div class="n">利润总额</div><div class="v num">5,812<small>万元</small></div><div class="s">同比<b class="num dn">-2.15%</b></div></div><div class="mkpi"><div class="n">毛利率</div><div class="v num">21.3<small>%</small></div><div class="s">同比<b class="num up">+0.8 点</b></div></div><div class="mkpi"><div class="n">费用率 · 反向</div><div class="v num">12.6<small>%</small></div><div class="s">同比<b class="num up">-0.4 点</b></div></div></div></div></div></div><div class="demo-cap c">标签栏滚动：超出时自适应宽度，左右间距 12px，左边距 4px</div></div>
<div class="phone-w"><div class="phone"><div class="ph-bar"><span>9:41</span><span class="ph-t">经营分析</span><span>●●●</span></div><div class="mbody"><div class="mmod" style="padding:0 0 12px"><div class="mtabs in" data-tog=""><button class="on">当月</button><button class="">累计</button></div><div style="padding:0 12px"><svg viewBox="0 0 340 160" role="img"><line class="gl" x1="44" x2="326" y1="136.0" y2="136.0"></line><text x="38" y="140.0" text-anchor="end">0%</text><line class="gl" x1="44" x2="326" y1="110.8" y2="110.8"></line><text x="38" y="114.8" text-anchor="end">10%</text><line class="gl" x1="44" x2="326" y1="85.6" y2="85.6"></line><text x="38" y="89.6" text-anchor="end">20%</text><line class="gl" x1="44" x2="326" y1="60.4" y2="60.4"></line><text x="38" y="64.4" text-anchor="end">30%</text><line class="gl" x1="44" x2="326" y1="35.2" y2="35.2"></line><text x="38" y="39.2" text-anchor="end">40%</text><line class="gl" x1="44" x2="326" y1="10.0" y2="10.0"></line><text x="38" y="14.0" text-anchor="end">50%</text><text x="44.0" y="154" text-anchor="middle">1月</text><text x="69.6" y="154" text-anchor="middle">2月</text><text x="95.3" y="154" text-anchor="middle">3月</text><text x="120.9" y="154" text-anchor="middle">4月</text><text x="146.5" y="154" text-anchor="middle">5月</text><text x="172.2" y="154" text-anchor="middle">6月</text><text x="197.8" y="154" text-anchor="middle">7月</text><text x="223.5" y="154" text-anchor="middle">8月</text><text x="249.1" y="154" text-anchor="middle">9月</text><text x="274.7" y="154" text-anchor="middle">10月</text><text x="300.4" y="154" text-anchor="middle">11月</text><text x="326.0" y="154" text-anchor="middle">12月</text><path class="ln" data-s="0" d="M44.0,52.8 C48.3,55.8 61.1,65.0 69.6,70.5 C78.2,75.9 86.7,82.7 95.3,85.6 C103.8,88.5 112.4,89.0 120.9,88.1 C129.5,87.3 138.0,85.6 146.5,80.6 C155.1,75.5 163.6,62.5 172.2,57.9 C180.7,53.3 189.3,51.6 197.8,52.8 C206.4,54.1 214.9,60.8 223.5,65.4 C232.0,70.1 240.5,81.4 249.1,80.6 C257.6,79.7 266.2,68.8 274.7,60.4 C283.3,52.0 291.8,34.4 300.4,30.2 C308.9,26.0 321.7,34.4 326.0,35.2" fill="none" stroke="#FF4F31" stroke-width="2" stroke-linecap="round"></path><path d="M44.0,42.8 C48.3,41.1 61.1,30.6 69.6,32.7 C78.2,34.8 86.7,54.1 95.3,55.4 C103.8,56.6 112.4,41.1 120.9,40.2 C129.5,39.4 138.0,52.4 146.5,50.3 C155.1,48.2 163.6,25.5 172.2,27.6 C180.7,29.7 193.5,57.0 197.8,62.9 L197.8,136.0 L44.0,136.0Z" fill="#00BBB3" opacity=".1"></path><path class="ln" data-s="1" d="M44.0,42.8 C48.3,41.1 61.1,30.6 69.6,32.7 C78.2,34.8 86.7,54.1 95.3,55.4 C103.8,56.6 112.4,41.1 120.9,40.2 C129.5,39.4 138.0,52.4 146.5,50.3 C155.1,48.2 163.6,25.5 172.2,27.6 C180.7,29.7 193.5,57.0 197.8,62.9" fill="none" stroke="#00BBB3" stroke-width="2" stroke-linecap="round"></path><circle cx="197.8" cy="62.9" r="3.5" fill="#fff" stroke="#00BBB3" stroke-width="2"></circle><path class="ln" data-s="2" d="M44.0,65.4 C48.3,64.2 61.1,60.0 69.6,57.9 C78.2,55.8 86.7,53.3 95.3,52.8 C103.8,52.4 112.4,53.7 120.9,55.4 C129.5,57.0 138.0,59.6 146.5,62.9 C155.1,66.3 163.6,73.0 172.2,75.5 C180.7,78.0 189.3,78.5 197.8,78.0 C206.4,77.6 214.9,75.9 223.5,73.0 C232.0,70.1 240.5,57.0 249.1,60.4 C257.6,63.8 266.2,85.6 274.7,93.2 C283.3,100.7 291.8,104.9 300.4,105.8 C308.9,106.6 321.7,99.5 326.0,98.2" fill="none" stroke="#ECB500" stroke-width="2" stroke-linecap="round"></path></svg></div></div></div></div><div class="demo-cap c">模块内使用：无边距</div></div></div>
```

## 指标卡（r/m-kpi）

只读指标卡 · #F7F8FA · 边距 8px
主指标 14px/600，数值 18–24px；次级 12px
联动指标卡：选中指标卡背景色运用图表色，与联动折线图图例色值一致，默认指标卡为背景色为灰色
只读指标卡：仅读，无交互，背景色，色值#F7F8FA；
主指标卡/突出分类：主指标卡或突出分类类型指标卡需要加图标，也可根据实际图标颜色修改背景色突出分类
指标卡宽度根据栅格化布局每排指标的个数等分自适应宽度，高度根据文字与间距自适应，边距为8px，其他间距标注如下：

| 14px | Semibold/font - weight：600 | 强调/正文标题 #1D2129 |
| --- | --- | --- |
| 数值 | 参考2.4文本相应内容 | 18/24px | Semibold/font - weight：600 | 强调/正文标题 #1D2129 |
| 12px | Regular | 强调/正文标题 #4E5969 |
| 数值 | 参考2.4文本相应内容 | 12px | Semibold/font - weight：600 | 强调/正文标题 #1D2129 |

### 实例 1

```html
<div class="phones"><div class="phone-w"><div class="phone"><div class="ph-bar"><span>9:41</span><span class="ph-t">经营分析</span><span>●●●</span></div><div class="mbody"><div class="mmod"><div class="mmain"><span class="xk-ic"><svg data-icon="user" class="ico "/></span><div><div class="n">整体月末人数</div><div class="v num">82,849<small>人</small></div><div class="s">同比<b class="num dn">-865 人</b>环比<b class="num up">+234 人</b></div></div></div></div><div class="mmod"><h6>只读指标卡 · #F7F8FA · 边距 8px</h6><div class="mk2"><div class="mkpi"><div class="n">主营业务收入</div><div class="v num">43,345<small>万元</small></div><div class="s">同比<b class="num up">+4.23%</b></div></div><div class="mkpi"><div class="n">利润总额</div><div class="v num">5,812<small>万元</small></div><div class="s">同比<b class="num dn">-2.15%</b></div></div></div></div><div class="mmod"><h6>联动指标卡</h6><div class="mk2"><div class="mkpi lk on" style="--sc:#00BBB3"><div class="n"><i></i>实际收入</div><div class="v num">43,345<small>万元</small></div></div><div class="mkpi lk" style="--sc:#FF4F31"><div class="n"><i></i>计划收入</div><div class="v num">43,345<small>万元</small></div></div></div></div></div></div><div class="demo-cap c">主指标 14px/600，数值 18–24px；次级 12px</div></div></div>
```

## 图表分析维度（charts/analysis）

通过对用户行为数据的分析，设计师可以发现产品中存在的问题和不足之处，从而进行改进和优化，提高产品的设计质量。同时，通过对用户行为数据的分析，设计师可以了解市场上同类产品的优势和劣势，从而进行改进和优化，提高产品的竞争力

集团报表规范 第 4 章

## 图表词典（charts/dict）

按数据关系选择图表，并控制数据条数。每种图表下方附示例，数据为示例数据。

集团报表规范 第 5 章
速查

| 图表 | 用途 | 数据条数上限 |
| --- | --- | --- |
| 折线图 | 趋势 | 大于两条 |
| 柱状图 | 分类对比 | 分类 ≤ 20，分组 ≤ 10 |
| 条形图 | 分类对比、排名 | 分类 ≤ 20，分组 ≤ 10 |
| 饼图 | 占比 | 区块 ≤ 9，超出合并为“其它” |
| 雷达图 | 多维综合对比 | 3 至 8 个维度 |
| 四象限图 | 分层归类 | 20 至 80 个点，最少 10、最多 100 |
| 折线 + 柱状 | 规模与增速 | 柱 ≤ 3 个系列，折线 ≤ 2 条 |
| 表格 | 精确明细 | 同含义指标只保留一列 |

5.1 折线图

折线图：又叫趋势图，是用于显示数据在一个连续的时间间隔或者时间跨度上的变化，它的特点是反映事物随时间或有序类别而变化的趋势。

| 适合的数据 | 「两个连续字段数据」，或者「一个有序的分类」+「一个连续数据字段」 |
| --- | --- |
| 功能 | 观察数据的变化趋势 |
| 数据与图形的映射 | 两个连续字段分别映射到横轴和纵轴 |
| 适合的数据条数 | 大于两条 |

趋势：时间连续，2 条以上系列
主营业务收入率趋势
计划
实际
同期
0%
10%
20%
30%
40%
50%
1月
2月
3月
4月
5月
6月
7月
8月
9月
10月
11月
12月
示例数据
5.2 柱状图

柱形图：描述分类数据之间的对比，如果把时间周期，理解为一种分类数据 ，那么柱状图也可以用于描述时间周期之间的数值比较。

| 适合的数据 | 「一组或多组分类数据」+「一组或者多组对应的数值」 |
| --- | --- |
| 功能 | 对比分类数据的数值大小 |
| 数据与图形的映射 | 分类数据字段映射到横轴的位置，连续数据字段映射到矩形的高度，分类数据也可以设置颜色增强分类的区分度 |
| 适合的数据条数 | 分类数据不宜过多，不建议超过 20 条，如有多组分类数据，不建议超过 10 组 |

分类对比：分类不超过 20 条，分组不超过 10 组
各大区收入对比（亿元）
实际
同期
0
10
20
30
40
50
华东
华南
华北
华中
西南
西北
示例数据
5.3 条形图

条形图：利用相同宽度下矩形的长度来表示维度之间度量值的大小区别，在大多数情况下，折线图和柱形图是可以互相替换的。

| 适合的数据 | 「一组或多组分类数据」+「一组或者多组对应的数值」 |
| --- | --- |
| 功能 | 对比分类数据的数值大小 |
| 数据与图形的映射 | 分类数据字段映射到横轴的位置，连续数据字段映射到矩形的高度，分类数据也可以设置颜色增强分类的区分度 |
| 适合的数据条数 | 分类数据不宜过多，不建议超过 20 条，如有多组分类数据，不建议超过 10 组 |

类别名称较长或需要排序时用条形图
品类毛利排名（亿元）
空调
48.2
冰箱
41.5
洗衣机
35
厨电
27.6
热水器
19.3
小家电
11.8
示例数据
5.4 饼图

饼图：展现数据的分类和占比情况。展现部分与部分之间，以及部分与整体的关系。部分相加之和等于整体的 100%，用整圆表示。

| 适合的数据 | 一个「分类维度字段」和一个「数值度量字段」 |
| --- | --- |
| 功能 | 对比分类数据的数值大小 |
| 数据与图形的映射 | 「维度字段」的计数映射区块颜色和数量；「度量字段」的聚合值映射区块弧长和面积 |
| 适合的数据条数 | 建议区块数目不超过 9 种，超出的部分可以考虑合并显示为“其它” |

占比：区块不超过 9 个，超出合并为“其他”
收入构成
100%
收入构成
家空
42%
商空
23%
出口
18%
配件
10%
其他
7%
示例数据
5.5 雷达图

雷达图：以中心点向外辐射多条维度轴，将多维度指标闭合形成多边形，直观对比多维度综合表现的多维分析图表。

| 适合的数据 | 多维度、同量级、需综合对比的指标；维度为评价类属性（能力、考核、品类特征等） |
| --- | --- |
| 功能 | 单样本：查看自身各维度优劣短板；多样本：横向对比多对象整体综合强弱；快速识别不均衡、偏科类数据特征。 |
| 数据与图形的映射 | 辐射轴是分析维度；轴刻度是指标数值大小；闭合多边形是单组样本全部维度数据；多层色块线条 = 多组对比样本 |
| 适合的数据条数 | 雷达图适用于展示 3 到 8 条数据，因为太多的数据会使图表变得过于复杂 |

多维对比：3–8 个维度
工厂综合能力对比
成本
交付
质量
效率
创新
安全
黄岛工厂
平度工厂
示例数据
5.6 四象限图

四象限图：以横轴x与纵轴y组成的坐标系，在xy坐标轴上按照某个标准（平均值、目标值、行业之、指定值）进行切分，组成四象限。

| 适合的数据 | 识别数据的模式和趋势，并根据图表中的数据点确定优先级 |
| --- | --- |
| 功能 | 数据自动分层归类，快速划分四类群体；辅助制定分层运营 / 管理策略。 |
| 数据与图形的映射 | 横轴：第一评价指标数值；纵轴：第二评价指标数值；圆点：单条业务数据对象 |
| 适合的数据条数 | 最优数据量：20～80 条；下限：不少于 10 条，样本过少无参考意义；上限：不超过 100 条，点位堆叠视觉过载 |

分层：建议 20–80 个点，按均值切分
分公司经营分层
横轴：收入增速 · 纵轴：利润率 · 虚线：均值
0%
10%
20%
30%
0%
10%
20%
30%
40%
明星：高增长 高利润
潜力：高利润 低增长
问题：低增长 低利润
现金：高增长 低利润
示例数据
5.7 折线图&柱状图复合图表

折线图&柱状图：双轴复合图表，柱状图承载一类指标、折线承载另一指标，分别独立纵轴，解决两类数值量级差异过大无法同屏对比的问题。

| 适合的数据 | 同一分类维度下存在两组量级差距悬殊的指标；一组适合看总量对比（柱状）、一组适合看趋势变化（折线）。 |
| --- | --- |
| 功能 | 同步对比静态基数与动态波动，快速定位规模 + 增速匹配关系。 |
| 数据与图形的映射 | 横轴：统一分类维度；左侧纵轴：柱状图对应指标；右侧纵轴：折线图对应指标 |
| 适合的数据条数 | 柱系列：数量≤3，多柱改用分组柱状，不与折线混搭多柱；折线系列：最多 2 条，线条过多重叠造成信息过载。 |

双轴：柱 ≤3 个系列，折线 ≤2 条
收入与利润率
收入（左轴，万元）
利润率（右轴）
0
1,000
2,000
3,000
4,000
5,000
1月
2月
3月
4月
5月
6月
7月
8月
9月
10月
11月
12月
0%
4%
8%
12%
16%
20%
示例数据
5.8 表格

表格：以行列结构化布局承载明细数据，可精准展示原始数值、多维度字段，支持精确读取、对比、筛选的数据基础组件。

| 适合的数据 | 需要精准查看明细、导出原始数据、多字段交叉查询；指标字段较多、无法用图形直观表达精确数值的场景。 |
| --- | --- |
| 功能 | 展示精确原始数值，无图表估算误差，满足对账、明细查看需求 |
| 数据与图形的映射 | 表头列：不同业务字段；数据行：单条业务实体；单元格：对应单条数据的字段取值 |
| 适合的数据条数 | 不堆砌冗余字段，同含义指标只保留一列，降低页面噪声 |

明细：单位写在表头，数值右对齐

| 产品线 | 主营业务收入（万元） | 计划完成率 | 同比 | 毛利率 | 毛利率同比 |
| --- | --- | --- | --- | --- | --- |
| 内销家空 | 23,323.32 | 98.6% | +4.23% | 21.3% | +0.8 点 |
| 内销商空 | 12,086.15 | 87.2% | -3.10% | 24.6% | -1.2 点 |
| 出口整体 | 18,540.60 | 104.5% | +9.87% | -- | -- |
| 合计 | 53,950.07 | 97.1% | +3.96% | 22.4% | +0.3 点 |

红色表示改善、蓝色表示恶化；毛利率变化单位为“点”，与百分比变化分开；缺失值显示“--”
5.9 使用建议

从内容展示分类上，给出图表用法说明，以便更佳准确的选择图表类型

### 实例 1

```html
<div class="xch"><div class="xch-h"><b>主营业务收入率趋势</b><div class="xlg"><span><i style="background:#FF4F31"></i>计划</span><span><i style="background:#00BBB3"></i>实际</span><span><i style="background:#ECB500"></i>同期</span></div></div><svg viewBox="0 0 560 200" role="img"><line class="gl" x1="44" x2="546" y1="176.0" y2="176.0"></line><text x="38" y="180.0" text-anchor="end">0%</text><line class="gl" x1="44" x2="546" y1="142.8" y2="142.8"></line><text x="38" y="146.8" text-anchor="end">10%</text><line class="gl" x1="44" x2="546" y1="109.6" y2="109.6"></line><text x="38" y="113.6" text-anchor="end">20%</text><line class="gl" x1="44" x2="546" y1="76.4" y2="76.4"></line><text x="38" y="80.4" text-anchor="end">30%</text><line class="gl" x1="44" x2="546" y1="43.2" y2="43.2"></line><text x="38" y="47.2" text-anchor="end">40%</text><line class="gl" x1="44" x2="546" y1="10.0" y2="10.0"></line><text x="38" y="14.0" text-anchor="end">50%</text><text x="44.0" y="194" text-anchor="middle">1月</text><text x="89.6" y="194" text-anchor="middle">2月</text><text x="135.3" y="194" text-anchor="middle">3月</text><text x="180.9" y="194" text-anchor="middle">4月</text><text x="226.5" y="194" text-anchor="middle">5月</text><text x="272.2" y="194" text-anchor="middle">6月</text><text x="317.8" y="194" text-anchor="middle">7月</text><text x="363.5" y="194" text-anchor="middle">8月</text><text x="409.1" y="194" text-anchor="middle">9月</text><text x="454.7" y="194" text-anchor="middle">10月</text><text x="500.4" y="194" text-anchor="middle">11月</text><text x="546.0" y="194" text-anchor="middle">12月</text><path class="ln" data-s="0" d="M44.0,66.4 C51.6,70.3 74.4,82.5 89.6,89.7 C104.8,96.9 120.1,105.7 135.3,109.6 C150.5,113.5 165.7,114.0 180.9,112.9 C196.1,111.8 211.3,109.6 226.5,103.0 C241.8,96.3 257.0,79.2 272.2,73.1 C287.4,67.0 302.6,64.8 317.8,66.4 C333.0,68.1 348.2,77.0 363.5,83.0 C378.7,89.1 393.9,104.1 409.1,103.0 C424.3,101.9 439.5,87.5 454.7,76.4 C469.9,65.3 485.2,42.1 500.4,36.6 C515.6,31.0 538.4,42.1 546.0,43.2" fill="none" stroke="#FF4F31" stroke-width="2" stroke-linecap="round"></path><path d="M44.0,53.2 C51.6,50.9 74.4,37.1 89.6,39.9 C104.8,42.6 120.1,68.1 135.3,69.8 C150.5,71.4 165.7,50.9 180.9,49.8 C196.1,48.7 211.3,65.9 226.5,63.1 C241.8,60.4 257.0,30.5 272.2,33.2 C287.4,36.0 310.2,72.0 317.8,79.7 L317.8,176.0 L44.0,176.0Z" fill="#00BBB3" opacity=".1"></path><path class="ln" data-s="1" d="M44.0,53.2 C51.6,50.9 74.4,37.1 89.6,39.9 C104.8,42.6 120.1,68.1 135.3,69.8 C150.5,71.4 165.7,50.9 180.9,49.8 C196.1,48.7 211.3,65.9 226.5,63.1 C241.8,60.4 257.0,30.5 272.2,33.2 C287.4,36.0 310.2,72.0 317.8,79.7" fill="none" stroke="#00BBB3" stroke-width="2" stroke-linecap="round"></path><circle cx="317.8" cy="79.7" r="3.5" fill="#fff" stroke="#00BBB3" stroke-width="2"></circle><path class="ln" data-s="2" d="M44.0,83.0 C51.6,81.4 74.4,75.8 89.6,73.1 C104.8,70.3 120.1,67.0 135.3,66.4 C150.5,65.9 165.7,67.5 180.9,69.8 C196.1,72.0 211.3,75.3 226.5,79.7 C241.8,84.1 257.0,93.0 272.2,96.3 C287.4,99.6 302.6,100.2 317.8,99.6 C333.0,99.1 348.2,96.9 363.5,93.0 C378.7,89.1 393.9,72.0 409.1,76.4 C424.3,80.8 439.5,109.6 454.7,119.6 C469.9,129.5 485.2,135.1 500.4,136.2 C515.6,137.3 538.4,127.9 546.0,126.2" fill="none" stroke="#ECB500" stroke-width="2" stroke-linecap="round"></path></svg><div class="xch-n">示例数据</div></div>
```

### 实例 2

```html
<div class="xch"><div class="xch-h"><b>各大区收入对比（亿元）</b><div class="xlg sq"><span><i style="background:#00BBB3"></i>实际</span><span><i style="background:#ECB500"></i>同期</span></div></div><svg viewBox="0 0 560 200"><line class="gl" x1="44" x2="546" y1="176.0" y2="176.0"></line><text x="38" y="180.0" text-anchor="end">0</text><line class="gl" x1="44" x2="546" y1="142.8" y2="142.8"></line><text x="38" y="146.8" text-anchor="end">10</text><line class="gl" x1="44" x2="546" y1="109.6" y2="109.6"></line><text x="38" y="113.6" text-anchor="end">20</text><line class="gl" x1="44" x2="546" y1="76.4" y2="76.4"></line><text x="38" y="80.4" text-anchor="end">30</text><line class="gl" x1="44" x2="546" y1="43.2" y2="43.2"></line><text x="38" y="47.2" text-anchor="end">40</text><line class="gl" x1="44" x2="546" y1="10.0" y2="10.0"></line><text x="38" y="14.0" text-anchor="end">50</text><text x="85.8" y="194" text-anchor="middle">华东</text><text x="169.5" y="194" text-anchor="middle">华南</text><text x="253.2" y="194" text-anchor="middle">华北</text><text x="336.8" y="194" text-anchor="middle">华中</text><text x="420.5" y="194" text-anchor="middle">西南</text><text x="504.2" y="194" text-anchor="middle">西北</text><rect x="72.8" y="36.6" width="12" height="139.4" rx="2" fill="#00BBB3"></rect><rect x="86.8" y="49.8" width="12" height="126.2" rx="2" fill="#ECB500"></rect><rect x="156.5" y="56.5" width="12" height="119.5" rx="2" fill="#00BBB3"></rect><rect x="170.5" y="73.1" width="12" height="102.9" rx="2" fill="#ECB500"></rect><rect x="240.2" y="76.4" width="12" height="99.6" rx="2" fill="#00BBB3"></rect><rect x="254.2" y="66.4" width="12" height="109.6" rx="2" fill="#ECB500"></rect><rect x="323.8" y="86.4" width="12" height="89.6" rx="2" fill="#00BBB3"></rect><rect x="337.8" y="103.0" width="12" height="73.0" rx="2" fill="#ECB500"></rect><rect x="407.5" y="103.0" width="12" height="73.0" rx="2" fill="#00BBB3"></rect><rect x="421.5" y="93.0" width="12" height="83.0" rx="2" fill="#ECB500"></rect><rect x="491.2" y="126.2" width="12" height="49.8" rx="2" fill="#00BBB3"></rect><rect x="505.2" y="136.2" width="12" height="39.8" rx="2" fill="#ECB500"></rect></svg><div class="xch-n">示例数据</div></div>
```

### 实例 3

```html
<div class="xch"><div class="xch-h"><b>品类毛利排名（亿元）</b></div><svg viewBox="0 0 560 200"><text x="54" y="27.3" text-anchor="end">空调</text><rect x="64" y="16.3" width="448.0" height="14" rx="3" fill="#F2F3F5"></rect><rect x="64" y="16.3" width="431.9" height="14" rx="3" fill="#00AAA6" opacity="1"></rect><text x="503.9" y="27.3" class="dk">48.2</text><text x="54" y="58.0" text-anchor="end">冰箱</text><rect x="64" y="47.0" width="448.0" height="14" rx="3" fill="#F2F3F5"></rect><rect x="64" y="47.0" width="371.8" height="14" rx="3" fill="#00BBB3" opacity="0.9"></rect><text x="443.8" y="58.0" class="dk">41.5</text><text x="54" y="88.7" text-anchor="end">洗衣机</text><rect x="64" y="77.7" width="448.0" height="14" rx="3" fill="#F2F3F5"></rect><rect x="64" y="77.7" width="313.6" height="14" rx="3" fill="#00BBB3" opacity="0.8"></rect><text x="385.6" y="88.7" class="dk">35</text><text x="54" y="119.3" text-anchor="end">厨电</text><rect x="64" y="108.3" width="448.0" height="14" rx="3" fill="#F2F3F5"></rect><rect x="64" y="108.3" width="247.3" height="14" rx="3" fill="#00BBB3" opacity="0.7"></rect><text x="319.3" y="119.3" class="dk">27.6</text><text x="54" y="150.0" text-anchor="end">热水器</text><rect x="64" y="139.0" width="448.0" height="14" rx="3" fill="#F2F3F5"></rect><rect x="64" y="139.0" width="172.9" height="14" rx="3" fill="#00BBB3" opacity="0.6"></rect><text x="244.9" y="150.0" class="dk">19.3</text><text x="54" y="180.7" text-anchor="end">小家电</text><rect x="64" y="169.7" width="448.0" height="14" rx="3" fill="#F2F3F5"></rect><rect x="64" y="169.7" width="105.7" height="14" rx="3" fill="#00BBB3" opacity="0.5"></rect><text x="177.7" y="180.7" class="dk">11.8</text></svg><div class="xch-n">示例数据</div></div>
```

### 实例 4

```html
<div class="xch"><div class="xch-h"><b>收入构成</b></div><svg viewBox="0 0 560 200"><path d="M120.0,22.0 A78,78 0 0 1 157.6,168.4 L143.1,142.1 A48,48 0 0 0 120.0,52.0Z" fill="#00AAA6" stroke="#fff" stroke-width="2"></path><path d="M157.6,168.4 A78,78 0 0 1 56.9,145.8 L81.2,128.2 A48,48 0 0 0 143.1,142.1Z" fill="#5082F9" stroke="#fff" stroke-width="2"></path><path d="M56.9,145.8 A78,78 0 0 1 51.6,62.4 L77.9,76.9 A48,48 0 0 0 81.2,128.2Z" fill="#ECB500" stroke="#fff" stroke-width="2"></path><path d="M51.6,62.4 A78,78 0 0 1 86.8,29.4 L99.6,56.6 A48,48 0 0 0 77.9,76.9Z" fill="#FF4F31" stroke="#fff" stroke-width="2"></path><path d="M86.8,29.4 A78,78 0 0 1 120.0,22.0 L120.0,52.0 A48,48 0 0 0 99.6,56.6Z" fill="#C9CDD4" stroke="#fff" stroke-width="2"></path><text x="120" y="98" text-anchor="middle" class="dk big">100%</text><text x="120" y="116" text-anchor="middle">收入构成</text><rect x="260" y="31" width="10" height="10" rx="2" fill="#00AAA6"></rect><text x="278" y="40" class="dk" text-anchor="start">家空</text><text x="420" y="40" class="dk" text-anchor="end">42%</text><rect x="260" y="59" width="10" height="10" rx="2" fill="#5082F9"></rect><text x="278" y="68" class="dk" text-anchor="start">商空</text><text x="420" y="68" class="dk" text-anchor="end">23%</text><rect x="260" y="87" width="10" height="10" rx="2" fill="#ECB500"></rect><text x="278" y="96" class="dk" text-anchor="start">出口</text><text x="420" y="96" class="dk" text-anchor="end">18%</text><rect x="260" y="115" width="10" height="10" rx="2" fill="#FF4F31"></rect><text x="278" y="124" class="dk" text-anchor="start">配件</text><text x="420" y="124" class="dk" text-anchor="end">10%</text><rect x="260" y="143" width="10" height="10" rx="2" fill="#C9CDD4"></rect><text x="278" y="152" class="dk" text-anchor="start">其他</text><text x="420" y="152" class="dk" text-anchor="end">7%</text></svg><div class="xch-n">示例数据</div></div>
```

### 实例 5

```html
<div class="xch"><div class="xch-h"><b>工厂综合能力对比</b></div><svg viewBox="0 0 560 220"><polygon points="150.0,89.5 167.8,99.8 167.8,120.3 150.0,130.5 132.2,120.3 132.2,99.8" fill="none" stroke="#E5E6EB"></polygon><polygon points="150.0,69.0 185.5,89.5 185.5,130.5 150.0,151.0 114.5,130.5 114.5,89.5" fill="none" stroke="#E5E6EB"></polygon><polygon points="150.0,48.5 203.3,79.3 203.3,140.8 150.0,171.5 96.7,140.8 96.7,79.3" fill="none" stroke="#E5E6EB"></polygon><polygon points="150.0,28.0 221.0,69.0 221.0,151.0 150.0,192.0 79.0,151.0 79.0,69.0" fill="none" stroke="#E5E6EB"></polygon><line x1="150" y1="110" x2="150.0" y2="28.0" stroke="#E5E6EB"></line><text x="150.0" y="17.2" text-anchor="middle">成本</text><line x1="150" y1="110" x2="221.0" y2="69.0" stroke="#E5E6EB"></line><text x="233.8" y="65.6" text-anchor="middle">交付</text><line x1="150" y1="110" x2="221.0" y2="151.0" stroke="#E5E6EB"></line><text x="233.8" y="162.4" text-anchor="middle">质量</text><line x1="150" y1="110" x2="150.0" y2="192.0" stroke="#E5E6EB"></line><text x="150.0" y="210.8" text-anchor="middle">效率</text><line x1="150" y1="110" x2="79.0" y2="151.0" stroke="#E5E6EB"></line><text x="66.2" y="162.4" text-anchor="middle">创新</text><line x1="150" y1="110" x2="79.0" y2="69.0" stroke="#E5E6EB"></line><text x="66.2" y="65.6" text-anchor="middle">安全</text><polygon points="150.0,39.5 201.1,80.5 213.9,146.9 150.0,164.1 108.8,133.8 93.2,77.2" fill="#00BBB3" fill-opacity=".14" stroke="#00BBB3" stroke-width="2"></polygon><rect x="320" y="70" width="10" height="10" rx="2" fill="#00BBB3"></rect><text x="338" y="79" class="dk" text-anchor="start">黄岛工厂</text><polygon points="150.0,52.6 208.2,76.4 202.6,140.3 150.0,174.0 100.3,138.7 106.0,84.6" fill="#5082F9" fill-opacity=".14" stroke="#5082F9" stroke-width="2"></polygon><rect x="320" y="98" width="10" height="10" rx="2" fill="#5082F9"></rect><text x="338" y="107" class="dk" text-anchor="start">平度工厂</text></svg><div class="xch-n">示例数据</div></div>
```

### 实例 6

```html
<div class="xch"><div class="xch-h"><b>分公司经营分层</b><span class="xch-x">横轴：收入增速 · 纵轴：利润率 · 虚线：均值</span></div><svg viewBox="0 0 560 240"><line class="gl" x1="44" x2="546" y1="210.0" y2="210.0"></line><text x="38" y="214.0" text-anchor="end">0%</text><line class="gl" x1="44" x2="546" y1="144.0" y2="144.0"></line><text x="38" y="148.0" text-anchor="end">10%</text><line class="gl" x1="44" x2="546" y1="78.0" y2="78.0"></line><text x="38" y="82.0" text-anchor="end">20%</text><line class="gl" x1="44" x2="546" y1="12.0" y2="12.0"></line><text x="38" y="16.0" text-anchor="end">30%</text><text x="44.0" y="228" text-anchor="middle">0%</text><text x="169.5" y="228" text-anchor="middle">10%</text><text x="295.0" y="228" text-anchor="middle">20%</text><text x="420.5" y="228" text-anchor="middle">30%</text><text x="546.0" y="228" text-anchor="middle">40%</text><line x1="295" x2="295" y1="12" y2="210" stroke="#86909C" stroke-dasharray="4 4"></line><line x1="44" x2="546" y1="111.0" y2="111.0" stroke="#86909C" stroke-dasharray="4 4"></line><text x="533.5" y="24.0" text-anchor="end" class="q">明星：高增长 高利润</text><text x="56.5" y="24.0" text-anchor="start" class="q">潜力：高利润 低增长</text><text x="56.5" y="204.0" text-anchor="start" class="q">问题：低增长 低利润</text><text x="533.5" y="204.0" text-anchor="end" class="q">现金：高增长 低利润</text><circle cx="290.7" cy="100.6" r="4" fill="#5082F9" fill-opacity="0.55"></circle><circle cx="121.3" cy="154.9" r="4" fill="#C9CDD4" fill-opacity="0.55"></circle><circle cx="269.3" cy="109.9" r="4" fill="#5082F9" fill-opacity="0.55"></circle><circle cx="104.6" cy="46.0" r="4" fill="#5082F9" fill-opacity="0.55"></circle><circle cx="335.4" cy="126.3" r="4" fill="#5082F9" fill-opacity="0.55"></circle><circle cx="197.6" cy="62.7" r="4" fill="#5082F9" fill-opacity="0.55"></circle><circle cx="366.1" cy="183.7" r="4" fill="#5082F9" fill-opacity="0.55"></circle><circle cx="294.3" cy="156.5" r="4" fill="#C9CDD4" fill-opacity="0.55"></circle><circle cx="372.7" cy="169.7" r="4" fill="#5082F9" fill-opacity="0.55"></circle><circle cx="322.3" cy="113.2" r="4" fill="#5082F9" fill-opacity="0.55"></circle><circle cx="148.7" cy="188.2" r="4" fill="#C9CDD4" fill-opacity="0.55"></circle><circle cx="493.4" cy="30.4" r="5" fill="#00AAA6" fill-opacity="0.9"></circle><circle cx="123.7" cy="120.6" r="4" fill="#C9CDD4" fill-opacity="0.55"></circle><circle cx="500.9" cy="164.3" r="4" fill="#5082F9" fill-opacity="0.55"></circle><circle cx="258.5" cy="102.4" r="4" fill="#5082F9" fill-opacity="0.55"></circle><circle cx="372.7" cy="148.6" r="4" fill="#5082F9" fill-opacity="0.55"></circle><circle cx="146.1" cy="27.7" r="4" fill="#5082F9" fill-opacity="0.55"></circle><circle cx="270.4" cy="156.9" r="4" fill="#C9CDD4" fill-opacity="0.55"></circle><circle cx="316.3" cy="140.1" r="4" fill="#5082F9" fill-opacity="0.55"></circle><circle cx="138.5" cy="64.2" r="4" fill="#5082F9" fill-opacity="0.55"></circle><circle cx="228.0" cy="136.7" r="4" fill="#C9CDD4" fill-opacity="0.55"></circle><circle cx="105.1" cy="37.9" r="4" fill="#5082F9" fill-opacity="0.55"></circle><circle cx="176.9" cy="45.1" r="4" fill="#5082F9" fill-opacity="0.55"></circle><circle cx="281.8" cy="156.3" r="4" fill="#C9CDD4" fill-opacity="0.55"></circle><circle cx="341.5" cy="127.9" r="4" fill="#5082F9" fill-opacity="0.55"></circle><circle cx="412.0" cy="84.8" r="5" fill="#00AAA6" fill-opacity="0.9"></circle><circle cx="130.5" cy="158.4" r="4" fill="#C9CDD4" fill-opacity="0.55"></circle><circle cx="272.6" cy="181.3" r="4" fill="#C9CDD4" fill-opacity="0.55"></circle><circle cx="90.6" cy="126.1" r="4" fill="#C9CDD4" fill-opacity="0.55"></circle><circle cx="376.7" cy="85.8" r="5" fill="#00AAA6" fill-opacity="0.9"></circle><circle cx="500.6" cy="141.0" r="4" fill="#5082F9" fill-opacity="0.55"></circle><circle cx="267.1" cy="111.7" r="4" fill="#C9CDD4" fill-opacity="0.55"></circle><circle cx="267.4" cy="52.9" r="4" fill="#5082F9" fill-opacity="0.55"></circle><circle cx="272.7" cy="121.4" r="4" fill="#C9CDD4" fill-opacity="0.55"></circle><circle cx="188.4" cy="156.2" r="4" fill="#C9CDD4" fill-opacity="0.55"></circle><circle cx="404.8" cy="174.2" r="4" fill="#5082F9" fill-opacity="0.55"></circle></svg><div class="xch-n">示例数据</div></div>
```

### 实例 7

```html
<div class="xch"><div class="xch-h"><b>收入与利润率</b><div class="xlg"><span><i style="background:#00BBB3"></i>收入（左轴，万元）</span><span><i style="background:#FF4F31"></i>利润率（右轴）</span></div></div><svg viewBox="0 0 560 210"><line class="gl" x1="48" x2="516" y1="186.0" y2="186.0"></line><text x="42" y="190.0" text-anchor="end">0</text><line class="gl" x1="48" x2="516" y1="151.2" y2="151.2"></line><text x="42" y="155.2" text-anchor="end">1,000</text><line class="gl" x1="48" x2="516" y1="116.4" y2="116.4"></line><text x="42" y="120.4" text-anchor="end">2,000</text><line class="gl" x1="48" x2="516" y1="81.6" y2="81.6"></line><text x="42" y="85.6" text-anchor="end">3,000</text><line class="gl" x1="48" x2="516" y1="46.8" y2="46.8"></line><text x="42" y="50.8" text-anchor="end">4,000</text><line class="gl" x1="48" x2="516" y1="12.0" y2="12.0"></line><text x="42" y="16.0" text-anchor="end">5,000</text><text x="67.5" y="204" text-anchor="middle">1月</text><text x="106.5" y="204" text-anchor="middle">2月</text><text x="145.5" y="204" text-anchor="middle">3月</text><text x="184.5" y="204" text-anchor="middle">4月</text><text x="223.5" y="204" text-anchor="middle">5月</text><text x="262.5" y="204" text-anchor="middle">6月</text><text x="301.5" y="204" text-anchor="middle">7月</text><text x="340.5" y="204" text-anchor="middle">8月</text><text x="379.5" y="204" text-anchor="middle">9月</text><text x="418.5" y="204" text-anchor="middle">10月</text><text x="457.5" y="204" text-anchor="middle">11月</text><text x="496.5" y="204" text-anchor="middle">12月</text><text x="522" y="190.0" text-anchor="start">0%</text><text x="522" y="155.2" text-anchor="start">4%</text><text x="522" y="120.4" text-anchor="start">8%</text><text x="522" y="85.6" text-anchor="start">12%</text><text x="522" y="50.8" text-anchor="start">16%</text><text x="522" y="16.0" text-anchor="start">20%</text><rect x="59.5" y="74.6" width="16" height="111.4" rx="2" fill="#00BBB3" opacity=".85"></rect><rect x="98.5" y="88.6" width="16" height="97.4" rx="2" fill="#00BBB3" opacity=".85"></rect><rect x="137.5" y="64.2" width="16" height="121.8" rx="2" fill="#00BBB3" opacity=".85"></rect><rect x="176.5" y="50.3" width="16" height="135.7" rx="2" fill="#00BBB3" opacity=".85"></rect><rect x="215.5" y="39.8" width="16" height="146.2" rx="2" fill="#00BBB3" opacity=".85"></rect><rect x="254.5" y="25.9" width="16" height="160.1" rx="2" fill="#00BBB3" opacity=".85"></rect><rect x="293.5" y="43.3" width="16" height="142.7" rx="2" fill="#00BBB3" opacity=".85"></rect><rect x="332.5" y="60.7" width="16" height="125.3" rx="2" fill="#00BBB3" opacity=".85"></rect><rect x="371.5" y="71.2" width="16" height="114.8" rx="2" fill="#00BBB3" opacity=".85"></rect><rect x="410.5" y="53.8" width="16" height="132.2" rx="2" fill="#00BBB3" opacity=".85"></rect><rect x="449.5" y="32.9" width="16" height="153.1" rx="2" fill="#00BBB3" opacity=".85"></rect><rect x="488.5" y="19.0" width="16" height="167.0" rx="2" fill="#00BBB3" opacity=".85"></rect><path d="M67.5,88.6 C74.0,89.6 93.5,97.0 106.5,94.6 C119.5,92.3 132.5,78.4 145.5,74.6 C158.5,70.9 171.5,74.6 184.5,72.0 C197.5,69.4 210.5,62.0 223.5,59.0 C236.5,55.9 249.5,52.0 262.5,53.8 C275.5,55.5 288.5,64.9 301.5,69.4 C314.5,73.9 327.5,78.4 340.5,80.7 C353.5,83.1 366.5,85.5 379.5,83.3 C392.5,81.2 405.5,73.5 418.5,67.7 C431.5,61.9 444.5,52.6 457.5,48.5 C470.5,44.5 490.0,44.2 496.5,43.3" fill="none" stroke="#FF4F31" stroke-width="2"></path><circle cx="67.5" cy="88.6" r="2.5" fill="#fff" stroke="#FF4F31" stroke-width="1.6"></circle><circle cx="106.5" cy="94.6" r="2.5" fill="#fff" stroke="#FF4F31" stroke-width="1.6"></circle><circle cx="145.5" cy="74.6" r="2.5" fill="#fff" stroke="#FF4F31" stroke-width="1.6"></circle><circle cx="184.5" cy="72.0" r="2.5" fill="#fff" stroke="#FF4F31" stroke-width="1.6"></circle><circle cx="223.5" cy="59.0" r="2.5" fill="#fff" stroke="#FF4F31" stroke-width="1.6"></circle><circle cx="262.5" cy="53.8" r="2.5" fill="#fff" stroke="#FF4F31" stroke-width="1.6"></circle><circle cx="301.5" cy="69.4" r="2.5" fill="#fff" stroke="#FF4F31" stroke-width="1.6"></circle><circle cx="340.5" cy="80.7" r="2.5" fill="#fff" stroke="#FF4F31" stroke-width="1.6"></circle><circle cx="379.5" cy="83.3" r="2.5" fill="#fff" stroke="#FF4F31" stroke-width="1.6"></circle><circle cx="418.5" cy="67.7" r="2.5" fill="#fff" stroke="#FF4F31" stroke-width="1.6"></circle><circle cx="457.5" cy="48.5" r="2.5" fill="#fff" stroke="#FF4F31" stroke-width="1.6"></circle><circle cx="496.5" cy="43.3" r="2.5" fill="#fff" stroke="#FF4F31" stroke-width="1.6"></circle></svg><div class="xch-n">示例数据</div></div>
```

### 实例 8：红色表示改善、蓝色表示恶化；毛利率变化单位为“点”，与百分比变化分开；缺失值显示“--”

```html
<div class="xtw"><table class="xt s"><thead><tr><th>产品线</th><th class="r">主营业务收入（万元）</th><th class="r">计划完成率</th><th class="r">同比</th><th class="r">毛利率</th><th class="r">毛利率同比</th></tr></thead><tbody>
<tr><td>内销家空</td><td class="r num">23,323.32</td><td class="r num">98.6%</td><td class="r num up">+4.23%</td><td class="r num">21.3%</td><td class="r num up">+0.8 点</td></tr>
<tr><td>内销商空</td><td class="r num">12,086.15</td><td class="r num">87.2%</td><td class="r num dn">-3.10%</td><td class="r num">24.6%</td><td class="r num dn">-1.2 点</td></tr>
<tr><td>出口整体</td><td class="r num">18,540.60</td><td class="r num">104.5%</td><td class="r num up">+9.87%</td><td class="r num">--</td><td class="r num">--</td></tr>
<tr class="sum"><td>合计</td><td class="r num">53,950.07</td><td class="r num">97.1%</td><td class="r num up">+3.96%</td><td class="r num">22.4%</td><td class="r num up">+0.3 点</td></tr></tbody></table></div>
```

## 开发工具选择（res/tools）

Quick BI、永洪 BI 与自开发三种方式的定位、规模、优缺点和适用场景。

集团报表规范 第 6 章

| 维度 | Quick BI | 永洪 BI | 自开发 |
| --- | --- | --- | --- |
| 产品定位 | 云端轻量智能 BI，26 年新引入 AI 搭建功能 | 企业级一站式大数据分析平台，集团主力报表工具 | 纯前后端代码定制开发的集团&公司级汇报大屏、特殊场景报表大屏 |
| 使用规模 | 当前主要服务营销服（中国区） | 服务全集团：开发用户约 3000 人、订阅用户约 1.5 万人，有效报表约 5000 张，覆盖国内各事业部全领域 | 汇报固定场景，稳态运行 |
| 核心优点 | ① 交互体验好、学习成本低，拖拽式搭建上手快；②功能全：仪表板、数据大屏、电子表格、即席分析、自助取数、数据填报； ③ Quick 加速引擎，10 亿条数据查询+计算 0.3 秒；④ 行级/列级权限，移动端自适应、可挂载飞书，支持订阅推送与监控预警 | ① MPP 架构，百亿级数据秒级响应，擅长海量数据实时计算与探索式分析；② 复杂报表能力强（多级嵌套、动态参数、中国式电子表格） | ① 样式定制灵活、适配性强，美观度优于拖拉拽工具；② 已封装趋势图/柱状图/指标卡等通用组件可复用；③ 数据链路完全自主可控 |
| 核心缺点 | ① 复杂报表支撑弱；② 大数据量复杂计算效率弱于永洪；③ 存量永洪报表无法直接迁移，需重新开发；④页面样式可自定义弱 | ① 学习成本高；② 与飞书兼容弱，仅账号打通、轻应用层面 | ① 运维成本高，需固定 Java/JS 开发人员长期支撑；② 维度调整需逐行改代码，需求变更响应慢 |
| 适配的数据分析场景 | 业务自助分析、轻量化敏捷看板、临时取数（自助取数支持百万级下载）、移动端看数、AI 辅助快速搭建 | 经营决策与领域类报表、中国式复杂报表（监管报送/打印）、海量数据实时计算、探索式深度分析、需源码级定制的场景 | 集团级高管汇报大屏、固定展示场景，对视觉样式和定制化要求极高、需求稳定（每月仅少量调整）的看板 |
| 开发与维护要求 | 低门槛，业务人员可自助拖拽完成，IT 只需做数据集与指标定义 | 分析师经培训可自主开发报表，复杂需求由数据团队支撑 | 需专业前后端开发团队持续投入，不适合无人长期维护的项目 |

## 附件与下载（res/attach）

规范附件、字体安装包和 Figma 源文件。

集团报表规范 第 7 章
报表上架前注意项及自检重点

飞书文档，需要海信账号

D-DIN-PRO 字体安装包

指标数值字体，400 至 900 字重

Pangea Design 3 组件库

Figma 源文件，本站组件参数的来源

Pangea 3 图标库

Figma 源文件，本站图标 SVG 的来源

