---
BaseSpeed: 80
SpeedMultiplier: 0.5
HoursPerDay: 8
TravelDistance: 65
MilesPerHour: 3
TemperatureMaxTravelHours: 2
---

### PF2e 旅行计算器

# 旅行速度
更新下面的计算器会将更改传播到任何自动计算旅行距离的笔记。你需要刷新此笔记才能看到计算更改。

| PF2e Travel Calculator                                                                                                                                                                                                                                                                                                                          |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **队伍速度 (最慢的):** `INPUT[inlineSelect(option(1, 10英尺), option(1.5, 15英尺), option(2, 20英尺), option(2.5, 25英尺),  option(3, 30英尺),  option(3.5, 35英尺),  option(4, 40英尺),  option(5, 50英尺),  option(6, 60英尺)):MilesPerHour]`                                                                                    |
| **地形类型:** `INPUT[inlineSelect(option(1, 普通地形), option(0.5, 困难地形), option(0.333333, 更困难地形)):SpeedMultiplier]`                                                                                                                                                                                 |
| **温度:** `INPUT[inlineSelect(option(2, 极度严寒 - 每分钟中等伤害), option(4, 极端严寒 - 每10分钟轻微寒冷伤害), option(4, 严重严寒 - 每小时轻微寒冷伤害), option(4, 轻度严寒 - 无), option(8, 正常 - 无), option(4, 轻度炎热 - 无), option(4, 严重炎热 - 每小时轻微火焰伤害), option(4, 极端炎热 - 每10分钟轻微火焰伤害), option(2, 极度炎热 - 每分钟中等火焰伤害)):TemperatureMaxTravelHours]` |
| **每日最大旅行小时数:** `VIEW[round({TemperatureMaxTravelHours},1)]`                                                                                                                                                                                                                                                                      |
| **每日旅行小时数:** `INPUT[number:HoursPerDay]` `VIEW[{HoursPerDay}>{TemperatureMaxTravelHours} ? "遭受疲劳" : "无疲劳"]`                                                                                                                                                                                                                                                                          |
| **旅行距离 (英里):**  `INPUT[number:TravelDistance]`                                                                                                                                                                                                                                                                                            |
| **每日旅行距离:** `VIEW[round({MilesPerHour}*{HoursPerDay},1)]` 英里                                                                                                                                                                                                                                                            |
| **旅行天数 🕓:** `VIEW[round({TravelDistance} / (({MilesPerHour}*{HoursPerDay})*{SpeedMultiplier}),1)]`                                                                                                                                                                                                                                                                                                                                                |

## 表格 10-11: 环境伤害

| **类别** | **伤害** |
| ------------ | ---------- |
| Minor        | 1d6-2d6    |
| Moderate     | 4d6-6d6    |
| Major        | 8d6-12d6   |
| Massive      | 16d6-24d6  |
