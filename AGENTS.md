# AGENTS.md · 项目规则

> 📌 **文档基线**：2026-09-17（v0.5.0，commit `feat: 星空闪烁实验（含视频导出）`）完成四件套与目录规范更新
> **更新文档/代码后，请更新此行**（新日期 + 新 commit hash），并在 CHANGELOG 追加版本

## 技术栈
- 纯前端：原生 HTML + CSS + JS，**零依赖、零构建**（无 npm / 打包器）
- 绘图用原生 Canvas 2D 或内嵌 SVG；如需更高性能图表运行时再评估 WebGL/库，非必要不引入

## 关键坑
- 参数面板值变化要 `requestAnimationFrame` 防抖重绘，避免滑杆拖动卡顿
- Canvas 要按 `devicePixelRatio` 设置实际尺寸并 `setTransform(DPR,0,0,DPR,0,0)`，避免高分屏模糊
- **静态单帧渲染时透明度别设太低**（如 globalAlpha<0.1 且画一次就停 → 黑板一片看不见）；轨迹类效果普通透明度 0.2~0.35 即可
- 每个实验自包含，**不**引用其他实验脚本，保障"单文件打开即用"
- **视频导出**走 `canvas.captureStream()` + `MediaRecorder`：导出期间必须保持标签页在前台（后台标签页 rAF 被节流会丢帧）；分辨率/帧率过高易掉帧，导出失败先降这两项
- 导出循环视频时，**`recorder.stop()` 之前不要长等**：录制器仍在跑，会把末帧的静止画面一并录进尾部，循环回接时明显停顿。末帧用 `stream.getVideoTracks()[0].requestFrame()` 推流，只等一个帧间隔即可（实测尾段由 ~300ms 压到 ~20ms）
- 循环视频的时长要按**实际录制**算，别用「总帧数 ÷ 帧率」当实际时长展示——那个是标称值，会少报
- 参数滑杆若只改状态、把重绘全交给 rAF 循环，**暂停态会失效**（循环提前 return，拖滑杆只有数字在动）。要么在控件回调里补一次立即重绘，要么统一走一个 `requestRedraw()` 入口
- 视频循环要"无缝"，导出的循环周期须按帧率对齐（`round(周期×帧率)/帧率`），否则首尾差一帧会抖动

## 约定
- UI 标签、注释一律中文；标题中英文皆可
- 一个实验 = 一个独立 HTML，从 `experiments/_template/` 复制骨架
- **文件命名**：分类目录用中文（见下目录表），实验文件名用英文 slug（如 `star-spikes.html`）
- 每个实验需要一张真实截图，存到 `screenshots/<实验英文名>.png`，并在 README 索引 + index.html 卡片登记
- 新增**分类**时：在 `experiments/` 下建中文文件夹，并把分类登记进本文件下方「目录分类表」

## 目录分类表
| 分类目录 | 收什么 |
|---|---|
| `粒子动势` | 粒子 / 湍流 / 流动类动态效果 |
| `几何生成` | 参数化几何图形、星芒、分形、对称图案 |

## 常用命令
- 无需构建。本地预览：浏览器直接打开文件，或 `python -m http.server`
- 截图（无头 Edge）：`msedge --headless=new --screenshot=out.png --window-size=..., --force-device-scale-factor=1 文件url`
- 发布：改 CHANGELOG + 更新 README 索引表 + index.html 卡片 + 本文档基线

## 详细规则（生长式：本文件超 150 词后再拆分，目前内容仍内联在上面各节）
- 拆分目标位置：`rules/技术栈.md`、`rules/常见坑.md`、`rules/实验规范.md` —— **尚未创建**，别去打开