 # Admonition 插件演示

## 插件简介

Admonition 插件是一个强大的文档美化工具，它可以帮助您创建各种类型的提示框、信息块，让笔记内容更加直观和有条理。

## 基础语法

```
```ad-类型名称
title: 可选的自定义标题
collapse: 可选的折叠状态 (open, closed, 或 none)
icon: 可选的自定义图标名称
color: 可选的自定义颜色

这里是内容区域
````

## 预设类型演示

### 1. 基础信息类型

```ad-note
title: 笔记/注释
这是一个普通的笔记块，用于记录一般性的补充信息或个人想法。
```

```ad-abstract
title: 摘要/总结
这个块通常用于文章的开头或结尾，提供内容的概要信息。
```

### 2. 警告和提示类型

```ad-tip
title: 小贴士
collapse: open
这里分享一些实用的小技巧和建议！记住，学习是一个渐进的过程。
```

```ad-warning
title: 注意事项
请在操作前仔细阅读文档，避免因误操作导致的问题。
```

```ad-danger
title: 危险警告
⚠️ 这是一个高风险操作，请务必三思而后行！确保您已经备份了重要数据。
```

### 3. 问题和解决方案类型

```ad-bug
title: 已知问题
当前版本在处理大文件时可能会出现性能问题，开发团队正在努力修复中。
```

```ad-failure
title: 常见错误
这里列出一些常见的错误情况和避免方法。
```

```ad-success
title: 成功案例
恭喜！您已经成功完成了基础配置，接下来可以尝试更高级的功能。
```

### 4. 任务和进度类型

```ad-todo
title: 待办事项
- [x] 学习基础语法
- [x] 了解预设类型
- [ ] 创建自定义类型
- [ ] 实际应用练习
```

```ad-question
title: 常见问题
Q: 如何修改 admonition 的颜色？
A: 可以使用 color 参数指定十六进制颜色代码。
```

### 5. 内容展示类型

```ad-example
title: 代码示例
以下是一个简单的 Python 函数：

```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Obsidian"))
```

```ad-quote
title: 名言警句
> "知识就是力量，但更重要的是运用知识的智慧。"
> —— 培根
```

## 高级功能演示

### 折叠功能

```ad-faq
title: 折叠演示 - 默认展开
collapse: open

这个 admonition 默认是展开的，但用户可以点击标题来折叠它。
这在需要节省页面空间但又要保持内容可访问性时非常有用。
```

```ad-help
title: 折叠演示 - 默认折叠
collapse: closed

这个内容默认是折叠的，用户需要点击标题才能看到内容。
适合用于可选阅读的补充信息或详细说明。
```

### 自定义图标和颜色

```ad-info
title: 自定义样式演示
icon: star
color: 200, 200, 255

这个信息块使用了自定义的星星图标和淡蓝色配色方案。
您可以根据需要调整图标和颜色来匹配您的笔记风格。
```

```ad-warning
title: 橙色警告
color: #ff9500

这是一个使用十六进制颜色代码的橙色警告框。
```

## 实际应用场景

### 学习笔记中的应用

```ad-abstract
title: 章节概要
本章将介绍面向对象编程的三大特性：封装、继承和多态。
```

```ad-tip
title: 学习建议
建议先理解概念，再通过实际编程练习来加深理解。
```

```ad-example
title: 实践练习
尝试创建一个 Student 类，包含姓名、年龄和成绩属性。
```

### 项目文档中的应用

```ad-info
title: 系统要求
- Python 3.8 或更高版本
- 4GB 以上内存
- 支持的操作系统：Windows 10/11, macOS 10.15+, Ubuntu 18.04+
```

```ad-warning
title: 重要提醒
在生产环境中部署前，请务必进行充分的测试。
```

```ad-bug
title: 已知限制
当前版本不支持并发处理超过1000个请求。
```

### 教程文档中的应用

```ad-note
title: 前置知识
本教程假设您已经熟悉基本的 Markdown 语法。
```

```ad-step
title: 第一步
打开 Obsidian 并创建一个新的笔记文件。
```

```ad-success
title: 检查点
如果您看到了彩色的信息框，说明插件已经正确安装和配置。
```

## 嵌套和组合使用

```ad-question
title: 如何组合使用多个 admonition？
collapse: open

您可以在一个文档中使用多个不同类型的 admonition 来组织信息：

```ad-tip
title: 小贴士
先用 info 类型介绍背景，再用 example 展示示例。
```

```ad-warning
title: 注意
避免在同一视图中使用过多的 admonition，这可能会分散读者注意力。
```

## 最佳实践建议

```ad-best-practice
title: 使用建议
1. **适度使用**：不要过度使用 admonition，重点信息才需要特殊标记
2. **保持一致**：在整个项目中保持 admonition 类型使用的一致性
3. **合理分类**：根据内容性质选择合适的类型
4. **注意层次**：使用折叠功能来管理信息的层次结构
5. **自定义适配**：根据个人或团队的需求创建自定义类型
```

```ad-tip
title: 进阶技巧
- 可以在 admonition 中嵌入其他 Markdown 元素，如表格、列表、链接等
- 使用颜色编码来建立视觉语言（如红色表示危险，绿色表示成功）
- 利用折叠功能创建渐进式阅读体验
- 结合模板功能，为常用的 admonition 类型创建快捷输入方式
```