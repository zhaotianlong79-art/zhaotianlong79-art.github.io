# tianlong · 个人主页

一个极简、高级、完全响应式的个人主页。**纯前端、零构建依赖**，所有内容由顶部一份中心化配置驱动。

> 技术栈：React 18 + Tailwind CSS + Lucide 图标（均通过 CDN 引入），动效采用流畅的 CSS Transition + IntersectionObserver 滚动揭示。

## ✨ 特性

- 🎯 **配置驱动**：改 `window.SITE_CONFIG` 一处，整站内容/排版即变，无需碰组件代码。
- 🌗 **暗黑/明亮主题**：由 `layout.theme` 控制默认值，右上角按钮可一键切换。
- 🧩 **模块开关**：`showExperience` / `showProjects` 为 `false` 时对应模块自动不渲染。
- 🎨 **强调色**：`layout.accent` 支持 `indigo / emerald / rose / sky / amber`。
- 📱 **响应式**：手机、平板、桌面完美适配。
- ⚡ **零安装**：双击 `index.html` 即可在浏览器查看。

## 🚀 本地预览

直接**双击 `index.html`** 用浏览器打开即可（需联网以加载 CDN 资源）。

或启动一个本地静态服务器（推荐，避免个别浏览器的 file:// 限制）：

```bash
# 任选其一
npx serve .
python3 -m http.server 8000
```

然后访问 `http://localhost:8000`。

## ⚙️ 配置说明

打开 `index.html`，找到 `window.SITE_CONFIG`（注释清晰标注），按需修改：

| 字段 | 说明 |
| --- | --- |
| `profile.name / title / bio / avatar / location` | Hero 区基础信息，`avatar` 填头像图片链接 |
| `profile.socials` | 社交链接，**留空字符串则自动隐藏**该图标（支持 github / email / twitter / website / linkedin） |
| `layout.showExperience` | `false` → 隐藏「经历」时间轴模块 |
| `layout.showProjects` | `false` → 隐藏「项目」卡片模块 |
| `layout.theme` | `"dark"` 或 `"light"`，页面初始主题 |
| `layout.accent` | 主题强调色：`indigo / emerald / rose / sky / amber` |
| `experiences[]` | 时间轴条目：`{ time, role, company, desc }` |
| `projects[]` | 项目卡片：`{ name, repo, tech: [], desc, stars }`（`stars` 可省略） |

> 配置即 JSON 结构，可轻松外置为独立的 `config.js` / `config.json`。

## 🌐 部署到 GitHub Pages（免费上线）

1. 在 GitHub 新建一个仓库，例如 `tianlong.github.io`（用此命名可直接通过 `https://tianlong.github.io` 访问）或任意名字如 `homepage`。
2. 把本项目推送上去：

   ```bash
   git init
   git add .
   git commit -m "feat: personal homepage"
   git branch -M main
   git remote add origin https://github.com/tianlong/<仓库名>.git
   git push -u origin main
   ```

3. 打开仓库 **Settings → Pages**：
   - **Source** 选择 `Deploy from a branch`
   - **Branch** 选择 `main`、目录选 `/ (root)`，保存。
4. 等待约 1 分钟，访问：
   - 若仓库名为 `tianlong.github.io` → `https://tianlong.github.io`
   - 否则 → `https://tianlong.github.io/<仓库名>/`

完成！之后每次 `git push` 都会自动更新线上页面。

### 备选：Vercel / Netlify
直接 Import 该 GitHub 仓库，框架选 **Other / 静态站点**，无需任何构建命令即可上线。
