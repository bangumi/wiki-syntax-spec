# Bangumi 现有的 wiki 语法的规范

仓库状态: pre-alpha

bangumi 现有的需要进行语法解析的有前端和后端两部分，各个语言应当对相同的内容解析出相同的结果。

1. wiki 文本**可以**使用 `\n` 或者 `\r\n` 作为换行符。
2. wiki **应该**以`{{Infobox` 开始，以`}}`结束，空文本和 `{{Infobox\n}}` 具有相同的含义。
3. 每一个 wiki 最多具有一个类型，于`{{Infobox`位于同一行。型如`{{Infobox Type`，类型仅能包含`[a-zA-Z]` 和 `/`。类型**可以**省略。
4. wiki **可以**包含多个字段，每个字段**必需**使用`=`分割字段名和字段值。（一行中如果出现多个 `=` 应该如何处理？）
5. 字段值**可以**是字符串或者列表，默认为空字符串。
   1. 列表**必需**以`{`开始，以`}`结束。`=`和`{`之间**不应该**包含换行符。
   2. `{`，`}`和列表元素都**必需**独立成行。
   3. 所有的列表元素都应该以被包在`[]`中。（元素值有`[`或者`]`怎么办？）
   4. 列表的元素可以是没有名称`[value]`的简单元素，或者`[name|value]`的复杂元素，不能嵌套。（name 或者 value 包含`|`怎么办？）
   5. 空行应该被忽略。

...

本仓库包含了一系列的测试用例。用于帮助各个解析器能解析出相同的结果。
