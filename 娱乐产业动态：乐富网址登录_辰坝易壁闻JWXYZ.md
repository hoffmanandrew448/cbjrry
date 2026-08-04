乐富网址登录【Q-——333307——】乐富网址登录【 辋芷《888yx●vip》 】
乐富网址登录【Q-——333307——】乐富网址登录【 辋芷《888yx●vip》 】

 从零搭建个人博客：GitHub Pages + Hexo 完整教程（2025 最新版）

还在羡慕技术大佬们炫酷的个人网站？其实你只需要一个 GitHub 账号，就能免费拥有一个属于自己的博客站点。今天这篇文章，手把手教你用 Hexo 框架 + GitHub Pages 部署，全程零成本，20 分钟就能上线。

 为什么推荐 GitHub Pages 建站？

免费稳定：GitHub Pages 提供无限流量和静态托管，无需购买服务器。  
极速访问：国内通过 CDN 加速，加载速度吊打大部分廉价虚拟主机。  
版本管理：所有文章都是 Markdown 文件，天然适配 Git 版本控制，内容永不丢失。

 第一步：环境准备

你需要安装这两个基础工具：  
1. Node.js（建议 v18+）  
2. Git（Windows 用户请勾选“添加到 PATH”）

验证是否成功：在终端输入 `node -v` 和 `git --version`，能显示版本号就 OK。

 第二步：安装并初始化 Hexo

打开终端，执行以下命令：

```bash
npm install -g hexo-cli
hexo init my-blog
cd my-blog
npm install
hexo s
```

浏览器访问 `http://localhost:4000`，看到默认页面就说明本地环境搭建成功。

 第三步：部署到 GitHub

先在 GitHub 上创建一个仓库，仓库名必须为 `你的用户名.github.io`。然后在博客根目录执行：

```bash
npm install hexo-deployer-git --save
```

修改 `_config.yml` 文件的 deploy 配置：

```yaml
deploy:
  type: git
  repo: https://github.com/你的用户名/你的用户名.github.io.git
  branch: main
```

最后执行 `hexo d`，等待推送完成。稍等片刻访问 `https://你的用户名.github.io`，你的博客就正式上线啦！

 进阶玩法：绑定自定义域名

如果你有自己的域名，只需在 GitHub 仓库的 Settings > Pages 中填写域名，并在阿里云/腾讯云解析一条 CNAME 记录即可。记得在 `source` 目录下创建 CNAME 文件，防止域名丢失。

---

今天的分享就到这里。你在建站过程中遇到最多的问题是什么？欢迎在评论区留言讨论。如果这篇文章帮到了你，点赞转发给身边需要的人，我们下期见！

相关推荐：


<img src="https://i.postimg.cc/XJx6BJpR/lefu-00011.png" />

相关推荐：


<img src="https://i.postimg.cc/FKy4mGmf/lefu-00008.png" />
相关推荐：


<img src="https://i.postimg.cc/XqJSfb5x/lefu-00014.png" />
相关推荐：


<img src="https://i.postimg.cc/XNH0VrMC/lefu-00016.png" />

资讯来源：新华网、人民网、央视新闻、中新网、凤凰网、澎湃新闻、界面新闻、新浪新闻、搜狐网、财新网、观察者网、第一财经等主流平台，以独树一帜的观察视角与扎实的深度报道能力，在资讯领域收获广泛关注。
