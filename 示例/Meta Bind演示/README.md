# Meta Bind插件演示文档

## 📚 文档说明

本文件夹包含了Meta Bind插件的完整功能演示和实用模板，帮助您快速掌握这个强大的Obsidian交互式插件。

## 📁 文件结构

### 1. 基础功能演示
- **`Meta Bind插件完整功能演示.md`** - 基础语法和核心功能演示
- **`Meta Bind按钮功能演示.md`** - 按钮功能的深入演示
- **`语法调试.md`** - 语法测试和调试用文件

### 2. 实际应用模板
- **`Meta Bind实际应用模板.md`** - 三个完整的实际应用场景模板
  - 学习管理系统
  - 项目管理系统
  - 阅读追踪器

## 🚀 快速开始

### 安装Meta Bind插件
1. 打开Obsidian设置 → 社区插件
2. 搜索"Meta Bind"
3. 安装并启用插件

### 基础语法
```markdown
# 输入字段
`INPUT[type:property]`

# 显示字段
`VIEW[{property}]`

# 按钮（代码块）
```meta-bind-button
label: 按钮标签
actions:
  - type: updateMetadata
    bindTarget: property
    evaluate: false
    value: newValue
```
```

## 📋 核心功能一览

### 输入字段类型
| 类型 | 语法示例 | 描述 |
|------|----------|------|
| `text` | `INPUT[text:name]` | 文本输入 |
| `number` | `INPUT[number:age]` | 数字输入 |
| `toggle` | `INPUT[toggle:completed]` | 开关切换 |
| `inlineSelect` | `INPUT[inlineSelect(option(A), option(B)):choice]` | 内联选择器 |
| `date` | `INPUT[date:deadline]` | 日期选择 |
| `textArea` | `INPUT[textArea:notes]` | 多行文本 |
| `slider` | `INPUT[slider(minValue(0), maxValue(100)):progress]` | 滑块 |
| `multiSelect` | `INPUT[multiSelect(option(A), option(B)):tags]` | 多选（代码块） |

### 常用参数
| 参数 | 用法 | 说明 |
|------|------|------|
| `option(value)` | 选择器选项 | 定义可选项 |
| `minValue(n)` | 数值范围 | 最小值 |
| `maxValue(n)` | 数值范围 | 最大值 |
| `stepSize(n)` | 数值步长 | 调整精度 |
| `placeholder(text)` | 占位符 | 输入提示 |
| `defaultValue(value)` | 默认值 | 初始值 |

### VIEW字段功能
| 用法 | 示例 | 说明 |
|------|------|------|
| 显示属性 | `VIEW[{name}]` | 显示frontmatter属性 |
| 数学计算 | `VIEW[{a} + {b}]` | 执行数学运算 |
| 条件显示 | `VIEW[{done} ? "完成" : "未完成"]` | 三元运算符 |
| 函数计算 | `VIEW[Math.max({a}, {b})]` | JavaScript函数 |

### 按钮动作类型
| 动作类型 | 说明 | 主要用途 |
|----------|------|----------|
| `updateMetadata` | 更新元数据 | 修改frontmatter属性 |
| `inlineJS` | 执行JavaScript | 复杂逻辑处理 |
| `createNote` | 创建笔记 | 生成新文件 |
| `command` | 执行命令 | 调用Obsidian命令 |
| `open` | 打开文件/链接 | 导航操作 |

## 💡 使用技巧

### 1. Frontmatter设置
```yaml
---
# 为所有绑定属性设置默认值
title: ""
completed: false
progress: 0
tags: []
---
```

### 2. 数据绑定类型
- **本地绑定**：`property` - 绑定到当前文件
- **跨文件绑定**：`OtherFile#property` - 绑定到其他文件
- **内存绑定**：`memory^temp` - 临时存储
- **全局内存**：`globalMemory^setting` - 全局设置

### 3. 复杂计算示例
```markdown
# 进度百分比
`VIEW[{completed_tasks} / {total_tasks} * 100]`%

# 剩余天数
`VIEW[Math.ceil((new Date("{deadline}") - new Date()) / (1000*60*60*24))]`天

# 多条件判断
`VIEW[{score} >= 90 ? "优秀" : ({score} >= 80 ? "良好" : "一般")]`
```

### 4. 按钮最佳实践
```yaml
# 多动作按钮
```meta-bind-button
label: 完成任务
actions:
  - type: updateMetadata
    bindTarget: completed
    evaluate: false
    value: true
  - type: updateMetadata
    bindTarget: completedDate
    evaluate: true
    value: "new Date().toISOString().split('T')[0]"
  - type: inlineJS
    code: new Notice("任务已完成！", 3000);
```
```

## 🎯 实际应用场景

### 学习笔记
- 课程进度追踪
- 复习计划管理
- 知识点标记
- 学习时间统计

### 项目管理
- 任务状态跟踪
- 进度可视化
- 团队协作
- 风险评估

### 个人管理
- 习惯追踪
- 目标设定
- 阅读记录
- 健康管理

## 🔧 故障排除

### 常见问题
1. **语法错误**：检查括号和引号匹配
2. **属性未定义**：确保frontmatter中已声明属性
3. **按钮不工作**：检查actions语法和缩进
4. **VIEW字段为空**：确认属性名称正确

### 调试技巧
1. 从简单示例开始
2. 逐步添加复杂功能
3. 检查Obsidian控制台错误
4. 参考官方文档和社区

## 📖 参考资源

### 官方文档
- [Meta Bind官方文档](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/)
- [GitHub仓库](https://github.com/mProjectsCode/obsidian-meta-bind-plugin)

### 社区资源
- [Obsidian论坛讨论](https://forum.obsidian.md/tag/meta-bind)
- [示例库](https://github.com/mProjectsCode/obsidian-meta-bind-plugin/tree/master/exampleVault)

---

**提示**：建议先从基础功能演示开始，然后根据需要探索按钮功能和实际应用模板。每个演示文件都可以直接复制使用，也可以作为学习参考。 