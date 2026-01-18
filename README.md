# wow-mythic-plus-11.27-class-analysis
Data analysis of Mythic+ class performance for average players (keys 7–14) in WoW patch 11.27 using Warcraft Logs data.

# WoW Mythic+ Class Performance Analysis (Patch 11.27)
# 《魔兽世界》11.27 版本普通玩家大秘境职业强度分析

---

## Project Overview
This project analyzes class and specialization performance in World of Warcraft Mythic+ dungeons
for **average players**, focusing on keystone levels **7–14** in patch **11.27**.

Using data from **Warcraft Logs (WCL)**, the goal is to evaluate **real-world class strength under
controlled difficulty and item level conditions**, rather than top-end or speedrun performance.

## 项目概述
本项目基于 **Warcraft Logs（WCL）** 的真实战斗日志数据，分析《魔兽世界》**11.27 版本**
中 **普通玩家** 在 **大秘境 7–14 层** 区间内，不同职业与专精在 **不同装等条件下的实际表现**。

项目关注的是**真实游戏环境中的职业强度**，而非极端高端玩家或竞速环境下的表现。

---

## Motivation
Most class balance discussions are based on top percentile players or extreme keystone levels.
However, the majority of players participate in mid-range Mythic+ content.

This project aims to answer:
- How do different classes perform for **average players**?
- How much of class performance is driven by **item level** rather than class mechanics?
- Which classes provide **stable and consistent performance** in mid-range keys?

## 项目动机
当前大多数职业强度讨论往往基于 **顶级玩家** 或 **极高层大秘境**，
但这些结论并不能很好地反映 **普通玩家** 的实际体验。

本项目希望回答以下问题：
- 在普通玩家群体中，不同职业的实际表现差异有多大？
- 职业强度在多大程度上受 **装等** 影响，而非职业机制本身？
- 哪些职业在中等层数大秘境中表现 **稳定且可靠**？

---

## Scope and Assumptions
- **Game mode**: Mythic+ Dungeons  
- **Keystone levels**: 7–14  
- **Player segment**: Average (non-elite) players  
- **Patch version**: 11.27  
- **Data source**: Warcraft Logs (WCL)  

Top percentile logs and extreme keystone levels are intentionally excluded to reduce selection bias.

## 分析范围与假设
- **游戏模式**：大秘境（Mythic+）
- **层数范围**：7–14 层
- **玩家群体**：普通玩家（非顶尖玩家）
- **游戏版本**：11.27
- **数据来源**：Warcraft Logs（WCL）

为减少样本偏差，项目**刻意排除了**顶级分位数玩家与极端高层数据。

---

## Key Metrics
- Overall DPS
- DPS normalized by item level (DPS per item level)
- Performance distribution (median, IQR)
- Performance stability across key levels

## 核心指标
- 总体 DPS
- 装等归一化 DPS（单位装等输出）
- 表现分布（中位数、四分位距）
- 不同层数下的表现稳定性

---

## Analysis Pipeline
1. Data collection from Warcraft Logs
2. Data cleaning and filtering
3. Item level and keystone stratification
4. Class and specialization comparison
5. Visualization and interpretation

## 分析流程
1. 从 Warcraft Logs 获取原始数据
2. 数据清洗与筛选
3. 按装等与大秘境层数分组
4. 职业与专精对比分析
5. 可视化与结果解读

---

## Repository Structure
