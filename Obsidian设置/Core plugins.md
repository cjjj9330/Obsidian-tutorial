>[!SUMMARY] 目录
>    - [[Core plugins#1. Audio recorder |1. Audio recorder ]]
>    - [[Core plugins#2. Backlinks|2. Backlinks]]
>    - [[Core plugins#3. Canvas|3. Canvas]]
>    - [[Core plugins#4. Command palette|4. Command palette]]
>    - [[Core plugins#5. Daily notes|5. Daily notes]]
>        - [[Core plugins#1. Date format|1. Date format]]
>        - [[Core plugins#2. New file location|2. New file location]]
>        - [[Core plugins#3. Template location|3. Template location]]
>        - [[Core plugins#4. Open daily note on startup|4. Open daily note on startup]]
>    - [[Core plugins#6. File recovery|6. File recovery]]
>        - [[Core plugins#1. Snapshot interval|1. Snapshot interval]]
>        - [[Core plugins#2. History length|2. History length]]
>        - [[Core plugins#3. Snapshots|3. Snapshots]]
>        - [[Core plugins#4. Clear history|4. Clear history]]
>    - [[Core plugins#7. Files|7. Files]]
>    - [[Core plugins#8. Format converter|8. Format converter]]
>    - [[Core plugins#9. Graph view|9. Graph view]]
>    - [[Core plugins#10. Note composer|10. Note composer]]
>        - [[Core plugins#1. Text after extraction|1. Text after extraction]]
>        - [[Core plugins# 2. Template file location | 2. Template file location ]]
>        - [[Core plugins#3. Confirm file merge|3. Confirm file merge]]
>    - [[Core plugins#11. Outgoing links|11. Outgoing links]]
>    - [[Core plugins#12. Outline|12. Outline]]
>    - [[Core plugins#13. Page view|13. Page view]]
>    - [[Core plugins#14. Properties view|14. Properties view]]
>    - [[Core plugins#15. Publish|15. Publish]]
>    - [[Core plugins#16. Quick switcher|16. Quick switcher]]
>    - [[Core plugins#17. Random note|17. Random note]]
>    - [[Core plugins#18. Search|18. Search]]
>    - [[Core plugins#19. Slash commands|19. Slash commands]]
>    - [[Core plugins#20. Slides|20. Slides]]
>    - [[Core plugins#21. Sync|21. Sync]]
>    - [[Core plugins#22. Tags view|22. Tags view]]
>    - [[Core plugins#23. Templates|23. Templates]]
>        - [[Core plugins#1. Template folder location|1. Template folder location]]
>        - [[Core plugins#2. Date format|2. Date format]]
>        - [[Core plugins#3. Time format|3. Time format]]
>    - [[Core plugins#24. Unique note creator|24. Unique note creator]]
>    - [[Core plugins#25. Web viewer|25. Web viewer]]
>        - [[Core plugins#1. Open external links|1. Open external links]]
>        - [[Core plugins#2. Homepage|2. Homepage]]
>        - [[Core plugins#3. Saved page folder|3. Saved page folder]]
>        - [[Core plugins#4. Search engine|4. Search engine]]
>        - [[Core plugins#5. Enable ad blocker|5. Enable ad blocker]]
>        - [[Core plugins#6. Ad blocking rules|6. Ad blocking rules]]
>        - [[Core plugins#7. Ad block update frequency|7. Ad block update frequency]]
>        - [[Core plugins#8. Web viewer data|8. Web viewer data]]
>    - [[Core plugins#26. Word count|26. Word count]]
>    - [[Core plugins#27. Workspaces|27. Workspaces]]

核心插件，这些插件是Obsidian官方开发并内置的功能。虽然叫“核心插件”，但它们实现的基本是一些基础功能。如果Obsidian官方不开发这些插件，我想第三方插件商店中也会有相应替代品。而且第三方插件商店实际有好几个专门针对官方核心插件的强化插件，我们下面也会提到

![[Pasted image 20250510134256.png]]
## 1. Audio recorder 

录音机，允许你直接在 Obsidian 中录制音频。录制的音频文件会作为附件保存在你的库（Vault）中，并且可以嵌入到笔记里。这功能适合喜欢在移动段用Obsidian的用户。用来录制会议、课堂等内容比较合适

## 2. Backlinks

反向链接。这是 Obsidian 双向链接功能的核心。它会自动检测并显示有哪些其他的笔记链接到了你当前正在查看的笔记。这有助于你发现笔记之间的联系，了解一个概念是如何被引用的。你可以选择在侧边栏面板或笔记底部查看这些反向链接

当你开启这个插件，设置中“Core plugins"部分会对应出现其设置项，可以点击后选择在底部展示反向链接

![[Pasted image 20250508220521.png]]

> [!info]+ 双向链接，反向链接，外链，出链，入链接，这些都是什么？ ^bidirectional-links
> 
> 我们来详细解释一下“双向链接”（Bidirectional Links）是什么，这是 Obsidian 这类笔记软件中一个非常核心和强大的概念。
> 
> **首先，理解传统的“单向链接”：**
> 
> 我们平时在网页上或者普通文档中遇到的链接大多是“单向”的。比如，你有一篇笔记 A，在里面创建了一个指向笔记 B 的链接。
> 
> `笔记 A --> 笔记 B`
> 
> 这时：
> * 你可以从笔记 A 点击链接跳转到笔记 B。
> * 但是，笔记 B 本身并不知道笔记 A 链接到了它。除非你手动也在笔记 B 中创建一个返回到笔记 A 的链接，否则这个连接是单方向的。
> 
> **什么是“双向链接”？**
> 
> 双向链接则更进了一步。在支持双向链接的系统中（比如 Obsidian）：
> 
> 1.  当你从**笔记 A** 中创建一个链接指向**笔记 B** 时 (这被称为“出链”或 Outgoing Link 从笔记 A 发出)。
> 2.  系统会自动在**笔记 B** 中记录下“笔记 A 链接到了我”这个信息。这个自动出现的、指向笔记 A 的引用，就被称为**笔记 B 的“反向链接”或“入链” (Backlink / Incoming Link)**。
> 
> 所以，链接关系变成了这样：
> 
> `笔记 A <-- --> 笔记 B`
> 
> 重要的是，这个反向的连接是**自动建立和显示**的，你不需要在笔记 B 中做任何额外的操作来创建指向笔记 A 的链接。
> 
> **Obsidian 中双向链接的体现：**
> 
> * **出链 (Outgoing Links)**：你正常地在笔记中通过 `[[笔记名称]]` 或者 `[[笔记名称#标题]]` 等方式创建链接。
> * **反向链接 (Backlinks)**：Obsidian 会有一个专门的面板（通常叫做“反向链接”或“Backlinks”面板）来显示当前笔记的所有反向链接。当你打开笔记 B 时，就能在这个面板里看到笔记 A（以及其他任何链接到笔记 B 的笔记）的列表和相关上下文。
> 
> **双向链接为什么重要和强大？**
> 
> 双向链接对于知识管理、学习和思考具有非常大的价值：
> 
> 1.  **发现上下文和隐藏联系**：当你查看一个笔记时，能立刻知道还有哪些笔记提到了它、依赖它或者与它相关。这能帮你发现之前可能没有意识到的知识点之间的联系。
> 2.  **构建知识网络**：你的笔记不再是孤立的信息点，而是通过双向链接形成了一个相互连接的知识网络。你可以顺着链接（包括反向链接）在网络中自由穿梭，探索不同的思路。
> 3.  **减少维护成本**：你只需要创建单向的链接，系统会自动帮你维护反向的连接，省去了手动创建和管理另一方向链接的麻烦。
> 4.  **促进思考和创意**：通过查看反向链接，你可以回顾当初是在什么情境下提到当前这个概念的，这可能会激发新的思考和创意。例如，你写了一个关于“习惯养成”的笔记，通过反向链接，你可能会发现之前在“项目管理”、“学习方法”、“个人成长”等不同主题的笔记中都曾链接到过“习惯养成”，这能让你对“习惯养成”这个概念有更全面的理解。
> 5.  **避免信息孤岛**：确保了即使是很久以前创建的笔记，只要它被其他笔记引用，就不会被轻易遗忘，其价值也能在新的情境下被重新发现。
> 
> 简单来说，双向链接让你的笔记“活”了起来，它们能够互相“看见”和“对话”，极大地增强了知识的连接性和可发现性，这对于构建个人知识体系（PKM - Personal Knowledge Management）是非常有益的。

不过我现在暂时感觉这个用处不大，可能是没用起来吧
## 3. Canvas

画布。提供一个自由形态的、无限延伸的可视化空间。你可以在画布上随意放置笔记、卡片（可以是新的文本卡片）、图片、网页链接等元素，并用线条将它们连接起来，创建概念图、流程图、思维导图等。非常适合进行头脑风暴、梳理复杂信息和项目规划

开启后，可通过左侧[[Appearance#3. Show Ribbon|Ribbon]]中的图标打开Canvas

之前有看过大佬用类似的软件，但一直没机会接触。这次用Obsidian正好碰到了，最近刚用这个Canvas帮助我理清如何用Obsidian规划我的工作任务：

![[Pasted image 20250508221810.png]]

感觉确实挺有用的，希望以后能帮我解决其他复杂问题，大家也可以学着用下，说不定能帮到大家

## 4. Command palette

这个真的可以称为核心插件。按下[[Hotkeys|快捷键]] `Cmd/Ctrl+P` 后会弹出一个可搜索的输入框，列出了Obsidian 中几乎所有的可用命令（包括核心功能、已启用插件的命令等）。你只需要输入命令的关键词，就可以快速找到并执行相应的操作，它是你调用所有功能的中枢处

开启这个插件后，设置面板中"Core plugins"板块会相应出现其设置面板，它的后台设置主要是让用户选择将哪些命令置顶以便每次按Ctrl + P时更快访问

![[Pasted image 20250508234549.png]]

比如我现在已经将图中“Pinned commands"下的命令置顶，你可以在这里重新配置需要置顶的命令以及它们的顺序 ^pinned-commands

## 5. Daily notes

帮助你轻松创建以当天日期命名的笔记。这对于写日记、记录每日待办事项、进行每日回顾或任何以日期为单位进行追踪的活动都非常有用。通常可以配合“Templates (模板)”插件使用，为每日笔记设定一个固定的格式

同样，当你启用这个插件，设置中”Core plugins“板块下将出现其对应设置面板

![[Pasted image 20250508235102.png]]
### 1. Date format

这个设置决定了当你创建每日笔记时，笔记文件的名称会使用什么样的日期格式。

- `YYYY` 代表四位数的年份 (例如：2025)
- `MM` 代表两位数的月份 (例如：05)
- `DD` 代表两位数的日期 (例如：08)

你可以自定义这个格式。例如，如果你想用 `2025年05月08日` 这样的格式，你可以设置为 `YYYY年MM月DD日`。Obsidian 使用 Moment.js 的日期格式化标准，所以有很多可用的占位符，比如 `dddd` 代表星期几 (例如 "Thursday")

> [!hint]- Moment.js是什么？ ^moment-js
> [Moment.js](https://momentjs.com/docs/#/displaying/format/) 是一个曾经非常流行和广泛使用的 **JavaScript 日期/时间处理库 (library)**。
> 
> 简单来说，它的主要用途是帮助开发者在 JavaScript 程序中更轻松地完成与日期和时间相关的各种操作，比如：
> 
> 1.  **解析 (Parse)**：将字符串（比如 "2025-05-08"）或不同格式的日期输入转换成程序可以理解的日期对象。
> 2.  **校验 (Validate)**：判断一个日期是否有效。
> 3.  **操作 (Manipulate)**：对日期进行加减运算（例如，计算7天后的日期，3个月前的日期），获取日期的某个部分（如年份、月份、星期几），比较日期先后等。
> 4.  **格式化显示 (Display/Format)**：将日期对象按照用户指定的格式输出为字符串。**这一点与你在 Obsidian "Daily notes" 插件设置中遇到的 "Date format" (日期格式) 直接相关。**
> 
> **为什么 Moment.js 很重要/很有用 (尤其对于 Obsidian 用户理解日期格式而言)？**
> 
> 在编程中，直接处理日期和时间可能非常繁琐和容易出错，因为涉及到时区、闰年、不同国家地区的日期表达习惯等复杂问题。Moment.js 通过提供一套简洁易懂的API（应用程序编程接口），极大地简化了这些工作。
> 
> 对于 Obsidian 用户来说，最直接接触到的就是它的**日期格式化功能**。Obsidian 的“每日笔记”插件（以及其他可能涉及日期的地方）使用 Moment.js 定义的**格式化占位符 (formatting tokens)** 来允许你自定义日期在文件名或笔记内容中是如何显示的。
> 
> **一些常见的 Moment.js 格式化占位符（你在 Obsidian 中可能会用到）：**
> 
> * `YYYY`: 四位数的年份 (例如：2025)
> * `MM`: 两位数的月份 (01-12)
> * `DD`: 两位数的日期 (01-31)
> * `dddd`: 星期几的全称 (例如：Thursday, 星期四)
> * `ddd`: 星期几的简称 (例如：Thu, 周四)
> * `HH`: 24小时制的小时 (00-23)
> * `mm`: 分钟 (00-59)
> * `ss`: 秒 (00-59)
> 
> 所以，当你在 Obsidian 的每日笔记设置中输入 `YYYY-MM-DD` 时，你实际上是在告诉 Obsidian 使用 Moment.js 的规则来生成一个像 "2025-05-08" 这样的文件名。如果你输入 `YYYY年MM月DD日 dddd`，那么文件名可能就会是 "2025年05月08日 Thursday"。
> 
> **关于 Moment.js 的现状：**
> 
> 需要提一下的是，Moment.js 目前已经进入**维护模式 (legacy project in maintenance mode)**。它的开发者已经宣布不再添加新功能，主要进行必要的维护和修复严重bug。对于新的开发项目，他们推荐使用一些更现代的替代库（如 Luxon, Day.js, date-fns 等），这些新库在体积、性能和设计理念上可能更有优势。
> 
> 不过，由于 Moment.js 曾经非常流行，很多现有的应用和系统（包括 Obsidian 的某些部分）仍然在使用它，尤其是它的日期格式化语法，已经成为一种事实上的标准被广泛认知。因此，了解它的格式化占位符对于自定义 Obsidian 中的日期显示依然是有用的。
> 
> 总而言之，Moment.js 是一个帮你处理和格式化日期时间的 JavaScript 工具，Obsidian 借用了它的日期格式化规则，让你能够灵活定义每日笔记文件名等场景下的日期展现形式。

### 2. New file location

新的每日笔记将放置在此处。这个设置让你指定新创建的每日笔记默认保存在你 Obsidian 库（Vault）中的哪个文件夹下，你可以在后方输入框中选择

### 3. Template location

选择用作模板的文件。选择后，每当你创建一个日记，Obsidian 会自动将这个模板文件的所有内容复制到新的每日笔记开头

### 4. Open daily note on startup

如果启用这个选项（打开开关），那么每次你启动 Obsidian 并打开这个库的时候，它会自动为你创建（如果当天还没有的话）并打开当天的每日笔记

## 6. File recovery

这个插件会定期为你的 Markdown 笔记创建快照（版本历史）。如果你不小心删除了内容或者想回退到之前的某个版本，可以通过这个功能来恢复。这是一个防止数据丢失的重要保障

Notion也有类似的页面版本历史功能，但如果不是会员，好像只能看最近七天的记录。如果你使用Git进行同步，这个插件可能用处就不是很大了，因为Git本身就是用于历史版本控制。大家可以根据实际情况决定如何设置Git与File recovery

启用这个插件后，设置面板中，"Core plugins"部分会列出其具体设置：

![[Pasted image 20250509000606.png]]

### 1. Snapshot interval

两个快照之间的最小间隔分钟数。这个设置决定了 Obsidian 多久为你的笔记文件创建一个快照（版本备份）。例如，设置为5分钟，意味着 Obsidian 会尝试每隔5分钟检查一次文件是否有改动，如果有改动，则保存一个新的快照。如果文件在这5分钟内没有变化，则不会创建新的快照

### 2. History length

快照保存的天数。这个设置决定了 Obsidian 会将每个文件的快照保留多长时间。例如，设置为90天，意味着一个快照在创建90天后，如果它不再是最新的快照之一（即有更新的快照持续产生），它可能会被系统自动删除，以节省存储空间

### 3. Snapshots

查看和恢复已保存的快照。这不是一个让你输入值的设置项，而是一个操作按钮。点击“View”按钮后，会打开一个新的界面或弹窗。在这里，你需要先搜索目标笔记，obsidian会列出该笔记已保存的快照，可通过“Copy”按钮复制快照

### 4. Clear history

擦除所有快照。点击“Clear”按钮会删除你库中所有笔记的所有已保存快照

## 7. Files

文件浏览器。就是左边边栏这个最核心的东西：

![[Pasted image 20250509002624.png]]

没想到吧，这也是一个插件。当之无愧的核心插件，当然要开启啦！
## 8. Format converter

将来自其他应用的 Markdown 转换为 Obsidian 格式。这个插件主要用于帮助你导入和清理从其他笔记软件（如 Roam Research, Bear, Zettelkasten 系统等）迁移过来的 Markdown 文件。它会尝试修复一些不兼容的 Markdown 语法或将其转换为 Obsidian 更偏好的格式，例如处理特定的链接格式或标签格式

这个稍微和[[Obsidian设置/Editor#1. Convert pasted HTML to Markdown|convert pasted HTML to markdown]]有些重复，具体区别可参考对这一项的详细解释：


> [!info]- Format converter详细解释
> 好的，Obsidian 的 "Format converter" (格式转换器) 插件主要用于帮助你将从其他应用程序导入或粘贴过来的 Markdown 内容，或者一些不太标准的 Markdown 语法，转换成 Obsidian 更偏好或更兼容的格式。
> 
> 它的作用可以理解为对“外来”的笔记内容进行一次“格式化清理和统一”，让这些笔记在 Obsidian 中能更好地显示和工作。
> 
> 以下是一些具体的例子来说明它的作用：
> 
> 1.  **转换高亮 (Highlight) 语法：**
>     * **场景**：假设你从一个笔记应用（比如早期版本的 Bear App，或者某些 Markdown 编辑器）迁移笔记，那个应用可能使用 `::要高亮的文本::` 这样的语法来标记高亮文本。
>     * **Obsidian 的语法**：Obsidian 自身以及现在比较通用的 Markdown 高亮语法是 `==要高亮的文本==`。
>     * **Format Converter 的作用**：当你导入或粘贴了包含 `::要高亮的文本::` 这种内容后，格式转换器可以帮助你将这些非标准的高亮语法自动转换成 Obsidian 支持的 `==要高亮的文本==`。这样，你的高亮内容就能在 Obsidian 中正确显示了。
> 
> 2.  **HTML 内容粘贴转换为 Markdown：**
>     * **场景**：当你从网页、Word文档或其他富文本编辑器复制内容，然后粘贴到 Obsidian 中时，这些内容背后往往是 HTML 代码。
>     * **Obsidian 的处理**：Obsidian 会尽力将粘贴的 HTML 转换为 Markdown。
>     * **Format Converter 的作用**：这个插件可以增强这种转换能力，或者处理一些更复杂的 HTML 到 Markdown 的转换情况，确保转换后的 Markdown 尽可能干净和标准。例如：
>         * 将 HTML 的加粗标签 `<b>加粗</b>` 或 `<strong>加粗</strong>` 转换为 Markdown 的 `**加粗**`。
>         * 将 HTML 的斜体标签 `<i>斜体</i>` 或 `<em>斜体</em>` 转换为 Markdown 的 `*斜体*`。
>         * 处理 HTML 的列表 (`<ul>`, `<ol>`, `<li>`) 转换为 Markdown 的 `- ` 或 `1. ` 列表。
>         * 转换 HTML 的链接 (`<a href="...">链接</a>`) 为 Markdown 的 `[链接](...)`。
> 
> 3.  **处理其他应用特有的 Markdown 变体：**
>     * **场景**：不同的 Markdown 编辑器或笔记应用，为了实现特定功能，有时会引入一些自己独有的 Markdown 扩展语法。当你把这些笔记迁移到 Obsidian 时，这些特殊语法可能无法被正确识别。
>     * **Format Converter 的作用**：如果这些特殊语法是已知的或者有转换规律可循，格式转换器就可能包含将它们转换为标准 Markdown 或 Obsidian 支持的等效功能的规则。例如，某种特殊的任务列表格式、特定的嵌入内容语法等。
> 
> 4.  **清理不必要的格式或字符：**
>     * **场景**：从某些地方导入的文本可能包含很多多余的空行、不规范的缩进，或者一些在 Obsidian 中没有意义的特殊控制字符。
>     * **Format Converter 的作用**：它可以帮助清理这些内容，使笔记格式更统一、更整洁。
> 
> **如何使用（通常情况下）：**
> 
> 这个插件的功能可能通过以下几种方式触发：
> 
> * **自动转换**：在你从外部源粘贴内容到 Obsidian 时自动进行。
> * **手动命令**：通过命令面板 (Ctrl/Cmd + P) 调出类似 "Format converter: Convert pasted HTML to Markdown" 或其他特定的转换命令，对选中的文本或整个笔记执行操作。
> 
> 总的来说，"Format converter" 插件就像一个清道夫和翻译官，它帮助你将在其他地方创建的、格式可能不太一样的笔记内容，更好地适应 Obsidian 的环境，确保内容的一致性和可读性。对于经常需要从不同来源导入或整理笔记的用户来说，这个插件会比较有用。


> [!tip] 请忽略上方dataview报错
> 

## 9. Graph view

关系图谱。这个插件会将你的笔记以及它们之间的内部链接以图形化的网络形式展示出来。在图谱中，每个笔记是一个节点，笔记之间的链接则表现为连接节点的线。你可以通过关系图谱直观地看到哪些笔记是核心节点（被大量引用），哪些笔记比较孤立，以及不同知识簇群是如何形成的。它有助于宏观地理解你的知识库结构，并发现潜在的联系。你可以查看整个库的全局图谱，也可以查看与当前笔记相关的局部图谱

开启这个插件后，左侧[[Appearance#3. Show Ribbon ribbon|Ribbon]]会列出一个属于Graph view的按钮，点击即可查看

我还没怎么用过这个功能，等用的多了再来更新一下吧 #有待更新 

## 10. Note composer

笔记合并/拆分。合并两个笔记或将一个笔记拆分为两个。

这插件一共有三个功能

![[Pasted image 20250510082025.png]]

1.  Extract current selections: 用于将当前选中内容合并到指定笔记的**末尾**，只有选中笔记中的文字时按ctrl + p才会出现这个选项
2. Extract this heading: 将选中的标题及这部分的内容提取为一个新文件
3. Merge current file with another file: 将当前笔记与另外一个选中的笔记合并（置于末尾），合并后当前笔记将被删除

![[Pasted image 20250510075303.png]]

可以通过Ctrl + p[[Hotkeys|快捷键]]调出命令面板[[Core plugins#4. Command palette|Command palette]]，然后输入Note composer来调出这个插件支持的操作
### 1. Text after extraction

提取选定文本后，在原位置显示的内容。这个设置决定了当你使用“提取文本到新笔记”（Extract selection to new note）这个功能时，原始笔记中被提取走的那部分内容会被什么所替换

- Link to new file (链接到新文件): 当文本被提取到新笔记后，原位置会被一个指向那个新创建笔记的内部链接（Wikilink）所取代。这样可以保持上下文的连贯性，让你知道这部分内容去了哪里，并且可以方便地跳转过去
- Embed new file (嵌入新文件): 提取后，原位置会被一个嵌入新笔记的链接（例如 `![[新笔记名称]]`）所取代，直接在当前笔记中显示新笔记的内容
- None: 提取后，原位置的文本直接被删除，不留下任何东西

###  2. Template file location 

模板文件位置。这个选项允许你指定一个模板笔记，当执行“extract current selection”或“merge current file with another file”的操作时，将模板文件的内容置于被合并内容顶部一起加到目标笔记末尾

模板文件可用的变量：{{content}} 内容, {{fromTitle}} 源标题, {{newTitle}} 新标题, {{date:FORMAT}} 日期，例如 {{date:YYYY-MM-DD}}

当你把一段文本提取成一个新笔记时，这个新笔记的初始内容可以不仅仅是被提取的文本 (`{{content}}`)，还可以包含模板中预设的其他内容、标题格式等。模板中可以使用变量，例如：

- `{{content}}`: 代表被提取或合并过来的主要文本内容
- `{{fromTitle}}`: 代表源笔记的标题（在合并或从特定笔记提取时）
- `{{newTitle}}`: 代表新创建笔记的标题
- `{{date:FORMAT}}`: 代表当前的日期，你可以指定格式，例如 `{{date:YYYY-MM-DD}}` 会插入像 "2025-05-09" 这样的日期

你可以像这样创建[[Note composer模板]]

### 3. Confirm file merge

确认文件合并。当这个选项开启时，如果你执行“合并笔记”的操作，Obsidian 会在实际执行合并之前弹出一个确认对话框，让你再次确认是否要进行这个操作

## 11. Outgoing links

出链。这个插件通常会在侧边栏提供一个面板，显示与当前笔记相关的两种链接信息：

![[Pasted image 20250510104244.png]]

- **链接的提及 (Linked mentions)**：列出当前笔记中明确创建的、指向其他笔记或外部网址的链接
- **未链接的提及 (Unlinked mentions)**：Obsidian 会在当前笔记中搜索那些与你库中其他笔记标题完全相同的文本字符串，即使这些字符串当前还不是一个可点击的链接。它会把这些“潜在链接”列出来，你可以一键将它们转换为真正的内部链接。这对于发现和建立被遗漏的连接非常有帮助

可以通过Ctrl + p[[Hotkeys|快捷键]]调出命令面板[[Core plugins#4. Command palette|Command palette]]，然后输入outgoing links来调出这个插件支持的操作

虽然第二个”未链接的提及“看起来比较有用，可以帮我们快速建立笔记间的联系，从而使[[Core plugins#9. Graph view|Graph view]]更完善，但不知道是插件的bug还是我理解有误，这种情况下它居然不在Unlinked MENTIONS部分列出Appearance的未链接提及：

![[Pasted image 20250510105107.png]]

有可能是我理解有误，后面有时间证实后再回来更新吧 #有待更新 

## 12. Outline

在侧边栏（通常是右侧）生成并显示当前打开笔记的层级大纲。这个大纲是基于笔记中的标题（例如 Markdown 中的 `#` 一级标题, `##` 二级标题, `###` 三级标题等）自动构建的。你可以点击大纲中的任何一个标题，快速跳转到笔记中的相应位置。这对于阅读、编辑和导航结构清晰的长篇笔记非常方便

## 13. Page view

页面预览。当你将鼠标指针悬停在一个指向其他笔记的内部链接（即 Wikilink `[[笔记名称]]`）/[[Core plugins#7. Files|左侧文件列表]]中的笔记/[[Core plugins#3. Canvas|Canvas]]、Excalidraw 中的笔记，总之几乎所有直接与笔记相关的链接上时，都会弹出一个小型的浮动窗口，即时预览被链接笔记的内容摘要

这样你就可以快速了解链接指向的内容，而不需要实际点击并跳转到那个笔记，从而避免打断当前的工作流程。在编辑模式下，通常需要按住 `Ctrl` (Windows/Linux) 或 `Cmd` (macOS) 键再进行悬停才能触发预览，以免在正常编辑时光标移动时频繁触发

##
![[Pasted image 20250510134331.png]]
## 14. Properties view

属性视图。这个插件提供了一个专门的界面（通常在右侧边栏）来集中查看和编辑当前笔记的“属性”（[[Obsidian设置/Editor#Properties in document|Properties]]）。笔记属性就是笔记的元数据，通常以 YAML frontmatter 的形式写在笔记的最顶部（由 `---` 包裹），或者通过 Obsidian 的属性编辑界面添加。这些属性可以是标签、别名、创建日期、作者，或者任何你自定义的键值对信息（例如 `status: ongoing`，`priority: high`）。属性视图使得管理这些结构化数据更加方便直观

可以通过Ctrl + p[[Hotkeys|快捷键]]调出命令面板[[Core plugins#4. Command palette|Command palette]]，然后输入Properties view来调出这个插件支持的操作

![[Pasted image 20250510120835.png]]

- Show all properties: 列出你的Vault中所有笔记包含的属性
- Show file properties: 列出当前笔记包含的属性

## 15. Publish

这是 Obsidian 官方提供的**付费服务**的配套核心插件。如果你订阅了 Obsidian Publish 服务，就可以通过这个插件像Notion那样选择性地将你的笔记、附件和整个知识库发布到互联网上，创建一个公开的、可在线访问的个人网站、知识库、博客或项目文档。你可以控制哪些笔记被发布，并对发布站点进行一些自定义

由于我没有订阅过Obsidian付费服务，这个和下面的Sync都是大概介绍一下，不详细展开

## 16. Quick switcher

快速切换器。这是一个导航工具。默认[[Hotkeys|快捷键]]通常是 `Ctrl/Cmd + O`。按下后会弹出一个简洁的搜索框，你可以通过输入笔记文件名（或其一部分）的关键词来快速模糊搜索并定位到你库中的任何一篇笔记。选中后按回车即可快速打开该笔记

## 17. Random note

随机笔记。启用此插件后，[[Appearance#3. Show Ribbon}左侧Ribbon]]会出现一个图标，点击它或通过[[Core plugins#4. Command palette|Command palette]]执行Random note命令会随机从你的整个笔记库中挑选并打开一篇笔记

## 18. Search

提供全局搜索功能。你可以在左侧或右侧边栏的放大镜面板中输入关键词、标签、路径或其他搜索条件，Obsidian 会在你的整个笔记库中进行查找，并列出所有匹配的笔记及其中的匹配上下文。搜索功能支持布尔操作符（AND, OR, NOT）、正则表达式、按路径或标签搜索等高级语法

![[Pasted image 20250510122124.png]]

## 19. Slash commands

斜杠命令。使用过Notion的小伙伴应该对这个不陌生，启用此插件后，当你在笔记编辑器中输入正斜杠 `/` 时，会自动弹出一个小型的命令菜单，列出一些常用的编辑命令或格式化操作（例如插入模板、设置标题级别、创建列表、插入表格等）。你可以通过继续输入命令的关键词来筛选列表，然后选择并执行相应的命令，你可以在[[Core plugins#4. Command palette|Command palette]]面板中，设置将哪些你常用的命令在斜杠命令中[[Core plugins#^pinned-commands|置顶]]以便更好地调用

## 20. Slides

幻灯片。允许你直接使用 Markdown 笔记来创建和演示幻灯片。你可以在笔记中使用三个或更多的连字符 `---` (通常在一行中单独出现) 作为幻灯片之间的分隔符。笔记中的标题、列表、图片等 Markdown 元素会被渲染成幻灯片的内容。这是一个快速将笔记内容转化为演示稿的便捷方式。这里有一个[[Advanced Slides 插件演示|Slides插件使用示例]]

这样做出来的演示文稿是可以通过快捷键命令在Obsidian中直接播放，或者配合Pandoc等插件导出为PPT文件，但我还没用过，我知道有一个第三方插件商店中有一个Advanced Slides插件专门用于在obsidian中做PPT，是这个插件的加强版

## 21. Sync

这是 Obsidian 官方提供的**付费同步服务**的配套核心插件。如果你订阅了 Obsidian Sync 服务，启用此插件后，你的整个笔记库（Vault），包括所有笔记、附件、主题和设置，都可以在你的多个设备（如电脑、手机、平板）之间进行端到端加密的安全同步。它还支持版本历史和选择性同步等功能

## 22. Tags view

标签视图/标签面板。在你启用此插件后，通常会在侧边栏提供一个“标签面板”。这个面板会扫描你整个库中的所有笔记，并列出所有使用过的标签（例如 `#mytag`）

![[Pasted image 20250510130517.png]]

每个标签旁边通常会显示它在库中出现的总次数。你可以点击列表中的任何一个标签，快速搜索并找到所有包含该标签的笔记

## 23. Templates

允许你创建和使用笔记模板。你可以预先创建一些包含常用结构、格式或提示内容的笔记文件，并将它们存放在一个指定的模板文件夹中。启用此插件后，设置中“Core plugins"部分会出现一个Templates插件控制面板：

![[Pasted image 20250510130843.png]]

### 1. Template folder location

模板文件夹位置。这个设置让你指定一个文件夹，Obsidian 会将这个文件夹里的所有 Markdown 文件 (`.md` 文件) 都识别为可用的模板。当你执行“插入模板”命令时（通过[[Core plugins#4. Command palette|命令面板]]或[[Hotkeys|快捷键]]），Obsidian 会从这个指定的文件夹中加载模板列表供你选择，如我现在指定的是根目录下Templates这个文件夹

### 2. Date format

模板文件中的 `{{date}}` 将被替换为此值。你也可以使用 `{{date:YYYY-MM-DD}}` 来单次覆盖格式。更多语法，参考[格式参考](https://momentjs.com/docs/#/displaying/format/)

### 3. Time format

时间格式。模板文件中的 `{{time}}` 将被替换为此值。你也可以使用 `{{time:HH:mm}}` 来单次覆盖格式。更多语法，参考[格式参考](https://momentjs.com/docs/#/displaying/format/)

> [!faq]- 单次覆盖格式是什么意思？
> “单次覆盖格式”这句话的意思是，即使你在 Obsidian“Templates”（模板）插件的设置中为 `{{date}}`（日期）和 `{{time}}`（时间）设定了一个**全局的默认显示格式**，你依然可以在某一个具体的模板文件中的**某一个特定位置**，为那一次的日期或时间插入指定一个**与默认设置不同的、临时的格式**。
> 
> 这种指定只对那**一次**使用有效，不会改变你在插件设置中定义的全局默认格式。
> 
> 让我们通过一个例子来理解：
> 
> **假设你在“Templates”插件的设置中是这样配置的：**
> 
> 1.  **Date format (日期格式)**：设置为 `YYYY-MM-DD` (这是默认格式)
>     * 这意味着，如果你在模板中只写 `{{date}}`，它会被替换成类似 `2025-05-09` 这样的格式。
> 
> 2.  **Time format (时间格式)**：设置为 `HH:mm` (这是默认格式)
>     * 这意味着，如果你在模板中只写 `{{time}}`，它会被替换成类似 `22:15` (24小时制) 这样的格式。
> 
> **现在，你创建一个模板文件，内容如下：**
> 
> ```markdown
> # 我的笔记
> 
> 今天的日期 (默认格式): {{date}}
> 今天的日期 (详细格式 - 单次覆盖): {{date:dddd, MMMM Do YYYY}}
> 
> 当前时间 (默认格式): {{time}}
> 当前时间 (带秒和AM/PM - 单次覆盖): {{time:hh:mm:ss A}}
> 
> ---
> 笔记内容：
> 
> ```
> 
> **当你使用这个模板插入内容时（假设今天是2025年5月9日，星期五，晚上10点15分30秒）：**
> 
> Obsidian 会这样替换这些变量：
> 
> * `{{date}}`：会使用你在插件设置中定义的**默认日期格式** `YYYY-MM-DD`。
>     * 所以，它会被替换为：`2025-05-09`
> 
> * `{{date:dddd, MMMM Do YYYY}}`：这里你通过在冒号后面指定了 `dddd, MMMM Do YYYY` 这个具体的格式，这就**“单次覆盖”**了默认的 `YYYY-MM-DD` 格式。
>     * 所以，它会被替换为：`Friday, May 9th 2025` (星期五，2025年5月9日)
> 
> * `{{time}}`：会使用你在插件设置中定义的**默认时间格式** `HH:mm`。
>     * 所以，它会被替换为：`22:15`
> 
> * `{{time:hh:mm:ss A}}`：这里你通过在冒号后面指定了 `hh:mm:ss A` 这个具体的格式，这就**“单次覆盖”**了默认的 `HH:mm` 格式。
>     * 所以，它会被替换为：`10:15:30 PM` (晚上10点15分30秒，12小时制)
> 
> **总结一下“单次覆盖格式”的含义：**
> 
> * **默认设置是基础**：插件设置中的日期和时间格式是你大部分情况下会得到的格式（当你只使用 `{{date}}` 或 `{{time}}` 时）。
> * **灵活性**：如果你在模板的某个特定地方需要一个不同于默认的日期或时间格式（比如更详细、或者不同的语言风格、或者12/24小时制的切换），你可以直接在那个变量后面加上冒号和你想要的具体格式代码，例如 `{{date:你想要的格式}}` 或 `{{time:你想要的格式}}`。
> * **“单次”有效**：这种指定只影响当前这一个变量的输出。它不会改变你在插件设置中保存的全局默认格式。如果你在同一个模板的其他地方再次使用 `{{date}}` (不带特定格式)，它仍然会使用全局默认格式。
> 
> 这种机制让你既能有一个方便的全局默认设置，又能灵活地满足在特定情境下对日期时间格式的特殊需求。

第三方插件商店中有一个叫Templater的插件，专门针对这个templates插件进行强化，如果使用那个插件这个插件就不需要了，但它们工作方式基本是一样的。因为Templater是Obsidian最强大的插件之一，建议使用Templater而不是这个Obsidian自带的模板插件 #链接回来
## 24. Unique note creator

唯一笔记创建器。创建带有唯一时间戳前缀的笔记，适用于像卡片盒笔记法或滑箱笔记法这样的工作流

这个插件主要用于帮助实践卡片盒笔记法 (Zettelkasten) 的用户。它提供了一个命令来创建新笔记，并且会自动为这个新笔记的文件名添加一个基于当前日期和时间的唯一ID作为前缀（通常是 `YYYYMMDDHHmmss` 这样的格式）。这样做可以确保每个笔记都有一个独一无二的标识符，方便引用和管理，即使笔记标题发生改变，基于ID的链接也不会断裂

这个我不是很了解，大家感兴趣的可以自行挖掘更多信息

## 25. Web viewer

在 Obsidian 内部打开指向网页的外部链接。通常，当你在 Obsidian 中点击一个指向外部网站的链接时，它会在你系统的默认浏览器中打开。启用这个插件后，可能会允许某些外部链接（或者所有，取决于具体实现）直接在 Obsidian 的一个新标签页或面板中以内嵌网页的形式打开和显示。这可以减少在不同应用之间切换的次数，让你保持在 Obsidian 的工作环境中浏览网页内容

启用后，设置中“Core plugins"部分会出现其对应设置选项

![[Pasted image 20250510132554.png]]

这插件我用的挺多的，确实可以节省一些来回切换应用的时间，是核心插件中功能最实用的插件之一。但它的网页浏览器不能使用扩展插件，对于cookie保存有时也有点问题，导致需要重复输入账号密码。总的来说虽然有缺陷，但一般情况下使用都不会有什么问题，还可以

### 1. Open external links

打开外部链接。当这个选项开启时，如果你在笔记中点击一个指向外部网站的普通链接 (例如 `https://www.google.com`)，该链接会在 Obsidian 应用内的一个新标签页或面板中打开，而不是像通常那样跳转到你电脑上安装的 Chrome, Safari, Edge 等默认浏览器。如果关闭此选项，外部链接将总是在系统默认浏览器中打开

### 2. Homepage

这里设置的是当你新打开一个空白的网页查看器标签页时，默认加载的网址。你可以把它设置成你常用的搜索引擎、个人门户网站或任何你希望快速访问的网页。当前设置为谷歌搜索引擎

### 3. Saved page folder

已保存页面的文件夹。作为 markdown 保存的网站将放置在此处。Web viewer有一个按钮（打开网页后点击右上方三个点，选择”Save to Vault"）允许你将网页以markdown格式保存到指定文件夹中。如果这里的文件夹为空则保存到Vault根目录

### 4. Search engine

默认搜索引擎。当你在网页查看器的地址栏中直接输入搜索词（而不是一个完整的网址）并按回车时，这个设置决定了会使用哪个搜索引擎来进行搜索。你可以从预设的选项中选择，如 Google, DuckDuckGo, Bing 等

### 5. Enable ad blocker

启用广告拦截器。启用后，网页查看器会尝试根据下面“广告拦截规则”中定义的列表来拦截网页上的广告内容

### 6. Ad blocking rules

广告拦截规则。里你可以指定一个或多个广告拦截规则列表的URL。这些列表（如 EasyList, EasyPrivacy）包含了大量已知的广告域名、URL模式等，广告拦截器会根据这些规则来判断并阻止广告的加载。这些规则是公开维护的，你可以添加或修改这些URL。这些规则会被你所有库中的网页查看器共享

### 7. Ad block update frequency

广告拦截更新频率。这个设置决定了网页查看器插件自动从上面指定的URL更新广告拦截规则列表的频率（以天为单位）。设置为0表示禁用自动更新。这个设置同样是所有库共享的

### 8. Web viewer data

网页查看器数据。点击这个按钮会清除网页查看器插件存储的浏览数据，包括cookies、缓存文件、浏览历史（如果插件记录的话）等

## 26. Word count

字数统计。启用后，会在 Obsidian 窗口底部的状态栏实时显示当前打开笔记（或选中文字）的字数统计、字符数统计等信息

第三方插件商店中有一个插件叫Better Word Count，是这个插件的加强版，建议使用这个插件 #链接回来 

## 27. Workspaces

工作区。允许你保存当前 Obsidian 界面的整体布局——包括打开了哪些笔记和面板（如文件浏览器、大纲、反向链接面板等）、这些面板的位置和大小、侧边栏的显隐状态等——作为一个“工作区”。你可以创建多个不同的工作区预设（例如，“写作模式”、“研究模式”、“规划模式”），并在它们之间快速切换。这对于针对不同任务优化工作环境非常方便




