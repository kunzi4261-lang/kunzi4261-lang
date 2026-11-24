# 你好，我是 kunzi4261-lang

仓库里的一张截图改了名，哪几篇文档要跟着改？我做了 **mdpath** 来回答这个问题。它用 Python 标准库检查 Markdown 里的本地链接，把失效引用定位到具体的一行。[打开 mdpath ↗](https://github.com/kunzi4261-lang/mdpath)

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
