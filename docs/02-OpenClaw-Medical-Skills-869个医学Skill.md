# OpenClaw Medical Skills · 全球最大开源医学AI技能库（869个）

> **GitHub**: [FreedomIntelligence/OpenClaw-Medical-Skills](https://github.com/FreedomIntelligence/OpenClaw-Medical-Skills)
> **定位**: 港大HKUDS生态开源，为OpenClaw/NanoClaw设计的医学Agent技能库
> **协议**: MIT
> **兼容**: Claude Code / Cursor / Codex CLI / Windsurf / Copilot / 任何MCP兼容工具

## 一句话

869个医学Skill，让Claude Code/Cursor直接变成临床+科研双栖助手，已接入PubMed、ClinicalTrials.gov、ChEMBL、DrugBank、FDA等真实数据库。

每个Skill是一个独立的 `SKILL.md` 文件，遵循开放Agent Skills标准。

## 869个Skill分类总览

| 类别 | 数量 | 覆盖范围 |
|------|------|----------|
| General & Core | 10 | 浏览器/搜索、文档工具、开发者工作流基础件 |
| **Medical & Clinical** | **119** | 临床报告、CDS、肿瘤、影像、医疗AI |
| Scientific Databases | 43 | 基因组/蛋白/药物数据库，生物医学知识检索 |
| Bioinformatics (gptomics) | 239 | 变异分析、测序QC、差异表达、通路、单细胞、表观组 |
| Omics & Computational Biology | 59 | 单细胞/空间、蛋白质组、化学信息学、蛋白设计 |
| ClawBio Pipelines | 21 | scRNA/GWAS/祖源/结构工作流编排 |
| **BioOS Extended Suite** | **285** | 肿瘤、免疫、临床AI、基础设施扩展套件 |
| Data Science & Tools | 93 | 统计、可视化、自动化、模拟、科研工具 |
| **合计** | **869** | 聚合自12+开源Skill仓库 |

## 和医生日常最相关的核心Skill

### 临床文书与决策（直接可用）

| Skill | 干什么 |
|-------|--------|
| **clinical-reports** | 写临床报告：病例报告(CARE指南)、放射/病理/检验诊断报告、临床试验报告(ICH-E3/CSR)、患者文档(SOAP、H&P、出院小结)。HIPAA/FDA/ICH-GCP合规 |
| **clinical-decision-support** | 生成CDS文档：患者队列分析(生物标志物分层+结局)、治疗推荐报告(GRADE证据分级+决策算法)、风险比/生存曲线/瀑布图 |
| **tooluniverse-clinical-guidelines** | 检索12+来源临床指南：NICE、WHO、ADA、AHA/ACC、NCCN、SIGN、CPIC等。覆盖心内科、肿瘤、糖尿病、药物基因组学 |
| **tooluniverse-disease-research** | 生成疾病研究综述：流行病学、机制、诊断、治疗、在研试验 |
| **tooluniverse-drug-drug-interaction** | 药物相互作用预测：CYP450/转运体机制、严重程度分级、处理策略。支持多药联用(3+种)分析和替代药推荐 |
| **tooluniverse-pharmacovigilance** | 药物安全信号分析：FDA不良事件报告、PRR/ROR计算、严重不良事件识别、药物基因组学风险评估 |
| **tooluniverse-rare-disease-diagnosis** | 罕见病鉴别诊断：表型匹配HPO术语、Orphanet/OMIM候选疾病、变异意义解读 |
| **literature-review** | 系统文献综述：PubMed/arXiv/bioRxiv/Semantic Scholar多库检索，APA/Nature/Vancouver引用格式输出 |
| **biomedical-search** | 生物医学一站式搜索：PubMed+预印本+临床试验+FDA药品标签，Valyu语义搜索驱动 |

### 科研与新药研发

| Skill | 干什么 |
|-------|--------|
| **tooluniverse-drug-research** | 药物全景报告：身份、药理学、靶点、临床试验、安全性、药物基因组学、ADMET |
| **tooluniverse-drug-repurposing** | 药物重定位：靶点驱动/化合物驱动/疾病驱动三策略，找老药新用候选 |
| **tooluniverse-precision-oncology** | 精准肿瘤治疗推荐：解读肿瘤突变、FDA获批疗法、临床试验、耐药机制 |
| **tooluniverse-clinical-trial-matching** | 患者-试验匹配：按分子eligibility、临床标准、生物标志物、地理位置打分(0-100分) |
| **clinical-trial-protocol-skill** | 生成临床试验方案：医疗器械/药物临床试验设计、FDA申报文档 |

### 患者侧与工程接口

| Skill | 干什么 |
|-------|--------|
| **patiently-ai** | 把医生信函、检验报告、处方、出院小结翻译成患者能听懂的个性化语言 |
| **fhir-developer-skill** | FHIR API开发指南：Patient/Observation/Encounter/Condition/MedicationRequest等REST端点 |
| **prior-auth-review-skill** | 保险预授权(PA)审核自动化：医疗必要性评估、覆盖政策校验、PA决策生成 |
| **drug-photo** | 拍药盒照片识别药物(Claude视觉)，调取基因型指导的剂量建议 |

## 装了和没装的区别

| 没装Skills（裸AI） | 装了OpenClaw Medical Skills |
|---------------------|------------------------------|
| 泛泛而谈的医学回答 | 真实PubMed / ClinicalTrials.gov / FDA查询 |
| 没有生物信息学能力 | RNA-seq、scRNA-seq、GWAS、变异检测流水线 |
| 没有药物情报 | ChEMBL、DrugBank、DDI预测、药物警戒 |
| 没有临床文书 | SOAP、出院小结、预授权决策 |
| 没有基因组支持 | VCF注释、ACMG分级、PRS计算 |
| 没有法规指导 | FDA、CE mark、IEC 62304、ISO 14971合规 |

## 安装方式

```bash
# 通过 skills-hub CLI 一键安装单个Skill
npx @skills-hub-ai/cli install <skill-slug>

# 浏览全部869个Skill
curl https://skills-hub.ai/api/v1/skills?source=openclaw-medical
```

---

*来源: [GitHub · FreedomIntelligence/OpenClaw-Medical-Skills](https://github.com/FreedomIntelligence/OpenClaw-Medical-Skills)*
