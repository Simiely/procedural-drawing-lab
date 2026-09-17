# DEVELOPMENT.md · 开发说明

## 项目概览
- 目的：程序化作图（生成式 / 算法绘图）的前瞻实验场，纯前端零依赖单 HTML，浏览器内调参看效果
- 范围：experiments/ 每个文件即一个独立实验；index.html 为总入口卡片浏览
- 原则：单文件自包含、零依赖、中文命名、参数面板 + 可复现随机种子（确定性几何图形无需种子）

## 架构说明
- index.html：实验总览，卡片 + 分类/标签筛选（清单是 index.html 内硬编码的 `EXPERIMENTS` 数组，**不**自动扫描目录，新增实验必须手动登记）
- experiments/<名>.html：单实验，结构 = 画布 + 参数面板 + 重绘逻辑
- experiments/_template/：新实验的复制骨架
- 无构建链：全部浏览器原生运行

## 如何新增一个实验（工作流）
1. 复制 `experiments/_template/index.html` 到 `experiments/<中文分类>/<英文 slug>.html`
2. 调整标题 / 描述 / 参数定义（面板自动生成滑杆；`color` / `select` 需模板支持）
3. 在绘图函数里写生成逻辑（读参数 → 画到 Canvas / SVG）
4. 本地打开验证调参流畅、控制台零报错
5. 出一张**真实截图**存到 `screenshots/<英文 slug>.png`（尺寸对齐同分类已有截图）
6. 在 `index.html` 的 `EXPERIMENTS` 数组加一张卡片（标题 / 说明 / 分类 / 标签 / 截图路径）
7. 更新 README 实验索引表（行序与 index 卡片顺序保持一致）+ CHANGELOG 追加版本
8. 更新 AGENTS.md 顶部「文档基线」行（新日期 + 新版本 + commit 主题）

> 第 5～8 步是硬性要求：漏登记会留下"有截图没卡片、有实验没索引"的不一致状态。

## 关键问题与方案（一坑一篇，格式与 knowledge-base 一致）

### 问题：(待补充)

**TL;DR**：(待补充)

- 问题：
- 根因：
- 解决：
- 预防：

---

> 生长式规则：README 超 150 行拆 docs/使用指南.md、docs/API.md；AGENTS 超 150 词拆 rules/*.md；本文件超 200 行拆 docs/架构.md、docs/问题记录/。