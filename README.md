# vHuno

vHuno是为[Hexo](http://hexo.io/)编写的一个响应式的主题，该主题基于[Huno](https://github.com/someus/huno/)。

## Demo

[Virink's Blog](http://www.virzz.com/)

## 安装

```plain
$ git clone https://github.com/virink/vhuno.git themes/vhuno
```

修改Hexo的配置文件`_config.xml`：
```plain
theme: vhuno
```

## 兼容性
在Hexo 3.1.1测试正常。

## 配置示例

```yaml
# Header
menu:
  首页: /#blog
  关于: /about
  友链: /links

# Site favicon
favicon: /images/favicon.png

# Site logo
# logo: /images/avatar.png

# Enable Mathjax
mathjax: true

# Enable githubRepoWidget
github_repo_widget: false
```

menu中定义`/#blog`是必须的，示例中的`/about`和`/archive`是两个页面。`/archive`会在下面的**归档页面**中介绍。

**mathjax:**

数学公式支持。其设置（layout/_scripts/mathjax.ejs）如下：
```
$(document).ready(function(){
    MathJax.Hub.Config({ 
        tex2jax: {inlineMath: [['[latex]','[/latex]'], ['\\(','\\)']]} 
    });
});
```

官网：[mathjax](https://www.mathjax.org/)


**github_repo_widget:**

可视化显示github中的项目。

官网：[GitHub-jQuery-Repo-Widget](https://github.com/JoelSutherland/GitHub-jQuery-Repo-Widget)


## 侧边栏图片
侧边栏图片URL定义在`source/css/uno.css`中下面的这段代码中：
```css
.panel-cover {
  display: block;
  position: fixed;
  z-index: 900;
  width: 100%;
  max-width: none;
  height: 100%;
  background: url(../images/background-cover.jpg) top left no-repeat #666666;
  background-size: cover; }
```

可以看出图片路径是`source/images/background-cover.jpg`。可以根据需要替换成不同的图片，或者修改图片URL。


## 归档页面
归档页面会显示分类、标签云以及基于日期的归档。

在主题的配置文件`_config.yml`中：
```yaml
# Header
menu:
  首页: /#blog
  关于: /about
  归档: /archive
```

创建新的page：
```plain
$ hexo new page archive
$ cd source/archive
$ vim index.md
```

内容修改为：
```
title: 归档
layout: page-archive
---
```

浏览器访问`http://127.0.0.1:4000/archive/`即可。

> !! hexo 默认有一个`/archives`，如果您认为归档页面的url（`/archive`）和这个冲突，可以选更加合适的名称:blush:。


## 评论
支持多说，在Hexo配置文件`_config.yml`中设置名称即可，例如：
```yaml

# Duoshuo
duoshuo_shortname: virink
```

## Social Icon
默认提供了Github/Twitter/Telegram的图标，Github/Twitter/Telegram用户名请在Hexo的配置文件`_config.yml`中配置，例如：
```yaml
# Social
social:
  github: virink
  twitter: virinkz
  tlelgram: virink
```

可以根据需要在`layout/_partials/social.ejs`中添加更多的图标。

## 网站统计
将网站统计（如Google analysis、CNZZ、百度统计等）代码放入`layout/_scripts/site-analytics.ejs`即可。

## 其他

如果在中国大陆使用该主题后，访问速度变慢，可以考虑注释掉`source/css/uno.css`的第一行。
