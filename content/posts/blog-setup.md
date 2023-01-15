---
title: 本博搭建记录
date: 2023-01-14T17:00:04-08:00
draft: true
summary: 三流程序员现身啦
---


# 本博搭建记录

搭建环境：macOS

《总结一下要用GitHub Pages+Hugo，以及本篇非教程（指路教程），而是记录》

## 注册GitHub账号

用GitHub Pages建站的话，默认网址会是`用户名.github.io`。因为暂时没打算买域名，所以纠结了好一会儿选什么用户名好。

15:26 终于选好了名字注册

15:35 顺便开启了2FA

## 建立GitHub Pages repo

《《图片》》

建立一个新的repo，名为`用户名.github.io`。注意如果GitHub账户是免费plan，这个用来设置GitHub Pages的repo一定要是public repo。

我选择用GitHub Desktop，跟着官方网页上的步骤来clone repo到本地。

[GitHub Pages | Websites for you and your projects, hosted directly from your GitHub repository. Just edit, push, and your changes are live.](https://pages.github.com/)

## 设置Hugo

根据[Quick Start | Hugo (gohugo.io)](https://gohugo.io/getting-started/quick-start/)，打开Terminal并输入

```bash
brew install hugo
hugo new site 用户名.github.io -f yml --force
```

1. 因为我已经有[Homebrew](https://brew.sh/)了，直接用了`brew install hugo`的方法安装。
2. 需要用刚装好的hugo将repo设置好。因为已经把clone到了本地的一个文件夹里，所以用了`--force`。`-f yml`的部分是根据PaperMod的指示。

《（不重要的步骤：把.DS_Store加入gitignore）》

15:59休息，16:17回归

##设置PaperMod Theme

决定用Hugo的PaperMod这个theme，因为感觉好看，功能看起来也比较全。跟着PaperMod的安装步骤走：[Installation · adityatelange/hugo-PaperMod Wiki (github.com)](https://github.com/adityatelange/hugo-PaperMod/wiki/Installation)

刚开始使用了Installation中的Method 1，直接git clone到repo里。但后面碰到了一些问题，所以换成了使用Method 1的git submodules。最后一步需要修改文件夹里的`config.yml`，我在Visual Studio Code中打开了整个文件夹（其实用其他plain text editor也可以，不过用VSCode可以直接在里面打开Terminal，比较方便）。把其他行也改了一下，`languageCode`先删掉了（尝试了一下，如果设置成中文会导致后续有一些不方便的地方，之后有时间再改……吧，可以参考[I18n Tutorial: How to Go Multilingual with Hugo | Phrase](https://phrase.com/blog/posts/i18n-tutorial-how-to-go-multilingual-with-hugo/)）。

```yaml
baseURL: https://changxiawushi.github.io/
title: 长夏无事
theme: "PaperMod"
```

根据Hugo的[Quick Start](https://gohugo.io/getting-started/quick-start/)，现在已经可以用`hugo server`预览网站的样子了。现在只有我改的博客标题，旁边的图标可以在日间和夜间模式之间切换。如果修改文件夹里的文件，server都会自动检测到更新并重新build和加载本地预览。nice.

《图片》

## 创建第一篇博文

16:47休息，16:58回归

跟着Hugo的步骤，试着创建了第一篇博文。

[Quick Start | Hugo (gohugo.io)](https://gohugo.io/getting-started/quick-start/#add-content)

```bash
hugo new posts/hello-world.md
```

所有的博文都会用Markdown文件，`hello-world`是文件的名字，也会出现在博文的链接里，即`用户名.github.io/posts/hello-word`。简单修改了生成的标题。

发现Hugo的默认本地预览不包括草稿，所以关掉了前面的server（Control+C），并输入`hugo server -D`。

就这样出现在首页啦。《图片》

## 修改设置

PaperMod的设置列表：[Variables | Front Matter | PaperMod (adityatelange.github.io)](https://adityatelange.github.io/hugo-PaperMod/posts/papermod/papermod-variables/)

PaperMod的demo网站：[PaperMod (adityatelange.github.io)](https://adityatelange.github.io/hugo-PaperMod/)

我开始看这个demo网站的设置，并开始搬运到自己的`config.yml`：[hugo-PaperMod/config.yml at exampleSite · adityatelange/hugo-PaperMod (github.com)](https://github.com/adityatelange/hugo-PaperMod/blob/exampleSite/config.yml)

```yaml
# 一页显示5篇文章
paginate: 5
# 要表情！
enableEmoji: true

# params底下的应该是PaperMod的设置
params:
  env: production
  defaultTheme: auto
  ShowReadingTime: true
  # 刚开始很疑惑为什么我的博文没有像demo站一样在一个框框里，后来发现是第一篇文章有特别的显示设置，把下面这行加上就好啦
  disableSpecial1stPost: true
  ShowPostNavLinks: true
  ShowBreadCrumbs: true
  ShowCodeCopyButtons: true
  ShowRssButtonInSectionTermList: true
  ShowToc: true
```

设置了`disableSpecial1stPost: true`以后，所有的博文都会在框框里啦。

《图片》

### 添加菜单

在`config.yml`中添加

```yaml
# 在页面上方加入菜单
menu:
  main:
    - name: 标签
      url: tags/
      # 指定“标签”作为第一个出现的
      weight: 1
    - name: RSS订阅
      url: index.xml
      weight: 2
    - name: 文章
      url: posts/
      weight: 3
```

《再插入图片》

RSS订阅参考了[Setting up an RSS feed for a Hugo blog using the PaperMod Theme | by Erica Pisani | Medium](https://medium.com/@ericapisani/setting-up-an-rss-feed-for-a-hugo-blog-using-the-papermod-theme-a141b3fa1ccd)

在`config.yml`中添加

```yaml
outputs:
  home:
    - HTML
    - RSS
    - JSON
```

《需要测试一下捏》

现在还没有标签，所以需要去博文中添加一下。

### 修改博文

#### 标签

```markdown
---
title: "Hello World"
date: 2023-01-14T16:14:48-08:00
draft: false
summary: 你好哇！
tags: ["测试", "你好"]
---
```

最后的tags就是标签啦，可以定义多个，拿逗号隔开就好。这些标签会自动出现在`网站/tags`（本地预览可能会有些延迟），点击任何一个就会显示所有带此标签的文章。

#### 图片

官方链接：[Page Resources | Hugo (gohugo.io)](https://gohugo.io/content-management/page-resources/)

参考demo网页带图博文的文件结构：[hugo-PaperMod/content/posts/papermod/papermod-features at exampleSite · adityatelange/hugo-PaperMod (github.com)](https://github.com/adityatelange/hugo-PaperMod/tree/exampleSite/content/posts/papermod/papermod-features)

在`content/posts`里创建一个新的文件夹`hello-world`（与原markdown文件同名），把`hello-world.md`移到新创建的`hello-word`文件夹里再改名为`index.md`，最后在`hello-world`文件夹中另创建一个`images`文件夹放图片。

注：在本地预览时图片可能加载不出来，如果需要确认，可以把`config.yml`里的`baseURL`改成本地预览的链接，如`baseURL: http://localhost:1313`（[参考](https://discourse.gohugo.io/t/preview-images-with-localhost/33095)）。或者用Markdown Editor（比如Typora）查看确认就不用改设置啦。

再注：用Markdown语法插入图片时，记得`./images/xxx.png`或者`images/xxx.png`都可以，但`/images/xxx.png`

再再注：保险起见，我安装了[ExifTool](https://exiftool.org/)，并在上传前用它抹去图片中可能暴露个人信息的metadata（[参考](https://stackoverflow.com/questions/66192531/exiftool-how-to-remove-all-metadata-from-all-files-possible-inside-a-folder-an)）。

```bash
brew install exiftool
exiftool -a -all:all= -r path/to/images
```

## 发布测试

现在可以把本地的文件都push到GitHub，看一下网站的效果啦。

跟着Hugo的教程：[Host on GitHub | Hugo (gohugo.io)](https://gohugo.io/hosting-and-deployment/hosting-on-github/)

创建GitHub Action的时候，因为不熟悉碰到了好多问题。首先是看不到action有在跑，然后发现是把文件放错了位置，一定要放在`.github/workflows/`这个文件夹里面才可以。放对了位置以后push能看到action在跑，但碰到了另一个error message。尝试了一些网上的建议无果以后，发现[mzfr.github.io/.gitmodules at f02722a1499b155816d1cc15d81a74af6864c0c6 · mzfr/mzfr.github.io](https://github.com/mzfr/mzfr.github.io/blob/f02722a1499b155816d1cc15d81a74af6864c0c6/.gitmodules)





## 一些困难

- 语言设置
  - 可参考[hugo-PaperModX/config.default.yml at master · reorx/hugo-PaperModX (github.com)](https://github.com/reorx/hugo-PaperModX/blob/master/exampleSite/config.default.yml)
- Hugo vs PaperMod

## 立Flag

后续想做的：

- 增加搜索功能
- 添加评论区
- 细分到每个标签的RSS订阅链接