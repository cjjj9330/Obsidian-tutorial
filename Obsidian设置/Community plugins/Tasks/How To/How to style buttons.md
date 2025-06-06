---
publish: true
---

# 如何设置任务按钮样式

<span class="related-pages">#css</span>

## 动机和假设

在Tasks结果中，默认情况下每个任务都显示两个按钮 &ndash;
一个用于[[Create or edit Task|编辑]]任务，一个用于[[Postponing|推迟]]任务，使用相应的图标。
在当前版本的Tasks中，它们看起来是这样的：

![Task buttons with default style](../images/tasks-buttons-default.png)

至少在Windows 11上是这样的 -
图标在不同平台上可能会略有不同。

如果您不喜欢这些图标的外观，本指南展示了如何修改它们的外观。

我们假设您知道如何[在Obsidian中使用CSS片段](https://help.obsidian.md/How+to/Add+custom+styles#Use+Themes+and+or+CSS+snippets)。

## 单色按钮

如您所见，默认按钮是彩色的，有些人可能会觉得分散注意力。如果您更喜欢单色按钮，您可以通过[此CSS片段](https://github.com/obsidian-tasks-group/obsidian-tasks/blob/main/resources/sample_vaults/Tasks-Demo/.obsidian/snippets/tasks-buttons-gray.css)简单地将按钮转换为灰度：

<!-- snippet: resources/sample_vaults/Tasks-Demo/.obsidian/snippets/tasks-buttons-gray.css -->
```css
.tasks-edit, .tasks-postpone {
    filter: grayscale(100%);
}
```
<!-- endSnippet -->

这给我们这个结果：

![Task buttons with gray style](../images/tasks-buttons-gray.png)

或者您可以使用替代字符，它们默认是单色的，如[此CSS片段](https://github.com/obsidian-tasks-group/obsidian-tasks/blob/main/resources/sample_vaults/Tasks-Demo/.obsidian/snippets/tasks-buttons-alt.css)：

<!-- snippet: resources/sample_vaults/Tasks-Demo/.obsidian/snippets/tasks-buttons-alt.css -->
```css
.tasks-edit::after {
    content: '\1f589';
}

.tasks-postpone::after {
    content: '\2bee';
}
```
<!-- endSnippet -->

这看起来是这样的：

![Task buttons with alt characters](../images/tasks-buttons-alt.png)

请注意，这里使用的Unicode字符来自Unicode版本7和8，
可能在所有平台上还不受支持。如果您想支持更多平台，
您应该选择更广泛可用的Unicode 6中的字符。

## 更多样式，请

如果您想让按钮看起来更像真正的按钮并给它们一些颜色，这也是可能的，如[此CSS片段](https://github.com/obsidian-tasks-group/obsidian-tasks/blob/main/resources/sample_vaults/Tasks-Demo/.obsidian/snippets/tasks-buttons-stylish.css)：

<!-- snippet: resources/sample_vaults/Tasks-Demo/.obsidian/snippets/tasks-buttons-stylish.css -->
```css
.tasks-edit::after {
    content: '\1f58b';
}

.tasks-postpone::after {
    content: '\1f4a4';
}

.tasks-edit, .tasks-postpone {
    background: linear-gradient(to bottom, #ffda89, #ffa07a);
    padding: 2px 5px;
    border-radius: var(--radius-s);
    box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}
```
<!-- endSnippet -->

此示例片段产生以下样式：

![Task buttons with more style](../images/tasks-buttons-stylish.png)

## 回到根源

本节展示如何重现Tasks 6.0.0之前编辑按钮的外观。

您也可以使用自己的图形而不是现有的Unicode字符，如[此示例CSS片段](https://github.com/obsidian-tasks-group/obsidian-tasks/blob/main/resources/sample_vaults/Tasks-Demo/.obsidian/snippets/tasks-buttons-svg.css)：

<!-- snippet: resources/sample_vaults/Tasks-Demo/.obsidian/snippets/tasks-buttons-svg.css -->
```css
.tasks-edit, .tasks-postpone {
    background-color: var(--text-faint);
    -webkit-mask-size: contain;
    margin-left: .66em;
    display: inline-block;
}

.tasks-edit {
    -webkit-mask-image: url("data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20xmlns%3Axlink%3D%22http%3A%2F%2Fwww.w3.org%2F1999%2Fxlink%22%20aria-hidden%3D%22true%22%20focusable%3D%22false%22%20width%3D%221em%22%20height%3D%221em%22%20style%3D%22-ms-transform%3A%20rotate(360deg)%3B%20-webkit-transform%3A%20rotate(360deg)%3B%20transform%3A%20rotate(360deg)%3B%22%20preserveAspectRatio%3D%22xMidYMid%20meet%22%20viewBox%3D%220%200%201536%201536%22%3E%3Cpath%20d%3D%22M363%201408l91-91l-235-235l-91%2091v107h128v128h107zm523-928q0-22-22-22q-10%200-17%207l-542%20542q-7%207-7%2017q0%2022%2022%2022q10%200%2017-7l542-542q7-7%207-17zm-54-192l416%20416l-832%20832H0v-416zm683%2096q0%2053-37%2090l-166%20166l-416-416l166-165q36-38%2090-38q53%200%2091%2038l235%20234q37%2039%2037%2091z%22%20fill%3D%22%23626262%22%2F%3E%3C%2Fsvg%3E");
}

.tasks-postpone {
    -webkit-mask-image: url("data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20xmlns%3Axlink%3D%22http%3A%2F%2Fwww.w3.org%2F1999%2Fxlink%22%20aria-hidden%3D%22true%22%20focusable%3D%22false%22%20width%3D%221em%22%20height%3D%221em%22%20style%3D%22-ms-transform%3A%20rotate%28360deg%29%3B%20-webkit-transform%3A%20rotate%28360deg%29%3B%20transform%3A%20rotate%28360deg%29%3B%22%20preserveAspectRatio%3D%22xMidYMid%20meet%22%20viewBox%3D%220%200%201536%201536%22%3E%3Cpath%20d%3D%22M45%20-115q-19%20-19%20-32%20-13t-13%2032v1472q0%2026%2013%2032t32%20-13l710%20-710q9%20-9%2013%20-19v710q0%2026%2013%2032t32%20-13l710%20-710q9%20-9%2013%20-19v678q0%2026%2019%2045t45%2019h128q26%200%2045%20-19t19%20-45v-1408q0%20-26%20-19%20-45t-45%20-19h-128q-26%200%20-45%2019t-19%2045v678q-4%20-10%20-13%20-19l-710%20-710%20q-19%20-19%20-32%20-13t-13%2032v710q-4%20-10%20-13%20-19z%22%20fill%3D%22%23626262%22%2F%3E%3C%2Fsvg%3E");

}

.tasks-edit::after, .tasks-postpone::after {
    content: none;
}
```
<!-- endSnippet -->

上述CSS片段显示了按钮，外观类似于早期版本的Tasks：

![Task buttons with old style](../images/tasks-buttons-svg.png)

使用图形时，还可以保证图标在所有平台上看起来都相同。

## 基于文本的按钮

最后，如果您更喜欢看起来更像链接的简单基于文本的按钮，那么[此CSS片段](https://github.com/obsidian-tasks-group/obsidian-tasks/blob/main/resources/sample_vaults/Tasks-Demo/.obsidian/snippets/tasks-buttons-text.css)展示如何做到这一点：

<!-- snippet: resources/sample_vaults/Tasks-Demo/.obsidian/snippets/tasks-buttons-text.css -->
```css
.tasks-edit, .tasks-postpone {
    font-size: var(--font-ui-smaller);
    font-variant: small-caps;
    font-weight: bold;
    margin-left: 1em;
}

.tasks-edit::after {
    content: '[edit]';
}

.tasks-postpone::after {
    content: '[move]';
}
```
<!-- endSnippet -->

上述CSS片段产生以下样式：

![Task buttons with text style](../images/tasks-buttons-text.png)

## 相关页面

有关使用CSS设置任务样式的详细信息，请参阅[[Styling|样式化]]。
