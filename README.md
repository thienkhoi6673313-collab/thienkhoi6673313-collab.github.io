# 个人网站部署指南

## 项目结构

```
├── index.html      # 主页面
├── css/
│   └── style.css   # 样式文件（含明暗主题）
├── js/
│   └── main.js     # 交互脚本
└── README.md       # 本文件
```

## 本地预览

```bash
# 方式一：用 Node.js
node server.js

# 方式二：用 Python
python -m http.server 3000

# 方式三：用 VS Code Live Server 插件
# 右键 index.html → Open with Live Server
```

浏览器打开 `http://localhost:3000` 即可预览。

## 部署到 GitHub Pages

### 第一步：创建 GitHub 仓库

1. 登录 [GitHub](https://github.com)
2. 点击右上角 **+** → **New repository**
3. 仓库名填 `你的用户名.github.io`（例如 `zhangsan.github.io`）
4. 选择 **Public**
5. 勾选 **Add a README file**
6. 点击 **Create repository**

### 第二步：上传文件

将 `index.html`、`css/`、`js/` 三个文件/文件夹上传到仓库根目录：

**方式一：网页上传**
1. 在仓库页面点击 **Add file** → **Upload files**
2. 拖入所有文件
3. 填写 commit message，点击 **Commit changes**

**方式二：Git 命令行**
```bash
git clone https://github.com/你的用户名/你的用户名.github.io.git
# 把 index.html, css/, js/ 复制到克隆的目录中
cd 你的用户名.github.io
git add .
git commit -m "Initial website"
git push origin main
```

### 第三步：启用 GitHub Pages

1. 进入仓库 → **Settings** → **Pages**
2. **Source** 选择 **Deploy from a branch**
3. **Branch** 选择 `main`，文件夹选 `/ (root)`
4. 点击 **Save**
5. 等待 1-2 分钟，访问 `https://你的用户名.github.io` 即可看到网站

## 自定义修改指南

### 修改个人信息
打开 `index.html`，搜索以下关键词替换为你自己的内容：
- `开发者` → 你的名字
- `hello@example.com` → 你的邮箱
- `https://github.com/` → 你的 GitHub 主页
- 项目名称、描述、技术栈等

### 修改配色方案
打开 `css/style.css`，在 `:root` 中修改 CSS 变量：
```css
--accent: #6366f1;          /* 主色调 */
--gradient-1: #6366f1;       /* 渐变起点 */
--gradient-2: #a855f7;       /* 渐变中点 */
--gradient-3: #ec4899;       /* 渐变终点 */
```

### 添加/删除项目
在 `index.html` 的 `project-grid` 区域，复制/删除 `project-card` 块即可。

### 添加动态更新
在 `index.html` 的 `timeline` 区域，复制 `timeline-item` 块并修改内容。

## 功能特性

- ✅ 明暗主题切换（自动跟随系统偏好，可手动切换）
- ✅ 响应式设计（桌面 / 平板 / 手机全适配）
- ✅ 滚动入场动画
- ✅ 项目分类筛选
- ✅ 数字计数动画
- ✅ 平滑锚点跳转
- ✅ 导航栏滚动高亮
- ✅ Hero 视差效果
- ✅ 纯静态，零依赖，加载极快
