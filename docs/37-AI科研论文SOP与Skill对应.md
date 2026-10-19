# 用AI做科研论文 · 从选题到投稿的完整SOP（对应OpenClaw Medical Skills）

> **日期：** 2026-10-19
> **对应仓库：** https://github.com/FreedomIntelligence/OpenClaw-Medical-Skills

---

## 一、完整SOP流程（7个阶段）

```
选题 → 文献综述 → 研究设计 → 数据分析 → 论文写作 → 投稿准备 → 修回回复
```

---

## 二、每个阶段对应哪个Skill

### 阶段1：选题（找方向、找gap）

**要做什么：**
- 了解某个疾病/领域的研究现状
- 找研究空白（research gap）
- 确定研究问题

**对应Skill：**

| Skill | 干什么 | 什么时候用 |
|-------|--------|-----------|
| **biomedical-search** | 一站式搜索：PubMed+预印本+临床试验+FDA标签 | 刚开始找方向时，快速摸一个领域的全貌 |
| **tooluniverse-disease-research** | 生成疾病研究综述：流行病学、机制、诊断、治疗、在研试验 | 选定某个疾病后，系统了解这个领域 |
| **literature-review** | 系统文献综述：多库检索+规范引用 | 深度文献调研，写综述的基础 |
| **tooluniverse-clinical-guidelines** | 检索临床指南（NICE/WHO/AHA/NCCN等） | 看现有指南还有什么没覆盖的，找临床gap |

**选题SOP：**
1. 先用 biomedical-search 搜一下你感兴趣的方向，看看最近都在发什么
2. 用 tooluniverse-disease-research 生成一份这个疾病的全景综述
3. 对照临床指南，看哪些问题指南还没回答
4. 确定一个具体的研究问题

---

### 阶段2：文献综述

**要做什么：**
- 系统检索相关文献
- 写综述部分
- 找理论依据

**对应Skill：**

| Skill | 干什么 |
|-------|--------|
| **literature-review** | 核心工具：PubMed/arXiv/bioRxiv/Semantic Scholar多库检索，APA/Nature/Vancouver引用格式 |
| **biomedical-search** | 补充搜索，找预印本和最新临床试验 |

**综述SOP：**
1. 用 literature-review 跑一轮系统检索
2. 筛选高相关文献
3. AI帮你整理成结构化综述
4. 手动筛选、补充、修改

---

### 阶段3：研究设计

**要做什么：**
- 确定研究类型（回顾性/前瞻性/RCT/meta分析）
- 写研究方案
- 确定统计方法

**对应Skill：**

| Skill | 干什么 | 适用场景 |
|-------|--------|---------|
| **clinical-trial-protocol-skill** | 生成临床试验方案：设计、样本量、终点、FDA申报文档 | 做RCT或前瞻性研究时 |
| **clinical-decision-support** | 队列分析、治疗推荐、统计图表 | 做临床观察性研究、预后分析 |
| **Data Science & Tools（93个）** | 统计、可视化、模拟工具 | 任何需要统计分析的研究 |

**研究设计SOP：**
1. 确定研究类型
2. 用 clinical-trial-protocol-skill 生成方案框架
3. 调整样本量、终点、纳入排除标准
4. 找统计师确认统计方法

---

### 阶段4：数据分析

**要做什么：**
- 跑统计分析
- 做图表
- 解读结果

**对应Skill：**

| 专业方向 | 对应Skill |
|---------|----------|
| **临床研究** | clinical-decision-support（生存曲线、风险比、瀑布图） |
| **生物信息学** | Bioinformatics gptomics系列239个（变异分析、差异表达、通路、单细胞） |
| **药物研究** | tooluniverse-drug-research（ADMET、药物基因组学） |
| **通用统计** | Data Science & Tools 93个统计/可视化工具 |

**数据分析SOP：**
1. 把数据导入
2. 用对应skill跑分析
3. AI帮你出图、出统计结果
4. 你自己判断结果是否合理

---

### 阶段5：论文写作（IMRAD结构）

**要做什么：**
- 写Introduction
- 写Methods
- 写Results
- 写Discussion

**对应Skill：**

| Skill | 干什么 |
|-------|--------|
| **clinical-reports** | 核心写作工具：SOAP、H&P、出院小结、病例报告（CARE指南）、诊断报告、临床试验报告（ICH-E3/CSR） |
| **literature-review** | 写Introduction的文献支撑 |

