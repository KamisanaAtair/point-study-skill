# 学习配置示例

适用于 point-study-skill v0.1.0。供 Agent 手动读取，不依赖原生技能安装。

本文件位于技能的 `assets` 目录时用作模板。复制到 `<output_root>/study-config.md` 后，将下面两个路径和课程目录名填写或核实为你的实际选择，即成为运行配置，无须额外激活。若你的真实目录恰好与示例相同，可以保留对应值。不要把运行配置或学习记录写回技能目录。

```yaml
materials_root: 'C:\PointStudy\materials'
output_root: 'C:\PointStudy\outputs'
course_id: 'my-course'
```

配置仅含以上三个字段：

| 字段 | 填写要求 |
|---|---|
| `materials_root` | 现有教材或笔记目录的绝对路径；默认只读。 |
| `output_root` | 本次学习全部新增文件的独立产出目录，使用绝对路径。 |
| `course_id` | 单一目录名，例如 `my-course`；不写完整路径，不含路径分隔符，不使用 `.` 或 `..`。 |

教材目录与产出目录不得相同或互相包含；两者也不得与技能目录相同或互相包含。使用前让 Agent 核对真实路径及访问能力；不能确认时先说明缺失信息，不猜路径。

根据这三个字段派生位置，无须另填路径：

| 位置 | 用途 |
|---|---|
| `<output_root>/study-config.md` | 本次运行配置，供后续手动读取。 |
| `<output_root>/notes/<course_id>/学习进度.md` | 唯一当前教学状态源，首次由 Agent 根据进度模板初始化。 |
| `<output_root>/notes/<course_id>/` | 教学笔记、讲义及必要的课程范围文件。 |
| `<output_root>/code/<course_id>/` | 代码与可运行练习。 |
| `<output_root>/artifacts/<course_id>/` | 截图、运行输出等其他产出，按类型细分。 |

目录按需创建。课程计划和覆盖清单只定义范围、顺序与来源，不另记一份当前进度。学习范围、已有基础、目标和当次时间由对话确认并写入学习进度，不添加为配置字段。
