<!-- 文件路径：README.md -->

# OpenUniGuide

OpenUniGuide 是一个基于 GitHub 的开源协作知识库，目标是用社区协作的方式，结构化整理全球高校硕士与博士申请的基础信息，包括专业设置、硬性门槛、申请截止日期、重点实验室与官方来源链接。

## 项目愿景

海外研究生申请信息长期存在以下问题：

- 信息分散在学院官网、项目页面、FAQ、实验室主页和教授个人主页中。
- 民间经验贴质量不一，时间点混杂，容易过期。
- 不同学校、国家和项目的字段口径不统一，难以横向比较。
- 申请者重复检索同一类基础信息，社区知识难以沉淀。

OpenUniGuide 希望把这些信息整理成统一、可审查、可追踪来源的 Markdown 数据库，让后来者可以快速定位项目基础情况，并继续补充和校正。

## 当前进度

状态：**初期建设中**

目前项目包含基础目录结构、贡献模板、新加坡国立大学计算机相关硕士/博士项目的样板间文件，以及学校级 `_labs` 实验室目录。NUS CS 两个专业文件用于示范：如何区分官网事实、保守备注、选填扩展和实验室相对路径引用。北美地区已加入 Stanford University PhD in Computer Science，作为美国高校博士项目信息的首个示例。

## 样板间

当前样板间位于：

- `data/Asia/Singapore/National_University_of_Singapore/MSc_Computer_Science.md`
- `data/Asia/Singapore/National_University_of_Singapore/PhD_Computer_Science.md`

样板间的写法原则：

- 能从官网核实的内容，写成确定信息，并附官方链接。
- 官网没有明确数值的字段，不写成硬性门槛。
- 非官方情报必须标注来源和不确定性。
- 跨专业共享的实验室信息放入 `_labs`，专业文件通过相对路径引用。

## 文件树结构

```text
OpenUniGuide/
├── README.md
├── CONTRIBUTING.md
├── _template.md
└── data/
    ├── Asia/
    │   └── Singapore/
    │       └── National_University_of_Singapore/
    │           ├── _labs/
    │           │   ├── README.md
    │           │   ├── NUS_Artificial_Intelligence_Laboratory.md
    │           │   ├── NUS_Data_System_Research_Group.md
    │           │   └── VERSE_Lab.md
    │           ├── MSc_Computer_Science.md
    │           └── PhD_Computer_Science.md
    ├── Europe/
    └── North_America/
        └── USA/
            └── Stanford_University/
                ├── _labs/
                │   ├── README.md
                │   ├── Stanford_Artificial_Intelligence_Laboratory.md
                │   ├── Stanford_Natural_Language_Processing_Group.md
                │   └── Stanford_Statistical_Machine_Learning_Group.md
                └── PhD_Computer_Science.md
```

## 数据组织规则

所有数据统一放在 `data` 文件夹下，并按以下层级组织：

```text
data/大洲/国家/学校/
├── _labs/
│   └── 实验室名称.md
├── 学位_专业.md
└── 学位_专业.md
```

命名规则：

- 大洲、国家、学校、专业和实验室文件均使用英文。
- 单词之间使用下划线 `_` 连接。
- 大洲文件夹当前仅包含 `Asia`、`Europe`、`North_America`。
- 专业文件命名格式为 `Degree_Program.md`，例如 `MSc_Computer_Science.md`、`PhD_Computer_Science.md`。
- 每个学校文件夹下可以包含一个 `_labs` 文件夹，用于存放该校跨专业的重点实验室介绍文件。
- 实验室文件命名格式建议为 `Lab_Name.md`，例如 `NExT_Lab.md`、`NUS_Artificial_Intelligence_Laboratory.md`。

## 学校级实验室目录

`_labs` 是学校级目录，不属于任何单一专业。它适合存放跨专业共享的实验室、研究中心、研究组介绍，例如实验室名称、研究方向、核心教授、主页链接、招生方向和相关项目。

专业文件可以通过相对路径引用同一学校目录下的实验室文件。例如：

```markdown
- 相关实验室: [NExT Lab](_labs/NExT_Lab.md)
```

当多个专业都涉及同一个实验室时，优先在 `_labs` 下维护一份实验室介绍，再由各专业文件引用，避免重复维护和信息不一致。

## 快速开始

1. Fork 本仓库。
2. 复制根目录下的 `_template.md`。
3. 按 `data/大洲/国家/学校/学位_专业.md` 的路径创建或更新专业文件。
4. 如需补充学校级实验室信息，在对应学校目录下的 `_labs` 文件夹中创建 `Lab_Name.md` 文件。
5. 填写所有核心字段，尤其是“官方项目链接”和“最后核实日期”。
6. 提交 Pull Request，并在 PR 描述中附上官网来源链接。

## 重要原则

OpenUniGuide 不是中介宣传页，也不是个人经验贴合集。每一条关键申请信息都应尽量回到官方页面、学院页面、项目手册或实验室主页。无法确认来源的信息，应明确标注为“待核实”，而不是当作事实写入。
