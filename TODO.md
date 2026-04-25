# TODO

## Goal
将页面从 Tab 切换改为单页滚动布局，板块顺序：about → skills → blog → projects → contact，保留笔记阅读功能和底部 statusline。

## Tasks

### 1. 重构 HTML 结构：去掉 Tab 系统，改为上下排列的板块
- [ ] 删除 `.tabline` 整个元素
- [ ] 删除所有 `.panel` 包裹层，每个板块变成独立 `<section>` 或 `<div>`
- [ ] 删除 JS 中的 Tab 切换逻辑
- [ ] 删除 CSS 中 `.panel`、`.tabline` 相关样式

### 2. 更新 CSS 为单页滚动布局
- [ ] 移除 `.vim` 的 max-width / border / flex 限制（改为全宽或留白适中的单栏）
- [ ] 各板块之间用间距或分割线分隔
- [ ] 适配移动端

### 3. 按顺序重写各板块内容
- [ ] about 板块（保持现有纯文字内容）
- [ ] skills 板块（保持现有内容）
- [ ] blog 板块（保持现有笔记链接，保留 openNote 功能）
- [ ] projects 板块（保持现有项目列表）
- [ ] contact 板块（保持现有联系链接）

### 4. 保留底部 statusline
- [ ] 保留 `.statusline`，样式不变
- [ ] 保留时钟功能
- [ ] 保留文件名显示（当查看笔记时）

### 5. 保留笔记阅读功能
- [ ] 笔记阅读视口保持不变
- [ ] `openNote` / `backToBlog` 函数适配单页模式
- [ ] 阅读笔记时滚动到笔记区域或覆盖显示

### 6. 清理不再需要的 JS 和 CSS
- [ ] 移除 Tab 切换相关 JS
- [ ] 移除 `.panel`、`.tabline`、`.ln` 等不再使用的 CSS

## Notes
- 板块内容保持上次精简后的干净文本风格
- 笔记功能（marked + image rendering + click interceptor）不变
- 状态栏（statusline）保留不动
