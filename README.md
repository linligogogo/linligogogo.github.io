# 我的个人网站（基于 Asorn 开源博客模板改造）

这是一个用 **Asorn 博客开源模板** 改造的纯静态个人站点（HTML / CSS / JS，零依赖、零构建）。
由 WorkBuddy 完成重品牌：姓名/邮箱/社交链接已替换为占位符，主色抽成 CSS 变量，方便你改成自己的。

## 如何改成你自己的
1. **名字 / 邮箱 / 社交**：全局搜索并替换这些占位符：
   - `你的名字`（站点主人名）
   - `your@email.com`（联系邮箱）
   - `yourwechat`（微信号）
   - `yourname`（各社交平台用户名，如 `dribbble.com/yourname`）
   - `你的公司` / 项目 & 经历文案（在对应区块直接改文字）
2. **主色**：打开 `css/style.css`，改最顶部 `:root` 里的 `--brand`（例如 `#00C896` 或 `#FF7A33`）。全站 15 处主色会自动跟着变。
3. **图片**：现引用原作者 Asorn 的 CDN（`asorn.framer.website/assets/...`），替换成你自己的图片后改对应 `src` 即可。

## 本地预览
```bash
python3 -m http.server 8080
# 浏览器打开 http://127.0.0.1:8080
```

## 部署（GitHub Pages）
仓库根目录即站点根。推到 `username/username.github.io` 的 `main` 分支，或任意仓库开启 Pages（分支选 `main`、目录 `/root`）即可。
如遇样式/脚本不加载，确保仓库根目录有 `.nojekyll`（已包含）。

## 授权说明
源码来自 Asorn 付费开源（见 `asorn.cn`）。你可**改造自用**，但**禁止二次销售或商用**（设计 + 代码已申请专利）。
