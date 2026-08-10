# Personal Academic Site (Astro + Tailwind)

这是一个使用 Astro 和 TailwindCSS 搭建的学术个人主页示例。

快速开始：

```bash
npm install
npm run dev
```

说明：
- 开发服务器：`npm run dev`（默认 http://localhost:3000）
- 构建：`npm run build`
- 预览：`npm run preview`

你可以编辑 `src/pages` 和 `src/components` 开发内容。

新增内容：
- 联系页：`/contact`，包含 `mailto` 和表单示例（Formspree 占位）。
- 论文数据：`src/data/publications.json`，`/publications` 页面会从该文件渲染列表。
- 可下载 CV：将你的 PDF 放入 `public/cv.pdf`，站点会在页眉显示 `CV` 链接以便下载。
- 基础 SEO/OpenGraph：站点现在在 `Layout` 中包含 `description`、OpenGraph 和 Twitter meta 标签。可在 `src/data/site.json` 中修改站点描述与默认图片。
 - OpenGraph 图片：我已添加占位 OG 图片到 `public/`（`og-default.svg`, `og-home.svg`, `og-about.svg`, `og-publications.svg`, `og-contact.svg`）。
	 替换这些 SVG 或用 PNG/JPEG 生成更漂亮的图片即可。页面已支持传入 `image` 覆盖默认图片。

OpenGraph 图片替换与测试指南（可选，暂不自动生成）
- 推荐尺寸：1200×630 px（社交平台通用），比例约 1.91:1；也可使用 SVG 以便随尺寸缩放。
- 格式：PNG 或 JPEG（保守兼容），SVG 也可用于现代平台但在某些缓存或代理上可能不被渲染。
- 文件位置：把图片放入 `public/` 目录（例如 `public/og-home.png`），并在页面 frontmatter 或 `Layout` 的 `image` 属性中使用绝对路径（以 `/` 开头），例如：`image="/og-home.png"`。
- 设计建议：在图像中包含站点/姓名、页面主要标题、清晰的副标题或年份；保证文字在手机端仍可辨认（大字号、对比度高）。
- 生成工具：Figma、Canva、Bannerbear、Satori（JS）、或用 Puppeteer / Playwright 渲染 HTML 到图片。若需要，我可以提供一个 Node 脚本示例将 SVG 转 PNG。
- 缓存与调试：社交平台会缓存 OG 图像，替换后请使用 Facebook Sharing Debugger 和 Twitter Card Validator 清理缓存并预览。也可在终端用 `curl` 检查页面返回的 meta 标签。
- 流程小结：
	1. 设计或生成图片 → 保存为 `public/your-og.png`。
	2. 在页面中传入 `image`（例如 `<Layout image="/your-og.png" ...>`）或修改 `src/data/site.json` 的默认 `image`。
	3. 部署并使用分享调试工具验证显示效果。

目前我已添加占位图并把页面配置好以支持自定义 OG 图片；如需我生成 PNG 或写转换脚本，请告诉我想要的工具（例如 `sharp` / `puppeteer` / `satori`）。
