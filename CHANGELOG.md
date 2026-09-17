# CHANGELOG.md

## [v0.4.0] - 2026-09-17
### 新增
- 新增粒子类实验「粒子流动线条 Flow Lines」：粒子水平拖出流光丝线匀速横贯画面，含 10 项视觉参数 + 4 套预设（细雨 / 流光 / 霓虹 / 光带）
- 该实验支持**导出循环视频**：分辨率 6 档（720P / 1080P / 2K / 4K / 方形 / 竖屏）× 帧率 30·60fps × 循环次数 1～8，按帧率对齐循环周期保证无跳帧，导出 WebM/MP4
- 新增 `screenshots/flow-lines.png`，README 索引与 index 卡片已登记
### 变更
- (暂无)
### 修复
- 修复 `flow-lines` 导出视频尾部固定多出约 300ms 静止画面：`sleep()` 写在 `recorder.stop()` **之前**，录制器仍在跑，把末帧静止画面一并录进视频，循环回接时出现明显停顿。改为末帧用 `track.requestFrame()` 强制推流、只等一个帧间隔；三档分辨率实测「录制时长 − 标称时长」由 +304/+302/+363ms 降到 **+35/+17/+20ms**
- 修复 `flow-lines` **暂停状态下拖动参数画面不刷新**（只有数值回显在变）：重绘原先完全依赖 rAF 循环，而暂停时循环提前 `return`。新增统一 `requestRedraw()` 入口，暂停时立即补画一帧（暂停下来慢慢调参正是它最主要的用法）
- 修复 `flow-lines` 结果弹窗把「标称时长」（总帧数 ÷ 帧率算出来的）当作实际时长展示，改为同时展示「循环周期」与「实际录制时长」
- 修复 `index.html` **分类导航是死 UI**：`renderCats()` 生成的分类 chip 未绑定点击事件，`activeCat` 恒为「全部」，分类筛选逻辑虽已实现却无法触发；补上事件绑定与 `.cat.active` 高亮样式
- 修复 `experiments/_template` 声称支持 `color`/`select` 却只实现 `range`：补齐两种控件的生成逻辑与样式（此前 4 个实验中 3 个因此绕过模板手写面板）
- 修复 `DEVELOPMENT.md` 末行混入一个**裸 CR(0x0D)**，导致 `rules/*.md` 显示为 `ules/*.md`；该损坏自首个 commit `eb8762c` 起就存在，GitHub 上一直是坏的
- 修复 `DEVELOPMENT.md` 与实现不符的描述：实验清单并非「读取 experiments/ 清单」，实为 `index.html` 内硬编码的 `EXPERIMENTS` 数组；「如何新增实验」工作流补齐截图与文档基线两个必做步骤
- 修复 `AGENTS.md` 把「将来要拆分的目标文件」写成当前可 @ 引用的路径（`rules/*.md` 实际不存在，且 git 历史中从未存在过）
- 修复 `README.md` 过度概括的「每图带随机种子」表述（实际仅流场类实验有可复现种子；确定性几何图形无需种子）

## [v0.3.0] - 2026-09-16
### 新增
- 新增几何类实验「雪花 Snowflake」：参数化分形雪花（对称臂数 / 主臂与分支长度 / 张开角度 / 递减比例 / 尖端 V 形 / 中心半径 + 颜色自选）
- 新增 `screenshots/snowflake.png`，README 索引与 index 卡片已登记
### 变更
- (暂无)
### 修复
- (暂无)

## [v0.2.0] - 2026-09-16
### 新增
- 新增首个几何类实验「星芒 Star Spikes」（参数化尖角星芒，含尖角数量/中心圆/尖角长度/基部半角/内凹程度 + 颜色自选）
- 建立目录分类：`experiments/几何生成/`、`experiments/粒子动势/`（flow-field 归入粒子动势）
- 新增 `screenshots/`：为全部实验配置真实截图（star-spikes.png / flow-field.png）
- index.html 升级：卡片支持分类 + 标签筛选，缩略图改用真实截图
- AGENTS.md 新增「目录分类表」与文件命名/截图规范
### 变更
- 实验与页面改用分类子目录组织，原 `experiments/flow-field.html` 移至 `experiments/粒子动势/flow-field.html`
- 优化流场粒子默认参数（透明度/轨迹/密度），静态单帧即可见清晰丝带；速度改为按画布尺寸归一化
### 修复
- (暂无)

## [v0.1.0] - 2026-09-16
### 新增
- 初始化仓库骨架，按 knowledge-base 单项目规范建立四件套（README / AGENTS / DEVELOPMENT / CHANGELOG）
- 新增 index.html 卡片式总览入口（零依赖）
- 新增 experiments/_template 复制骨架
- 新增首个实验 流场粒子 Flow Field（参数面板 + 随机种子）
### 变更
- (暂无)
### 修复
- (暂无)