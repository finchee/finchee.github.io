# 使用指南

## markdown 编译部署到 github pages

[MkDocs（Windows 上安装并使用）](https://lyh-man.github.io/MyDocs/tool/mk-docs/#5mkdocs-material)

## gh-deploy 命令推送到 github 自定义域名失效的解决办法

[部署文档](https://hellowac.github.io/mkdocs-docs-zh/user-guide/deploying-your-docs/#_1)

## mkdocs 支持无序列表嵌套的方法

安装 mdx_truly_sane_lists

    pip install mdx_truly_sane_lists

在 mkdoc.yml 中添加

    markdown_extensions:
        - mdx_truly_sane_lists

## mkdocs 支持 mermaid 图表功能

参考 [Markdown 的项目文档](https://wdk-docs.github.io/mkdocs-docs/) `插件`中的`图像，表格，图表和图形`

安装 mkdocs-mermaid2-plugin

    pip install mkdocs-mermaid2-plugin

在 mkdoc.yml 中添加

    plugins:
        - search
        - mermaid2
