# TODO

## Goal
点击博客链接后，整个页面切换为笔记阅读视图（不是新标签页，不是覆盖层），点返回恢复主页。

## Tasks

### 1. 删除 read.html
- [ ] 删除 `read.html` 文件（不再需要）

### 2. 重写 openNote 为全页切换
- [ ] `openNote` 将整个 `.vim` 的内容替换为笔记阅读视图
- [ ] 阅读视图包含返回链接 + 笔记内容（markdown + 图片 + 公式）
- [ ] `backToMain` 函数恢复主页原始内容

### 3. 移除主页面板上不再需要的元素
- [ ] 删除内联 note-viewer 面板
- [ ] 删除 status-filename 显示（不再需要）
- [ ] 删除 openNote / backToBlog 以外的无用 JS 和 CSS

### 4. 清理与推送
- [ ] 测试主页→笔记→返回流程
- [ ] 提交并推送