**写作SOP：**
1. 用 clinical-reports 搭好论文框架
2. 逐段填充内容
3. Introduction用 literature-review 的文献结果
4. Methods按临床研究规范写
5. Results放图表和统计结果
6. Discussion讨论临床意义和局限性

---

### 阶段6：投稿准备

**要做什么：**
- 选期刊
- 写cover letter
- 调整格式
- 准备补充材料

**对应Skill：**

| Skill | 干什么 |
|-------|--------|
| **clinical-reports** | 按ICH-E3/CSR规范写临床试验报告，直接符合期刊要求 |
| **biomedical-search** | 查目标期刊最近发过什么类似文章 |

**投稿SOP：**
1. 查目标期刊的作者指南
2. 调整论文格式
3. 写cover letter（为什么投这个期刊、创新点是什么）
4. 准备补充材料

---

### 阶段7：修回回复

**要做什么：**
- 回复审稿人意见
- 修改论文
- 写point-by-point response

**对应Skill：**

| Skill | 干什么 |
|-------|--------|
| **clinical-reports** | 按规范修改论文，补数据、补分析 |
| **literature-review** | 审稿人质疑文献支撑时，补充检索 |
| **biomedical-search** | 找最新文献支持你的观点 |

**修回SOP：**
1. 把审稿人意见列出来
2. 逐条回复，需要补分析的补分析
3. 需要补文献的用 literature-review 补
4. 写point-by-point response letter

---

## 三、不同专业领域要选不同Skill

**答案是：要区分。** 不同科室/专业方向，常用的skill不一样。

| 专业方向 | 核心Skill组合 | 说明 |
|---------|-------------|------|
| **临床科室（内/外/妇儿）** | clinical-reports + clinical-decision-support + literature-review | 以临床病例、队列分析为主 |
| **急诊科** | clinical-reports + clinical-decision-support + tooluniverse-clinical-guidelines | 急危重症、分诊、预后 |
| **肿瘤科** | tooluniverse-precision-oncology + clinical-reports + clinical-trial-matching | 精准治疗、临床试验、耐药 |
| **药学/药剂科** | tooluniverse-drug-research + tooluniverse-drug-drug-interaction + tooluniverse-pharmacovigilance | 药物相互作用、ADMET、药物警戒 |
| **生物信息学/基础医学** | Bioinformatics gptomics 239个 + Omics 59个 | 测序分析、单细胞、蛋白组 |
| **公卫/流行病** | Data Science 93个 + clinical-decision-support | 队列研究、统计建模、流行病分析 |
| **罕见病** | tooluniverse-rare-disease-diagnosis + literature-review | HPO表型匹配、Orphanet/OMIM |

---

## 四、怎么用最高效

**不要把869个skill全装上。** 按你的专业方向选5-10个核心的就行。

### 通用核心（所有科室都用）
1. biomedical-search — 搜文献
2. literature-review — 写综述
3. clinical-reports — 写论文
4. clinical-decision-support — 做统计分析

### 按专业再加
- 肿瘤科 → 加 tooluniverse-precision-oncology
- 药学 → 加 tooluniverse-drug-research + drug-interaction
- 生物信息 → 加 gptomics 系列
- 公卫 → 加 Data Science 统计工具

---

## 五、SOP总览表

| 阶段 | 核心Skill | 你自己要做的 |
|------|----------|------------|
| 1. 选题 | biomedical-search + disease-research + clinical-guidelines | 判断什么问题有价值 |
| 2. 文献综述 | literature-review | 筛选真正重要的文献 |
| 3. 研究设计 | clinical-trial-protocol-skill + clinical-decision-support | 确定研究问题和方法 |
| 4. 数据分析 | 对应专业的统计/生信Skill | 判断结果是否合理 |
| 5. 论文写作 | clinical-reports + literature-review | 写你的核心观点和讨论 |
| 6. 投稿准备 | clinical-reports + biomedical-search | 选期刊、写cover letter |
| 7. 修回回复 | clinical-reports + literature-review + biomedical-search | 回复审稿人、补充分析 |

---

*总结：AI帮你做检索、写作、统计这些"苦力活"，你做判断——选什么题、结果是否有意义、讨论怎么写。*
