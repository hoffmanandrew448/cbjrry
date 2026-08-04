乐富娱乐开号【Q-——333307——】乐富娱乐开号【 辋芷《888yx●vip》 】
乐富娱乐开号【Q-——333307——】乐富娱乐开号【 辋芷《888yx●vip》 】

 从零搭建个人博客：GitHub Pages + Hexo 完整教程

你是不是也想拥有一个属于自己的技术博客，但卡在“不会买服务器”“不想备案”“担心折腾成本太高”？这很正常，三年前我也一样。直到我遇到了 GitHub Pages + Hexo 这套组合，才真正体会到什么叫“零成本、高颜值、免维护”的极简建站方案。今天这份教程，我会带你完整跑通从环境准备到部署上线的全过程，手把手实操。

 为什么是 Hexo 而不是 WordPress？

先说结论：对新手、程序员、写作者来说，Hexo 的“静态博客”理念远比 WordPress 的“动态站点”更合适。

- 速度快：页面是纯静态 HTML，没有数据库查询，加载速度秒杀动态站。
- 免费托管：部署到 GitHub Pages 上，域名和带宽都免费，还能自定义域名。
- 专注写作：用 Markdown 写文章，一条命令 `hexo g && hexo d` 即可发布，极度清爽。
- 主题丰富：社区生态成熟，Next、Fluid、Butterfly 等主题开箱即用，颜值能打。

这也正是百度搜索偏好收录的“结构化、低成本、可实操”内容——本篇文章将按这个逻辑逐步拆解。

 第一步：环境准备（Node.js + Git）

你需要先安装 Node.js（建议 v18+ 或 v20 LTS）和 Git。安装完成后，打开终端（Mac/Linux 用 Terminal，Windows 用 PowerShell），分别输入 `node -v` 与 `git --version` 验证是否成功。如果显示版本号，说明环境没问题。

 第二步：安装 Hexo 并初始化博客

全局安装 Hexo 脚手架：

```bash
npm install -g hexo-cli
```

然后在本地新建一个文件夹（例如 `my-blog`），进入该文件夹并初始化 Hexo：

```bash
hexo init my-blog
cd my-blog
npm install
```

重启终端后，执行 `hexo server`，浏览器访问 `http://localhost:4000`，你应该能看到默认的 Hello World 页面。成功运行后按 `Ctrl+C` 停掉服务。

 第三步：配置站点信息（重点：关键词与描述）

打开站点根目录下的 `_config.yml` 文件，这是 Hexo 的全局配置。这里我建议你仔细写，因为百度等搜索引擎主要依靠这里的 Title 和 Description 做收录判断。

```yaml
title: 你的博客名字
subtitle: 一句话描述你的技术方向或写作目标
description: 这里写一段50-100字的站点介绍，自然放入“前端开发”、“Linux”、“自动化测试”等垂直关键词
keywords: 前端开发, Git教程, 自动化运维, Hexo教程
author: 你的昵称
language: zh-CN
```

建议将 `language` 设置为 `zh-CN`，让 baidu 爬虫能更准确地识别你的内容语言。

 第四步：部署到 GitHub Pages

首先在 GitHub 上新建一个仓库，仓库名必须为 `你的用户名.github.io`（例如 `JasonChen123.github.io`）。然后在 `_config.yml` 底部找到 `deploy` 配置：

```yaml
deploy:
  type: git
  repo: https://github.com/你的用户名/你的用户名.github.io.git
  branch: main
```

安装自动部署插件，然后生成并推送：

```bash
npm install hexo-deployer-git --save
hexo clean && hexo generate
hexo deploy
```

访问 `https://你的用户名.github.io`，你的博客就已经上线了。以后写新文章，只需在 `source/_posts` 下新建 `.md` 文件，重复上述 grep 命令，10 秒上线。

 进阶优化：让百度更容易收录

1. 开启站点地图（sitemap）：安装 `hexo-generator-sitemap` 后，用 `hexo g` 重新生成，将 `sitemap.xml` 提交到百度搜索资源平台。
2. 添加 robots.txt：放行爬虫并指定 sitemap 路径，减少无效抓取。
3. 内链建设：在多篇文章中互相链接，增加页面权重。

 小结与互动

至此，你已经拥有了一个全球可访问、免费且支持 HTTPS 的 Hexo 博客。这篇教程从环境准备、站点配置到部署上线，逻辑已全部打通。你可以先尝试将默认 Hello World 替换成一篇文章，然后部署一遍。如果部署中遇到 404、SSH 权限或图片无法显示，欢迎在评论区留言——我看到都会第一时间回复。也欢迎关注我的博客，后续将输出“Hexo 主题深度美化”“百度 SEO 实战”等系列。你的一键三连，就是我熬夜写教程的最大动力。

相关推荐：

https://github.com/leebradley6/ubrqlg/blob/main/%E6%B2%89%E9%86%89%E6%96%87%E5%BF%83%E5%AF%BB%E6%A2%A6%EF%BC%9A%E4%B9%90%E5%AF%8C%E4%B8%BB%E7%AE%A1%E5%B9%B3%E5%8F%B0_%E5%87%89%E8%B6%9F%E6%8B%BC%E4%B8%88%E9%9B%8DNUGUW.md

<img src="https://i.postimg.cc/tJTQ3j6x/lefu-00013.png" />

相关推荐：

https://github.com/leebradley6/ubrqlg/commit/100102b91bd194dd059d254f5693b0987e06c3fb

<img src="https://i.postimg.cc/sf6RVMFw/lefu-00017.png" />
相关推荐：

https://github.com/richardsonhannah5/draixy/blob/main/%E6%BC%94%E8%89%BA%E5%9C%88%E6%96%B0%E9%B2%9C%E6%8A%A5%EF%BC%9A%E4%B9%90%E5%AF%8C%E7%BD%91%E5%9D%80%E5%AE%A2%E6%9C%8D_%E9%85%92%E6%B2%83%E5%92%B3%E6%95%9B%E9%83%B4SSSST.md

<img src="https://i.postimg.cc/FKy4mGmf/lefu-00008.png" />
相关推荐：

https://github.com/richardsonhannah5/draixy/commit/29856737dad585498bbdc2a7a8690d472529c450

<img src="https://i.postimg.cc/9McjfTF9/lefu-00009.png" />

资讯来源：新华网、人民网、央视新闻、中新网、凤凰网、澎湃新闻、界面新闻、新浪新闻、搜狐网、财新网、观察者网、第一财经等主流平台，以独树一帜的观察视角与扎实的深度报道能力，在资讯领域收获广泛关注。
