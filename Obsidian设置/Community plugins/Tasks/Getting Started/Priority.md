---
publish: true
---

# 优先级

## 优先级和顺序

任务可以有优先级。
为了指定任务的优先级，您可以附加以下"优先级标识符"之一，这里按优先级递减顺序显示：

1. 🔺 表示最高优先级
2. ⏫ 表示高优先级
3. 🔼 表示中等优先级
4. 不使用标识符表示无优先级
5. 🔽 表示低优先级
6. ⏬️ 表示最低优先级

如果任务完全没有优先级，则被认为介于低优先级和中等优先级之间。
这意味着🔽低优先级任务的优先级被认为低于没有任何特定优先级的任务的优先级。
这个想法是您可以轻松过滤掉不重要的任务，而无需为所有相关任务分配优先级。

```markdown
- [ ] 倒垃圾 🔼
```

> [!released]
> 优先级'最低'和'最高'在Tasks 3.9.0中引入。

## 轻松添加优先级

您可以不手动添加表情符号，而是：

- 在创建或编辑任务时使用`Tasks: Create or edit`命令。
  您将能够从[[Create or edit Task|'Create or edit Task' Modal]]中的选项中选择优先级。
- 使用[[Auto-Suggest|智能自动建议]]，
  开始输入`high`、`medium`或`low`的前几个字符，然后按`<return>`接受建议的标识符。

## 相关任务块指令

以下指令在任务中使用优先级标识符。

- `priority is (above, below)? (lowest, low, none, medium, high, highest)`
  - [[Filters#Priority|文档]]
- `sort by priority`
  - [[Sorting#Priority|文档]]
- `group by priority`
  - [[Grouping#Priority|文档]]
- `hide priority`
  - [[Layout|文档]]

- 可作为[[Task Properties#Values for Other Task Properties|任务属性]]访问：
  - `task.priorityNumber`
  - `task.priorityName`
  - `task.priorityNameGroupText`
