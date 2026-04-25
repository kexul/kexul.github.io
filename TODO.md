# TODO

## Goal
精简个人主页，去掉所有 Vim 模拟装饰符号（`"--` 注释头、`:echo` 命令、`~` 空行标记、`:about` 冒号等），保留 Solarized 配色、Tab 切换和笔记阅读功能，内容更干净简洁。

## Tasks

### 1. Tab 标签去冒号
- [ ] `:about` → `about`, `:skills` → `skills`, `:projects` → `projects`, `:blog` → `blog`, `:contact` → `contact`

### 2. 重写 about 面板
- [ ] 去掉 `me = { ... }` 代码块风格，改用纯文字
- [ ] 去掉 `"-- about me ---"`、`"-- highlights ---"`、`"-- quick links ---"` 这类注释装饰
- [ ] 去掉 `:help me build cool stuff` 和 `~` 空行

### 3. 重写 skills 面板
- [ ] 去掉 `"-- Languages ---"` 等注释头
- [ ] 去掉 `:echo "always learning new things"` 和 `~` 空行
- [ ] 语言条目去掉进度条符号，保持简洁

### 4. 重写 projects 面板
- [ ] 去掉 `"-- pi coding agent ecosystem ---"` 等分类注释头
- [ ] 去掉 `:echo "all repos → ..."` 和 `~` 空行
- [ ] 项目条目保持纯文字 + 链接

### 5. 重写 blog 面板
- [ ] 去掉 `"--` 注释头
- [ ] 去掉 `:echo "stay tuned..."` 和 `~` 空行

### 6. 重写 contact 面板
- [ ] 去掉 `"-- reach me at ---"` 注释头
- [ ] 去掉 `:echo "feel free to reach out!"` 和 `~` 空行

### 7. 重写 note-viewer 面板
- [ ] 笔记标题栏去掉 `" notes/` 注释风格

### 8. 精简 CSS 中不再需要的样式类
- [ ] 移除 `.tilde`、`.h1`、`.h2` 等不再使用的样式

## Notes
- 整体 Solarized 配色、Tab 栏、状态栏、底部 statusline 保持不变
- 笔记阅读功能（openNote、backToBlog）保持不变
- 每完成一个面板就推送一次，方便验证效果
