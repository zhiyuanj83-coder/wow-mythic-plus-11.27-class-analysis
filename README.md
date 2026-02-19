# WoW Mythic+ Class Performance Analysis (Patch 11.27)
### 《魔兽世界》11.27 版本普通玩家大秘境职业强度分析

Data analysis of Mythic+ class performance for average players (keys 7–14) in WoW patch 11.27 using Warcraft Logs data.
本项目基于 Warcraft Logs 的真实战斗数据，分析 11.27 版本中普通玩家（7–14 层）的职业表现。

---

## 1. Project Overview / 项目概述
This project analyzes class and specialization performance in World of Warcraft Mythic+ dungeons for **average players**, focusing on keystone levels **7–14** in patch **11.27**.
Using data from **Warcraft Logs (WCL)**, the goal is to evaluate real-world class strength under controlled difficulty and item level conditions.

本项目基于 **Warcraft Logs (WCL)** 的真实战斗日志数据，分析《魔兽世界》11.27 版本中 **普通玩家** 在 **大秘境 7–14 层** 区间内的实际表现。
项目的核心目标是在控制难度与装等变量的前提下，评估各职业专精的真实强度。

---

## 2. Motivation / 项目动机
Most class balance discussions are based on top percentile players. However, the majority of players participate in mid-range Mythic+ content. This project aims to answer:
* How do different classes perform for **average players**?
* How much of class performance is driven by **item level**?
* Which classes provide **stable and consistent performance**?

大多数平衡性讨论都基于顶级玩家，但绝大多数玩家活跃在中层大秘境。本项目旨在回答：
* 不同职业在普通玩家手中的表现如何？
* 职业表现受 **装等** 的影响程度有多大？
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
* **Frost Death Knight**: The "numerical gold standard" of 11.27 ($n=444$).
* **Fire Mage**: High scores despite low popularity, suggesting **"Survivor Bias"**.

![DPS Ranking](figures/dps_ranking.png)
![DPS Popularity vs Score](figures/dps_pop_vs_score.png)

#### 🔵 坦克赛道 (Tank): Popularity vs. Fragility
* **Protection Warrior**: Remains the most reliable choice for average players.
* **Protection Paladin**: **"Deceptive popularity"** ($n=338$). Significantly **"squishier"** than Warriors.

![Tank Ranking](figures/tank_ranking.png)
![Tank Popularity vs Score](figures/tank_pop_vs_score.png)

#### 🔴 治疗赛道 (Healer): The Shaman Monopoly
* **Restoration Shaman**: Dominates with nearly 40% popularity.
* **Preservation Evoker**: The "hidden gem" with the highest ceiling.

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
