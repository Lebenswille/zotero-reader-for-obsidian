# Zotero Reader for Obsidian

一个在 Obsidian 中阅读和标注 PDF / EPUB / HTML 的插件。

这个项目基于 [duanxianpi/obsidian-zotero-reader-plugin](https://github.com/duanxianpi/obsidian-zotero-reader-plugin) 修改而来。原项目已经不再继续维护，我在此基础上修复了标注存储过于脆弱的问题，把标注相关元数据从笔记正文中拆出来独立保存，并补了一些同步与细节修正。

## 安装

手动安装：

1. 下载本仓库内容。
2. 放入你的 Obsidian 仓库目录：
   `.obsidian/plugins/zotero-reader-for-obsidian`
3. 重新加载 Obsidian，并启用本插件。

## 基本使用

这个插件不是直接对 PDF / EPUB / HTML 文件本身操作，而是通过一个 Markdown 笔记作为入口。这个笔记需要在 frontmatter 中提供 `source` 字段。

最简单的例子：

```md
---
source: Papers/MyPaper.pdf
---
```

`source` 可以是：

- Vault 内文件路径
- Wikilink
- Markdown 链接
- `http://` 或 `https://` URL

使用流程：

1. 新建一个 Markdown 笔记。
2. 在 frontmatter 中填写 `source`。
3. 打开这个笔记，并用插件的按钮进入 Reader。
4. 在 Reader 中阅读、标注。
5. 标注内容会写回笔记，并带有可跳回 Reader 的链接。

## 当前版本的特点

- 标注正文会写回笔记，方便阅读和整理。
- 标注元数据与阅读状态独立保存，不再强依赖笔记正文格式。
- 删除笔记中的标注 callout 时，对应标注会同步清理。
- 点击笔记中的标注链接，可以回到对应阅读位置。

## 注意

- `source` 是识别 Reader Note 的关键字段，不要删除。
- 你可以自由编辑自己的笔记正文。
- 如果删除标注对应的 callout / 链接，插件会把对应标注视为已移除。

## 致谢

感谢原作者 [duanxianpi](https://github.com/duanxianpi) 提供项目基础。
