# 🚀 LLM-Based Stock Analysis Agent

> 基于大模型（LLM）的智能股票分析 Agent，支持自然语言查询、自动数据分析与可视化输出

------

## ✨ 项目简介

本项目构建了一个基于大模型的智能股票分析系统，通过 LLM Agent 实现自然语言驱动的数据查询、分析与预测。

用户无需编写 SQL 或数据分析代码，仅通过自然语言即可完成：

- 股票数据查询
- 趋势分析与预测
- 技术指标检测
- 实时金融信息获取

系统具备完整的 **“LLM + 工具调用 + 数据分析”闭环能力**。

------

## 🧠 项目亮点

- 🧩 **多工具协同 Agent（Tool Orchestration）**
   基于 Qwen-Agent，实现 LLM 自动选择工具并执行任务流程
- 🔍 **NL2SQL 自动分析**
   自然语言自动转换为 SQL 并执行，完成数据查询与统计分析
- 📊 **自动可视化输出**
   查询结果自动生成表格 + 图表，无需手动处理
- 📈 **时间序列预测能力**
   集成 ARIMA 与 Prophet，实现短期预测与周期分析
- 📉 **技术指标分析（Bollinger Bands）**
   自动识别股票超买/超卖区间
- 🌐 **联网搜索能力**
   集成 Tavily API，获取最新金融资讯

------

## 🏗️ 系统架构

```
用户输入（自然语言）
        ↓
      LLM（Qwen）
        ↓
   Agent 决策（工具选择）
        ↓
 ┌────────────────────┐
 │ SQL 查询工具        │
 │ ARIMA 预测工具      │
 │ 布林带检测工具      │
 │ Prophet 分析工具    │
 │ Tavily 搜索工具     │
 └────────────────────┘
        ↓
数据处理 + 可视化输出
        ↓
返回结果（文本 + 图表）
```

------

## 🧩 核心功能

### 1️⃣ 自然语言数据查询（NL2SQL）

- 输入：“查询贵州茅台2024年收盘价走势”
- 自动生成 SQL 并执行
- 返回表格 + 图表

------

### 2️⃣ 时间序列预测

- ARIMA
  - 适用于短期预测
- Prophet
  - 分析趋势与周期性变化

------

### 3️⃣ 技术指标分析

- 布林带（Bollinger Bands）
- 自动检测：
  - 超买区间
  - 超卖区间

------

### 4️⃣ 多工具自动调用（Agent）

系统基于 LLM 自动选择最合适的工具：

- 查询数据 → SQL Tool
- 预测趋势 → ARIMA / Prophet
- 分析异常 → Boll Tool
- 获取新闻 → Tavily

------

## 🛠️ 技术栈

- **LLM / Agent：** Qwen-Agent
- **数据处理：** Pandas / SQLAlchemy
- **数据库：** MySQL
- **可视化：** Matplotlib
- **时间序列：** ARIMA / Prophet
- **搜索：** Tavily API
- **核心能力：** Function Calling / Tool Orchestration

## ⚡ 快速开始

### 配置环境变量

```
export TAVILY_API_KEY=your_api_key
export DB_URL=mysql+mysqlconnector://user:password@localhost:3306/bi
```