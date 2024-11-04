---
title: Pygments
date: 2024-01-24 12:15:55
tags:
- Python
categories:
- Python
---


## Pygments 代码高亮

Pygments是一个基于python的代码语法高亮库。

Pygments由四个组件实现代码的语法高亮:
- Lexer（词法分析器） Lexer把代码分割为token。token是具有类型的代码片段，可以决定文本的语义表示（例如，关键字，字符串或注释）。每一种语言或者文本标记格式，Pygments都有相应的Lexer。
- Filter（过滤器） token可以以流的形式通过Filter管道。Filter通常用来修改token类型或者文本，例如大写所有关键字。
- Formatter（格式器） 然后，Formatter把token流以HTML、LaTeX或这RTF的格式输出到文件。
- Style（样式） 在token流输出时，style决定了怎样高亮所有不同的token类型。它把token类型和属性关联起来，如设置字体为红色并加粗

```
from pygments import highlight
from pygments.lexers import PythonLexer
from pygments.formatters import HtmlFormatter

code = 'print "Hello World"'
print(highlight(code, lexer=PythonLexer(), formatter=HtmlFormatter()))

```

print
```
<div class="highlight">
<pre><span class="k">print</span> <span class="s">&quot;Hello World&quot;</span></pre>
</div>
```

- highlight->用于生成格式化之后的代码，生成的格式由后面的formatter决定
- lexer->译做词法分析程序，用于判断当前输入的代码属于哪种编程语言（C、C++、Python、Java等）
- formatter->格式化选项，这里是格式化为html代码，也可以格式化为.png、.jpg格式的图片等