---
layout: wiki
wiki: hexo-stellar
title: 实现「笔记」栏目
---

## 创建描述文件

```yaml blog/source/_data/wiki/notes.yml
name: 备忘录
title: 备忘录
icon: # 列表页图标
cover: # 封面页大图
coverpage: [cover, title, description] # 封面页显示的内容

sidebar: 
  - layout: search
    override: search
    filter: /notes/
    placeholder: 在此处搜索...
  - toc

comments:
  giscus:
    'data-term': '23'
    'data-mapping': number

path: /notes/
toc:
  '日常问题解决方案':
    - mac
  '移动端开发笔记':
    - ios
    - flutter
  '前端学习笔记':
    - nodejs
    - server
  '在线工具':
    - json
```

## 设置 menu_id

然后笔记页面的 `front-matter` 中指定要高亮的 `menu_id`：

```yaml blog/source/notes/index.md
---
layout: wiki
wiki: notes # 这个跟上面的 /wiki/notes.yml 关联起来
menu_id: notes # 这个跟配置文件中的 `sidebar.menu.notes` 关联起来，这很重要，如果没有这个，就像普通的wiki项目一样了
---
```

这样就可以啦～