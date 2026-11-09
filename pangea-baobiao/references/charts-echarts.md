# ECharts 图表规范（PC 端）

报表、会议大屏、中后台中的图表统一用 ECharts（5.x）绘制。单文件离线页面把 `echarts.min.js` 内嵌，不依赖外网。图表类型的选择和数据条数上限见 `report-spec.md` 第 5 章；完整示例见 `assets/集团报表UI组件库.html` 的“图表”目录（ECharts 规范、柱形图、折线图、面积图、组合图、堆积图）。

## 必须遵守的设置

| 项目 | 设置 |
| --- | --- |
| x 轴线 | `axisLine.lineStyle.color: '#C9CDD4'` |
| x 轴刻度线 | 隐藏：`axisTick.show: false` |
| x 轴文字 | `axisLabel.color: '#4E5969'`，12px |
| y 轴网格线 | `splitLine.lineStyle: { color: '#E5E6EB', type: 'dashed' }` |
| y 轴文字 | `axisLabel.color: '#4E5969'`，12px；y 轴线与刻度隐藏 |
| 数据标签 | `label: { show: true, color: '#1D2129', fontSize: 12 }` |
| 折线数据点 | 隐藏：`showSymbol: false` |
| 坐标轴名称 | 不显示（`name` 为空），单位写在卡片标题或图例旁 |
| 系列色 | 图表色 1–12 按顺序：`#00BBB3 #5B8FF9 #31CEE5 #FFC124 #FF8000 #FF5555 #B02700 #A9E400 #59C286 #00D5C9 #FF93C4 #597EC3`。计划、实际、同期等有固定含义的系列优先用业务语义色（见 `tokens.md` 第 3 节），同一指标跨页颜色一致 |
| 面积 | 用系列色的低透明度纯色（`areaStyle.opacity` 0.1–0.2），不用渐变 |

## 基础配置

```js
const palette = ['#00BBB3','#5B8FF9','#31CEE5','#FFC124','#FF8000','#FF5555',
                 '#B02700','#A9E400','#59C286','#00D5C9','#FF93C4','#597EC3']; // 图表色 1–12
const base = {
  color: palette,
  grid: { left: 8, right: 24, top: 40, bottom: 8, containLabel: true },
  legend: { top: 0, right: 0, textStyle: { color: '#4E5969', fontSize: 12 } },
  tooltip: { trigger: 'axis' },
  xAxis: { type: 'category', name: '',
    axisLine: { lineStyle: { color: '#C9CDD4' } }, axisTick: { show: false },
    axisLabel: { color: '#4E5969', fontSize: 12 } },
  yAxis: { type: 'value', name: '',
    axisLine: { show: false }, axisTick: { show: false },
    axisLabel: { color: '#4E5969', fontSize: 12 },
    splitLine: { lineStyle: { color: '#E5E6EB', type: 'dashed' } } }
};
```

## 各类图表要点

- **柱形图**：`barMaxWidth` 12–20，顶部圆角 `[2,2,0,0]`；分组柱 `barGap: '20%'`；排名用横向条形图（x、y 轴互换）。
- **折线图**：`smooth: true, showSymbol: false, lineStyle.width: 2`；未发生的月份数据填 `null`，不要填 0。
- **面积图**：在折线上加 `areaStyle`；`xAxis.boundaryGap: false`。
- **组合图**：柱（≤3 个系列）用左轴，折线（≤2 条）用右轴 `yAxisIndex: 1`；右轴隐藏网格线。
- **堆积图**：同一 `stack` 名；组成部分顺序在所有分类中保持一致，只给最上层加顶部圆角。
- 图表容器高度随卡片变化时调用 `chart.resize()`；页面整体缩放（CSS zoom）后也要重新 resize。
