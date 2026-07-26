<!-- 文件路径：README.md -->

# OpenUniGuide

OpenUniGuide 是一个基于 GitHub 的开源协作知识库，目标是用结构化、可审查、可追溯的方式整理全球高校硕士与博士申请信息，包括专业设置、硬性门槛、申请截止日期、重点实验室和官方来源链接。

## 项目愿景

海外研究生申请信息长期存在以下问题：

- 信息分散在学院官网、项目页面、FAQ、实验室主页和教授个人主页中。
- 民间经验质量不一，时间点混杂，容易过期。
- 不同学校、国家和项目的字段口径不统一，难以横向比较。
- 申请者重复检索同一类基础信息，社区知识难以沉淀。

OpenUniGuide 希望把这些信息整理成统一、可审查、可追溯来源的 Markdown 数据库，方便后来者快速定位项目基础情况，并继续补充和校正。

## 当前进度

状态：**初期建设中**

目前项目包含基础目录结构、贡献模板、新加坡国立大学计算机相关硕士/博士项目的样板间文件，以及学校级 `_labs` 实验室目录。NUS CS 两个专业文件用于示范：如何区分官网事实、保守备注、选填扩展和实验室相对路径引用。北美地区已加入 Carnegie Mellon University M.S. in Neural Technologies、PhD in Computer Science、PhD in Electrical and Computer Engineering（ECE，覆盖 CMU ECE 官方博士项目下的 EE/ECE 研究方向），以及 Stanford University PhD in Bioengineering、PhD in Computer Science、PhD in Electrical Engineering、PhD in Neuroscience、PhD in Statistics 和 PhD in Psychology，作为美国高校项目信息的示例。

## 样板间

当前样板间位于：

- `data/Asia/Singapore/National_University_of_Singapore/MSc_Computer_Science.md`
- `data/Asia/Singapore/National_University_of_Singapore/PhD_Computer_Science.md`

样板间的写法原则：

- 只写能从官网核实的内容，并附官方链接。
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
            ├── Carnegie_Mellon_University/
            │   ├── _labs/
            │   │   ├── README.md
            │   │   ├── Advanced_Chip_Test_Laboratory.md
            │   │   ├── Carnegie_Mellon_Database_Group.md
            │   │   ├── Carnegie_Mellon_Neuroscience_Institute.md
            │   │   ├── Center_for_the_Neural_Basis_of_Cognition.md
            │   │   ├── Claire_and_John_Bertucci_Nanotechnology_Laboratory.md
            │   │   ├── Computer_Architecture_Labs_at_Carnegie_Mellon.md
            │   │   ├── CyLab_Security_and_Privacy_Institute.md
            │   │   ├── Data_Storage_Systems_Center.md
            │   │   ├── Microelectromechanical_Systems_Laboratory.md
            │   │   └── Principles_of_Programming_Group.md
            │   ├── MSc_Neural_Technologies.md
            │   ├── PhD_Computer_Science.md
            │   └── PhD_Electrical_and_Computer_Engineering.md
            └── Stanford_University/
                ├── _labs/
                │   ├── README.md
                │   ├── Stanford_Artificial_Intelligence_Laboratory.md
                │   ├── Stanford_Bio_X.md
                │   ├── Stanford_Brains_in_Silicon_Lab.md
                │   ├── Stanford_Center_on_Longevity.md
                │   ├── Stanford_Center_for_Image_Systems_Engineering.md
                │   ├── Stanford_CLiMB_Lab.md
                │   ├── Stanford_Cognitive_Tools_Lab.md
                │   ├── Stanford_Compression_Forum.md
                │   ├── Stanford_Computation_and_Cognition_Lab.md
                │   ├── Stanford_Data_Science.md
                │   ├── Stanford_Interactive_Perception_and_Robot_Learning_Lab.md
                │   ├── Stanford_Mussallem_Center_for_Biodesign.md
                │   ├── Stanford_Natural_Language_Processing_Group.md
                │   ├── Stanford_Neural_Dynamics_and_Computation_Lab.md
                │   ├── Stanford_NeuroAILab.md
                │   ├── Stanford_Nano_Facilities.md
                │   ├── Stanford_Photonics_Research_Center.md
                │   ├── Stanford_Robotics_and_Embodied_AI_Lab.md
                │   ├── Stanford_Sarafan_ChEM_H.md
                │   ├── Stanford_Statistical_Machine_Learning_Group.md
                │   ├── Stanford_SystemX_Alliance.md
                │   ├── Stanford_Vision_and_Learning_Lab.md
                │   └── Stanford_Wu_Tsai_Neurosciences_Institute.md
                ├── PhD_Bioengineering.md
                ├── PhD_Computer_Science.md
                ├── PhD_Electrical_Engineering.md
                ├── PhD_Neuroscience.md
                ├── PhD_Psychology.md
                └── PhD_Statistics.md
```

## 数据组织规则

所有数据统一放在 `data` 文件夹下，并按以下层级组织：

```text
data/大洲/国家/学校/
├── _labs/
│   └── 实验室名.md
└── 学位_专业.md
```

命名要求：

- 大洲、国家、学校、专业和实验室文件均使用英文。
- 单词之间使用下划线 `_` 连接。
- 大洲文件夹当前仅包含 `Asia`、`Europe`、`North_America`。
- 专业文件命名格式为 `Degree_Program.md`，例如 `MSc_Computer_Science.md`、`PhD_Computer_Science.md`、`PhD_Psychology.md`。
- 每个学校文件夹下可以包含一个 `_labs` 文件夹，用于存放该校跨专业的重点实验室介绍文件。
- 实验室文件命名格式建议为 `Lab_Name.md`，例如 `NExT_Lab.md`、`Stanford_Center_on_Longevity.md`。

## 学校级实验室目录

`_labs` 是学校级目录，不属于任何单一专业。它适合存放跨专业共享的实验室、研究中心和研究组介绍，例如实验室名称、研究方向、核心教授、主页链接、招生方向和相关项目。

专业文件可以通过相对路径引用同一学校目录下的实验室文件。例如：

```markdown
- **相关实验室**： [Stanford Artificial Intelligence Laboratory](_labs/Stanford_Artificial_Intelligence_Laboratory.md)
```

当多个专业都涉及同一个实验室时，优先在 `_labs` 下维护一份实验室介绍，再由各专业文件引用，避免重复维护和信息不一致。

## 快速开始

1. Fork 本仓库。
2. 复制根目录下的 `_template.md`。
3. 按 `data/大洲/国家/学校/学位_专业.md` 的路径创建或更新专业文件。
4. 如需补充学校级实验室信息，在对应学校目录下的 `_labs` 文件夹中新建 `Lab_Name.md`。
5. 填写所有核心字段，尤其是“官方项目链接”和“最后核实日期”。
6. 提交 Pull Request，并在 PR 描述中附上官方来源链接。

## 重要原则

OpenUniGuide 不是中介宣传页，也不是个人经验拼贴集。每一条关键信息都应尽量回到官网、学院页面、项目手册或实验室主页。无法核实的内容，应明确标注为“待核实”，而不是当作事实写入。
