---
publish: true
---

# 标签

## 什么是标签？

Obsidian [标签文档](https://help.obsidian.md/Editing+and+formatting/Tags)说：

> [!Quote]
> 标签是帮助您快速找到所需笔记的关键词或主题。<br>
> 要创建标签，请在编辑器中输入井号符号（#），然后输入关键词。例如，`#meeting`。

## 为什么使用标签？

标签的选择当然是个人决定。

但这里有一些可能与Tasks结合使用的有用标签示例：

- 对于[Getting Things Done/GTD](https://en.wikipedia.org/wiki/Getting_Things_Done)概念，例如上下文：
  - `#context/work`、`#context/home/ground-floor`
- 在一天开始和结束时要做的事情
  - `#when/morning`、`#when/evening`
- 分类：
  - `#🏢/companyA`

## Tasks和您的任务行

### 简单情况

如果您将标签保持为井号符号（`#`）后跟以下任何字符，您可以忽略下面[[#识别标签]]部分的详细信息。

- 字母
- 下划线（`_`）
- 连字符（`-`）
- 正斜杠（`/`）

### 识别标签

Obsidian和Tasks在识别标签方面有一些重要差异。

> [!Info]
> 我们在[issue #929](https://github.com/obsidian-tasks-group/obsidian-tasks/issues/929)中跟踪这些差异。<br>
> 目前尚未决定Tasks中的标签识别是否会被修改以与Obsidian更一致。

| 情况                                  | Obsidian                                                                                                                                                                                                                                                                                                                                                                              | Tasks插件                                                                                                                |
|------------------------------------| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 标签中允许的字符                 | <p>请参阅Obsidian的[标签格式](https://help.obsidian.md/Editing+and+formatting/Tags#Tag+format)</p><ul><li>字母</li><li>数字</li><li>下划线（`_`）</li><li>连字符（`-`）</li><li>正斜杠（`/`）用于[嵌套标签](https://help.obsidian.md/Editing+and+formatting/Tags#Nested+tags)</li></ul><p>标签必须包含至少一个非数字字符。</p> | <p>除以下字符外的任何字符</p><ul><li><tt>空格</tt></li><li><tt>!@#$%^&*(),.?":{}\|&lt;&gt;</tt></li></ul> |
| 纯数字标签                           | 标签必须包含至少一个非数字字符。<br>所以`#1234`**不**被识别为标签。                                                                                                                                                                                                                                                                                                                    | 对全数字标签没有限制。<br>所以`#1234`**被**识别为标签。                                                 |
| 看起来像浮点数的标签 | 标签必须包含至少一个非数字字符。<br>所以`#12.34`**不**被识别为标签。                                                                                                                                                                                                                                                                                                                   | 对全数字标签没有限制，但标签中不允许`.`。<br>所以`#12.34`被视为标签`#12`。                 |
| `%%`注释中的类标签文本             | 忽略                                                                                                                                                                                                                                                                                                                                                                               | 识别                                                                                                                  |
| `<!-- .... -->`注释中的类标签文本 | 忽略                                                                                                                                                                                                                                                                                                                                                                               | 识别                                                                                                                  |

### 在YAML、Frontmatter或文件属性中使用标签

Obsidian允许在笔记开头添加[属性](https://help.obsidian.md/Editing+and+formatting/Properties)。

这些属性也被称为Frontmatter或YAML。

这里是一个使用标签的示例：

```text
---
tags:
 - 🏷/some_tag
 - 🏢/companyA
---
```

从Tasks 7.7.0开始，Tasks**现在**读取这些数据。

您可以在以下位置了解更多信息：

- [[Obsidian Properties]]，以及该文件中的示例
- [在具有特定标签的笔记中查找任务](https://github.com/obsidian-tasks-group/obsidian-tasks/blob/main/resources/sample_vaults/Tasks-Demo/How%20To/Find%20tasks%20in%20notes%20with%20particular%20tag.md)。

### 任务行中标签的顺序

- 标签可以在任务的任何位置以任何顺序出现。
  - 它们可以与您的标识符（截止日期、优先级等）混合。
  - 请参阅[[Auto-Suggest#What do I need to know about the order of items in a task?|我需要了解任务中项目顺序的什么？]]
- 但是，当Tasks编辑行时（例如，通过[[Create or edit Task|'Create or edit Task' Modal]]，或当任务完成时），标签可能会被移动。

## 限制

- [[Create or edit Task|'Create or edit Task' Modal]]中的描述字段在您输入标签时不提供任何帮助完成。
  - 我们在[discussion #229](https://github.com/obsidian-tasks-group/obsidian-tasks/discussions/229)中跟踪此问题。
- 如果您使用标签作为全局过滤器，请不要在搜索中包含它。
- Tasks不从文件Frontmatter/YAML/属性中读取标签（或任何其他信息）：标签值仅从任务行中读取
  - 我们在[discussion #232](https://github.com/obsidian-tasks-group/obsidian-tasks/discussions/232)中跟踪此问题。
  - 请参阅上面的[[Tags#Using tags in YAML, Frontmatter or file Properties|在YAML、Frontmatter或文件属性中使用标签]]了解dataview辅助的解决方法。

## 标签和全局过滤器

> [!Warning]
> 如果启用了[[Global Filter|全局过滤器]]，并且是一个标签，**请不要在您的Tasks搜索中使用该全局过滤器标签**。
> 全局过滤器标签在读取任务行时被删除，因此您不会得到预期的结果。

## 相关任务块指令

以下指令使用任务行上的任何标签。

- `no tags`
- `has tags`
- `tags (include|do not include) <tag>` _或_
- `tag (includes|does not include) <tag>`
- `tags (regex matches|regex does not match) /<JavaScript-style Regex>/` _或_
- `tag (regex matches|regex does not match) /<JavaScript-style Regex>/`
  - [[Filters#Tags|文档]]
- `sort by tag`
- `sort by tag 2`
  - [[Sorting#Tags|文档]]
- `group by tags`
  - [[Grouping#Tags|文档]]
- `hide tags`
  - [[Layout|文档]]
- 可作为自定义过滤器和组中的`task.tags`访问
  - [[Task Properties#Values for Other Task Properties|文档]]
