# A4 ML Projects → IA 转化指南

**IB DP Computer Science Internal Assessment · 用 ML 项目做 IA**

---

## 🎯 为什么这些项目适合 IA

IB CS IA 评分标准有 5 个 criteria:
- **A: Planning** (6) — 问题定义 + 标准衡量成功
- **B: Solution Overview** (6) — 系统设计 + 技术说明
- **C: Development** (12) — 代码实现 + 测试
- **D: Functionality & Extensibility** (6) — 功能完整 + 可扩展
- **E: Evaluation** (6) — 评估 + 未来改进

ML 项目天然满足:
- **Planning:** 有明确的预测目标、可量化的成功指标（准确率、r²）
- **Development:** 完整的数据处理→建模→评估 pipeline
- **Evaluation:** 有客观的指标对比（baseline vs 改进后）

---

## 🔄 从项目到 IA 的转化策略

### 策略 1: 换数据集（推荐 ⭐）

**最简单、最安全的 IA 路径。**

| 项目 | 原数据 | 你可以换成 |
|------|--------|-----------|
| P3 房价预测 | California Housing | **本地房价数据**、Kaggle 上的 Real Estate 数据集 |
| P7 客户流失 | Telco Churn | **学校相关流失**、会员订阅流失、游戏玩家流失 |
| P8 客户分群 | Mall Customers | **学生成绩分组**、电商用户分群、社交媒体用户 |
| P9 购物篮 | Online Retail | **学校食堂购买记录**、图书馆借书记录 |
| P10 图像分类 | Fashion-MNIST | **手写汉字**、水果分类、交通标志 |

**怎么做:**
1. 找到类似结构的新数据集 (Kaggle / 公开数据)
2. 套用项目中的代码框架
3. 修改特征处理适配新数据

### 策略 2: 换问题（中等难度）

| 原项目 | 原问题 | 你可以改成 |
|--------|--------|-----------|
| P3 回归 | 预测房价 | 预测考试成绩、预测能源消耗、预测二手手机价格 |
| P7 分类 | 预测流失 | 预测考试及格/不及格、预测疾病风险、预测贷款违约 |
| P8 聚类 | 客户分群 | 学习策略分群、阅读偏好分群、运动类型分群 |

### 策略 3: 组合多个项目（高难度）

把 P2 的数据预处理 + P3 的建模 + P4 的调参 + P6 的偏见检测组合成一个完整的 IA。

---

## 📋 IA 提案模板

用这个模板快速生成 IA 提案:

### Section A: Planning

```
**Title:** Predicting [Your Target] Using Machine Learning

**Problem:** [描述问题]。例如 "学校食堂每天浪费大量食物，
因为无法预测每天的就餐人数。"

**Stakeholder:** [谁需要这个方案]。例如 "食堂经理"

**Success Criteria:**
1. Model achieves R² > 0.70 on test data
2. Prediction error < 15% of actual values
3. System can process new data in under 5 seconds
4. Model is interpretable (top features identified)
```

### Section B: Solution Overview

```
**Dataset:** [来源 + 行数 + 特征数]
**ML Task:** [回归/分类/聚类]
**Algorithms:** [至少对比 2 种]
**Evaluation:** [r² / RMSE / Accuracy / F1]

**Diagram:**
[画出 ML pipeline: 数据 → 清洗 → 特征工程 → 训练 → 评估]
```

### Section C: Development

基于项目的代码，但要展示:
1. **你自己的数据处理** — 不直接复制，要适配新数据
2. **多项测试** — 不同参数、不同算法、不同数据拆分
3. **错误处理** — 数据有问题时怎么办？
4. **优化过程** — 从 baseline 到改进的步骤记录

### Section D: Functionality

```
**Working features:**
- 数据加载与清洗 ✅
- 特征选择 ✅
- 模型训练 ✅
- 结果评估 (r²/RMSE/混淆矩阵) ✅
- 可视化 ✅

**Extensibility:**
- 支持新数据一键预测
- 可通过修改 config 切换算法
- 可添加更多特征
```

### Section E: Evaluation

```
**Results:**
| Metric | Baseline | Improved | Target |
|--------|----------|----------|--------|
| R²     | 0.47     | 0.58     | 0.70   |

**Limitations:**
- 数据仅来自 [源]，可能不具普遍性
- 未考虑 [某些重要特征]
- 模型可能在 [特定子集] 上有偏见

**Improvements:**
- 收集更多数据 (2025-2026 年)
- 尝试集成方法 (Random Forest)
- 部署为 Web App
```

---

## ⚠️ 常见扣分点与避免方法

| 扣分点 | 原因 | 避免方法 |
|--------|------|----------|
| 代码无注释 | IA 需要说明你做了什么 | 每段关键代码至少一行注释 |
| 没有对比 baseline | 看不出模型的改进 | 先做一个简单模型（均值预测、简单回归） |
| 数据太小 | 100 行以下说服力不足 | 至少 500 行（时间序列可 200+） |
| 只有准确率没分析错误 | IB 看重反思能力 | 分析 confusion matrix / residual plot |
| 项目不是原创 | 直接复制不被认可 | 换数据、换问题、改进方法 |
| 忽略了伦理 | A4.4 是考点 | 加一段偏见分析 / 隐私讨论 |

---

## 💡 IA 选题灵感

### 校内数据（High-scoring）

1. **学生成绩预测** — 用月考成绩预测期末成绩（回归）
2. **课程选择推荐** — 根据兴趣偏好推荐课程（分类/聚类）
3. **图书借阅分析** — 哪些书常被一起借？（关联规则）
4. **食堂人流预测** — 根据时间/天气预测就餐人数（回归）

### 公开数据集（Kaggle）

1. **Titanic** — 经典生存预测（分类，Kaggle 入门）
2. **Wine Quality** — 红酒品质评分（回归/分类）
3. **Heart Disease** — 心脏病风险预测（分类）
4. **Video Game Sales** — 游戏销量预测（回归）
5. **Mental Health Survey**  — 心理健康分析（聚类/分类）

---

## 📎 参考资源

- **本项目代码:** 作为代码框架直接使用
- **Kaggle:** https://kaggle.com — 找数据集
- **UCI ML Repository:** https://archive.ics.uci.edu/ml — 经典数据集
- **Google Dataset Search:** https://datasetsearch.research.google.com

---

_用真实数据，做真实分析，拿高分 IA。— Victor 🧠_
