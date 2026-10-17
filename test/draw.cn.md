# x-cmd/draw 图表实验场（中文版）

> 基于 [x-cmd.com/draw](https://x-cmd.com/draw) 的 SVG 端点。本文档所有图的 `title=` / `labels=` / `unit=` / `alt=` 文案均为中文，方便中文场景测试。
> 用法：随便改一个 `labels=` / `values=` 看一眼，找到喜欢的再搬到正式 README。
>
> **通用参数**：`t=`（风格） · `scheme=dark|light`（默认跟随系统） · `num=all|peak|none`（数值标注） · `v=1`（冻结版本） · `w/h=`（尺寸）

---

## 目录

- [PIE · 饼图](#饼图)
- [BAR · 柱状图](#柱状图)
- [HBAR · 水平柱状图](#水平柱状图)
- [LINE · 折线图](#折线图)
- [AREA · 面积图](#面积图)
- [COMBO · 柱+线](#柱+线)
- [RADAR · 雷达图](#雷达图)
- [GAUGE · 仪表盘](#仪表盘)
- [SCATTER · 散点图](#散点图)
- [SANKEY · 桑基图](#桑基图)
- [QR · 二维码](#二维码)
- [LAYOUT · 排版实验](#layout--排版实验)

---

## PIE · 饼图

> 适合占比、份额、市场结构。`donut=0` 切回实心饼。

### `donut=1` 默认环

![浏览器市场份额 · Chrome 占主导](https://x-cmd.com/draw?type=pie&title=Chrome%20%E5%8D%A0%E6%8D%AE%E6%B5%8F%E8%A7%88%E5%99%A8%E5%B8%82%E5%9C%BA&labels=Chrome,Safari,%E7%81%AB%E7%8B%90,Edge,%E5%85%B6%E4%BB%96&values=65,18,7,6,4)

### `t=evil` 圆角扇区+数值内标

![浏览器市场份额 · evil 风](https://x-cmd.com/draw?type=pie&t=evil&title=%E6%B5%8F%E8%A7%88%E5%99%A8%E5%B8%82%E5%9C%BA%E4%BB%BD%E9%A2%9D&labels=Chrome,Safari,%E7%81%AB%E7%8B%90,Edge,%E5%85%B6%E4%BB%96&values=275,200,187,173,90)

### `t=evil-mono` 引线外标

![浏览器市场份额 · evil 外标风](https://x-cmd.com/draw?type=pie&t=evil-mono&title=%E6%B5%8F%E8%A7%88%E5%99%A8%E5%B8%82%E5%9C%BA%E4%BB%BD%E9%A2%9D&labels=Chrome,Safari,%E7%81%AB%E7%8B%90,Edge,%E5%85%B6%E4%BB%96&values=275,200,187,173,90)

### `t=market-mono` 灰阶+双列图例

![市场份额 · 灰阶版](https://x-cmd.com/draw?type=pie&t=market-mono&unit=%E4%BA%BF&title=%E5%B8%82%E5%9C%BA%E4%BB%BD%E9%A2%9D&labels=Skyline,Datawell,Cloudpeak,Taskbridge,Streamforge&values=27,21,13,21,12)

### `t=progress` 点状进度环（适合 2-4 大类）

![工作时间都耗到哪儿了](https://x-cmd.com/draw?type=pie&t=progress&unit=%E5%8F%97%E8%AE%BF&title=%E5%B7%A5%E4%BD%9C%E6%97%B6%E9%97%B4%E9%83%BD%E8%80%97%E5%88%B0%E5%93%AA%E5%84%BF%E4%BA%86&labels=%E9%A2%9D%E5%A4%96%E6%94%AF%E6%8C%81%E8%AF%B7%E6%B1%82,%E4%B8%8D%E5%87%86%E7%A1%AE%E7%9A%84%E9%A2%84%E6%B5%8B&values=48,67)

### `t=revenue` 渐变扇区+右图例

![收入结构](https://x-cmd.com/draw?type=pie&t=revenue&unit=%E8%AE%A2%E5%8D%95&title=%E6%94%B6%E5%85%A5%E7%BB%93%E6%9E%84&labels=%E7%9B%B4%E9%94%80,%E5%B9%B3%E5%8F%B0,%E6%89%B9%E5%8F%91,%E4%BB%A3%E7%90%86&values=52400,38900,24150,16300)

### `donut=0` 实心饼

![份额 · 实心](https://x-cmd.com/draw?type=pie&donut=0&title=%E4%BB%BD%E9%A2%9D&labels=TS,Py,Go&values=48,23,9)

---

## BAR · 柱状图

### `t=evil` 分组柱（双系列）

![按月下载 · 桌面 vs 移动](https://x-cmd.com/draw?type=bar&t=evil&labels=Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec&series=Desktop:34,87,51,63,45,78,39,92,65,53,80,27&series=Mobile:18,49,29,39,31,45,23,56,37,36,51,14)

### `t=base` 单系列（数值入柱）

![每周下载量](https://x-cmd.com/draw?type=bar&t=base&title=%E6%AF%8F%E5%91%A8%E4%B8%8B%E8%BD%BD%E9%87%8F&labels=%E5%91%A8%E4%B8%80,%E5%91%A8%E4%BA%8C,%E5%91%A8%E4%B8%89,%E5%91%A8%E5%9B%9B,%E5%91%A8%E4%BA%94&values=1200,1800,1500,2400,2100)

### `t=grid` 单元格柱（密集时序）

![按 2 小时分桶的提交数](https://x-cmd.com/draw?type=bar&t=grid&labels=00:00,02:00,04:00,06:00,08:00,10:00,12:00,14:00,16:00,18:00,20:00,22:00,00:00,02:00,04:00,06:00,08:00,10:00,12:00,14:00,16:00,18:00,20:00,22:00&values=3,2,1,1,2,2,3,5,7,9,10,11,10,12,11,10,9,8,7,6,5,4,3,2)

### 多系列并排

![每周下载量 · 多端对比](https://x-cmd.com/draw?type=bar&title=%E6%AF%8F%E5%91%A8%E4%B8%8B%E8%BD%BD%E9%87%8F&labels=%E5%91%A8%E4%B8%80,%E5%91%A8%E4%BA%8C,%E5%91%A8%E4%B8%89&series=draw:1200,1800,1500&series=quickchart:900,1000,1100)

### `stack=1` 堆叠

![流量来源堆叠](https://x-cmd.com/draw?type=bar&title=%E6%B5%81%E9%87%8F%E6%9D%A5%E6%BA%90&stack=1&labels=%E5%91%A8%E4%B8%80,%E5%91%A8%E4%BA%8C,%E5%91%A8%E4%B8%89&series=direct:30,25,40&series=organic:20,35,25)

### `stack=1` 自动百分比堆叠（量级差过大）

![量级悬殊自动切百分比](https://x-cmd.com/draw?type=bar&title=%E9%87%8F%E7%BA%A7%E6%82%AC%E6%AE%8A&stack=1&labels=Q1,Q2,Q3,Q4&series=organic:2000,3500,2500,4000&series=paid:30,25,40,35)

---

## HBAR · 水平柱状图

> 排行、长标签、参考线场景。

### 默认：排行（标签左值右）

![热门语言 · 星标](https://x-cmd.com/draw?type=hbar&title=%E6%98%9F%E6%A0%87&labels=TypeScript,Python,Go,Rust&values=4821,2312,980,645)

### `t=opendata` 参考线（WCAG 等阈值场景）

![对比度 vs WCAG AA](https://x-cmd.com/draw?type=hbar&t=opendata&unit=%E4%B8%8E%E7%99%BD%E8%89%B2%E7%9A%84%E5%AF%B9%E6%AF%94%E5%BA%A6&ref=4.5&reflabel=WCAG%20AA%20%C2%B7%204.5%3A1&labels=%E7%9F%B3%E6%9D%BF%E7%81%B0,%E7%BB%BF,%E7%BA%A2,%E6%A9%99,%E9%9D%92,%E8%93%9D,%E6%B7%B1%E7%B4%AB&values=2.8,3.9,4.2,4.6,4.8,5.3,8.6)

### `t=xcmd` 语言像素格（百分比）

![</> 以 C 为主](https://x-cmd.com/draw?type=hbar&t=xcmd&title=%3C%2F%3E%20%E4%BB%A5%20C%20%E4%B8%BA%E4%B8%BB&labels=C,CHeader,Sh,其他&values=80.4,11.1,2.5,6.0)

### `t=xcmd-issue` 新建/关闭蝴蝶

![Issue 生命周期](https://x-cmd.com/draw?type=hbar&t=xcmd-issue&labels=0-30d,30-60d,60-90d,90-180d,180-360d,360-720d&series=新建:2,1,12,5,7,7&series=关闭:2,1,9,4,5,6)

### `t=rank` 实色基础 + 斜纹增益

![LLM 排行榜](https://x-cmd.com/draw?type=hbar&t=rank&labels=GPT-6%20%28Astra%29,GPT-5.6%20Sol,DeepSeek%20V4.1%20Flash,Muse%20Spark%201.3,Claude%20Fable%205.1,Claude%20Opus%205,Kimi%20K3,GLM%205.3&series=基础得分:35,31.4,20.3,31,31.9,34,24,20&series=搜索增益:35.3,35.3,45,34.3,29.1,25.3,32.3,35.3)

---

## LINE · 折线图

### 默认：虚线网格+空心点

![趋势 · 双系列](https://x-cmd.com/draw?type=line&title=%E8%B6%8B%E5%8A%BF&labels=Jan,Feb,Mar,Apr,May,Jun&series=draw:20,27,25,32,30,38&series=qc:15,17,17,19,20,18)

### `t=evil` 直线+大点+右上图例

![桌面 vs 移动 · 全年](https://x-cmd.com/draw?type=line&t=evil&labels=Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec&series=Desktop:524,902,663,749,587,420,690,905,730,590,388,262&series=Mobile:342,458,400,433,382,290,391,467,405,362,299,218)

### `t=evil-glow` 渐变发光

![已结算 vs 待结算](https://x-cmd.com/draw?type=line&t=evil-glow&labels=Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec&series=Payouts:430,430,470,530,670,770,700,730,810,860,880,910&series=Pending:600,540,500,380,320,210,250,230,180,150,130,110)

### `t=evil-mono` 当前 vs 上周

![本周 vs 上周](https://x-cmd.com/draw?type=line&t=evil-mono&labels=%E5%91%A8%E4%B8%80,%E5%91%A8%E4%BA%8C,%E5%91%A8%E4%B8%89,%E5%91%A8%E5%9B%9B,%E5%91%A8%E4%BA%94,%E5%91%A8%E5%85%AD&series=本周:34,40,42,38,30,44&series=上周:44,49,43,35,31,52)

### `t=opendata` 线端标签 + 旋转 Y 轴标题（数据叙事）

![Python 在 2018 年前后超越 Java](https://x-cmd.com/draw?type=line&t=opendata&title=Python%20%E5%9C%A8%202018%20%E5%B9%B4%E5%89%8D%E5%90%8E%E8%B6%85%E8%B6%8A%20Java&labels=2015,2016,2017,2018,2019,2020,2021,2022&series=Python:28,33,40,52,62,70,78,84&series=Java:72,70,65,58,52,48,45,42&series=JavaScript:45,48,50,52,54,55,56,53)

### `num=peak` 仅标峰值

![新增注册 · 仅标峰](https://x-cmd.com/draw?type=line&num=peak&title=%E6%96%B0%E5%A2%9E%E6%B3%A8%E5%86%8C&labels=W1,W2,W3,W4,W5,W6,W7,W8&series=注册数:120,180,240,210,290,340,310,420)

---

## AREA · 面积图

> 累计、趋势、增长曲线。

### 默认 evil 风

![下载面积 · 桌面 vs 移动](https://x-cmd.com/draw?type=area&labels=Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec&series=Desktop:342,876,512,630,458,782,394,924,646,533,806,270&series=Mobile:185,491,291,391,309,448,233,558,367,358,515,148)

### `t=star` 手绘感 GitHub Star

![Star 历史曲线 · 手绘](https://x-cmd.com/draw?type=area&t=star&title=Star%20%E5%8E%86%E5%8F%B2%E6%9B%B2%E7%BA%BF&unit=%E9%A2%97%E6%98%9F&labels=12%E6%9C%88,1%E6%9C%88,2%E6%9C%88,3%E6%9C%88,4%E6%9C%88,5%E6%9C%88,6%E6%9C%88&values=120,300,520,900,1300,1500,1750)

### `t=pixel` 像素风 Star History（README 招牌）

![Star 历史 · 像素](https://x-cmd.com/draw?type=area&t=pixel&unit=%E9%A2%97%E6%98%9F&labels=2024%E5%B9%B412%E6%9C%88,2025%E5%B9%B41%E6%9C%88,2%E6%9C%88,3%E6%9C%88,4%E6%9C%88,5%E6%9C%88,6%E6%9C%88,7%E6%9C%88,8%E6%9C%88,9%E6%9C%88,10%E6%9C%88,11%E6%9C%88,12%E6%9C%88,2026%E5%B9%B41%E6%9C%88,2%E6%9C%88,3%E6%9C%88,4%E6%9C%88,5%E6%9C%88,6%E6%9C%88,7%E6%9C%88,8%E6%9C%88,9%E6%9C%88&values=0,18,52,98,160,245,360,480,610,735,850,960,1060,1140,1210,1270,1320,1360,1395,1420,1440,1458)

### `t=polka` 波点对比（多仓库）

![Star 对比 · x-cmd 双仓库](https://x-cmd.com/draw?type=area&t=polka&labels=Dec%202024,Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec%202025,Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep&series=x-cmd%2Fx-cmd:0,18,52,98,160,245,360,480,610,735,850,960,1060,1140,1210,1270,1320,1360,1395,1420,1440,1458&series=x-cmd%2Fllm:0,8,22,48,82,126,190,270,360,455,545,630,705,770,825,870,905,932,951,965,978,986)

### `t=opendata` 数据叙事版

![Apple 股价因 AI 热潮创纪录新高](https://x-cmd.com/draw?type=area&t=opendata&title=Apple%20%E8%82%A1%E4%BB%B7%E5%9B%A0%20AI%20%E7%83%AD%E6%BD%AE%E5%88%9B%E7%BA%AA%E5%BD%95%E6%96%B0%E9%AB%98&subtitle=AAPL%20%E6%9C%88%E5%BA%A6%E6%94%B6%E7%9B%98%E4%BB%B7%EF%BC%8C2023%20%E5%B9%B4%201%20%E6%9C%88%E8%87%B3%202024%20%E5%B9%B4%2012%20%E6%9C%88&source=%E6%9D%A5%E6%BA%90%EF%BC%9ANasdaq%20%E5%8E%86%E5%8F%B2%E6%95%B0%E6%8D%AE&unit=%E8%82%A1%E4%BB%B7&labels=2023%E5%B9%B41%E6%9C%88,2023%E5%B9%B42%E6%9C%88,2023%E5%B9%B43%E6%9C%88,2023%E5%B9%B44%E6%9C%88,2023%E5%B9%B45%E6%9C%88,2023%E5%B9%B46%E6%9C%88,2023%E5%B9%B47%E6%9C%88,2023%E5%B9%B48%E6%9C%88,2023%E5%B9%B49%E6%9C%88,2023%E5%B9%B410%E6%9C%88,2023%E5%B9%B411%E6%9C%88,2023%E5%B9%B412%E6%9C%88,2024%E5%B9%B41%E6%9C%88,2024%E5%B9%B42%E6%9C%88,2024%E5%B9%B43%E6%9C%88,2024%E5%B9%B44%E6%9C%88,2024%E5%B9%B45%E6%9C%88,2024%E5%B9%B46%E6%9C%88,2024%E5%B9%B47%E6%9C%88,2024%E5%B9%B48%E6%9C%88,2024%E5%B9%B49%E6%9C%88,2024%E5%B9%B410%E6%9C%88,2024%E5%B9%B411%E6%9C%88,2024%E5%B9%B412%E6%9C%88&values=130,147,125,170,177,194,196,188,171,171,190,193,186,188,171,170,192,211,222,227,226,226,237,243)

---

## COMBO · 柱+线

> 量级差距小的双 y 轴场景。

### 紫柱绿线经典

![月度收入与利润](https://x-cmd.com/draw?type=combo&t=evil&labels=Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec&series=Revenue:42,58,41,62,54,78,61,82,59,68,72,91&line=Profit:18,24,16,29,22,35,27,39,25,31,33,43)

### 双系列柱 + 单线

![下载量 · 双柱一线](https://x-cmd.com/draw?type=combo&title=%E4%B8%8B%E8%BD%BD%E9%87%8F&labels=%E5%91%A8%E4%B8%80,%E5%91%A8%E4%BA%8C,%E5%91%A8%E4%B8%89,%E5%91%A8%E5%9B%9B,%E5%91%A8%E4%BA%94&series=draw:1200,1800,1500,2400,2100&series=qc:900,1000,1100,1150,1200&line=增长率:5,8,6,12,10)

---

## RADAR · 雷达图

### 默认：3-12 维

![技能雷达](https://x-cmd.com/draw?type=radar&title=%E6%8A%80%E8%83%BD&labels=TS,Rust,Go,Python,SQL&values=90,60,45,80,70)

### `t=evil` 双系列

![桌面 vs 移动 · 技术栈](https://x-cmd.com/draw?type=radar&t=evil&labels=JavaScript,Python,CSS,Node.js,React,TypeScript&series=Desktop:58,72,70,76,68,84&series=Mobile:34,48,44,81,38,66)

### `t=xcmd` 手写体五维（中文友好）

![六维评估](https://x-cmd.com/draw?type=radar&t=xcmd&labels=%E6%80%A7%E8%83%BD,%E6%98%93%E7%94%A8%E6%80%A7,%E5%8A%9F%E8%83%BD,%E5%8F%AF%E7%A7%BB%E6%A4%8D%E6%80%A7,%E5%8F%AF%E9%9D%A0%E6%80%A7&values=68,54,62,76,73)

---

## GAUGE · 仪表盘

### 半圆多环（默认）

![浏览器性能多环](https://x-cmd.com/draw?type=gauge&labels=Chrome,Safari,%E7%81%AB%E7%8B%90,Edge,%E5%85%B6%E4%BB%96&values=86,72,64,58,31)

### `t=gradient` 渐变多环

![浏览器性能多环 · 渐变](https://x-cmd.com/draw?type=gauge&t=gradient&labels=Chrome,Safari,%E7%81%AB%E7%8B%90,Edge,%E5%85%B6%E4%BB%96&values=88,76,69,61,43)

### `t=reliability` 单环四分区（交付可靠性）

![交付可靠性](https://x-cmd.com/draw?type=gauge&t=reliability&title=%E4%BA%A4%E4%BB%98%E5%8F%AF%E9%9D%A0%E6%80%A7&value=842&max=1000)

### 单环直白（覆盖率）

![代码覆盖率](https://x-cmd.com/draw?type=gauge&title=%E4%BB%A3%E7%A0%81%E8%A6%86%E7%9B%96%E7%8E%87&value=84&max=100)

---

## SCATTER · 散点图

### 双数值轴（latency vs load）

![延迟 vs 负载](https://x-cmd.com/draw?type=scatter&title=%E5%BB%B6%E8%BF%9F%20vs%20%E8%B4%9F%E8%BD%BD&x=10,20,30,40,50,60&y=5,8,7,12,18,30)

### 双系列对比

![当前 vs 基线](https://x-cmd.com/draw?type=scatter&x=-18,-14,-11,-8,-5,-2,2,5,8,11,15,18&x=-17,-13,-10,-6,-3,1,4,7,10,13,16,19&y=-8,4,-2,12,8,19,14,25,18,31,27,39&y=15,10,22,16,28,23,34,30,42,38,49,44)

---

## SANKEY · 桑基图

### 基础款（营销漏斗）

![营销漏斗](https://x-cmd.com/draw?type=sankey&labels=%E8%87%AA%E7%84%B6%E6%90%9C%E7%B4%A2,%E4%BB%98%E8%B4%B9%E5%B9%BF%E5%91%8A,%E7%A4%BE%E4%BA%A4%E5%AA%92%E4%BD%93,%E8%90%BD%E5%9C%B0%E9%A1%B5,%E5%95%86%E5%93%81%E9%A1%B5,%E8%B4%AD%E7%89%A9%E8%BD%A6,%E8%B7%B3%E5%87%BA,%E8%B4%AD%E4%B9%B0&links=%E8%87%AA%E7%84%B6%E6%90%9C%E7%B4%A2%3E%E8%90%BD%E5%9C%B0%E9%A1%B5:42000%3B%E4%BB%98%E8%B4%B9%E5%B9%BF%E5%91%8A%3E%E8%90%BD%E5%9C%B0%E9%A1%B5:28000%3B%E7%A4%BE%E4%BA%A4%E5%AA%92%E4%BD%93%3E%E8%90%BD%E5%9C%B0%E9%A1%B5:18000%3B%E8%90%BD%E5%9C%B0%E9%A1%B5%3E%E5%95%86%E5%93%81%E9%A1%B5:52000%3B%E8%90%BD%E5%9C%B0%E9%A1%B5%3E%E8%B7%B3%E5%87%BA:36000%3B%E5%95%86%E5%93%81%E9%A1%B5%3E%E8%B4%AD%E7%89%A9%E8%BD%A6:31000%3B%E5%95%86%E5%93%81%E9%A1%B5%3E%E8%B7%B3%E5%87%BA:21000%3B%E8%B4%AD%E7%89%A9%E8%BD%A6%3E%E8%B4%AD%E4%B9%B0:24000%3B%E8%B4%AD%E7%89%A9%E8%BD%A6%3E%E8%B7%B3%E5%87%BA:7000)

### `t=fund` 基金流向

![资金流向 · 季度至今](https://x-cmd.com/draw?type=sankey&t=fund&title=%E8%B5%84%E9%87%91%E6%B5%81%E5%90%91&unit=%E6%9C%AC%E5%AD%A3%E5%BA%A6%E8%87%B3%E4%BB%8A&labels=%E6%B5%81%E5%85%A5,%E8%82%A1%E7%A5%A8,%E5%80%BA%E5%88%B8,%E7%8E%B0%E9%87%91,%E5%A2%9E%E9%95%BF%E5%9E%8B,%E6%94%B6%E7%9B%8A%E5%9E%8B,%E5%82%A8%E5%A4%87&links=%E6%B5%81%E5%85%A5%3E%E8%82%A1%E7%A5%A8:78000%3B%E6%B5%81%E5%85%A5%3E%E5%80%BA%E5%88%B8:46000%3B%E6%B5%81%E5%85%A5%3E%E7%8E%B0%E9%87%91:24000%3B%E8%82%A1%E7%A5%A8%3E%E5%A2%9E%E9%95%BF%E5%9E%8B:52000%3B%E8%82%A1%E7%A5%A8%3E%E6%94%B6%E7%9B%8A%E5%9E%8B:26000%3B%E5%80%BA%E5%88%B8%3E%E6%94%B6%E7%9B%8A%E5%9E%8B:19000%3B%E5%80%BA%E5%88%B8%3E%E5%82%A8%E5%A4%87:27000%3B%E7%8E%B0%E9%87%91%3E%E5%A2%9E%E9%95%BF%E5%9E%8B:9000%3B%E7%8E%B0%E9%87%91%3E%E5%82%A8%E5%A4%87:15000)

### `t=pipeline` 收入管线

![收入管线](https://x-cmd.com/draw?type=sankey&t=pipeline&labels=%E6%89%B9%E5%8F%91,%E9%9B%B6%E5%94%AE,%E6%9C%8D%E5%8A%A1,%E6%8E%88%E6%9D%83,%E6%89%A9%E5%BC%A0,%E5%82%A8%E5%A4%87,%E6%94%AF%E6%8C%81,%E5%B7%A5%E5%85%B7&links=%E6%89%B9%E5%8F%91%3E%E6%89%A9%E5%BC%A0:46220%3B%E9%9B%B6%E5%94%AE%3E%E6%89%A9%E5%BC%A0:6420%3B%E9%9B%B6%E5%94%AE%3E%E5%82%A8%E5%A4%87:25060%3B%E6%9C%8D%E5%8A%A1%3E%E5%82%A8%E5%A4%87:21650%3B%E6%9C%8D%E5%8A%A1%3E%E6%94%AF%E6%8C%81:6690%3B%E6%8E%88%E6%9D%83%3E%E6%94%AF%E6%8C%81:5780%3B%E6%8E%88%E6%9D%83%3E%E5%B7%A5%E5%85%B7:9180)

---

## QR · 二维码

> `d=` 直接放文本，`fg=#RRGGBB` 控制模块颜色，`title=` / `unit=` 配卡下说明。

### 默认蓝

![扫码访问 x-cmd/draw](https://x-cmd.com/draw?type=qr&d=https://x-cmd.com/draw&title=x-cmd.com&unit=%E6%89%AB%E7%A0%81%E6%89%93%E5%BC%80%E5%9B%BE%E8%A1%A8%E6%9C%8D%E5%8A%A1)

### 自配色（紫）

![x-cmd/draw 二维码 · 自配色](https://x-cmd.com/draw?type=qr&d=https://x-cmd.com/draw&fg=%236366f1)

### 暗背景配色

![x-cmd/draw 二维码 · 暗背景](https://x-cmd.com/draw?type=qr&d=https://x-cmd.com/draw&fg=%23ffffff&bg=%23111827)

---

## LAYOUT · 排版实验

> GitHub Flavored Markdown 支持 HTML 并排布局。**坑点**：
> 1. `<td>` 里写 `![alt](url)` 在 GitHub 渲染器中**不稳定**——改用 `<img>` 标签最稳。
> 2. 多列时图会撑爆单元格——必须用 `<img width="...">` 或 x-cmd URL `&w=` 限宽。
> 3. `<table>` 必须块级独占，前后留空行；GitHub 不会包 `<p>`。
>
> 以下 demo 全部用 `<table>` + `<img>` + `width`，文案已切到中文。

### 2×2 网格

<table>
<tr>
<td align="center"><img src="https://x-cmd.com/draw?type=pie&t=progress&w=400&title=SaaS%20%E4%BB%BD%E9%A2%9D&labels=Salesforce,HubSpot,Oracle,%E5%85%B6%E4%BB%96&values=23,18,14,45" alt="SaaS 份额" width="380"></td>
<td align="center"><img src="https://x-cmd.com/draw?type=pie&donut=0&w=400&title=%E4%BA%91%E6%9C%8D%E5%8A%A1%E6%8B%86%E5%88%86&labels=%E8%AE%A1%E7%AE%97,%E5%AD%98%E5%82%A8,%E7%BD%91%E7%BB%9C,%E5%85%B6%E4%BB%96&values=42,28,18,12" alt="云服务拆分" width="380"></td>
</tr>
<tr>
<td align="center"><img src="https://x-cmd.com/draw?type=pie&t=revenue&w=400&title=%E6%B5%81%E9%87%8F%E6%9D%A5%E6%BA%90&labels=%E7%9B%B4%E6%8E%A5,%E6%8E%A8%E4%BB%8B,%E8%87%AA%E7%84%B6,%E4%BB%98%E8%B4%B9&values=44,28,18,10" alt="流量来源" width="380"></td>
<td align="center"><img src="https://x-cmd.com/draw?type=pie&t=market-mono&w=400&title=%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F%E5%8D%A0%E6%AF%94&labels=macOS,Linux,Windows,其他&values=42,33,18,7" alt="操作系统占比" width="380"></td>
</tr>
</table>

### 3 列 —— gauge 并排

<table>
<tr>
<td align="center"><img src="https://x-cmd.com/draw?type=gauge&w=320&title=%E8%A6%86%E7%9B%96%E7%8E%87&value=84&max=100" alt="覆盖率" width="280"></td>
<td align="center"><img src="https://x-cmd.com/draw?type=gauge&w=320&title=%E5%8F%AF%E9%9D%A0%E6%80%A7&value=842&max=1000" alt="可靠性" width="280"></td>
<td align="center"><img src="https://x-cmd.com/draw?type=gauge&w=320&title=%E5%BB%B6%E8%BF%9F&value=42&max=100" alt="延迟" width="280"></td>
</tr>
</table>

### 4 列 —— 折线对比

<table>
<tr>
<td align="center"><img src="https://x-cmd.com/draw?type=line&t=evil&w=260&title=Q1&labels=W1,W2,W3,W4,W5,W6,W7,W8&series=Q1:120,160,140,200,180,240,210,290" alt="第一季度" width="220"></td>
<td align="center"><img src="https://x-cmd.com/draw?type=line&t=evil&w=260&title=Q2&labels=W1,W2,W3,W4,W5,W6,W7,W8&series=Q2:140,180,160,220,200,260,230,310" alt="第二季度" width="220"></td>
<td align="center"><img src="https://x-cmd.com/draw?type=line&t=evil&w=260&title=Q3&labels=W1,W2,W3,W4,W5,W6,W7,W8&series=Q3:160,200,180,240,220,280,250,330" alt="第三季度" width="220"></td>
<td align="center"><img src="https://x-cmd.com/draw?type=line&t=evil&w=260&title=Q4&labels=W1,W2,W3,W4,W5,W6,W7,W8&series=Q4:180,220,200,260,240,300,270,350" alt="第四季度" width="220"></td>
</tr>
</table>

### 仪表盘专题 —— 单图多环

<img src="https://x-cmd.com/draw?type=gauge&t=gradient&title=%E5%B7%A5%E7%A8%8B%E5%81%A5%E5%BA%B7%E5%BA%A6&labels=%E8%A6%86%E7%9B%96%E7%8E%87,%E5%8F%AF%E9%9D%A0%E6%80%A7,%E5%BB%B6%E8%BF%9F,%E6%BB%A1%E6%84%8F%E5%BA%A6,%E9%80%9F%E5%BA%A6&values=84,82,71,88,76" alt="工程健康度" width="800">

### 双系列对比 —— 旧 vs 新

<table>
<tr>
<td align="center"><img src="https://x-cmd.com/draw?type=line&t=evil-mono&w=520&title=Legacy&labels=W1,W2,W3,W4,W5&series=Legacy:120,140,160,180,200" alt="旧版" width="460"></td>
<td align="center"><img src="https://x-cmd.com/draw?type=line&t=evil-glow&w=520&title=New&labels=W1,W2,W3,W4,W5&series=New:80,180,300,460,640" alt="新版" width="460"></td>
</tr>
</table>

### 暗色模式预览 —— 加 `&scheme=dark`

<table>
<tr>
<th>浅色</th>
<th>深色</th>
</tr>
<tr>
<td align="center"><img src="https://x-cmd.com/draw?type=pie&t=progress&w=400&title=%E6%B5%85%E8%89%B2&labels=A,B&values=72,28&scheme=light" alt="浅色模式" width="360"></td>
<td align="center"><img src="https://x-cmd.com/draw?type=pie&t=progress&w=400&title=%E6%B7%B1%E8%89%B2&labels=A,B&values=72,28&scheme=dark" alt="深色模式" width="360"></td>
</tr>
</table>

### 另一种思路 —— 用 Markdown 表格语法

| 浅色 | 深色 |
|:---:|:---:|
| ![浅色](https://x-cmd.com/draw?type=pie&t=progress&w=300&title=%E6%B5%85&labels=A,B&values=72,28&scheme=light) | ![深色](https://x-cmd.com/draw?type=pie&t=progress&w=300&title=%E6%B7%B1&labels=A,B&values=72,28&scheme=dark) |

---

## 备注

- `scheme=` 不指定时跟随查看者系统；想确定请显式写 `scheme=light` 或 `scheme=dark`
- `v=1` 锁定版本号，防止 x-cmd 端升级导致图变形
- 二维码对 URL 长度敏感，长文本建议先用短链服务压缩
- 所有 `&` 之间用普通空格或空行隔开均可；标签里如有逗号或特殊字符务必做 URL 编码（`%20` 等）
- 中文在 URL 中走 UTF-8 % 编码；脚本生成时 `safe=",-_~."` 保留 ASCII 标点
- 完整数据 schema 见 x-cmd/draw 各 type 示例；JSON 体可走 `?d=...` 一并传
