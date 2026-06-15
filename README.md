# A4 Machine Learning Projects — 教师指南

**IB DP Computer Science 2027 · Oxford Course Companion 对标**
**Foundation (SL+HL) + Extension (HL Only)**

---

## 📋 总览

| 项目数量 | 数据集 | 总 HTML 数 | Notebooks | 总课时 |
|---------|--------|-----------|-----------|--------|
| 10 | 5 个真实数据集 | 11 (含 index) | 10 | 16-18 |

### 两套项目的衔接

```
Foundation (Suite 1: 项目 1-6)
    │ 8 课时 (SL 可止于课时 8)
    │ HL 继续
    ▼
Extension (Suite 2: 项目 7-10)
    │ 8-10 课时 (HL only)
    │
    ▼
IA 选题 / Paper 2 备考
```

---

## 🗓️ 课时安排

### Suite 1: Foundation（SL + HL）

| 课时 | 项目 | 内容 | 考点 | SL/HL |
|------|------|------|------|-------|
| 1-2 | P1: EDA & ML Types | 加载真实数据、三种 ML 类型、数据可视化、硬件讨论 | A4.1.1-2 | SL ✅ 可止于此 |
| 3-4 | P2: Data Preprocessing | 缺失值、异常值、特征选择、PCA | A4.2.1-3 | HL |
| 5 | P3: Linear Regression | 一元/多元回归、r²、残差分析、Ridge/Lasso | A4.3.1, 3.3 | HL |
| 6-7 | P4: Hyperparameter Tuning | K-Fold CV、Grid Search、学习曲线、过拟合 | A4.3.3 | HL |
| 7½ | P5: Classification Demo | K-NN, Decision Tree, 分类指标 | A4.3.2 | HL |
| 8 | P6: Ethics & Bias | 算法偏见、隐私、环境成本、讨论 | A4.4.1-2 | SL ✅ |

### Suite 2: Extension（HL Only）

| 课时 | 项目 | 内容 | 考点 |
|------|------|------|------|
| 1-2 | P7: Customer Churn | 特征工程、混淆矩阵、ROC AUC、Precision/Recall | A4.3.2-3 |
| 3-4 | P8: Customer Segmentation | K-Means、层次聚类、DBSCAN、Silhouette | A4.3.4 |
| 5 | P9: Market Basket | Apriori、Support/Confidence/Lift | A4.3.5 |
| 6-8 | P10: ANN vs CNN | ANN 架构、CNN 卷积、模型选择、Fashion-MNIST | A4.3.8-10 |

---

## 🎯 差异化教学提示

### 对 SL 学生（只完成 Suite 1）

| 需要涵盖 | 不需要涵盖 |
|----------|-----------|
| A4.1.1 — 三种 ML 类型及例子 | A4.3.1 — 线性回归公式推导 |
| A4.1.2 — 硬件需求对比 | A4.3.2 — K-NN / Decision Tree |
| A4.4.1 — 伦理影响 | A4.3.3 — 超参数调优 |
| A4.4.2 — 技术融入生活 | A4.2.1-3 — 数据预处理细节 |
| 基础 EDA、数据可视化 | |

**策略:** 让 SL 学生完成 P1 的 EDA + visualized ML types，然后跳到 P6 做伦理讨论。P2-P5 可以作为扩展阅读，不要求掌握。

### 对 HL 学生

全部 10 个项目都要完成。重点关注:

- **Paper 1 考点:** 概念对比（监督 vs 无监督、K-NN vs 决策树、ANN vs CNN）
- **Paper 2 考点:** 真实数据分析能力（读懂输出、解释指标、评估模型）
- **IA 素材:** 每个项目都可以作为 IA 的起点

### 对学有余力的学生

- 尝试不同的数据集（Kaggle 上找同类型数据）
- 尝试更复杂的模型（Random Forest, XGBoost, Transfer Learning）
- 调参实验（对比不同 Grid Search 范围对结果的影响）
- 部署演示（用 Streamlit 把模型做成 Web App）

---

## 📝 评估建议

### 形成性评估（每节课后）

- Check Your Understanding 问题（每个 HTML 最后都有）
- 课堂口头问答: "解释 ROC AUC 的含义"
- 小测验: 用 Python Tutor 或 Google Forms

### 总结性评估

| 形式 | 内容 | 时长 | 分值 |
|------|------|------|------|
| Paper 1 风格 | 概念题 + 短答题（参考 Mock Exams 已有材料） | 60min | 100 |
| Paper 2 风格 | Case Study 分析题（给一个新数据集，要求学生写代码/解释结果） | 90min | 100 |
| IA 提案 | 用 Project 2 的方法 → 学生自己的数据集 | 课后 | IA 评分 |

---

## 💡 课堂技巧

### 如何用 HTML 文件上课

1. **课前:** 在浏览器打开对应 HTML，投影到屏幕
2. **讲解:** 先看代码（学生看到真实 Python 代码），再看输出结果
3. **演示:** 点击 **▶ Run in Colab** → 直接在浏览器运行 notebook
4. **练习:** 学生在自己电脑上打开 Colab → 修改参数 → 观察变化

### 无网络环境

所有 HTML 是自包含的（图片内嵌）。数据集已打包在 `datasets/` 目录。学生可以下课后再运行 Colab。

### 常见学生问题与答案

| 学生问 | 回答 |
|--------|------|
| "这些代码我写不出来" | 不用写，先读代码、运行、改参数。IB 不考手写 ML 代码。 |
| "r² 怎么算的？" | 不要求推导。理解 r² 是「模型解释了多少方差」就行。 |
| "考试会考这些吗？" | Paper 1 考概念，Paper 2 考分析能力。会读输出、会解释、会评估。 |
| "我可以用这个做 IA 吗？" | ✅ 完全可以。参考 IA 衔接文档。 |

---

## 🔗 参考链接

- **GitHub 仓库:** https://github.com/lucyyuhongxia-gmail/A4_ML_Projects
- **Colab:** 每个 HTML 顶部有 ▶ 按钮
- **Oxford Course Book:** `D:\ibcs-2027\1.MaterialBank\0.CourseBook\`
- **Syllabus:** `D:\ibcs-2027\1.MaterialBank\0.Syllabus\`
- **已有 Mock Exams:** `D:\ibcs-2027\1.MaterialBank\1.PastPaper\`

---

_Last updated: 2026-06-15 · Victor 🧠_
