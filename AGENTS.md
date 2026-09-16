# AGENTS.md · 项目规则

> :point_right: **文档基线**：2026-09-16（commit 见 CHANGELOG v0.1.0）完成四件套初始
> **更新文档/代码后，请更新此行**（新日期 + 新 commit hash），并在 CHANGELOG 追加版本

## 技术栈
- 纯前端：原生 HTML + CSS + JS，**零依赖、零构建**（无 npm / 打包器）
- 绘图用原生 Canvas 2D API；如需更高性能图表运行时再评估 WebGL/库，非必要不引入

## 关键坑
- 参数面板值变化要 equestAnimationFrame 防抖重绘，避免滑杆拖动时卡顿
- 图形坐标单位：用设备像素比 devicePixelRatio 处理高分屏模糊
- 每个实验自包含，**不**引用其他实验的脚本，保障"单文件打开即用"

## 约定
- UI 标签、注释一律用中文；单文件交付，无外部资源
- 图形命名（文件/标题/标签）用中文，保持统一检索
- 一个实验 = 一个独立 HTML，共用骨架从 experiments/_template/ 复制

## 常用命令
- 无需构建。本地预览：浏览器直接打开文件，或在目录起静态服务 python -m http.server
- 发布：改 CHANGELOG + 更新 README 实验索引表

## 详细规则（按需 @引用，超出 150 词后拆分）
- @rules/技术栈.md  @rules/常见坑.md  @rules/实验规范.md