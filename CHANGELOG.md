# CHANGELOG.md

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