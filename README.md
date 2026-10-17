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

## 部署上线（三种任选，仓库根目录即站点根）

### 方案 A · GitHub Pages（免费，域名 `你的名.github.io`）
1. 新建仓库，命名为 `你的GitHub用户名.github.io`（这样直接获得该域名）。
2. 把本目录推上去：
   ```bash
   git remote add origin https://github.com/你的名/你的名.github.io.git
   git branch -M main
   git push -u origin main
   ```
3. 仓库 **Settings → Pages → Branch 选 `main`、目录 `/root` → Save**。
4. 等 1~2 分钟，访问 `https://你的名.github.io` 即可。
   （用任意仓库名也行，同样在第 3 步开启 Pages 即可，只是域名带仓库路径。）

### 方案 B · Vercel（免费，可绑自定义域名）
1. 注册 Vercel，点 **Add New → Project → Import Git Repository** 选你的仓库。
2. Framework Preset 选 **Other**，Build Command 留空，Output Directory 填 `.`（根目录）。
3. 点 Deploy，几十秒后给一个 `xxx.vercel.app` 域名，可在 Settings 里绑自己的域名。

### 方案 C · Cloudflare Pages（免费，全球 CDN 快）
1. 登录 Cloudflare → **Workers & Pages → Create → Pages → Connect to Git** 选仓库。
2. Build command 留空，Build output directory 填 `/`（根目录）。
3. 点 Save and Deploy，得到 `xxx.pages.dev` 域名，Settings → Custom domains 绑自己的域名。

> 根目录已含 `.nojekyll`，纯静态无需任何构建命令，三平台都能直接识别。
> 推送如需用令牌：GitHub → Settings → Developer settings → Personal access tokens → Fine-grained，权限选目标仓库 `Contents: Read and write`。

## 授权说明
源码来自 Asorn 付费开源（见 `asorn.cn`）。你可**改造自用**，但**禁止二次销售或商用**（设计 + 代码已申请专利）。
