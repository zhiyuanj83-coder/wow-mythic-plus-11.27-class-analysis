# WoW Mythic+ Class Performance Analysis (Patch 11.27)
### 《魔兽世界》11.27 版本普通玩家大秘境职业强度分析

Data analysis of Mythic+ class performance for average players (keys 7–14) in WoW patch 11.27 using Warcraft Logs data.
本项目基于 Warcraft Logs 的真实战斗数据，分析 11.27 版本中普通玩家（7–14 层）的职业表现。

---

## 1. Project Overview / 项目概述
This project analyzes class and specialization performance in World of Warcraft Mythic+ dungeons for **average players**, focusing on keystone levels **7–14** in patch **11.27**.
Using data from **Warcraft Logs (WCL)**, the goal is to evaluate real-world class strength under controlled difficulty and item level conditions.

本项目基于 **Warcraft Logs (WCL)** 的真实战斗日志数据，分析《魔兽世界》11.27 版本中 **普通玩家** 在 **大秘境 7–14 层** 区间内的实际表现。
项目的核心目标是在控制难度与装等变量的前提下，评估各职业专精的真实强度，而非单纯关注顶尖选手的竞速表现。

---

## 2. Motivation / 项目动机
Most class balance discussions are based on top percentile players. However, the majority of players participate in mid-range Mythic+ content. This project aims to answer:
* How do different classes perform for **average players**?
* How much of class performance is driven by **item level**?
* Which classes provide **stable and consistent performance**?

大多数平衡性讨论都基于顶级玩家或极限层数，但绝大多数玩家活跃在中层大秘境。本项目旨在回答：
* 不同职业在普通玩家手中的实际表现如何？
* 职业表现受 **装等** 的影响程度有多大，还是主要取决于机制？
* 哪些职业在中层大秘境中表现得最为 **稳定可靠**？

---

## 3. Scope & Metrics / 范围与指标
* **Game Mode / 模式**: Mythic+ Dungeons (7–14 Keys)
* **Patch / 版本**: 11.27
* **Data Source / 数据源**: Warcraft Logs (WCL)
* **Key Metrics / 核心指标**: Overall DPS, Score distribution, and Popularity (Sample size $n$).

---

## 4. Key Insights & Conclusion / 核心洞察与结论

### 4.1 Role-Specific Analysis / 职责深度剖析

#### 🟢 输出赛道 (DPS): Frost DK Dominance & Fire Mage Paradox
* **Frost Death Knight**: The "numerical gold standard" of 11.27 ($n=444$), showing high mean scores across all analyzed tiers.
* **Fire Mage**: A high-tier performer despite low popularity, suggesting **"Survivor Bias"**—likely piloted by specialists in this bracket.
* **冰DK**: 11.27 版本的数值标杆，拥有极高的平均分和庞大的样本量 ($n=444$)，是当前版本的强势首选。
* **火法**: 一个有趣的异常点。虽然出场率较低但评分处于第一梯队。这反映了明显的 **“幸存者偏差”**——目前在 7-14 层坚持玩火法的多为对该职业有极高熟练度的老手，而非普通跟风玩家。

![DPS Ranking](figures/dps_ranking.png)
![DPS Popularity vs Score](figures/dps_pop_vs_score.png)

#### 🔵 坦克赛道 (Tank): Popularity vs. Fragility
* **Protection Warrior**: Remains the most reliable choice for average players due to robust physical mitigation.
* **Protection Paladin**: Exhibits **"deceptive popularity"** ($n=338$). It is significantly **"squishier"** than Warriors in 11.27, requiring higher player proficiency.
* **防战**: 凭借扎实的物理减伤和稳定的硬度，依然是普通玩家最可靠、容错率最高的选择。
* **防骑**: 呈现出 **“虚假的人气繁荣”** ($n=338$)。虽然功能性极其强大（打断、辅助位），但数据和实战反馈显示其硬度明显弱于防战，对于普通玩家来说，在高层更容易出现突然暴毙的情况。

![Tank Ranking](figures/tank_ranking.png)
![Tank Popularity vs Score](figures/tank_pop_vs_score.png)

#### 🔴 治疗赛道 (Healer): The Shaman Monopoly
* **Restoration Shaman**: Dominates the bracket with nearly 40% popularity while staying in the top performance tier.
* **Preservation Evoker**: The "hidden gem" for上分, showing the highest ceiling in scores but suffering from a steep learning curve.
* **奶萨**: 统治级表现，出场率接近 40% 且评分稳居第一梯队。其简单粗暴的治疗量和功能性使其成为版本的“官方答案”。
* **奶龙**: “上分利器”，拥有极高的评分上限，但由于操作门槛和英雄天赋理解要求较高，在大众群体中普及率较低，处于典型的“高手专属”象限。

![Healer Ranking](figures/healer_ranking.png)
![Healer Popularity vs Score](figures/healer_pop_vs_score.png)

---

## 5. Repository Structure / 仓库结构

```text
├── data/
│   ├── raw/                # Original WCL API exports
│   └── processed/          # Cleaned dataset (mplus_S3_7_14_CLEANED.csv)
├── figures/                # Exported analysis charts
│   ├── dps_ranking.png     # DPS performance rankings
│   ├── dps_pop_vs_score.png   # DPS popularity quadrant
│   ├── tank_ranking.png    # Tank performance rankings
│   ├── tank_pop_vs_score.png  # Tank popularity quadrant
│   ├── healer_ranking.png  # Healer tier distribution
│   └── healer_pop_vs_score.png # Healer popularity quadrant
├── notebooks/
│   ├── 02_data_cleaning.ipynb # Data preprocessing logic
│   └── 03_analysis.ipynb      # Main visualization logic
└── README.md
```
---

## 6. Analysis Pipeline / 分析流程
1. **Data collection**: Extracting raw battle logs via Warcraft Logs API.
2. **Data cleaning**: Stratifying data by item level and filtering for keystone levels 7–14.
3. **Role Sharding**: Segregating data into DPS, Tank, and Healer subsets to ensure intra-role fairness.
4. **Visualization**: Generating distribution plots and popularity-score quadrants to identify Meta outliers.

1. **数据采集**：通过 Warcraft Logs API 提取原始战斗日志。
2. **数据清洗**：按装等分层并筛选 7–14 层核心数据。
3. **职责分流**：将数据切分为输出、坦克、治疗子集，确保职责内部对比的公平性。
4. **可视化分析**：生成表现分布图与流行度-评分象限图，识别版本强势与异常职业。
