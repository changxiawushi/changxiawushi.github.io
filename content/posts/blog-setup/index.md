---
title: 本博搭建记录 (Hugo + GitHub Pages)
date: 2023-01-15T21:00:09-08:00
draft: false
summary: 这可不是一个技术博客呢，别误会了！
tags:
  - 记录
cover:
  image: images/work.jpg
---

搭建环境：macOS

本文记录了用GitHub Pages+Hugo搭建本博客的过程，仅供参考而非教程（搭建教程可见写得更详细解释得更好的[Hugo | 一起动手搭建个人博客吧 | 小球飞鱼 (mantyke.icu)](https://mantyke.icu/posts/2021/hugo-build-blog/)或者[更为简单的Markdown博客模版](https://go5.dev/@madstick/109667387895709907)）。

❗️ 真的不太推荐用这个方法建站，除非你已经有了搭建静态博客的经验，或者是对网页开发有一定的了解，否则真的是太多地方容易出问题了，在不理解的情况下解决问题会很辛苦。经历了全部建站过程的我表示，那些博客平台收钱还是有收钱的道理，能省好多事儿。

假如你有一定的经验又好奇搭建步骤的话，本篇或许能供你参考。想要看我对这种搭建博客的方式有什么想法可以跳到最后的[总结](#总结)。

{{< toggle "🤠一些不太重要的背景信息🤠" >}}

为什么选择Hugo+GitHub Pages呢？几年前我用过GitHub Pages+Jekyll搭建个人博客，所以算是了解搭建过程。但听说了Hugo很久，也发现了[PaperMod](https://adityatelange.github.io/hugo-PaperMod/)这个顺眼的模版，就想尝试一番。~~以及不想花钱~~

{{< /toggle >}}

---

## 注册GitHub账号

用GitHub Pages建站的话，默认网址会是`用户名.github.io`。因为暂时没打算买域名，所以纠结了好一会儿选什么用户名好。

## 建立GitHub Pages repo

![建立repo](./images/create-repo.png#center)

建立一个新的repo，名为`用户名.github.io`。注意如果GitHub账户是免费plan，这个用来设置GitHub Pages的repo一定要是public repo。

我选择用GitHub Desktop，跟着官方网页上的步骤来clone repo到本地。

[GitHub Pages | Websites for you and your projects, hosted directly from your GitHub repository. Just edit, push, and your changes are live.](https://pages.github.com/)

## 设置Hugo

根据[Quick Start | Hugo (gohugo.io)](https://gohugo.io/getting-started/quick-start/)，打开Terminal：

```bash
brew install hugo
hugo new site 用户名.github.io -f yml --force
```

1. 因为我已经有[Homebrew](https://brew.sh/)了，直接用了`brew install hugo`的方法安装。
2. 需要用刚装好的hugo将repo设置好。因为已经把clone到了本地的一个文件夹里，所以用了`--force`。`-f yml`的部分是参考了PaperMod的[指示](https://github.com/adityatelange/hugo-PaperMod/wiki/Installation)。

## 设置PaperMod Theme

决定用Hugo的PaperMod这个theme，因为感觉好看，功能看起来也比较全。跟着PaperMod的安装步骤走：[Installation · adityatelange/hugo-PaperMod Wiki (github.com)](https://github.com/adityatelange/hugo-PaperMod/wiki/Installation)

刚开始使用了Installation中的Method 1，直接git clone到repo里。但后面碰到了一些问题（详情见下面的[发布测试](#发布测试)），所以换成了使用Method 2的git submodules。

最后一步需要修改文件夹里的`config.yml`，我在Visual Studio Code中打开了整个文件夹（其实用其他plain text editor也可以，不过用VSCode可以直接在里面打开Terminal，比较方便）。把其他行也改了一下，`languageCode`先删掉了（尝试了一下，如果设置成中文会导致后续有一些不方便的地方，之后有时间再改……吧）。

```yaml
baseURL: https://用户名.github.io/
title: 长夏无事
theme: "PaperMod"
```

根据Hugo的[Quick Start](https://gohugo.io/getting-started/quick-start/)，现在已经可以用`hugo server`预览网站的样子了。现在只有我改的博客标题，旁边的图标可以在日间和夜间模式之间切换。如果修改文件夹里的文件，server都会自动检测到更新并重新build和加载本地预览，并不需要我手动刷新。nice.

![blog-initial-setup](./images/initial-blog-preview.png#center)

## 创建第一篇博文

跟着Hugo的步骤，试着创建了第一篇博文。

[Quick Start | Hugo (gohugo.io)](https://gohugo.io/getting-started/quick-start/#add-content)

```bash
hugo new posts/hello-world.md
```

所有的博文都会用Markdown文件，`hello-world`是文件的名字，也会出现在博文的链接里，即`用户名.github.io/posts/hello-word`。生成的Markdown文件上方的部分叫[Front Matter](https://gohugo.io/content-management/front-matter/)。

发现Hugo的默认本地预览不包括草稿，所以关掉了前面的server（Control+C），并输入`hugo server -D`。

就这样出现在首页啦。

![first-post-preview](./images/first-post-preview.png#center)

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

![config-update-card](./images/config-update-card.png#center)

### 添加菜单

参考[PaperMod的wiki](https://github.com/adityatelange/hugo-PaperMod/wiki/FAQs#add-menu-to-site)，在`config.yml`中添加

```yaml
# 在页面上方加入菜单
menu:
  main:
    - name: 首页
      # 回到主页
      url: /
      # 指定“首页”作为第一个出现的
      weight: 1
    - name: 标签
      url: tags/
      weight: 2
    - name: RSS订阅
      url: index.xml
      weight: 3
    - name: 友情链接
      url: friends/
      weight: 4
```
添加完就会出现在页面右上角啦。
![menu](./images/menu.png#center)
想再添加一个菜单选项放友情链接，找了一会儿没发现怎么做，于是凭借猜测创建了`content/friends.md`这个文件。这样`用户名.github.io/friends`就会显示这篇文章。
```yaml
---
title: "友情链接"
# 把日期删掉，就不会显示日期了
draft: false
# 不显示页面的阅读时间
ShowReadingTime: false
---
```

![friends](./images/friends.png#center)

RSS订阅参考了[Setting up an RSS feed for a Hugo blog using the PaperMod Theme | by Erica Pisani | Medium](https://medium.com/@ericapisani/setting-up-an-rss-feed-for-a-hugo-blog-using-the-papermod-theme-a141b3fa1ccd)。原来Hugo会自动生成RSS用的`index.xml`，非常方便。只需要在`config.yml`中添加

```yaml
outputs:
  home:
    - HTML
    - RSS
    - JSON
```

现在还没有任何标签，所以需要去博文中添加一下测试看看。

### 修改博文

#### 标签

```markdown
---
title: "Hello World"
date: 2023-01-14T16:14:48-08:00
draft: false
summary: 你好哇！
tags：
  - 测试
  - 你好
---
```

找到`posts/hello-world.md`，添加front matter，最后的tags就是标签啦，可以定义多个。这些标签会自动出现在`网站/tags`（本地预览可能会有些延迟），点击任何一个就会显示所有带此标签的文章。如果想要确认可以将server停掉，再重新开始。
![tags](./images/tags.png#center)

#### 图片

官方链接：[Page Resources | Hugo (gohugo.io)](https://gohugo.io/content-management/page-resources/)

参考demo网页带图博文的文件结构：[hugo-PaperMod/content/posts/papermod/papermod-features at exampleSite · adityatelange/hugo-PaperMod (github.com)](https://github.com/adityatelange/hugo-PaperMod/tree/exampleSite/content/posts/papermod/papermod-features)

在`content/posts`里创建一个新的文件夹`hello-world`（与原markdown文件同名），把`hello-world.md`移到新创建的`hello-word`文件夹里再改名为`index.md`，最后在`hello-world`文件夹中另创建一个`images`文件夹放图片。所以文件夹的结构变为

```
/
├── content/
│   └── posts/
│       └── hello-world/
│           └── images/
│               └── 图片.jpg
│           └── index.md
```

官方指南：[Page Bundles](https://gohugo.io/content-management/page-bundles/)

如果是一开始就想创建page bundle，可以直接使用下面的指令。不过`images`文件夹还是要自己创建。也可以用bash script优化更多步骤（[参考](https://discourse.gohugo.io/t/is-there-a-hugo-command-to-create-page-bundle/11942/2)）。
```bash
hugo new posts/<post-name>/index.md
```

> 注：在本地预览时如果图片加载不出来，可以把`config.yml`里的`baseURL`改成本地预览的链接，如`baseURL: http://localhost:1313`（[参考](https://discourse.gohugo.io/t/preview-images-with-localhost/33095)）。或者用Markdown Editor（比如Typora）查看确认就不用改设置啦。

> 再注：用Markdown语法插入图片时，记得`./images/xxx.png`或者`images/xxx.png`都可以，但如果用`/images/xxx.png`则表示`images`文件夹在根目录里，所以是不对的。

> 再再注：保险起见，我安装了[ExifTool](https://exiftool.org/)，并在上传前用它抹去图片中可能暴露个人信息的metadata（[参考](https://stackoverflow.com/questions/66192531/exiftool-how-to-remove-all-metadata-from-all-files-possible-inside-a-folder-an)）。

```bash
brew install exiftool
# 抹去metdata后直接覆盖原图片
exiftool -a -all:all= -r path/to/images -overwrite_original
```

## 发布测试

现在可以把本地的文件都push到GitHub，看一下网站的效果啦。

### 启用GitHub Pages

在GitHub repo的Settings > Pages 里可以启用该repo的GitHub Pages。Deploy branch我选择的是`gh-pages`，原因是Hugo提供的action会把处理后的文件push到这个branch。

### 设置GitHub Action

Hugo的[教程](https://gohugo.io/hosting-and-deployment/hosting-on-github/)里就有一个action的例子，我直接复制了过来。

创建GitHub Action的时候，因为不熟悉碰到了好多问题。首先是看不到action有在跑，然后发现是把文件放错了位置，一定要放在`.github/workflows/`这个文件夹里面才可以。放对了位置以后push能看到action在跑，但碰到了另一个error message。

```bash
hugo --minify
  shell: /usr/bin/bash -e {0}
Error: module "PaperMod" not found; either add it as a Hugo Module or store it in "/home/runner/work/changxiawushi.github.io/changxiawushi.github.io/themes".: module does not exist
Total in 0 ms
Error: Process completed with exit code 255.
```

试了一些网上的建议无果以后，随机发现一个使用Hugo和PaperMod主题的站里有[`.gitmodules`](https://github.com/mzfr/mzfr.github.io/blob/f02722a1499b155816d1cc15d81a74af6864c0c6/.gitmodules)这个文件。随即开始尝试把PaperMod用git submodule的方式安装。

这次不再有前面的错误信息。但是！又碰到了新的问题……

```bash
/usr/bin/git push origin gh-pages
  remote: Permission to changxiawushi/changxiawushi.github.io.git denied to github-actions[bot].
  fatal: unable to access 'https://github.com/changxiawushi/changxiawushi.github.io.git/': The requested URL returned error: 403
  Error: Action failed with "The process '/usr/bin/git' failed with exit code 128"
```

经过了漫长的搜索，我终于找到了答案。原来我用的action文件里没有给正确的permission，导致这个action无法push代码。解决方法是在action的文件里加入：

```yaml
permissions:
  contents: write
  pages: write
  id-token: write
```

终于看到了执行成功的action，感人！

![action-success](./images/action-success.png#center)

### 查看网页

GitHub Pages也通过一个action（`pages-build-deployment`）来部署网页。一旦看到这个action也成功执行，就可以到`https://用户名.github.io`看看效果了。

我在手机上打开了网页，并复制了RSS订阅链接，确保可以在RSS阅读器上看到内容。

## 一些其他功能

- {{< toggle "可展开缩起的toggle" >}}

参考了[这个回答](https://discourse.gohugo.io/t/unable-to-use-collapsible-expand-markdown/32810/2)，在`layouts/shortcodes/`中建立一个文件`toggle.html`并粘贴了回答中的代码。
{{< /toggle >}}

- 图片居中，参考[PaperMod的wiki](https://github.com/adityatelange/hugo-PaperMod/wiki/FAQs#centering-image-in-markdown)，只要在图片名后面加上`#center`就可以
- 在Markdown中插入HTML代码，参考[Simple Shortcode to Insert Raw HTML in Hugo · Ana Ulin](https://anaulin.org/blog/hugo-raw-html-shortcode/)
- 更改网页图标，根据[PaperMod的教程](https://adityatelange.github.io/hugo-PaperMod/posts/papermod/papermod-faq/#adding-custom-favicons)尝试了一些图，再用[Favicon.io](https://favicon.io/)生成图片后直接复制到`static`文件夹中。打开浏览器的DevTools，再右键刷新图标选择"Empty cache and hard refresh"就能看到了
  ![hard-refresh](./images/hard-refresh.png#center)

## 一些困难

- 默认语言是英文，我没有改，但其实应该改为中文？没有细查多语言设置，之后或许可参考
  - [hugo-PaperModX/config.default.yml at master · reorx/hugo-PaperModX (github.com)](https://github.com/reorx/hugo-PaperModX/blob/master/exampleSite/config.default.yml)
  - [I18n Tutorial: How to Go Multilingual with Hugo | Phrase](https://phrase.com/blog/posts/i18n-tutorial-how-to-go-multilingual-with-hugo/)
- Hugo vs PaperMod，我总是疑惑信息应该在Hugo的官方文档寻找，还是找PaperMod的

## 立Flag

后续想做的：

- 增加搜索功能（放在菜单栏）
- 添加评论区
- 找一下怎么加citation/reference（[例子](https://kpwn.de/2021/09/how-to-set-up-this-blog/#fn:1)，找到的一个[回答](https://discourse.gohugo.io/t/cite-within-a-post/27172/2)用不了）
- 学习一下shortcode
  - [官方链接](https://gohugo.io/content-management/shortcodes/)

## 总结

搭建下来我感觉，用这个方法的好处是

- 不要钱 😅
- 可供折腾的空间比较大

但缺点是

- 初始搭建比较费时，可能会碰到各种各样的问题
- 后续也需要用Markdown写作，某些功能（比如toggle）甚至需要找/写代码

但总算是搭下来啦！一定要多写文才能对得起投进去的时间了。

感谢阅读，有缘再见。