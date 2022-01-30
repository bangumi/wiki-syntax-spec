# Bangumi 现有的 wiki 语法的规范

仓库状态: pre-alpha

bangumi 现有的需要进行语法解析的有前端和后端两部分，各个语言应当对相同的内容解析出相同的结果。

1. wiki 文本可以使用 `\n` 或者 `\r\n` 作为换行符。
2. 最多包含两层信息。
3. wiki 应当以`{{Infobox` 开始，以`}}`结束，空文本和 `{{Infobox\n}}` 具有相同的含义。

...

本仓库包含了一系列的测试用例。用于帮助各个解析器能解析出相同的结果。
