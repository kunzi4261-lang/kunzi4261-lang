# 你好，我是 kunzi4261-lang

## 口袋实验室 · Pocket Lab

给港口起个名字，看看它入夜的样子；再给这幅画编一小节鼓点。两个浏览器实验都能分享，也能把自己做的图和声音导出来。

[![口袋实验室的试玩界面：黄昏的像素港湾与十六步节奏预览。](https://raw.githubusercontent.com/kunzi4261-lang/pocket-lab/main/docs/preview.png)](https://kunzi4261-lang.github.io/pocket-lab/)

[画一座像素港湾](https://kunzi4261-lang.github.io/pocket-lab/city/) · [编一段鼓点](https://kunzi4261-lang.github.io/pocket-lab/beat/) · [看实现](https://github.com/kunzi4261-lang/pocket-lab)

## mdpath · Markdown 链接检查器

仓库里的一张截图改了名，哪几篇文档要跟着改？我做了 **mdpath** 来回答这个问题。它用 Python 标准库检查 Markdown 里的本地链接，把失效引用定位到具体的一行。

[![打开 mdpath 项目。图中示例将丢失的图片定位到 README.md 第 3 行。](assets/mdpath.png)](https://github.com/kunzi4261-lang/mdpath)

### 一行 Markdown，要检查几张图？

假设 `notes.md` 的第一行这样写，两张图都没有放进仓库。

```markdown
语法示例：`![占位图](sample.png)`。实验结果：![曲线](result.png)。
```

反引号里的写法会原样显示，只有实验曲线需要加载图片。运行 mdpath，诊断指向这一处。

```text
notes.md:1: missing: result.png
```

解析器还要处理成组的反引号和路径里嵌套的括号。我把这些容易漏掉的写法都放进了测试。[读解析器](https://github.com/kunzi4261-lang/mdpath/blob/main/mdlinks.py) · [看边界用例](https://github.com/kunzi4261-lang/mdpath/blob/main/tests/test_mdlinks.py) · [看跨平台测试记录](https://github.com/kunzi4261-lang/mdpath/actions/workflows/check.yml)
