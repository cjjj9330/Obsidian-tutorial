---
publish: true
---

# 编辑日期

<span class="related-pages">#feature/dates</span>

## 概述

Tasks支持一系列日期属性来管理您的任务：请参阅[[Dates|日期]]。

本页面描述了在任务上添加、编辑和删除日期值的方法。

有一个[[#Date-picker on task dates|任务日期的日期选择器]]和一个[[#Context menu on task dates|任务日期的上下文菜单]]，或者您可以使用各种[[#other date-editing options|其他日期编辑选项]]。

## 任务日期的日期选择器

> [!released]
> 在Tasks 7.14.0中引入。

在**阅读模式**和**Tasks查询搜索结果**中**左键点击任何任务日期字段**，使用日期选择器和日历来编辑或删除日期。

![Hover over a date in Read mode or Tasks query search results](../images/date-picker-1.png)
<span class="caption">在阅读模式或Tasks查询搜索结果中悬停在日期上</span>

![In the date-picker, you can easily select a new date, or clear the current one](../images/date-picker-2.png)
<span class="caption">在日期选择器中，您可以轻松选择新日期或清除当前日期</span>

| 位置                         | 查看模式 | 是否有效? |
| ----------------------------- | ------------ | ------ |
| markdown文件中的任务行  | 源码模式  | ❌     |
| markdown文件中的任务行  | 实时预览 | ❌     |
| markdown文件中的任务行  | 阅读模式 | ✅     |
| Tasks查询搜索结果中 | 实时预览 | ✅     |
| Tasks查询搜索结果中 | 阅读模式 | ✅     |

在iPhone上，可能iPad也是如此，此日期选择器将一周的开始硬编码为星期一，而不是遵循用户的设置。我们在[issue #3239](https://github.com/obsidian-tasks-group/obsidian-tasks/issues/3239)中跟踪此问题。

## 任务日期的上下文菜单

> [!released]
> 在Tasks 7.10.0中引入。

在**阅读模式**和**Tasks查询搜索结果**中**右键点击任何任务日期字段**来：

- 推迟开始、计划和截止日期
- 提前创建、取消和完成日期

![Hover over a date in Read mode or Tasks query search results](../images/date-context-menu-1.png)
<span class="caption">在阅读模式或Tasks查询搜索结果中悬停在日期上</span>

![Chose an option from the context menu](../images/date-context-menu-2.png)
<span class="caption">从上下文菜单中选择一个选项</span>

| 位置                         | 查看模式 | 是否有效? |
| ----------------------------- | ------------ | ------ |
| markdown文件中的任务行  | 源码模式  | ❌     |
| markdown文件中的任务行  | 实时预览 | ❌     |
| markdown文件中的任务行  | 阅读模式 | ✅     |
| Tasks查询搜索结果中 | 实时预览 | ✅     |
| Tasks查询搜索结果中 | 阅读模式 | ✅     |

## 其他日期编辑选项

在**编辑模式**（源码模式和实时预览）中，选项包括：

- 自己输入日期。
- 使用[[Auto-Suggest|自动建议]]添加表情符号和一系列便捷日期。
- 使用`Create or edit Task`命令访问[[Create or edit Task|创建或编辑任务]]模态框/对话框。

在**阅读模式**和**Tasks查询搜索结果**中，选项包括：

- 点击或右键点击⏩使用[[Postponing|推迟]]按钮。
- 点击铅笔图标(📝)使用[[Create or edit Task|创建或编辑任务]]模态框/对话框。
