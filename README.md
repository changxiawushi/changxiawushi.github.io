# 长夏无事
一个博客。搭建见 https://changxiawushi.github.io/posts/blog-setup/

## Hugo Shortcodes

`/layouts/shortcodes/`

### Toggle
来自 https://discourse.gohugo.io/t/unable-to-use-collapsible-expand-markdown/32810/2
```
{{< toggle "可展开" >}}

*啥也没有哦*

{{< /toggle >}}
```

<details>
  <summary>可展开</summary>
    <i>啥也没有哦</i>
</details>

### 下划线
参考 https://codingnconcepts.com/hugo/custom-shortcode-hugo/#strike
```
{{< u "重要！" >}}
```
<u>重要！</u>