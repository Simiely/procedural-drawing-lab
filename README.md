# procedural-drawing-lab · 程序化作图前哨实验场

> 纯前端、**零依赖单 HTML** 的生成式 / 程序化绘图实验集合：在浏览器里直观查看图形，配合**参数面板实时调参**，作为程序化作图的技术前瞻测试场。

## 这是什么

一个「算法画图」实验仓库。每个 experiments/ 下的独立 HTML 即一个实验，打开即可看到图形与参数面板，拖动滑杆 / 换种子秒级出效果。适合快速验证图形算法方案再决定是否落到正式项目。

## 特性

- 零依赖、单文件，浏览器直接打开即用，无需构建
- 每图带 **参数滑杆 + 随机种子重置**，实时调参
- 以 index.html 卡片式浏览所有实验（标签筛选）
- 遵循 [knowledge-base 单项目规范](https://github.com/Simiely/knowledge-base) 维护

## 快速开始

1. 克隆本仓库
2. 打开 index.html 浏览全部实验，或直接双击任意 experiments/*.html
3. 拖动参数、点「重置种子」，观察图形变化

## 添加一个新实验

见 [DEVELOPMENT.md](./DEVELOPMENT.md)「如何新增实验」：复制骨架 → 填你的绘图逻辑 → 在 index.html 加一张卡片。

## 实验清单（索引）

| 实验 | 说明 | 参数要点 |
|---|---|---|
| *(首个实验待添加)* | — | — |

## 文档基线

| 文件 | 给谁看 | 说明 |
|---|---|---|
| [README.md](./README.md) | 用户 / 访客 | 本页 |
| [AGENTS.md](./AGENTS.md) | AI / 未来的你 | 技术栈、约定、关键坑 |
| [DEVELOPMENT.md](./DEVELOPMENT.md) | 开发者 | 架构、如何新增实验、问题记录 |
| [CHANGELOG.md](./CHANGELOG.md) | 所有人 | 版本变更 |