# TODO

## Goal
将页面从 Tab 切换改为单页滚动布局，板块顺序：about → skills → blog → projects → contact，保留笔记阅读功能和底部 statusline。

## Tasks

### 1. 重构 HTML 结构：去掉 Tab 系统，改为上下排列的板块
- [x] 删除 `.tabline` 整个元素
- [x] 删除所有 `.panel` 包裹层，每个板块变成独立 `<section>` 或 `<div>`
- [x] 删除 JS 中的 Tab 切换逻辑
- [x] 删除 CSS 中 `.panel`、`.tabline` 相关样式

### 2. 更新 CSS 为单页滚动布局
- [x] 移除 `.vim` 的 border-left/right，改为 padding
- [x] 各板块之间用分割线分隔
- [x] 移除无用 CSS（`.ln`、`.contact-list`、`.cursor` 等）

### 3. 按顺序重写各板块内容
- [x] about → skills → blog → projects → contact 顺序调整
- [x] 各板块内容保持不变（上次精简后的干净文本）

### 4. 保留底部 statusline
- [x] 保留 `.statusline`，样式不变
- [x] 保留时钟功能
- [x] 保留文件名显示

### 5. 保留笔记阅读功能
- [x] 笔记阅读视口保持不变（`.note-viewer.active`）
- [x] `openNote` 移除 tab 相关逻辑
- [x] `backToBlog` 改为滚动到 blog 板块位置

### 6. 清理不再需要的 JS 和 CSS
- [x] 移除 Tab 切换相关 JS
- [x] 移除 `.tabline`、`.panel`、`.ln`、`.cursor` 等 CSS

## Notes
- 状态栏（statusline）保留不动
- 笔记阅读功能完全保留
