<!-- 文件路径：data/Asia/Singapore/National_University_of_Singapore/_labs/README.md -->

# National University of Singapore - Labs

本目录用于存放 National University of Singapore 跨专业共享的重点实验室、研究中心和研究组介绍。

教授档案位于同级 `_professors/` 目录，用于复用实验室和项目中反复出现的姓名。

## 文件命名

实验室文件建议使用以下格式：

```text
Lab_Name.md
```

示例：

- `Center_for_Intelligent_Sensor_and_MEMS.md`
- `Green_Energy_Management_and_Smart_Grid_Research_Center.md`
- `Optical_Science_and_Engineering_Center.md`
- `Satellite_Technology_And_Research_Centre.md`
- `NUS_Artificial_Intelligence_Laboratory.md`
- `NUS_Data_System_Research_Group.md`
- `VERSE_Lab.md`

## 专业文件引用方式

同一学校目录下的专业文件可以使用相对路径引用实验室文件。下面示例按本文件所在位置书写：

```markdown
- **相关实验室**： [Center for Intelligent Sensor and MEMS](../_labs/Center_for_Intelligent_Sensor_and_MEMS.md)
```

教授档案同样可以用相对路径引用：

```markdown
- **核心教授**： [Leong Tze Yun](../_professors/Leong_Tze_Yun.md)
```

## 建议字段

每个实验室介绍文件建议包含：

- **实验室名称**：
- **所属院系**：
- **研究方向**：
- **核心教授**：
- **主页链接**：
- **相关项目**：
- **相关教授**：
- **最后核实日期**： YYYY-MM-DD
