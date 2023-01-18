---
title: Heading link example
date: 2023-01-18
publishdate: 2023-01-18
type: render-heading-example
---

<!-- markdownlint-disable-next-line MD025 -->
# Heading link example

## 目录

- [Heading link example](#heading-link-example)
    - [目录](#目录)
    - [简介](#简介)
    - [相关文件](#相关文件)
    - [内容](#内容)
        - [`/content/posts/render/heading/example.md`](#contentpostsrenderheadingexamplemd)
    - [模板](#模板)
        - [`/layouts/render-heading-example/_markup/render-heading.html`](#layoutsrender-heading-example_markuprender-headinghtml)

## 简介

本例为`Hugo`自定义`Heading`模板，仓库在

<https://github.com/huzhenghui/Hugo-Bootstrap-Templates>

效果参见

<https://huzhenghui.github.io/Hugo-Bootstrap-Templates/posts/render/heading/example/>

本文发表在

<https://blog.csdn.net/hu_zhenghui/article/details/128727127>

## 相关文件

```text
./
├── content/
│   └── posts/
│       └── render/
│           └── heading/
│               └── example.md
└── layouts/
    └── render-heading-example/
        └── _markup/
            └── render-heading.html
```

## 内容

### `/content/posts/render/heading/example.md`

本文件，位置在<https://github.com/huzhenghui/Hugo-Bootstrap-Templates/blob/master/content/posts/render/heading/example.md>

Since [v0.3](https://github.com/huzhenghui/Hugo-Bootstrap-Templates/tree/v0.3)

<https://github.com/huzhenghui/Hugo-Bootstrap-Templates/blob/v0.3/content/posts/render/heading/example.md>

在`front matter`中设置`type`属性

```markdown
---
title: Heading link example
date: 2023-01-18
publishdate: 2023-01-18
type: render-heading-example
---
```

`type`属性值为`render-heading-example`，表示优先使用`/layouts/render-heading-example/`中的模板，因此渲染时，在渲染`Markdown`的标题时，将使用
[`/layouts/render-heading-example/_markup/render-heading.html`](#layoutsrender-heading-example_markuprender-headinghtml)

效果为

```html
<h1 id="heading-link-example">
    Heading link example
    <a href="#heading-link-example">¶</a>
</h1>
```

## 模板

### `/layouts/render-heading-example/_markup/render-heading.html`

自定义`Heading`链接模板，位置在<https://github.com/huzhenghui/Hugo-Bootstrap-Templates/blob/master/layouts/render-heading-example/_markup/render-heading.html>

Since [v0.3](https://github.com/huzhenghui/Hugo-Bootstrap-Templates/tree/v0.3)

<https://github.com/huzhenghui/Hugo-Bootstrap-Templates/blob/v0.3/layouts/render-heading-example/_markup/render-heading.html>

```html
<h{{ .Level }} id="{{ .Anchor | safeURL }}">
    {{ .Text | safeHTML }}
    <a href="#{{ .Anchor | safeURL }}">¶</a>
</h{{ .Level }}>
```
