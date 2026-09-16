# DEVELOPMENT.md · 开发说明

## 项目概览
- 目的：程序化作图（生成式 / 算法绘图）的前瞻实验场，纯前端零依赖单 HTML，浏览器内调参看效果
- 范围：experiments/ 每个文件即一个独立实验；index.html 为总入口卡片浏览
- 原则：单文件自包含、零依赖、中文命名、参数面板 + 随机种子

## 架构说明
- index.html：实验总览，卡片 + 标签筛选（读取 experiments/ 清单）
- experiments/<名>.html：单实验，结构 = 画布 + 参数面板 + 重绘逻辑
- experiments/_template/：新实验的复制骨架
- 无构建链：全部浏览器原生运行

## 如何新增一个实验（工作流）
1. 复制 experiments/_template/index.html 到 experiments/<新名>.html
2. 调整标题 / 描述 / 参数定义（面板自动生成滑杆与种子按钮）
3. 在你的绘图函数里写生成逻辑（读参数 → 画到 Canvas）
4. 本地打开验证调参流畅
5. 在 index.html 实验索引加一张卡片（标题 / 说明 / 标签）
6. 更新 README 实验索引表 + CHANGELOG

## 关键问题与方案（一坑一篇，格式与 knowledge-base 一致）

### 问题：(待补充)

**TL;DR**：(待补充)

- 问题：
- 根因：
- 解决：
- 预防：

---

> 生长式规则：README 超 150 行拆 docs/使用指南.md、docs/API.md；AGENTS 超 150 词拆 ules/*.md；本文件超 200 行拆 docs/架构.md、docs/问题记录/。