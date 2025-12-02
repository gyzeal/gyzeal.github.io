# 个人博客

简洁的个人博客网站，使用纯静态 HTML 构建。

## 项目结构

```
gyzeal.github.io/
├── index.html              # 首页（文章归档列表）
├── style.css               # 全局样式
├── avatar.jpg              # 个人头像（需要自己添加）
├── art.html                # 艺术类分类页
├── agent.html              # Agent开发类分类页
├── rl.html                 # RL学习类分类页
├── posts/                  # 文章目录
│   ├── example-post.html   # 示例文章
│   └── article-template.html  # 文章模板
└── README.md               # 说明文档
```

## 初始设置

### 1. 添加个人头像

将你的头像图片命名为 `avatar.jpg`，放在根目录下。建议使用正方形图片（如 400x400px）。

### 2. 修改个人信息

编辑所有页面中的左侧边栏信息：

```html
<div class="profile">
    <img src="avatar.jpg" alt="Profile Photo" class="avatar">
    <h2 class="name">Your Name</h2>  <!-- 修改为你的名字 -->
    <p class="bio">简短的个人介绍</p>  <!-- 修改个人介绍 -->
</div>

<div class="contact">
    <a href="mailto:your@email.com">Email</a>  <!-- 修改邮箱 -->
    <a href="https://github.com/gyzeal" target="_blank">GitHub</a>  <!-- 修改GitHub链接 -->
</div>
```

需要修改的文件：
- index.html
- art.html
- agent.html
- rl.html
- posts/article-template.html
- posts/example-post.html

## 如何写新文章

### 步骤 1：创建文章页面

1. 复制 `posts/article-template.html` 文件
2. 重命名为你的文章名（建议：`2025-11-06-article-title.html`）
3. 编辑文件内容：
   - 修改 `<title>` 标签
   - 修改文章标题 `<h1>`
   - 修改日期和分类
   - 在 `<div class="post-content">` 中写入内容
   - 修改返回链接

### 步骤 2：添加到首页归档

编辑 `index.html`，在对应的年份/月份下添加：

```html
<article class="post-entry">
    <a href="posts/your-article.html" class="post-title">文章标题</a>
    <div class="post-info">
        <span class="post-date">Date: November 6, 2025</span>
        <span class="post-meta">Estimated Reading Time: 5 min</span>
        <span class="post-author">Author: Your Name</span>
    </div>
</article>
```

如果需要添加新的年份或月份：

```html
<section class="year-section">
    <h2 class="year">2025 <sup>1</sup></h2>  <!-- sup中的数字是该年的文章数 -->
    
    <div class="month-section">
        <h3 class="month">November <sup>1</sup></h3>  <!-- sup中的数字是该月的文章数 -->
        <!-- 文章列表 -->
    </div>
</section>
```

### 步骤 3：添加到分类页面

编辑对应的分类页面（`art.html` / `agent.html` / `rl.html`）：

```html
<article class="post-item">
    <h3><a href="posts/your-article.html">文章标题</a></h3>
    <div class="post-meta">
        <span class="date">Date: November 6, 2025</span>
        <span class="category">Category: 艺术类</span>
    </div>
    <p class="post-excerpt">文章摘要...</p>
    <a href="posts/your-article.html" class="read-more">Read More</a>
</article>
```

## 支持的内容格式

### 标题
```html
<h2>大标题</h2>
<h3>小标题</h3>
```

### 段落和文本
```html
<p>这是一个段落</p>
<strong>粗体文本</strong>
<em>斜体文本</em>
```

### 列表
```html
<ul>
    <li>无序列表项</li>
</ul>

<ol>
    <li>有序列表项</li>
</ol>
```

### 代码
```html
<code>行内代码</code>

<pre><code>代码块
多行代码
</code></pre>
```

### 引用
```html
<blockquote>
    引用的文字
</blockquote>
```

### 链接
```html
<a href="https://example.com">链接文本</a>
```

### 图片
```html
<img src="path/to/image.jpg" alt="图片描述">
```

## 发布到 GitHub Pages

1. 提交所有文件到 GitHub 仓库：
```bash
git add .
git commit -m "Update blog"
git push origin main
```

2. 在 GitHub 仓库设置中启用 GitHub Pages：
   - 进入 Settings → Pages
   - Source 选择 `main` 分支
   - 保存后等待几分钟

3. 访问 `https://gyzeal.github.io` 查看你的博客

## 本地预览

直接在浏览器中打开 `index.html` 文件即可预览。

## 设计说明

- 采用深色主题（背景 #1e1e1e，侧边栏 #252526）
- 左侧固定边栏，右侧内容区域
- 响应式设计，移动端自动调整布局
- 简洁专业的排版风格

## 未来升级

如果需要更多功能，可以考虑迁移到：
- **Jekyll** - 自动生成页面，支持 Markdown
- **Hugo** - 速度更快的静态网站生成器
- **Hexo** - 适合技术博客的生成器

## 许可证

MIT License
