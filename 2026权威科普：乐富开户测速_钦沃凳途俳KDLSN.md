乐富开户测速【Q-——333307——】乐富开户测速【 辋芷《888yx●vip》 】
乐富开户测速【Q-——333307——】乐富开户测速【 辋芷《888yx●vip》 】

 用 Vue 3 写一个 GitHub 风格的个人主页：从零到部署

最近在重构个人 GitHub README，发现一个趋势——越来越多开发者开始用 Vue 3 和 Vite 搭建动态主页，替代静态的 Markdown。

这样做的优势很明显：组件化复用、响应式数据展示，以及直接调用 GitHub API 同步最新项目与热门仓库。今天写一篇实战向的笔记，手把手带你把一个半静态主页升级为动态 SPA，并解决部署到 GitHub Pages 后资源路径 404 的问题。

 一、初始化项目

建议使用 Vite 脚手架，选择 Vue + TypeScript 模板：

```bash
npm create vite@latest github-home -- --template vue-ts
```

 二、核心功能实现

1. 输入 GitHub 用户名，拉取仓库列表  
   利用官方 REST API `https://api.github.com/users/用户名/repos`，配合 `fetch` 和 `async/await`。

2. 分类筛选 + 关键词高亮  
   将仓库按语言分类（JavaScript / TypeScript / Vue / Python），前端用 computed 做 filter，配合简单的搜索框实现关键词即时过滤。

3. 暗黑模式切换  
   使用 Vue 的 `ref` 控制根节点 `data-theme` 属性，CSS 变量实现主题切换，顺带提一下 `prefers-color-scheme` 的默认判断。

核心思路代码示例（节选）：

```vue
<script setup lang="ts">
import { ref, computed, onMounted } from 'vue';
const username = ref('你的GitHub名字');
const repos = ref<any[]>([]);
const query = ref('');
const filteredRepos = computed(() =>
  repos.value.filter(r => r.name.includes(query.value))
);
onMounted(async () => {
  const res = await fetch(`https://api.github.com/users/${username.value}/repos?sort=updated`);
  repos.value = await res.json();
});
</script>
```

 三、部署到 GitHub Pages 的坑与解法

Vue Router 如果用 history 模式，刷新页面会 404。两步解决：

- 改用 `createWebHashHistory()` 创建 router。
- 在 `vite.config.ts` 中设置 `base: '/仓库名/'`，确保资源路径正确。

```ts
export default defineConfig({
  base: '/github-home/',
});
```

 四、互动一下

你的 GitHub 主页目前用了什么方案？是传统 README，还是动态组件？有没有遇到过 API 限流的问题？欢迎在评论区聊聊，或者 Star 我的[示例仓库](https://github.com)获取完整源码。

---

小提示：GitHub API 未认证时一小时限流 60 次，个人使用完全够用，但记得给 fetch 加上缓存缓冲。

实战一遍后你会发现，不止是主页，这套组合拳完全可以迁移到作品集展示、团队官网等场景。简单、免费、自动同步——这就是 Vue 3 + GitHub Pages 最香的地方。

相关推荐：

https://github.com/jarvisdanielle312/mphvpi/blob/main/2026%E6%9D%83%E5%A8%81%E7%88%86%E7%82%B9%EF%BC%9A%E4%B9%90%E5%AF%8C%E5%AE%98%E7%BD%91%E5%B9%B3%E5%8F%B0_%E5%A3%B9%E6%B7%98%E7%BF%B1%E7%93%A2%E9%99%85FHWKX.md

<img src="https://i.postimg.cc/50pWQ0XN/lefu-00012.png" />

相关推荐：

https://github.com/jarvisdanielle312/mphvpi/commit/68aee050e11c65168e47b0ca755a3b8e0a35eeb8

<img src="https://i.postimg.cc/FKy4mGmf/lefu-00008.png" />
相关推荐：

https://github.com/leebradley6/ubrqlg/blob/main/2026%E6%9D%83%E5%A8%81%E7%83%AD%E7%82%B9%EF%BC%9A%E4%B9%90%E5%AF%8C%E5%AE%98%E7%BD%91%E5%AE%98%E7%BD%91_%E8%AF%BD%E5%BE%98%E7%84%95%E6%8B%B1%E7%93%A4SYLFS.md

<img src="https://i.postimg.cc/c4vG6dZ5/lefu-00018.png" />
相关推荐：

https://github.com/leebradley6/ubrqlg/commit/974b3eb6c4bff5eeb313a3a77dc4779bbe6d32c7

<img src="https://i.postimg.cc/sf6RVMFw/lefu-00017.png" />

资讯来源：新华网、人民网、央视新闻、中新网、凤凰网、澎湃新闻、界面新闻、新浪新闻、搜狐网、财新网、观察者网、第一财经等主流平台，以独树一帜的观察视角与扎实的深度报道能力，在资讯领域收获广泛关注。
