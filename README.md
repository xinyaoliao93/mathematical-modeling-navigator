# Mathematical Modeling Navigator

> 一个面向中文数学建模、科研分析与论文阅读场景的 Codex Skill：根据研究目标和数据结构筛选模型，并在确定模型后补齐公式、估计、误差、检验、诊断、验证与解释边界。

*A source-grounded Codex skill for selecting, comparing, and validating mathematical models from the research objective and data structure.*

## 它解决什么问题

很多建模困难并不是“不会写代码”，而是：

- 知道一些模型名称，却不清楚当前数据应该用哪一种；
- 在论文中遇到陌生模型，不知道应从哪里可靠地学习；
- 会拟合模型，但容易遗漏独立性、分布、共线性、平稳性等前置条件；
- 确定模型后，忘记检查显著性、误差结构、残差、稳健性或预测验证；
- 面对重复测量、分层、时间、空间或网络数据时，误把观测当作相互独立；
- 只关注结果是否“显著”，却没有说明模型为什么适用以及结论能否推广。

本 Skill 会先识别问题的目标、因变量类型、观测单位和依赖结构，再给出可辩护的候选模型，而不是从一张模型清单中机械匹配。

## 核心功能

### 1. 模型筛选

当你只有研究问题和数据，还没有确定模型时，它会：

1. 判断任务属于描述、关联、解释、因果、预测、评价、优化、控制还是模拟；
2. 识别连续、二分类、多分类、计数、比例、生存时间、多变量等响应类型；
3. 检查独立、配对、重复测量、嵌套、聚类、时间、空间、网络或面板依赖；
4. 给出 2–5 个候选模型，并比较适用条件、优势、风险和淘汰理由；
5. 在信息充分时推荐主模型，同时区分敏感性模型和基准模型。

### 2. 模型深挖

当你已经选定或明确提到某个模型时，它会提醒并补充适用部分：

- 数学公式、符号、参数、随机项、约束和目标量；
- 参数估计或优化方法，以及可识别性、凸性、平稳性等条件；
- 抽样误差、测量误差、过程噪声、参数不确定性和数值误差；
- 显著性检验、置信区间或贝叶斯可信区间（在有推断意义时）；
- 残差、拟合优度、收敛、校准、预测、最优性或稳定性诊断；
- 交叉验证、稳健性、敏感性、失效信号和备选模型；
- 相关与因果、插值与外推、总体适用范围等解释边界。

它不会强行给所有模型套用 p 值：预测模型强调样本外验证和校准，优化模型强调可行性与最优性差距，仿真模型强调验证、重复和蒙特卡洛误差。

### 3. 方案审查

如果你已经有论文、模型方案或分析结果，它会优先检查可能改变结论的问题，例如：

- 因变量分布选错；
- 忽略组内、时间或空间相关性；
- 数据泄漏或错误的验证划分；
- 伪重复、参数不可识别或奇异拟合；
- 用相关关系支持因果结论；
- 只报告显著性而没有报告效应、不确定性和诊断。

## 覆盖的建模主干

模型地图目前覆盖八个主分支：

1. 统计关系与推断：相关系数、回归、广义线性模型、生存分析、混合模型、GEE、因果推断等；
2. 多变量结构与降维：PCA、因子分析、聚类、判别、SEM、PLS 等；
3. 时间序列与纵向动态：ARIMA、ETS、VAR/VECM、GARCH、状态空间、增长曲线等；
4. 空间与时空模型：克里金、Gaussian Process、CAR/SAR/BYM、空间点过程等；
5. 预测、分类与机器学习：正则化、树模型、集成学习、SVM、神经网络、异常检测等；
6. 优化、控制与博弈：LP、MILP、NLP、多目标、随机/鲁棒优化、MDP、MPC、博弈等；
7. 机理、演化与网络：ODE、PDE、差分方程、Markov 链、网络传播、元胞自动机、Agent-based model 等；
8. 评价、决策、仿真与不确定性：AHP、TOPSIS、DEA、模糊评价、排队、可靠性、Monte Carlo、敏感性分析等。

完整导航见 [`references/model-map.md`](references/model-map.md)。混合问题可以跨分支组合，例如“预测后优化”“空间零膨胀计数”“混合效应生存分析”或“仿真优化”。

## 使用前需要什么

### 环境要求

- 支持 Skills 的 Codex 环境；
- Git（使用克隆安装时需要）；
- 需要查证陌生或关键模型时，应允许 Codex 访问相应的官方资料页面。

### 知识要求

不要求你提前知道模型名称，也不要求先写好 Python 或 MATLAB 代码。为了获得更可靠的推荐，最好能说明：

- 你真正想回答的问题；
- 每一行数据代表什么观测单位；
- 因变量和自变量的类型；
- 是否存在同一对象多次测量、班级/医院等分组、时间顺序、空间位置或网络关系；
- 样本量、缺失值、删失、类别不平衡、异常值和零值等情况；
- 最终需要的是解释、预测、排序、决策方案、机制还是情景模拟。

不知道的部分可以直接说“不确定”。Skill 会优先追问那个足以改变模型分支的最小问题。

## 安装

### 方法一：让 Codex 从 GitHub 安装（推荐）

在 Codex 中直接发送：

```text
请从 https://github.com/xinyaoliao93/mathematical-modeling-navigator 安装这个 Skill。
```

安装完成后，在下一轮对话或新任务中调用它。

