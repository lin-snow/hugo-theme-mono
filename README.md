# Mono — 极简轻量 Hugo 博客主题  

Mono 是一款专注博客内容的极简 Hugo 主题，仅包含博客首页、文章列表和友链页面，设计轻量，简洁，完全遵循最新版 Hugo 目录结构规范。

---

## 主题特点  

- 纯博客主题，专注内容展示  
- 主页展示最新文章列表  
- 内置友链页面，轻松展示友情链接  
- 轻量无依赖，快速加载  
- 响应式设计，兼容手机和平板  
- 完全符合 Hugo 最新目录规范，易于维护

---

## 安装  
### 前置条件  
Hugo Version：`hugo v0.147.5+extended`  
Node Version: `v22.15.0`  
PNPM Version: `9.15.5`  

1. 创建站点  
```shell
hugo new site myblog  
```

2. 安装主题  
```shell
git clone https://github.com/lin-snow/hugo-theme-mono.git themes/hugo-theme-mono  
```

3. 添加依赖  
```shell
pnpm install --save-dev tailwindcss @tailwindcss/cli 
```

4. 添加配置文件(修改根目录下的hugo.toml)  
```toml
baseURL = 'https://example.com/'
languageCode = 'zh-CN'
title = "My Blog"
disableKinds = ['section', 'taxonomy', 'term']
theme = "hugo-theme-mono"

[pagination]
  pagerSize = 5

[params]
  description = 'A simple and elegant Hugo theme'
  author = 'L1nSn0w'
  keywords = 'hugo, theme, mono, simple, elegant'
  icp = '粤ICP备2023006542号-3'
  [params.social]
    github = 'https://github.com/lin-snow'
  [params.comment]
    provider = 'giscus'
    [params.comment.giscus]
      repo = 'user/repo'
      repoId = 'xxxxxx1234567'
      category = 'Announcements'
      categoryId = 'xxxxxx1234567'
      mapping = 'pathname'
      reactionsEnabled = true
      emitMetadata = false
      inputPosition = 'top'
      theme = 'light_high_contrast'
      lang = 'zh-CN'

[markup]
  [markup.goldmark]
    [markup.goldmark.parser]
      wrapStandAloneImageWithinParagraph = false
      [markup.goldmark.parser.attribute]
        block = true

[outputs]
  disableKinds = ['rss']
```

4. 启动网站：  
```shell
hugo server
```

5. 创建友链页面：
在根目录的data文件夹创建`friends.yml`并写入  
```yml  
- name: "L1nSn0w's Log"
  url: "https://log.vaaat.com/"

- name: "Soopy~"
  url: "https://soopy.cn/"
```
在`content/pages/friends/`下创建`index.md`并写入  
```markdown
---
title: L1nSn0w の 小伙伴们
layout: "links"
slug: /links
---
```