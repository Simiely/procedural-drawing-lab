# procedural-drawing-lab · 程序化作图前哨实验场

> 纯前端、**零依赖单 HTML** 的生成式 / 程序化绘图实验集合：在浏览器里直观查看图形，配合**参数面板实时调参**，作为程序化作图的技术前瞻测试场。

## 这是什么

一个「算法画图」实验仓库。每个 `experiments/<分类>/` 下的独立 HTML 即一个实验，打开即可看到图形与参数面板，拖动滑杆 / 换种子秒级出效果。适合快速验证图形算法、界面动效方案再决定是否落到正式项目。

## 特性

- 零依赖、单文件，浏览器直接打开即用，无需构建
- 每图带**参数滑杆实时调参**；流场类实验另带可复现随机种子（几何图形是确定性的，无需种子）
- 部分实验支持**导出循环视频**（Canvas `captureStream` + `MediaRecorder`，输出 WebM/MP4）
- `index.html` 卡片式浏览，按分类 / 标签筛选，配真实截图
- 遵循 [knowledge-base 单项目规范](https://github.com/Simiely/knowledge-base) 维护

## 快速开始

1. 克隆本仓库
2. 打开 `index.html` 浏览全部实验，或直接双击任意 `experiments/*/*.html`
3. 拖动参数、点「重置种子 / 重新生成」，观察图形变化
4. 已在 GitHub Pages 在线部署，可直接访问 https://simiely.github.io/procedural-drawing-lab/

## 实验清单（索引）

| 截图 | 实验 | 分类 | 说明 | 参数要点 |
|---|---|---|---|---|
| ![流场粒子](screenshots/flow-field.png) | [流场粒子 Flow Field](experiments/粒子动势/flow-field.html) | 粒子动势 | 粒子沿确定性噪声场流动成丝带 | 数量 / 密度 / 噪声强度 / 轨迹 / 配色 / 种子 |
| ![流动线条](screenshots/flow-lines.png) | [粒子流动线条 Flow Lines](experiments/粒子动势/flow-lines.html) | 粒子动势 | 粒子水平拖出流光丝线，匀速横贯画面，**可导出循环视频** | 数量 / 间距 / 抖动 / 周期 / 长度 / 粗细 / 色相 / 亮度 + 导出分辨率·帧率·循环次数 |
| ![星空闪烁](screenshots/starry-twinkle.png) | [星空闪烁 Starry Twinkle](experiments/粒子动势/starry-twinkle.html) | 粒子动势 | 星芒与星尘散布夜空，各自按周期闪烁，**可导出循环视频** | 星芒·星尘数量 / 闪烁速度·强度 / 大小范围 / 尖角数·中心圆·尖角长度·内凹·基部半角 / 颜色 + 导出周期·分辨率·帧率 |
| ![电流](screenshots/electric-current.png) | [电流 Electric Current](experiments/粒子动势/electric-current.html) | 粒子动势 | 折线轨迹拖出电弧丝线，锯齿可调，支持向上 / 向右两种流向，**可导出视频** | 数量 / 速度 / 长度 / 粗细 / 折线 / 发光 / 方向 + 导出分辨率·时长 |
| ![星芒](screenshots/star-spikes.png) | [星芒 Star Spikes](experiments/几何生成/star-spikes.html) | 几何生成 | 参数化星芒：尖角可旋转分布，内凹成芒 | 尖角数 / 中心圆半径 / 尖角长度 / 基部半角 / 内凹程度 / 颜色 |
| ![雪花](screenshots/snowflake.png) | [雪花 Snowflake](experiments/几何生成/snowflake.html) | 几何生成 | 参数化雪花：分形分支 + 尖端 V 形，旋转复制对称 | 对称臂数 / 主臂与分支长度 / 张开角度 / 递减比例 / 尖端 V 形 |
| ![雷达扫描](screenshots/radar-scan.png) | [雷达扫描 Radar Scan](experiments/径向扫描/radar-scan.html) | 径向扫描 | 多条光束自圆心同时旋转扫过圆形区域，拖尾呈扇形渐隐 | 扫描速度 / 扫描数量 / 拖尾长度 / 顺·逆时针 / 网格 / 扫描颜色 |
| ![启动动画](screenshots/launch-splash.png) | [启动动画 Launch Splash](experiments/品牌动效/launch-splash.html) | 品牌动效 | 启动动画参数调试台：16:9 预览画布 + 毫秒级滑杆 + 缓动曲线下拉，3 套入场方案，实时预估总时长 | 入场方案 / 图标·文字·副标题时长 / 延迟·逐字错位 / 缓动曲线（Quart 系·ease）/ 整体 Logo 时长 |
| ![充电图标](screenshots/charging-icon.png) | [充电图标 Charging Icon](experiments/粒子动势/charging-icon.html) | 粒子动势 | 粒子自右下椭圆场弯曲汇聚到充电图标；叠加电线流光（单层白线 + 虚线流光 + 沿路径游动粒子）与脉冲/光波/描边/浮动，并支持手动描摹路径 | 5 页签面板：节奏 / 粒子 / 流光（线条层·粒子层）/ 图标 / 绘制（描摹·点集·应用文本）+ 重置种子 |
| ![沙漠行驶](screenshots/desert-sandstorm.png) | [沙漠行驶 · 湍流沙暴](experiments/粒子动势/desert-sandstorm.html) | 粒子动势 | fbm 噪声高度场生成沙丘，车辆尾部持续喷发沙粒与尘土，按寿命消散并受确定性噪声湍流扰动 | 车速 / 车身自转 / 喷射开角 / 湍流强度 / 沙粒生成量·寿命·大小·力度 / 尘土生成量·寿命 / 沙丘对比度 + 重置种子 |
| ![极光充电流](screenshots/aurora-charge-flow.png) | [极光充电流 Aurora Charge Flow](experiments/粒子动势/aurora-charge-flow.html) | 粒子动势 | 沿内置 SVG 曲线流动的渐变宽度脉冲：头部半圆收口、尾部渐细，单次 shadowBlur 单层泛光 + 本体双层叠加，另有白色底轨 | 头部/尾部粗细 / 脉冲长度·间隔 / 泛光范围·亮度 / 底轨可见度 / 本体透明度 / 流速 / 流光颜色 / 充电进度 + 重置相位 |
| ![能量坍塌](screenshots/energy-collapse.png) | [平滑圆形波纹 · 能量坍塌](experiments/粒子动势/energy-collapse.html) | 粒子动势 | 六边形剖分为 6 个等边三角形并按 1.5R / √3R 密铺全屏，按重心距离落入径向环带；扩张 / 收缩坍塌两段节奏，钟形曲线控制碎片缩放与淡出 | 三角形间隙 / 六边形大小 / 最大扩散半径 / 初始圆环厚度 / 扩散速度 / 循环停顿 / 碎片颜色 / 收缩额外缩小开关 + 暂停·重置相位·重置参数 |
| ![动态扩散圆环](screenshots/pulse-rings.png) | [动态扩散圆环 · 脉冲感循环](experiments/品牌动效/pulse-rings.html) | 品牌动效 | 按间隔生成径向渐变圆环，尺寸放大（scale 0→1.5）与透明度渐隐双轨并行，三色标径向渐变 + 9 条缓动曲线；纯 DOM + CSS + Web Animations，无 Canvas | 生成间隔 / 最大尺寸 / 产生时长 / 消失时长 / 尺寸曲线 / 渐隐曲线 / 0%·70%·100% 处透明度 + 暂停·重播·重置参数 |
| ![沙粒扬起](screenshots/desert-sand-lift.png) | [沙漠行驶 · 沙粒扬起](experiments/粒子动势/desert-sand-lift.html) | 粒子动势 | 俯视沙丘上小车自主寻路并避开边界，车尾**沙粒 / 尘土两套参数独立**喷发、受风力吹散按寿命淡出；沙丘由 fbm 高度场静态生成不逐帧重算。湍流沙暴的同主题迭代版，效果不同、独立并存 | 沙粒数量 / 沙粒消散速度 / 沙粒大小 / 飞散力度 / 尘土数量 / 尘土消散速度 / 车速 / 风力 / 沙丘对比度 + 暂停·重置参数·重置种子 |

## 目录规范（新增实验前必读）

```
experiments/
  _template/        # 新实验的复制骨架
  粒子动势/          # 粒子、湍流、流动类效果
  几何生成/          # 参数化几何图形、星芒、分形图案
  径向扫描/          # 旋转光束、雷达扫描类径向动效
  品牌动效/          # 品牌 Logo 入场、启动动画、界面转场类动效
  ...               # 新分类按需长出来（请登记到 AGENTS.md 目录表）
screenshots/        # 每个实验对应一张真实截图（<实验英文名>.png）
```

新增实验流程见 [DEVELOPMENT.md](./DEVELOPMENT.md)「如何新增一个实验」。

## 文档基线

| 文件 | 给谁看 | 说明 |
|---|---|---|
| [README.md](./README.md) | 用户 / 访客 | 本页 |
| [AGENTS.md](./AGENTS.md) | AI / 未来的你 | 技术栈、约定、目录分类、关键坑 |
| [DEVELOPMENT.md](./DEVELOPMENT.md) | 开发者 | 架构、如何新增实验、问题记录 |
| [CHANGELOG.md](./CHANGELOG.md) | 所有人 | 版本变更 |