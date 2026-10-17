# x-cmd/draw 图表实验场

> 基于 [x-cmd.com/draw](https://x-cmd.com/draw) 的 SVG 端点。所有图均为 GET `/draw?type=...` 渲染，URL 友好、可永久嵌入。
> 用法：随便改一个 `labels=` / `values=` 看一眼，找到喜欢的再搬到正式 README。
>
> **通用参数**：`t=`（风格）· `scheme=dark|light`（默认跟随系统）· `num=all|peak|none`（数值标注）· `v=1`（冻结版本）· `w/h=`（尺寸）。

---

## 目录

- [PIE · 饼图](#pie--饼图)
- [BAR · 柱状图](#bar--柱状图)
- [HBAR · 水平柱状图](#hbar--水平柱状图)
- [LINE · 折线图](#line--折线图)
- [AREA · 面积图](#area--面积图)
- [COMBO · 柱+线](#combo--柱线)
- [RADAR · 雷达图](#radar--雷达图)
- [GAUGE · 仪表盘](#gauge--仪表盘)
- [SCATTER · 散点图](#scatter--散点图)
- [SANKEY · 桑基图](#sankey--桑基图)
- [QR · 二维码](#qr--二维码)
- [LAYOUT · 排版实验](#layout--排版实验)

---

## PIE · 饼图

> 适合占比、份额、市场结构。`donut=0` 切回实心饼。

### `donut=1` 默认环
![Browser market — Chrome dominates](https://x-cmd.com/draw?type=pie&title=Chrome%20holds%20the%20browser%20market&labels=Chrome,Safari,Firefox,Edge,Other&values=65,18,7,6,4)

### `t=evil` 圆角扇区+数值内标
![Browser market — evil](https://x-cmd.com/draw?type=pie&t=evil&title=Browser%20market&labels=Chrome,Safari,Firefox,Edge,Other&values=275,200,187,173,90)

### `t=evil-mono` 引线外标
![Browser market — evil mono](https://x-cmd.com/draw?type=pie&t=evil-mono&title=Browser%20market&labels=Chrome,Safari,Firefox,Edge,Other&values=275,200,187,173,90)

### `t=market-mono` 灰阶+双列图例
![Market share — mono](https://x-cmd.com/draw?type=pie&t=market-mono&unit=B&title=Market%20share&labels=Skyline,Datawell,Cloudpeak,Taskbridge,Streamforge&values=27,21,13,21,12)

### `t=progress` 点状进度环（适合 2-4 大类）
![Where the workday leaks](https://x-cmd.com/draw?type=pie&t=progress&unit=responses&title=Where%20the%20workday%20leaks&labels=Additional%20support%20requests,Inaccurate%20forecasts&values=48,67)

### `t=revenue` 渐变扇区+右图例
![Revenue mix](https://x-cmd.com/draw?type=pie&t=revenue&unit=orders&title=Revenue&labels=Direct,Marketplace,Wholesale,Affiliate&values=52400,38900,24150,16300)

### `donut=0` 实心饼
![Share — solid](https://x-cmd.com/draw?type=pie&donut=0&title=Share&labels=TS,Py,Go&values=48,23,9)

---

## BAR · 柱状图

### `t=evil` 分组柱（双系列）
![Downloads by month](https://x-cmd.com/draw?type=bar&t=evil&labels=Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec&series=Desktop:34,87,51,63,45,78,39,92,65,53,80,27&series=Mobile:18,49,29,39,31,45,23,56,37,36,51,14)

### `t=base` 单系列（数值入柱）
![Weekly downloads](https://x-cmd.com/draw?type=bar&t=base&title=Weekly%20downloads&labels=Mon,Tue,Wed,Thu,Fri&values=1200,1800,1500,2400,2100)

### `t=grid` 单元格柱（密集时序）
![Commits by 2-hour bucket](https://x-cmd.com/draw?type=bar&t=grid&labels=00:00,02:00,04:00,06:00,08:00,10:00,12:00,14:00,16:00,18:00,20:00,22:00,00:00,02:00,04:00,06:00,08:00,10:00,12:00,14:00,16:00,18:00,20:00,22:00&values=3,2,1,1,2,2,3,5,7,9,10,11,10,12,11,10,9,8,7,6,5,4,3,2)

### 多系列并排
![Weekly — multi](https://x-cmd.com/draw?type=bar&title=Weekly%20downloads&labels=Mon,Tue,Wed&series=draw:1200,1800,1500&series=quickchart:900,1000,1100)

### `stack=1` 堆叠
![Traffic stacked](https://x-cmd.com/draw?type=bar&title=Traffic&stack=1&labels=Mon,Tue,Wed&series=direct:30,25,40&series=organic:20,35,25)

### `stack=1` 自动百分比堆叠（量级差过大）
![Stacked %](https://x-cmd.com/draw?type=bar&title=Mixed%20scale&stack=1&labels=Q1,Q2,Q3,Q4&series=organic:2000,3500,2500,4000&series=paid:30,25,40,35)

---

## HBAR · 水平柱状图

> 排行、长标签、参考线场景。

### 默认：排行（标签左值右）
![Top stars](https://x-cmd.com/draw?type=hbar&title=Stars&labels=TypeScript,Python,Go,Rust&values=4821,2312,980,645)

### `t=opendata` 参考线（WCAG 等阈值场景）
![Contrast ratio vs WCAG AA](https://x-cmd.com/draw?type=hbar&t=opendata&unit=Contrast%20ratio%20vs%20white&ref=4.5&reflabel=WCAG%20AA%20%C2%B7%204.5%3A1&labels=Slate%20Gray,Green,Red,Orange,Teal,Blue,Deep%20Purple&values=2.8,3.9,4.2,4.6,4.8,5.3,8.6)

### `t=xcmd` 语言像素格（百分比）
![</> 以 C 为主](https://x-cmd.com/draw?type=hbar&t=xcmd&title=%3C%2F%3E%20%E4%BB%A5%20C%20%E4%B8%BA%E4%B8%BB&labels=C,CHeader,Sh,其他&values=80.4,11.1,2.5,6.0)

### `t=xcmd-issue` 新建/关闭蝴蝶
![Issue lifecycles](https://x-cmd.com/draw?type=hbar&t=xcmd-issue&labels=0-30d,30-60d,60-90d,90-180d,180-360d,360-720d&series=新建:2,1,12,5,7,7&series=关闭:2,1,9,4,5,6)

### `t=rank` 实色基础 + 斜纹增益
![LLM leaderboard](https://x-cmd.com/draw?type=hbar&t=rank&labels=GPT-6%20%28Astra%29,GPT-5.6%20Sol,DeepSeek%20V4.1%20Flash,Muse%20Spark%201.3,Claude%20Fable%205.1,Claude%20Opus%205,Kimi%20K3,GLM%205.3&series=基础得分:35,31.4,20.3,31,31.9,34,24,20&series=搜索增益:35.3,35.3,45,34.3,29.1,25.3,32.3,35.3)

---

## LINE · 折线图

### 默认：虚线网格+空心点
![Trend](https://x-cmd.com/draw?type=line&title=Trend&labels=Jan,Feb,Mar,Apr,May,Jun&series=draw:20,27,25,32,30,38&series=qc:15,17,17,19,20,18)

### `t=evil` 直线+大点+右上图例
![Desktop vs Mobile](https://x-cmd.com/draw?type=line&t=evil&labels=Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec&series=Desktop:524,902,663,749,587,420,690,905,730,590,388,262&series=Mobile:342,458,400,433,382,290,391,467,405,362,299,218)

### `t=evil-glow` 渐变发光
![Payouts vs Pending](https://x-cmd.com/draw?type=line&t=evil-glow&labels=Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec&series=Payouts:430,430,470,530,670,770,700,730,810,860,880,910&series=Pending:600,540,500,380,320,210,250,230,180,150,130,110)

### `t=evil-mono` 当前 vs 上周
![This vs last week](https://x-cmd.com/draw?type=line&t=evil-mono&labels=Mon,Tue,Wed,Thu,Fri,Sat&series=this%20week:34,40,42,38,30,44&series=last%20week:44,49,43,35,31,52)

### `t=opendata` 线端标签 + 旋转 Y 轴标题（数据叙事）
![Python overtook Java](https://x-cmd.com/draw?type=line&t=opendata&title=Python%20overtook%20Java%20around%202018&labels=2015,2016,2017,2018,2019,2020,2021,2022&series=Python:28,33,40,52,62,70,78,84&series=Java:72,70,65,58,52,48,45,42&series=JavaScript:45,48,50,52,54,55,56,53)

### `num=peak` 仅标峰值
![Peak only](https://x-cmd.com/draw?type=line&num=peak&title=Signups&labels=W1,W2,W3,W4,W5,W6,W7,W8&series=Signups:120,180,240,210,290,340,310,420)

---

## AREA · 面积图

> 累计、趋势、增长曲线。

### 默认 evil 风
![Downloads area](https://x-cmd.com/draw?type=area&labels=Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec&series=Desktop:342,876,512,630,458,782,394,924,646,533,806,270&series=Mobile:185,491,291,391,309,448,233,558,367,358,515,148)

### `t=star` 手绘感 GitHub Star
![Star history — hand-drawn](https://x-cmd.com/draw?type=area&t=star&title=Star%20History&unit=stars&labels=Dec,Jan,Feb,Mar,Apr,May,Jun&values=120,300,520,900,1300,1500,1750)

### `t=pixel` 像素风 Star History（README 招牌）
![Star history — pixel](https://x-cmd.com/draw?type=area&t=pixel&unit=GitHub%20Stars&labels=Dec%202024,Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec%202025,Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep&values=0,18,52,98,160,245,360,480,610,735,850,960,1060,1140,1210,1270,1320,1360,1395,1420,1440,1458)

### `t=polka` 波点对比（多仓库）
![Stars — two repos](https://x-cmd.com/draw?type=area&t=polka&labels=Dec%202024,Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec%202025,Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep&series=x-cmd%2Fx-cmd:0,18,52,98,160,245,360,480,610,735,850,960,1060,1140,1210,1270,1320,1360,1395,1420,1440,1458&series=x-cmd%2Fllm:0,8,22,48,82,126,190,270,360,455,545,630,705,770,825,870,905,932,951,965,978,986)

### `t=opendata` 数据叙事版
![AAPL narrative](https://x-cmd.com/draw?type=area&t=opendata&title=Apple%20Shares%20Hit%20Record%20After%20AI-Fuelled%20Rally&subtitle=AAPL%20monthly%20closing%20price%2C%20Jan%202023%20to%20Dec%202024&source=Source%3A%20Nasdaq%20historical%20data&unit=Share%20Price&labels=Jan%2023,Feb%2023,Mar%2023,Apr%2023,May%2023,Jun%2023,Jul%2023,Aug%2023,Sep%2023,Oct%2023,Nov%2023,Dec%2023,Jan%2024,Feb%2024,Mar%2024,Apr%2024,May%2024,Jun%2024,Jul%2024,Aug%2024,Sep%2024,Oct%2024,Nov%2024,Dec%2024&values=130,147,125,170,177,194,196,188,171,171,190,193,186,188,171,170,192,211,222,227,226,226,237,243)

---

## COMBO · 柱+线

> 量级差距小的双 y 轴场景。

### 紫柱绿线经典
![Monthly Revenue + Profit](https://x-cmd.com/draw?type=combo&t=evil&labels=Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec&series=Revenue:42,58,41,62,54,78,61,82,59,68,72,91&line=Profit:18,24,16,29,22,35,27,39,25,31,33,43)

### 双系列柱 + 单线
![Downloads](https://x-cmd.com/draw?type=combo&title=Downloads&labels=Mon,Tue,Wed,Thu,Fri&series=draw:1200,1800,1500,2400,2100&series=qc:900,1000,1100,1150,1200&line=growth:5,8,6,12,10)

---

## RADAR · 雷达图

### 默认：3-12 维
![Skills](https://x-cmd.com/draw?type=radar&title=Skills&labels=TS,Rust,Go,Python,SQL&values=90,60,45,80,70)

### `t=evil` 双系列
![Desktop vs Mobile](https://x-cmd.com/draw?type=radar&t=evil&labels=JavaScript,Python,CSS,Node.js,React,TypeScript&series=Desktop:58,72,70,76,68,84&series=Mobile:34,48,44,81,38,66)

### `t=xcmd` 手写体五维（中文友好）
![六维评估](https://x-cmd.com/draw?type=radar&t=xcmd&labels=性能,易用性,功能,可移植性,可靠性&values=68,54,62,76,73)

---

## GAUGE · 仪表盘

### 半圆多环（默认）
![Browser perf](https://x-cmd.com/draw?type=gauge&labels=Chrome,Safari,Firefox,Edge,Other&values=86,72,64,58,31)

### `t=gradient` 渐变多环
![Browser perf gradient](https://x-cmd.com/draw?type=gauge&t=gradient&labels=Chrome,Safari,Firefox,Edge,Other&values=88,76,69,61,43)

### `t=reliability` 单环四分区（交付可靠性）
![Delivery Reliability](https://x-cmd.com/draw?type=gauge&t=reliability&title=Delivery%20Reliability&value=842&max=1000)

### 单环直白（覆盖率）
![Code coverage](https://x-cmd.com/draw?type=gauge&title=Code%20coverage&value=84&max=100)

---

## SCATTER · 散点图

### 双数值轴（latency vs load）
![Latency vs load](https://x-cmd.com/draw?type=scatter&title=Latency%20vs%20load&x=10,20,30,40,50,60&y=5,8,7,12,18,30)

### 双系列对比
![Current vs Baseline](https://x-cmd.com/draw?type=scatter&x=-18,-14,-11,-8,-5,-2,2,5,8,11,15,18&x=-17,-13,-10,-6,-3,1,4,7,10,13,16,19&y=-8,4,-2,12,8,19,14,25,18,31,27,39&y=15,10,22,16,28,23,34,30,42,38,49,44)

---

## SANKEY · 桑基图

### 基础款（营销漏斗）
![Marketing funnel](https://x-cmd.com/draw?type=sankey&labels=Organic%20Search,Paid%20Ads,Social%20Media,Landing%20Page,Product%20Page,Cart,Bounced,Purchase&links=Organic%20Search%3ELanding%20Page%3A42000%3BPaid%20Ads%3ELanding%20Page%3A28000%3BSocial%20Media%3ELanding%20Page%3A18000%3BLanding%20Page%3EProduct%20Page%3A52000%3BLanding%20Page%3EBounced%3A36000%3BProduct%20Page%3ECart%3A31000%3BProduct%20Page%3EBounced%3A21000%3BCart%3EPurchase%3A24000%3BCart%3EBounced%3A7000)

### `t=fund` 基金流向
![Fund flow](https://x-cmd.com/draw?type=sankey&t=fund&title=Where%20the%20fund%20flows&unit=Quarter%20to%20date&labels=Inflow,Equities,Bonds,Cash,Growth,Income,Reserve&links=Inflow%3EEquities%3A78000%3BInflow%3EBonds%3A46000%3BInflow%3ECash%3A24000%3BEquities%3EGrowth%3A52000%3BEquities%3EIncome%3A26000%3BBonds%3EIncome%3A19000%3BBonds%3EReserve%3A27000%3BCash%3EGrowth%3A9000%3BCash%3EReserve%3A15000)

### `t=pipeline` 收入管线
![Revenue pipeline](https://x-cmd.com/draw?type=sankey&t=pipeline&labels=Wholesale,Retail,Services,Licensing,Expansion,Reserve,Support,Tooling&links=Wholesale%3EExpansion%3A46220%3BRetail%3EExpansion%3A6420%3BRetail%3EReserve%3A25060%3BServices%3EReserve%3A21650%3BServices%3ESupport%3A6690%3BLicensing%3ESupport%3A5780%3BLicensing%3ETooling%3A9180)

---

## QR · 二维码

> `d=` 直接放文本，`fg=#RRGGBB` 控制模块颜色，`title=`/`unit=` 配卡下说明。

### 默认蓝
![x-cmd draw](https://x-cmd.com/draw?type=qr&d=https://x-cmd.com/draw&title=x-cmd.com&unit=%E6%89%AB%E7%A0%81%E6%89%93%E5%BC%80%E5%9B%BE%E8%A1%A8%E6%9C%8D%E5%8A%A1)

### 自配色（紫）
![x-cmd draw purple](https://x-cmd.com/draw?type=qr&d=https://x-cmd.com/draw&fg=%236366f1)

### 暗背景配色
![x-cmd draw on dark](https://x-cmd.com/draw?type=qr&d=https://x-cmd.com/draw&fg=%23ffffff&bg=%23111827)

---

## LAYOUT · 排版实验

> GitHub Flavored Markdown 支持 HTML 并排布局。**坑点**：
> 1. `<td>` 里写 `![alt](url)` 在 GitHub 渲染器中**不稳定**——改用 `<img>` 标签最稳。
> 2. 多列时图会撑爆单元格——必须用 `<img width="...">` 或 x-cmd URL `&w=` 限宽。
> 3. `<table>` 必须块级独占，前后留空行；GitHub 不会包 `<p>`。
>
> 以下 demo 全部用 `<table>` + `<img>` + `width`。

### 2×2 网格
<table>
<tr>
<td align="center"><img src="https://x-cmd.com/draw?type=pie&t=progress&w=400&title=SaaS%20share&labels=Salesforce,HubSpot,Oracle,Other&values=23,18,14,45" alt="SaaS" width="380"></td>
<td align="center"><img src="https://x-cmd.com/draw?type=pie&donut=0&w=400&title=Cloud%20split&labels=Compute,Storage,Network,Other&values=42,28,18,12" alt="Cloud" width="380"></td>
</tr>
<tr>
<td align="center"><img src="https://x-cmd.com/draw?type=pie&t=revenue&w=400&title=Traffic%20sources&labels=Direct,Referral,Organic,Paid&values=44,28,18,10" alt="Sources" width="380"></td>
<td align="center"><img src="https://x-cmd.com/draw?type=pie&t=market-mono&w=400&title=OS%20mix&labels=macOS,Linux,Win,Other&values=42,33,18,7" alt="OS" width="380"></td>
</tr>
</table>

### 3 列 —— gauge 并排
<table>
<tr>
<td align="center"><img src="https://x-cmd.com/draw?type=gauge&w=320&title=Coverage&value=84&max=100" alt="Coverage" width="280"></td>
<td align="center"><img src="https://x-cmd.com/draw?type=gauge&w=320&title=Reliability&value=842&max=1000" alt="Reliability" width="280"></td>
<td align="center"><img src="https://x-cmd.com/draw?type=gauge&w=320&title=Latency&value=42&max=100" alt="Latency" width="280"></td>
</tr>
</table>

### 4 列 —— 折线对比
<table>
<tr>
<td align="center"><img src="https://x-cmd.com/draw?type=line&t=evil&w=260&title=Q1&labels=W1,W2,W3,W4,W5,W6,W7,W8&series=Q1:120,160,140,200,180,240,210,290" alt="Q1" width="220"></td>
<td align="center"><img src="https://x-cmd.com/draw?type=line&t=evil&w=260&title=Q2&labels=W1,W2,W3,W4,W5,W6,W7,W8&series=Q2:140,180,160,220,200,260,230,310" alt="Q2" width="220"></td>
<td align="center"><img src="https://x-cmd.com/draw?type=line&t=evil&w=260&title=Q3&labels=W1,W2,W3,W4,W5,W6,W7,W8&series=Q3:160,200,180,240,220,280,250,330" alt="Q3" width="220"></td>
<td align="center"><img src="https://x-cmd.com/draw?type=line&t=evil&w=260&title=Q4&labels=W1,W2,W3,W4,W5,W6,W7,W8&series=Q4:180,220,200,260,240,300,270,350" alt="Q4" width="220"></td>
</tr>
</table>

### 仪表盘专题 —— 单图多环
<img src="https://x-cmd.com/draw?type=gauge&t=gradient&title=Engineering%20health&labels=Coverage,Reliability,Latency,Satisfaction,Velocity&values=84,82,71,88,76" alt="Engineering health" width="800">

### 双系列对比 —— 旧 vs 新
<table>
<tr>
<td align="center"><img src="https://x-cmd.com/draw?type=line&t=evil-mono&w=520&title=Legacy&labels=W1,W2,W3,W4,W5&series=Legacy:120,140,160,180,200" alt="Legacy" width="460"></td>
<td align="center"><img src="https://x-cmd.com/draw?type=line&t=evil-glow&w=520&title=New&labels=W1,W2,W3,W4,W5&series=New:80,180,300,460,640" alt="New" width="460"></td>
</tr>
</table>

### 暗色模式预览 —— 加 `&scheme=dark`
<table>
<tr>
<th>light</th>
<th>dark</th>
</tr>
<tr>
<td align="center"><img src="https://x-cmd.com/draw?type=pie&t=progress&w=400&title=Light&labels=A,B&values=72,28&scheme=light" alt="light" width="360"></td>
<td align="center"><img src="https://x-cmd.com/draw?type=pie&t=progress&w=400&title=Dark&labels=A,B&values=72,28&scheme=dark" alt="dark" width="360"></td>
</tr>
</table>

### 另一种思路 —— 用 Markdown 表格语法
| Light | Dark |
|:---:|:---:|
| ![light](https://x-cmd.com/draw?type=pie&t=progress&w=300&title=L&labels=A,B&values=72,28&scheme=light) | ![dark](https://x-cmd.com/draw?type=pie&t=progress&w=300&title=D&labels=A,B&values=72,28&scheme=dark) |

---

## 备注

- `scheme=` 不指定时跟随查看者系统；想确定请显式写 `scheme=light` 或 `scheme=dark`
- `v=1` 锁定版本号，防止 x-cmd 端升级导致图变形
- 二维码对 URL 长度敏感，长文本建议先用短链服务压缩
- 所有 `&` 之间用普通空格或空行隔开均可；标签里如有逗号或特殊字符务必做 URL 编码（`%20` 等）
- 完整数据 schema 见 x-cmd/draw 各 type 示例；JSON 体可走 `?d=...` 一并传
