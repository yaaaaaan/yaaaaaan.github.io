---
title: How to build your own blog.
date: 2017-04-25 08:53:47
tags: []

---

# 创建博客

## 安装 nodejs
[node js](https://nodejs.org/en/)

## 安装 hexo

[Hexo](https://hexo.io/)
```shell
# 使用淘宝的npm镜像地址
npm install hexo -g --registry=https://registry.npm.taobao.org
```

## 初始化并运行

```shell
mkdir yaaaaaan_blog
cd yaaaaaan_blog
hexo init
# 开启服务，监听4000端口
hexo s
```

通过浏览器打开[http://localhost:4000/](http://localhost:4000/)就可以预览当前的博客

## 新建文章

通过 `hexo new hello-hexo` 去添加新的文章，新文章添加在`source/_posts`文件夹下，为`Markdown`格式，默认内容如下

```markdown
---
title: hello-hexo
date: 2017-04-25 08:53:47
tags: [Blog]

---


```
添加完文章在浏览器刷新即可预览文章内容，无需重启服务。

## 修改主题

编辑 `_config.yml` 下的 `theme`字段就可以修改主题
一般的主题都会有教程，这里使用的主题是[Apollo](https://github.com/pinggod/hexo-theme-apollo)

# 部署

## 创建 Githut Pages
在[Github](https://github.com)上注册账号，并创建`Github Pages`需要的仓库
假设你的用户名是`yaaaaaan`，那么创建的仓库名就应该是`yaaaaaan.github.io`,
这种仓库会被自动识别为`Github Pages`的仓库，里面部署的静态页面可以通过`yaaaaaan.github.io`这个域名来访问

## 安装Hexo插件
通过`git`部署的话需要安装一个插件，在博客目录下执行如下命令
```shell
npm install hexo-deployer-git --save --registry=https://registry.npm.taobao.org
```

## 配置 Hexo 部署的参数
编辑`_config.yml` 下的内容，修改`deploy`如下

```
deploy:
  type: git
  repo: https://github.com/yaaaaaan/yaaaaaan.github.io.git
  branch: master

```

> 注意：repo要修改为你自己的仓库地址

## 部署并查看效果
在博客目录下执行 `hexo g -d` 会生成博客的静态页面并部署到配置的`Github`仓库中
之后通过浏览器打开`https://yaaaaaan.github.io`即可看到博客的效果

玩的开心 (•̀ᴗ•́)و ̑̑
