# TODO

## Goal
短笔记（≤ 20 行）在鼠标悬停时直接显示渲染后的完整 Markdown 内容，不再需要点击跳转。长笔记保持现有模态弹窗行为不变。

## Tasks

### 1. 定义短笔记列表 & 添加 CSS 工具提示样式
- [x] 在 `index.html` 中硬编码短笔记文件名列表（按行数 ≤ 20 判定）
- [x] 添加 `.note-tooltip` 弹出层 CSS（固定定位、阴影、最大宽高、滚动、Solarized 配色）
- [x] 添加 `.note-tooltip` 内部 `.note-rendered` 样式复用（内容渲染风格与模态一致）

### 2. 添加工具提示 HTML 容器
- [x] 在 `<body>` 末尾添加一个 `<div class="note-tooltip" id="note-tooltip">` 作为工具提示容器
- [x] 容器初始 `display: none`，JS 控制显示/隐藏/定位

### 3. 实现工具提示核心逻辑（JS）
- [x] 添加 `shortNotes` 集合（包含所有 ≤ 20 行的笔记文件名）
- [x] 实现 `noteTooltipCache` 对象，缓存已获取的短笔记内容
- [x] 实现 `renderTooltipContent(text, filename)`：用 marked + KaTeX 渲染 Markdown
- [x] 实现 `showNoteTooltip(filename, linkEl)`：获取内容 → 渲染 → 定位 → 显示
- [x] 实现 `hideNoteTooltip()` + 延迟隐藏机制（鼠标移到 tooltip 上不消失）
- [x] 定位策略：在链接附近显示，超出视口时自动调整

### 4. 为模态内的笔记链接添加 hover 支持
- [x] 在 `openNote` 的 `.md` 链接拦截代码中，对每个短笔记链接添加 `mouseenter` / `mouseleave` 事件
- [x] 模态内的长笔记链接保持现有点击行为不变

### 5. 测试
- [x] 代码审阅通过：shortNotes 集合、CSS、渲染函数、定位、延迟隐藏逻辑均正确
- [x] 修复：将 `DOMContentLoaded` 改为即时执行，确保 tooltip 事件绑定生效
- [x] 修复：marked 对中文链接做 URL 编码导致 `isShortNote` 匹配失败，增加 `decodeURIComponent` 处理
- [ ] 用户需要在浏览器中手动验证交互效果

### 6. 短笔记链接交互优化
- [x] 短笔记链接加 `.note-hover` 下划线样式（青色下划线，`cursor: default`）
- [x] 短笔记链接点击仅 `preventDefault`，不打开模态
- [x] 长笔记链接保持原有点击弹窗行为

## Notes
- 短笔记判定标准：行数 ≤ 20（含空行）。当前符合条件的笔记：`感知误差.md`(5行)、`二维.md`(10行)、`离散.md`(9行)、`离散/嵌入向量.md`(14行)、`Transformer.md`(7行)、`cross-attention.md`(20行)、`patch的对抗误差约束.md`(3行)
- 渲染复用现有 `marked.js` + `KaTeX` 库（已加载到页面中）
- 长笔记（≥ 21 行）保持现有模态弹窗行为不变
