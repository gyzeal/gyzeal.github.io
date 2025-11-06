# gyzeal.github.io

个人博客网站 - 使用纯静态 HTML 构建

## 📁 项目结构

```
gyzeal.github.io/
├── index.html              # 首页
├── style.css               # 全局样式
├── art.html                # 艺术类分类页
├── agent.html              # Agent开发类分类页
├── rl.html                 # RL学习类分类页
├── posts/                  # 文章目录
│   ├── example-post.html   # 示例文章
│   └── article-template.html  # 文章模板
└── README.md               # 说明文档
```

## 🎨 博客分类

- **艺术类** - 艺术创作与欣赏，美学思考
- **Agent开发类** - AI Agent 开发实践与探索
- **RL学习类** - 强化学习理论与应用

## ✍️ 如何写新文章

### 步骤 1：创建文章页面

1. 复制 `posts/article-template.html` 文件
2. 重命名为你的文章名（例如：`my-first-post.html`）
3. 编辑文件内容：
   - 修改 `<title>` 标签中的标题
   - 修改文章标题 `<h1>`
   - 修改日期和分类信息
   - 在 `<div class="post-content">` 中写入文章内容
   - 修改页脚的返回链接

### 步骤 2：添加到分类页面

根据文章分类，编辑对应的分类页面（`art.html` / `agent.html` / `rl.html`）：

1. 找到 `<div class="posts-list">` 部分
2. 添加以下代码：

```html
<article class="post-item">
    <h3><a href="posts/你的文章.html">文章标题</a></h3>
    <div class="post-meta">
        <span class="date">📅 2025-11-06</span>
        <span class="category">📁 分类名称</span>
    </div>
    <p class="post-excerpt">文章摘要...</p>
    <a href="posts/你的文章.html" class="read-more">阅读全文 →</a>
</article>
```

### 步骤 3：添加到首页

编辑 `index.html`，在"最新文章"部分添加同样的文章卡片。

## 🚀 发布到 GitHub Pages

1. 提交所有文件到 GitHub 仓库
```bash
git add .
git commit -m "Add new post"
git push origin main
```

2. 在 GitHub 仓库设置中启用 GitHub Pages
   - Settings → Pages
   - Source 选择 `main` 分支
   - 保存后等待几分钟

3. 访问 `https://gyzeal.github.io` 查看你的博客

## 🎯 支持的内容格式

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

### 图片
```html
<img src="path/to/image.jpg" alt="图片描述">
```

## 💡 提示

- 文章建议按日期命名，如：`2025-11-06-my-post.html`
- 定期备份文章内容
- 可以使用任何文本编辑器编辑 HTML 文件
- 在浏览器中本地预览：直接双击打开 `index.html`

## 🔄 未来升级

如果需要更多功能，可以考虑迁移到：
- **Jekyll** - 自动生成页面，支持 Markdown
- **Hugo** - 速度更快的静态网站生成器
- **Hexo** - 适合技术博客的生成器

## 📝 许可证

MIT License - 自由使用和修改
