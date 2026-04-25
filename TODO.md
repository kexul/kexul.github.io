# Performance TODO

## 已完成
- [x] 下载 marked.min.js / katex.min.js / katex.min.css 到 vendor/
- [x] 下载 KaTeX woff2 字体到 vendor/fonts/
- [x] katex.min.css 精简为仅 woff2（60→20 字体引用）
- [x] index.html: 替换 CDN preload 为本地 `<link>` + `<script>`
- [x] index.html: 删除 `loadLib()` 函数，简化 `fetchNoteContent()` 和 `openNote()`
- [x] 图片加 `loading="lazy"`
- [x] busuanzi 脚本 `defer` → `async`
- [x] katex.css 改为按需加载（随 JS 库一起动态插入）
- [x] marked.js + katex.js 改为按需加载（首次交互时才开始加载）
- [x] 首屏零 JS 阻塞 — 所有 JS 延迟到用户第一次 hover/click 才加载
- [x] 添加 `<meta name="description">` 和 `<meta name="color-scheme">`

## 可选优化（后续）
- [ ] 用 gzip/brotli 预压缩 vendor 文件（GitHub Pages 自动 brotli/gzip）
- [ ] 考虑用更轻量的 markdown 解析器替换 marked (39KB → 可能 10KB 以内)
- [ ] 考虑将 marked + katex 打包合并为一个请求（减少 HTTP 连接数）
- [ ] Service Worker 缓存（离线访问 + 二次加载零延迟）
- [ ] 添加 `<link rel="prefetch">` 在首屏加载后预取可能用到的笔记