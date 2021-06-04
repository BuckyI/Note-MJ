# README

## 文件来源与格式设定

这个文档是「马克思主义基本原理概论」的课堂笔记.
最初在 OneNote 上，后来给搬成 Markdown 文件.
为了还原之前良好的字体排版，用到了 css(less) 文件（具体格式设定可以看`style.css`).
![alt](assets/README/2021-05-20-17-41-22.png)

由于颜色太多没有完全还原。
并且，由于 markdown 语法并不统一，尽量使用了最基本的语法. 有一些之前是表格的样式转换成了列表.
并且由于（文件间）链接用起来不是很稳定，改为使用脚注的方式说明参考地方.

## 实现方式

### 通过 MPE 修改样式（废除）

最刚开始使用 MPE 的自定义 css 的方法.
每个文件都有两行：

```HTML
<!-- @import "newsprint.less" -->
<!-- @import "style.less" -->
```

第一行是设立一个基本样式，为了尽可能屏蔽其他地方的样式。
第二行是自定义样式。
> 其实也可以使用`<!-- @import "reset.less" -->`, 但是我 `2021.05.20` 目前不会用，因为它会把所有的样式都屏蔽掉，而全部都设置一遍工作量太大了.

所以目前就是根据基本样式进行修改。
也可以合并到一块，但分开可以看清楚最核心的格式要求（都在`style.less`里）.

使用 vscode 中的 MPE 插件可以查看正确的样式.

### 基于自定义 css

#### vscode

MPE 的方法的话，会受到自己设置的其他 MPE 格式的干扰. 并且 css 需要改成 less. 后来发现使用 vscode 工作区设置可以直接指定 css.

#### pandoc

如果要分享给别人，可以使用 pandoc 进行转换.

```shell
pandoc test.md -s --self-contained -c style.css -o test.html -f gfm
```
