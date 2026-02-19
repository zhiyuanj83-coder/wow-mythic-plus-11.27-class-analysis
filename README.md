# WoW Mythic+ Class Performance Analysis (Patch 11.27)
### 《魔兽世界》11.27 版本普通玩家大秘境职业强度分析

Data analysis of Mythic+ class performance for average players (keys 7–14) in WoW patch 11.27 using Warcraft Logs data.

---

## 1. Project Overview / 项目概述
This project analyzes class and specialization performance in World of Warcraft Mythic+ dungeons for **average players**, focusing on keystone levels **7–14** in patch **11.27**.
Using data from **Warcraft Logs (WCL)**, the goal is to evaluate real-world class strength under controlled difficulty and item level conditions, rather than top-end or speedrun performance.

本项目基于 **Warcraft Logs（WCL）** 的真实战斗日志数据，分析《魔兽世界》11.27 版本中 **普通玩家** 在 **大秘境 7–14 层** 区间内，不同职业与专精在不同装等条件下的实际表现。
项目关注的是真实游戏环境中的职业强度，而非极端高端玩家或竞速环境下的表现。

---

## 2. Motivation / 项目动机
Most class balance discussions are based on top percentile players or extreme keystone levels. However, the majority of players participate in mid-range Mythic+ content.
This project aims to answer:
* How do different classes perform for **average players**?
* How much of class performance is driven by **item level** rather than class mechanics?
* Which classes provide **stable and consistent performance** in mid-range keys?

本项目希望回答以下问题：
* 在普通玩家群体中，不同职业的实际表现差异有多大？
* 职业强度在多大程度上受 **装等** 影响，而非职业机制本身？
* 哪些职业在中等层数大秘境中表现 **稳定且可靠**？

---

## 3. Scope & Metrics / 范围与指标
* **Game Mode**: Mythic+ Dungeons (7–14 Keys)
* **Player Segment**: Average (non-elite) players
* **Patch**: 11.27
* **Data Source**: Warcraft Logs (WCL)
* **Key Metrics**: Overall DPS, Score distribution, Popularity (Sample size $n$), and Stability.

---

## 4. Key Insights & Conclusion / 核心洞察与结论

### 4.1 Role-Specific Analysis / 职责深度剖析

* **DPS: Frost DK Dominance & The Fire Mage Paradox / 输出赛道：冰DK的统治力与火法悖论**
    * **Frost Death Knight**: The "numerical gold standard" of 11.27, showing high mean scores and a massive sample size ($n=444$).
    * **Fire Mage**: A significant finding where a low-popularity spec maintains high-tier scores. This suggests **"Survivor Bias"**—it is primarily played by high-proficiency specialists in this bracket.
    * **Shadow Priest**: Despite its high community interest, performance is highly sensitive to affixes, placing it in a stable median tier.

* **Tank: Popularity vs. Fragility / 坦克赛道：流行度与“脆度”的博弈**
    * **Protection Warrior**: Remains the most reliable choice for average players due to robust physical mitigation and straightforward utility.
    * **Protection Paladin**: Exhibits **"deceptive popularity"** ($n=338$). While utility is high, it is significantly **"squishier"** than Warriors in 11.27, requiring much higher player proficiency to manage survival.
    * **Brewmaster Monk**: Maintains a stable but niche position with competitive scores.

* **Healer: The Shaman Monopoly / 治疗赛道：奶萨的断层垄断**
    * **Restoration Shaman**: Dominates the bracket with nearly 40% popularity while staying in the top performance tier.
    * **Preservation Evoker**: The "hidden gem" for climbing. It shows the highest ceiling in scores but suffers from a steep learning curve among average players.

### 4.2 Statistical Observations / 统计学总结
* **Meta Efficiency**: Scatter plot analysis reveals a clear gap between **"Community Meta"** (high popularity) and **"Data Meta"** (high performance).
* **Hero Talent Impact**: Preliminary results suggest that 11.27's hierarchy is heavily dictated by **Hero Talent** synergy with specific dungeon mechanics than base class tuning.

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
│   └── 03_analysis.ipynb      # Main visualization & statistical logic
└── README.md
