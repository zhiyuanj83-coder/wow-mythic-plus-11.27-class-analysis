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

* **DPS: Frost DK Dominance & The Fire Mage Paradox / 输出赛道：冰DK的统治力与火法悖论**
    * **Frost Death Knight**: The "numerical gold standard" of 11.27, showing high mean scores and massive popularity ($n=444$).
    * **Fire Mage**: A significant finding where a low-popularity spec maintains high-tier scores. This suggests **"Survivor Bias"**—it is primarily played by specialists.
    * **Shadow Priest**: High community interest, but performance is highly sensitive to dungeon affixes.

    * **冰DK**: 11.27 版本的数值标杆，拥有极高的平均分和庞大的样本量 ($n=444$)。
    * **火法**: 一个意外发现，虽然人气较低但评分极高。这暗示了 **“幸存者偏差”**——目前该专精主要由高熟练度的绝活玩家在使用。
    * **暗牧**: 玩家基数大，但表现受词缀影响波动显著。

* **Tank: Popularity vs. Fragility / 坦克赛道：流行度与“脆度”的博弈**
    * **Protection Warrior**: Remains the most reliable choice for average players due to robust physical mitigation.
    * **Protection Paladin**: Exhibits **"deceptive popularity"** ($n=338$). It is significantly **"squishier"** than Warriors, requiring higher player proficiency.

    * **防战**: 凭借扎实的物理减伤，依然是普通玩家最可靠的选择。
    * **防骑**: 呈现出 **“虚假的人气繁荣”** ($n=338$)。虽然功能性强，但实际硬度明显弱于战士，对玩家操作水平要求更高。

* **Healer: The Shaman Monopoly / 治疗赛道：奶萨的断层垄断**
    * **Restoration Shaman**: Dominates with nearly 40% popularity while staying in the top performance tier.
    * **Preservation Evoker**: The "hidden gem" with the highest ceiling but a steep learning curve.

    * **奶萨**: 统治级表现，出场率接近 40% 且评分稳居第一梯队。
    * **奶龙**: “上分利器”，拥有极高的上限，但由于上手门槛高，在大众群体中普及率较低。

---

## 5. Repository Structure / 仓库结构
```text
├── data/
│   ├── raw/                # Original WCL API exports
│   └── processed/          # Cleaned dataset (mplus_S3_7_14_CLEANED.csv)
├── figures/                # Exported analysis charts
│   ├── dps_ranking.png     # DPS performance rankings
│   ├── tank_pop_vs_score.png  # Tank popularity quadrant
│   └── healer_ranking.png  # Healer tier distribution
├── notebooks/
│   ├── 02_data_cleaning.ipynb # Data preprocessing logic
│   └── 03_analysis.ipynb      # Main visualization logic
└── README.md