### 方法二：使用 Git 克隆

Windows PowerShell：

```powershell
git clone https://github.com/xinyaoliao93/mathematical-modeling-navigator.git "$env:USERPROFILE\.codex\skills\mathematical-modeling-navigator"
```

macOS / Linux：

```bash
git clone https://github.com/xinyaoliao93/mathematical-modeling-navigator.git "$HOME/.codex/skills/mathematical-modeling-navigator"
```

如果设置了自定义 `CODEX_HOME`，请把仓库放到对应的 `CODEX_HOME/skills/mathematical-modeling-navigator`。安装后重新开始一轮对话；若目标目录已经存在，请更新现有仓库，不要重复克隆。

### 方法三：下载 ZIP 手动安装

1. 在 GitHub 仓库页面选择 **Code → Download ZIP**；
2. 解压后确认最外层目录中直接包含 `SKILL.md`；
3. 将该目录复制到 Codex 的 `skills` 目录，并命名为 `mathematical-modeling-navigator`；
4. 重新开始一轮对话。

## 如何调用

可以显式调用：

```text
使用 $mathematical-modeling-navigator，根据我的研究目标和数据结构推荐候选模型。
```

也可以直接描述建模问题。Skill 允许在合适的数学建模任务中被自动触发，但显式写出名称最确定。

## 典型提问方式

### 不知道该选什么模型

```text
我有 300 名学生连续 4 次考试成绩，还有班级、性别和学习时长。
我想分析学习时长是否影响成绩，但同一个学生的数据不是独立的。
请使用 $mathematical-modeling-navigator 给出候选模型、适用条件和选择依据，暂时不要写代码。
```

### 比较几个相近模型

```text
我的因变量是计数数据，零值很多，方差明显大于均值。
请比较 Poisson、负二项、零膨胀和 hurdle 模型，并告诉我需要做哪些检验和诊断。
```

### 深挖已选模型

```text
我决定使用线性混合模型。请给出模型公式、固定效应和随机效应的含义、
REML 与 ML 的选择、协方差结构、ICC、显著性分析、残差诊断、奇异拟合和验证方法。
```

### 审查论文或现有方案

```text
这项研究把每个患者的多次随访当成独立样本并做普通线性回归。
请审查这个方案，区分致命问题和可以补救的限制，并提出替代模型。
```

### 确定后再写代码

```text
候选模型中我选择了负二项广义线性混合模型。
先完整列出公式、假设、估计、误差、诊断和验证方案；确认无误后再用 Python 实现。
```

## 一次完整使用通常会得到什么

在信息足够时，推荐结果通常按以下顺序组织：

1. 为什么模型能回答当前问题；
2. 数学形式和参数含义；
3. 前置假设和最低数据要求；
4. 参数估计或求解方法；
5. 误差、协方差和数据依赖结构；
6. 显著性分析或模型对应的验证指标；
7. 诊断方法与失效信号；
8. 敏感性、稳健性、替代方案和解释限制；
9. 经用户确认后的实现计划与代码。

详细检查项见 [`references/model-analysis-checklist.md`](references/model-analysis-checklist.md)。

## 资料来源与准确性策略

默认优先使用五类可信资料：

- SpringerLink 的统计与优化参考工具书；
- Wiley Online Library / Wiley StatsRef；
- Penn State STAT Online；
- NIST/SEMATECH e-Handbook of Statistical Methods；
- MIT OpenCourseWare。

对陌生、冷门、有争议或会实质影响推荐的模型，Skill 会查找具体页面；重要判断尽量由两个相关来源交叉支持。如果这五类来源没有覆盖，它会明确指出缺口，并先询问是否可以扩展到原始论文或其他大学、学会、政府、出版社及官方软件资料，而不是把记忆当成已经核验的事实。

完整的来源策略见 [`references/authoritative-sources.md`](references/authoritative-sources.md)。

## 使用边界

- 这是模型导航、学习与审查工具，不是“包含全世界所有模型”的静态百科；
- 推荐依赖你提供的数据结构，关键信息缺失时应保留条件分支；
- 高相关不代表因果关系，统计显著也不等于模型充分或结果重要；
- 复杂模型必须带来可说明的收益，默认优先选择能回答问题且通过诊断的简单模型；
- 医学、金融、工程安全等高风险结论仍需要领域专家和真实数据验证；
- 代码只在用户确定模型并明确要求实现后生成。

## 仓库结构

```text
mathematical-modeling-navigator/
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
└── references/
    ├── authoritative-sources.md
    ├── model-analysis-checklist.md
    └── model-map.md
```

- `SKILL.md`：触发条件、三种工作模式和行为约束；
- `agents/openai.yaml`：Skill 的显示名称、简介和默认提示词；
- `references/model-map.md`：八大建模分支的模型导航地图；
- `references/model-analysis-checklist.md`：确定模型后的完整分析检查表；
- `references/authoritative-sources.md`：可信来源范围和核验协议。

## 更新

如果使用 Git 安装，可以在 Skill 目录中执行：

```bash
git pull --ff-only
```

更新后重新开始一轮对话，使 Codex 重新加载 Skill。

## 快速试用

安装完成后，可以从这句话开始：

```text
使用 $mathematical-modeling-navigator。我的研究目标是……；
每行数据代表……；因变量是……；观测之间可能存在……依赖；
我最终需要解释/预测/评价/优化……。请先推荐并比较模型，不要写代码。
```

