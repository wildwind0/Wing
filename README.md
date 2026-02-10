# Wing

简洁流畅、数据驱动、响应式的 WordPress 主题。

![Wing 主题截图](screenshot.png)

## 项目概览

Wing 是一个偏内容创作与轻交互的博客主题，核心目标是：

- 页面干净、加载流畅（支持 PJAX）
- 文章 + 笔记双内容形态
- 前端交互增强（Vue 驱动）
- 尽量通过主题选项完成常见站点配置

> 注意：主题前端默认 **不依赖 jQuery**。如果与你的某些插件发生兼容问题，优先尝试关闭 PJAX。

## 核心能力

- 自定义内容类型：`note`（笔记）+ `topic`（话题）
- 页面模板：`笔记`、`文章归档`、`友情链接`、`读者排行`
- AJAX 能力：文章/笔记拉取、评论提交与分页、点赞、话题与访客信息等
- 主题设置：CDN、Gravatar 镜像、PJAX、代码高亮、目录、评论行为、暗色模式等
- 内容增强：文章目录、图片灯箱、代码高亮、缩略图裁剪、社交元信息

## 技术栈

- WordPress 主题（PHP）
- 前端：Vue 2.x（CDN 加载）
- 样式：原生 CSS + Spectre.css + Normalize.css
- 工具库：dayjs、js-cookie、qrcode、UAParser.js、Prettify、ViewImage

## 目录结构

```text
Wing/
├── inc/                     # 主题核心逻辑（设置、REST/AJAX、笔记、更新）
├── static/                  # 前端脚本与静态资源
├── functions.php            # 主题入口与功能挂载
├── style.css                # 主题信息与全局样式
├── page-notes.php           # 笔记页面模板
├── page-archive.php         # 文章归档页面模板
├── page-links.php           # 友情链接页面模板
└── page-wall.php            # 读者排行页面模板
```

## 环境要求

- WordPress：`>= 5.9`（代码中有版本检查）
- PHP：`>= 7.0`
- 数据库：MySQL / MariaDB（与 WordPress 要求一致）

## 部署指南

### 1) 准备 WordPress 站点

先准备好一个可正常访问的 WordPress 站点（推荐 HTTPS），并确保：

- 固定链接已启用（建议“文章名”）
- 站点可访问外部 CDN（如 `cdn.staticfile.org`）

### 2) 安装主题

任选一种方式：

1. **Git 克隆**

   ```bash
   git clone https://github.com/Tokinx/Wing.git
   ```

2. **下载 ZIP**

   从 GitHub Releases 或仓库页面下载压缩包。

把主题目录放到：

```text
wp-content/themes/Wing
```

然后在后台 `外观 -> 主题` 中启用 **Wing**。

### 3) 初始化页面模板

在 WordPress 后台创建页面并分别指定模板（按需）：

- 笔记（`Template Name: 笔记`）
- 文章归档（`Template Name: 文章归档`）
- 友情链接（`Template Name: 友情链接`）
- 读者排行（`Template Name: 读者排行`）

### 4) 主题配置

进入 `外观 -> 自定义` 完成关键配置：

- 主题设置：PJAX、暗色模式、代码高亮、目录、静态资源 CDN、头像镜像
- 评论设置：纯英文评论策略、浏览器/系统信息显示、滚动加载
- 社交资料：作者信息、站点 Footer 信息

### 5) 生产环境建议

- 如果出现插件兼容问题，先关闭 PJAX 再排查
- 为静态资源配置 CDN（可在主题设置中直接填写）
- 建议启用页面缓存与对象缓存
- 建议保持 WordPress、PHP 与主题版本更新

### 6) 更新主题

- 后台更新：主题内置更新检查器，会请求远程更新元数据
- 手动更新：下载新版本覆盖主题目录（保留你自定义改动的备份）

## 常见问题

### 与插件冲突怎么办？

优先关闭 PJAX；如果问题仍存在，逐个禁用插件做冲突定位。

### 是否需要 npm/composer 构建？

当前仓库为可直接部署的 WordPress 主题形态，默认不依赖 npm/composer 构建流程。

## 相关链接

- Issues: <https://github.com/Tokinx/Wing/issues>
- Discussions: <https://github.com/Tokinx/Wing/discussions>
- Wiki: <https://github.com/Tokinx/Wing/wiki>

## License

MIT
