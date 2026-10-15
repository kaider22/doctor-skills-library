# 医生技能库 · Doctor Skills Library

> **面向临床医生与医学AI产品的开源Skill知识库**
>
> 把AI当成规培生——它干文书和检索，你干诊断和决策。

---

## 目录

1. [项目定位](#1-项目定位)
2. [收录项目总览](#2-收录项目总览)
3. [按临床场景的Skill地图](#3-按临床场景的skill地图)
4. [项目详细档案](#4-项目详细档案)
5. [选型决策树](#5-选型决策树)
6. [安装与使用指南](#6-安装与使用指南)
7. [待收录清单](#7-待收录清单)
8. [贡献规范](#8-贡献规范)

---

## 1. 项目定位

### 我们解决什么问题

通用大模型在医学领域存在三个gap：
- **知识gap**：知道事实但不知道怎么用（引用了指南但用错标准）
- **流程gap**：知道步骤但顺序错了（VBM预处理先剥头皮再做场校正，引入系统性偏差）
- **工具gap**：没有数据库直连，只能编不能查（说不出PubMed最新文献、FDA最新标签）

Agent Skills（SKILL.md格式）是解决这三个gap的标准方案：把专家决策框架编码成机器可读的结构化提示，按触发条件自动加载。

### 我们收录什么

- ✅ 遵循开放Agent Skills标准（SKILL.md格式）的医疗AI技能库
- ✅ 有真实数据库/API连接（PubMed、FDA、ChEMBL、DrugBank、FHIR）
- ✅ 有临床或科研场景的明确落地路径
- ❌ 不收录纯聊天机器人prompt模板
- ❌ 不收录无审计、无验证的黑盒模型

---

## 2. 收录项目总览

| # | 项目 | 出品方 | 数量 | Star | 最后更新 | 协议 | 核心领域 |
|---|------|--------|------|------|----------|------|----------|
| 1 | [OpenClaw Medical Skills](https://github.com/FreedomIntelligence/OpenClaw-Medical-Skills) | FreedomIntelligence/港大HKUDS | 869 | 3.0k | 2026-10-14 | MIT | 临床+科研+生信全家桶 |
| 2 | [OpenMed](https://github.com/maziyarpanahi/openmed) | maziyarpanahi | 72 | 5.7k | 2026-10-15 | Apache-2.0 | 数据隐私+临床NLP+FHIR/OMOP |
| 3 | [AWS HCLS Agent Skills](https://aws.amazon.com/blogs/machine-learning/improving-hcls-ai-reasoning-with-open-source-agent-skills/) | Amazon AWS | 38 | - | 2026-09-16 | MIT-0 | 基因组+药物发现+理赔+影像 |
| 4 | [MONAI Medical AI Skills](https://github.com/NVIDIA-Medtech/medical-AI-skills) | NVIDIA MedTech/MONAI | 12 | 31 | 2026-10-14 | Apache-2.0 | 医学影像DICOM/分割/生成 |
| 5 | [ClinSeekAgent](https://arxiv.org/abs/2605.20176) | UCSC/Yuyin Zhou | 20工具 | - | 2026-05 | 开源 | EHR+胸片多模态临床推理 |
| 6 | [BAAI Cardiac Agent](https://hub.baai.ac.cn/view/54499) | 智源BAAI+安贞医院 | 独立系统 | - | 2026-05 | 开源 | 心脏MRI多模态诊断 |

> 入门参考：抖音@阿尔法猎手推荐的5个临床日常Skill（口述病历/辅助诊断/用药安全/指南库/文献检索），是上述全家桶的轻量子集。

---

## 3. 按临床场景的Skill地图

### 3.1 临床文书与记录

| 能力 | 对应Skill | 来自项目 |
|------|-----------|----------|
| 口述转SOAP结构化病历 | `clinical-reports` / `medical-scribe-dictation` | OpenClaw / 抖音入门 |
| 出院小结生成 | `clinical-reports` | OpenClaw |
| 病例报告(CARE指南) | `clinical-reports` | OpenClaw |
| H&P病历书写 | `clinical-reports` | OpenClaw |
| 放射/病理/检验报告 | `clinical-reports` | OpenClaw |
| 患者版医学文档解读 | `patiently-ai` | OpenClaw |

### 3.2 诊断与决策支持

| 能力 | 对应Skill | 来自项目 |
|------|-----------|----------|
| 疑似诊断+鉴别诊断 | `tencent-health-ai-clinical-assistant` | 抖音入门 |
| CDS临床决策支持(GRADE分级) | `clinical-decision-support` | OpenClaw / AWS |
| 罕见病鉴别诊断(HPO/OMIM) | `tooluniverse-rare-disease-diagnosis` | OpenClaw |
| 临床指南检索(12+来源) | `tooluniverse-clinical-guidelines` | OpenClaw |
| 疾病全景研究报告 | `tooluniverse-disease-research` | OpenClaw |
| EHR+胸片主动推理 | ClinSeekAgent全部工具 | UCSC |
| 心脏MRI一站式诊断 | BAAI Cardiac Agent | 智源 |

### 3.3 用药与处方安全

| 能力 | 对应Skill | 来自项目 |
|------|-----------|----------|
| 药物相互作用预测(CYP450) | `tooluniverse-drug-drug-interaction` | OpenClaw |
| 药物警戒(FDA不良事件) | `tooluniverse-pharmacovigilance` | OpenClaw |
| 药物全景报告(药理/ADMET) | `tooluniverse-drug-research` | OpenClaw |
| 药物重定位 | `tooluniverse-drug-repurposing` | OpenClaw / AWS |
| 药盒拍照识别+剂量建议 | `drug-photo` / `medication-advisor` | OpenClaw / 抖音入门 |
| 临床NLP实体提取(药品) | `extracting-clinical-entities` | OpenMed |

### 3.4 科研与文献

| 能力 | 对应Skill | 来自项目 |
|------|-----------|----------|
| PubMed文献检索+证据分级 | `medical-lit` / `biomedical-search` | 抖音入门 / OpenClaw |
| 系统文献综述(APA/Nature/Vancouver) | `literature-review` | OpenClaw |
| 生物医学一站式搜索 | `biomedical-search` | OpenClaw |
| 深度文献研究(目标消歧+证据分级) | `tooluniverse-literature-deep-research` | OpenClaw |
| 临床试验方案设计 | `clinical-trial-protocol-skill` | OpenClaw |
| 患者-试验匹配打分 | `tooluniverse-clinical-trial-matching` | OpenClaw |

### 3.5 医学影像

| 能力 | 对应Skill | 来自项目 |
|------|-----------|----------|
| DICOM预检/元数据提取 | `dicom-series-preflight` / `dicom-metadata-extract` | MONAI |
| DICOM转NIfTI(HU校准) | `dicom-series-to-volume` | MONAI |
| CT全身分割(VISTA3D) | `nv-segment-ct` | MONAI |
| CT/MRI分割 | `nv-segment-ctmr` | MONAI |
| 胸片推理(3B模型) | `nv-reason-cxr` | MONAI |
| T1w MRI预处理(VBM) | `radiology-preprocessing` | AWS HCLS |
| CT/MRI合成生成 | `nv-generate-ct/mr/mr-brain` | MONAI |

### 3.6 数据合规与互操作

| 能力 | 对应Skill | 来自项目 |
|------|-----------|----------|
| PHI去标识化(34种语言) | `deidentifying-clinical-text` | OpenMed |
| HIPAA Safe Harbor执行 | OpenMed全套管线 | OpenMed |
| 中国PIPL合规 | OpenMed政策模板 | OpenMed |
| FHIR REST API开发 | `fhir-developer-skill` | OpenClaw |
| OMOP CDM转换 | OpenMed管线 | OpenMed |
| ICD-11离线集成 | OpenMed管线 | OpenMed |

### 3.7 基因组与精准医学

| 能力 | 对应Skill | 来自项目 |
|------|-----------|----------|
| ACMG/AMP变异分级 | `genomic-variant-interpretation` | AWS HCLS |
| VCF注释(ClinVar/gnomAD) | `tooluniverse-variant-analysis` | OpenClaw |
| GWAS多基因风险评分 | `tooluniverse-polygenic-risk-score` | OpenClaw |
| 肿瘤突变解读(EGFR/BRAF) | `tooluniverse-cancer-variant-interpretation` | OpenClaw |
| 精准肿瘤治疗推荐 | `tooluniverse-precision-oncology` | OpenClaw |
| 药物基因组学报告(CPIC) | `pharmgx-reporter` | OpenClaw |

---

## 4. 项目详细档案

### 4.1 OpenClaw Medical Skills（869个）

- **GitHub**: https://github.com/FreedomIntelligence/OpenClaw-Medical-Skills
- **Star**: 3,064 | **更新**: 2026-10-14 | **协议**: MIT
- **出品**: FreedomIntelligence（港大HKUDS生态）
- **一句话**: 全球最大开源医学AI技能库，临床+科研+生信全家桶

**分类统计**:
| 类别 | 数量 |
|------|------|
| General & Core | 10 |
| Medical & Clinical | 119 |
| Scientific Databases | 43 |
| Bioinformatics | 239 |
| Omics & Computational Biology | 59 |
| ClawBio Pipelines | 21 |
| BioOS Extended Suite | 285 |
| Data Science & Tools | 93 |

**已连接数据库**: PubMed, ClinicalTrials.gov, ChEMBL, DrugBank, FDA, OpenTargets, OMIM, UniProt, KEGG, Reactome

**适合场景**: 需要一个覆盖临床日常+科研全流程的Skill库，不想东拼西凑

---

### 4.2 OpenMed v2.0（72个）

- **GitHub**: https://github.com/maziyarpanahi/openmed
- **Star**: 5,687 | **更新**: 2026-10-15 | **协议**: Apache-2.0
- **一句话**: 本地优先的医疗AI平台，数据脱敏+临床NLP+互操作

**核心能力**:
- 34种PII语言去标识化，确定性标识符包
- 临床NLP：放射报告解析、药品/检验/诊断实体提取、时序归一化
- FHIR导出、OMOP CDM、OpenMRS/DHIS2集成
- 合规模板：HIPAA、GDPR、中国PIPL、印度DPDP、EU AI Act
- 全平台：Python/JS/Swift(iOS/watchOS)/Android/Docker

**适合场景**: 处理真实患者数据，需要本地部署不出端，需要合规与互操作

---

### 4.3 AWS HCLS Agent Skills（38个）

- **出处**: https://aws.amazon.com/blogs/machine-learning/improving-hcls-ai-reasoning-with-open-source-agent-skills/
- **发布**: 2026-09-16 | **协议**: MIT-0（可商用无署名）
- **一句话**: 亚马逊官方出品，基因组+药物发现+医保理赔+医学影像

**两类Skill**:
- **Reasoning（推理型）**: 编码决策框架，如ACMG/AMP变异分级、CMS-HCC风险调整
- **Pipeline（流水线型）**: 编码工具命令，如GATK4变异检测、VBM预处理

**实测效果**: 装了Skill的Agent对比裸Agent胜率 **70-86%**，批判性思维维度提升最显著(d=0.65-1.03)

**适合场景**: 生物制药研发、医保理赔运营、医学影像研究，需要可商用无署名

---

### 4.4 MONAI Medical AI Skills（12个）

- **GitHub**: https://github.com/NVIDIA-Medtech/medical-AI-skills
- **Star**: 31 | **更新**: 2026-10-14 | **协议**: Apache-2.0
- **出品**: NVIDIA MedTech + MONAI生态
- **一句话**: 医学影像专用，DICOM→分割→生成→推理全链路

**四个方向**:
- DICOM工具(CPU)：预检、元数据、转NIfTI
- 分割(GPU)：全身CT分割、CT/MRI分割、微调
- 合成生成(GPU)：CT/MRI/脑MRI合成、VAE微调
- 推理(GPU)：胸片推理(NV-Reason-CXR-3B)

**特色**: 每个Skill带配对验证器(Verifier)，输出结构化JSON+证据包，解剖合理性/HU范围/PHI范围自动审计

**适合场景**: 医学影像AI研发，需要DICOM预处理到分割出报告的工程流水线

---

### 4.5 ClinSeekAgent（UCSC）

- **论文**: arXiv 2605.20176 | **机构**: UC Santa Cruz
- **一句话**: 主动证据检索的多模态临床推理Agent

**工具集**: 11个EHR检索工具 + 3个网络搜索工具 + 6个胸片影像工具
**特色**: 无固定检索顺序，Agent自主规划工具调用，根据新证据修正假设，整合后给出临床回答

**适合场景**: 学术研究，探索EHR+影像多模态临床决策的Agent架构

---

### 4.6 BAAI Cardiac Agent（智源+安贞）

- **出品**: 北京智源人工智能研究院 + 首都医科大学附属北京安贞医院
- **一句话**: 业内首个心脏磁共振(CMR)多模态推理诊断智能体

**能力链**: 结构分割与分析 → 功能定量评估 → 疾病诊断
**适合场景**: 心血管影像专科诊断研究

---

## 5. 选型决策树

```
你的核心需求是什么？
│
├─ 我要日常临床文书+指南+用药，开箱即用
│  └─→ OpenClaw Medical Skills（869个全家桶）
│
├─ 我要处理真实患者数据，必须本地部署+合规
│  └─→ OpenMed v2.0（脱敏+FHIR+PIPL合规）
│
├─ 我是生物制药/医保方向，需要可商用
│  └─→ AWS HCLS Agent Skills（MIT-0，38个）
│
├─ 我做医学影像AI，需要DICOM流水线
│  └─→ MONAI Medical AI Skills（NVIDIA出品，带验证器）
│
├─ 我做学术研究，探索多模态临床推理
│  └─→ ClinSeekAgent（UCSC）
│
└─ 我做心脏影像专科
   └─→ BAAI Cardiac Agent（智源+安贞）
```

---

## 6. 安装与使用指南

### 通用安装方式

```bash
# 方式1：通过 skills-hub CLI（推荐）
npx @skills-hub-ai/cli install <skill-slug>

# 方式2：浏览全部OpenClaw Medical Skills
curl https://skills-hub.ai/api/v1/skills?source=openclaw-medical

# 方式3：OpenMed全套安装
git clone https://github.com/maziyarpanahi/openmed
cd openmed && ./install-skills.sh

# 方式4：MONAI单个Skill安装
npx skills add NVIDIA-Medtech/medical-AI-skills \
  --skill nv-segment-ct --agent claude-code --yes
```

### 兼容工具列表

- Claude Code
- Cursor
- Codex CLI
- Windsurf
- GitHub Copilot
- Amazon Bedrock AgentCore / Strands SDK / Kiro
- 任何遵循开放Agent Skills标准的MCP兼容工具

### 安全边界

> ⚠️ **所有Skill都是辅助工具，不是医疗器械。**
> - 输出必须经过合格临床医生审核
> - 不得自动触发诊断、治疗、计费决策
> - 真实PHI数据使用前需完成去标识化和合规审查
> - 药物相关输出必须与最新版FDA标签和当地指南核对

---

## 7. 待收录清单

- [ ] 国内厂商出品的医疗AI Skill（腾讯健康、讯飞医疗、京东健康）
- [ ] 中医/中西医结合方向的Skill
- [ ] 护理与慢病管理方向（高血压随访、糖尿病管理）
- [ ] 病历质控与医疗安全方向
- [ ] 医疗医保DRG/DIP分组相关Skill
- [ ] 基层全科/家庭医生方向Skill

---

## 8. 贡献规范

欢迎新发现的医疗AI Skill/Agent项目，提Issue或PR时请包含：

1. **项目名称+GitHub链接**
2. **出品方背景**（学术机构/企业/开源社区）
3. **Skill数量+覆盖领域**
4. **协议**（是否可商用）
5. **已连接的真实数据库/API**
6. **适用场景一句话**
7. **与已有收录项目的差异化**

---

*维护者：kaider22 | 最近更新：2026-10-15*
