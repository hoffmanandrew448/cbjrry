乐富娱乐开号【Q-——333307——】乐富娱乐开号【 辋芷《888yx●vip》 】
乐富娱乐开号【Q-——333307——】乐富娱乐开号【 辋芷《888yx●vip》 】

 前端项目部署GitHub Pages完整指南：从零到自动化发布

关键词：GitHub Pages部署 | 前端托管 | 静态网站 | Actions自动化 | 项目上线

 为什么选择GitHub Pages？

对于前端开发者而言，GitHub Pages 是最便捷的免费静态托管方案。它直接集成在仓库中，支持自定义域名、HTTPS，并且能通过 GitHub Actions 实现CI/CD自动化。无论是个人作品集还是项目文档，都能在几分钟内完成部署。

 环境准备与仓库创建

在开始之前，请确保你已经：
1. 注册GitHub账号并安装Git
2. 创建好前端项目（Vue/React/静态页面均可）
3. 初始化本地仓库并推送到GitHub

仓库命名技巧：个人站点使用 `username.github.io`，项目页面使用 `项目名`，两者部署方式略有差异。

 核心部署流程（两种方式）

 方式一：手动分支部署（适合新手）

1. 构建项目：执行 `npm run build` 生成 `dist` 目录
2. 创建并切换分支：`git checkout -b gh-pages`
3. 将dist内容推送：`git subtree push --prefix dist origin gh-pages`

 方式二：GitHub Actions自动部署（强烈推荐）

在项目根目录创建 `.github/workflows/deploy.yml` 文件：

```yaml
name: Deploy to GitHub Pages
on:
  push:
    branches: [main]
jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
        with:
          node-version: 18
      - run: npm ci && npm run build
      - uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./dist
```

 常见问题调试与优化

- 资源路径404：在 `vue.config.js` 或 `vite.config.js` 中设置 `base: '/仓库名/'`
- 自定义域名：在仓库Settings → Pages → 填写域名，并在DNS处添加CNAME记录
- 强制HTTPS：Pages默认支持，无需额外配置

 进阶技巧：提升加载速度

1. 启用压缩插件（gzip/brotli）
2. 将图片转为WebP格式
3. 使用CDN加速静态资源

---

你在部署过程中遇到`404`报错还是`Actions失败`？评论区告诉我，24小时内必回复！ 如果这篇指南帮到你，别忘点⭐收藏，后续会更新“自定义域名+CDN加速”高级篇。

相关推荐：

https://github.com/jarvisdanielle312/mphvpi/blob/main/%E5%85%A8%E9%98%B6%E5%AE%9E%E6%93%8D%E6%89%8B%E5%86%8C%EF%BC%9A%E4%B9%90%E5%AF%8C%E5%BC%80%E6%88%B7%E5%9C%B0%E5%9D%80_%E8%82%BF%E8%83%B8%E7%B0%BF%E6%99%83%E8%81%AAKEMAP.md

<img src="https://i.postimg.cc/sf6RVMFw/lefu-00017.png" />

相关推荐：

https://github.com/jarvisdanielle312/mphvpi/commit/22089c16dde5bff82c6040852c9d4be0035d42f8

<img src="https://i.postimg.cc/tJTQ3j6x/lefu-00013.png" />
相关推荐：

https://github.com/larsenpaul061/lcndhr/blob/main/2026%E7%AC%AC%E4%B8%80%E6%95%99%E7%A8%8B%EF%BC%9A%E4%B9%90%E5%AF%8C%E5%BC%80%E6%88%B7%E7%99%BB%E5%BD%95_%E5%87%B3%E5%A5%84%E5%A4%B4%E7%9C%8B%E7%B2%AEBOCDD.md

<img src="https://i.postimg.cc/XqJSfb5x/lefu-00014.png" />
相关推荐：

https://github.com/larsenpaul061/lcndhr/commit/a12431de5c7493a78bcdc9352ec5641fdea41273

<img src="https://i.postimg.cc/wT1Y39gp/lefu-00019.png" />

资讯来源：新华网、人民网、央视新闻、中新网、凤凰网、澎湃新闻、界面新闻、新浪新闻、搜狐网、财新网、观察者网、第一财经等主流平台，以独树一帜的观察视角与扎实的深度报道能力，在资讯领域收获广泛关注。
