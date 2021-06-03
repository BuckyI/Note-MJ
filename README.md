# README

## 文件来源

这个文档是「马克思主义基本原理概论」的课堂笔记.
最初在 OneNote 上，后来给搬成 Markdown 文件.
为了还原之前良好的字体排版，用到了 css(less) 文件.
![alt](assets/README/2021-05-20-17-41-22.png)

```CSS
// 字体格式设置
.i_emm{ // 页码，或其他最重要的强调
  color: rgb(180,53,18);
}
.i_em{ // 强调
  // 为了方便，使用 **text** 实现
  color: rgb(232,76,34);
}
.i_explain{ // 解释说明
  // 为了方便，使用 *text* 实现
  color: rgb(204,193,217);
}
.i_exp{ // 其他解释
  color: rgb(112,173,71);
}
.i_method{  // 方法论
  color: rgb(131,60,11);
}
```

## 实现方式

### MPE

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

### vscode

MPE 的方法的话，会受到自己设置的其他 MPE 格式的干扰. 并且 css 需要改成 less. 后来发现使用 vscode 工作区设置可以直接指定 css.

### pandoc

如果要分享给别人，可以使用 pandoc 进行转换.

```shell
pandoc test.md -s --self-contained -c style.css -o test.html -f gfm
```
