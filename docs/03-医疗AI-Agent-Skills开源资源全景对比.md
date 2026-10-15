# 医疗AI Agent Skills开源资源全景对比（2026年10月）

> 收录6个主流开源医疗AI Skill/Agent项目，覆盖临床文书、影像、生信、合规、用药等全场景。

## 总览对比

| 项目 | 出品方 | Skill数量 | 核心定位 | 协议 | 兼容工具 |
|------|--------|-----------|----------|------|----------|
| **OpenClaw Medical Skills** | FreedomIntelligence / 港大HKUDS | **869** | 全科+科研+生信全家桶 | MIT | Claude Code/Cursor/Codex/Windsurf/Copilot |
| **OpenMed v2.0** | maziyarpanahi/openmed | **72** | 医疗数据隐私+临床NLP+FHIR/OMOP互操作 | 开源 | Claude Code/Codex/OpenCode |
| **AWS HCLS Agent Skills** | Amazon AWS | **38** | 基因组+药物发现+理赔运营+医学影像 | MIT-0 | Bedrock/Strands/Kiro/Claude Code/Codex |
| **MONAI Medical AI Skills** | NVIDIA MedTech / MONAI | **12** | 医学影像：DICOM/分割/合成生成/胸片推理 | Apache-2.0 | 所有兼容Agent Skills标准的工具 |
| **ClinSeekAgent** | UCSC / Yuyin Zhou | 20个工具 | 多模态临床推理：EHR检索+胸片影像 | 开源 | 独立Agent框架 |
| **BAAI Cardiac Agent** | 智源BAAI + 安贞医院 | 独立系统 | 心脏MRI多模态诊断（结构分割→功能定量→疾病诊断） | 开源 | 独立Agent框架 |

---

## 1. OpenClaw Medical Skills（869个）

- **GitHub**: https://github.com/FreedomIntelligence/OpenClaw-Medical-Skills
- **定位**: 全球最大开源医学AI技能库，港大HKUDS生态
- **亮点**: 临床文书(SOAP/出院小结)、指南检索(NCCN/AHA/WHO等12+来源)、用药安全、肿瘤精准治疗、生物信息学全流程
- **适合**: 需要从临床到科研一站式Skill库的团队
- **详细档案**: [见02号文档](./02-OpenClaw-Medical-Skills-869个医学Skill.md)

## 2. OpenMed v2.0（72个）

- **GitHub**: https://github.com/maziyarpanahi/openmed
- **发布**: 2026-07-28
- **核心方向**:
  - **数据隐私**: 34种PII语言去标识化，HIPAA Safe Harbor、GDPR、中国PIPL、印度DPDP合规
  - **临床NLP**: 放射报告解析、临床实体提取(药品/检验/诊断)、时序归一化、共指消解
  - **互操作**: FHIR导出、OMOP CDM、OpenMRS、DHIS2、ICD-11离线集成
  - **部署**: Python/JS/Swift(iOS/watchOS)/Android/容器，本地优先，PHI不出端
- **安装**:
  ```bash
  git clone https://github.com/maziyarpanahi/openmed
  cd openmed && ./install-skills.sh
  ```
- **适合**: 需要做医疗数据脱敏、FHIR/OMOP转换、本地化部署的团队
- **边界**: 辅助软件，非医疗器械，输出需人工审核

## 3. AWS HCLS Agent Skills（38个）

- **出处**: AWS官方博客 2026-09-16发布
- **11个领域**: 基因组学、药物发现、理赔运营、医学影像等
- **两类Skill**:
  - **Reasoning Skills（推理型）**: 编码决策框架，如ACMG/AMP变异分级、CMS-HCC风险调整
  - **Pipeline Skills（流水线型）**: 编码工具命令，如GATK4变异检测、VBM预处理
- **实测效果**: 装了Skill的Agent对比裸Agent，胜率70-86%，批判性思维维度提升最显著(78-85%)
- **关键Skill示例**:
  - `genomic-variant-interpretation` — 完整ACMG/AMP分类框架
  - `drug-repurposing` — DGIdb查询+证据层级排序+临床转化评估
  - `risk-adjustment` — ICD-10到HCC映射、V28层级解析、RAF评分
  - `radiology-preprocessing` — T1w MRI预处理顺序(FSL/ANTs)
  - `claims-billing-rules` — 理赔规则
- **适合**: 生物制药、医保理赔、医学影像研究团队
- **协议**: MIT-0（最宽松，可商用无署名要求）

## 4. MONAI Medical AI Skills（12个）

- **GitHub**: https://github.com/NVIDIA-Medtech/medical-AI-skills
- **出品**: NVIDIA MedTech + MONAI生态
- **12个Skill分4类**:
  - **DICOM工具(CPU)**: series预检、元数据提取、DICOM转NIfTI
  - **分割(GPU)**: NV-Segment-CT全身分割、NV-Segment-CTMR CT/MRI分割、微调
  - **合成生成(GPU)**: CT合成、MRI合成、脑MRI合成、VAE微调
  - **影像推理(GPU)**: NV-Reason-CXR胸片推理(3B模型)
- **特色**: 每个Skill都带验证器(Verifier)，输出结构化JSON+证据包，解剖合理性/HU范围/PHI范围自动审计
- **安装**:
  ```bash
  npx skills add NVIDIA-Medtech/medical-AI-skills \
    --skill nv-segment-ct --agent claude-code --yes
  ```
- **适合**: 医学影像AI研发团队，需要DICOM→分割→报告的流水线

## 5. ClinSeekAgent

- **论文**: arXiv 2605.20176, UCSC
- **定位**: 主动证据检索的多模态临床推理Agent
- **工具集**: 11个原始EHR检索工具 + 3个网络搜索工具 + 6个胸片影像工具
- **特色**: 没有固定检索顺序，Agent自己规划调用工具，根据新信息修正假设，整合证据后给出临床回答
- **适合**: 需要做EHR+影像多模态临床决策的研究

## 6. BAAI Cardiac Agent

- **出品**: 智源研究院(BAAI) + 首都医科大学附属北京安贞医院 + 河南医药大学第一附属医院
- **定位**: 业内首个心脏磁共振(CMR)多模态推理诊断智能体
- **能力链**: 结构分割与分析 → 功能定量评估 → 疾病诊断
- **适合**: 心血管影像诊断场景

---

## 选型建议

| 你的需求 | 推荐项目 |
|----------|----------|
| 临床日常文书+指南+用药 | **OpenClaw Medical Skills**（869个全家桶） |
| 医疗数据脱敏+FHIR/OMOP+本地部署 | **OpenMed v2.0** |
| 生物制药+医保理赔+基因组研究 | **AWS HCLS Agent Skills**（MIT-0可商用） |
| 医学影像分割/合成/推理 | **MONAI Medical AI Skills**（NVIDIA出品） |
| EHR+胸片多模态临床推理研究 | **ClinSeekAgent**（学术研究） |
| 心脏MRI诊断 | **BAAI Cardiac Agent**（专科方向） |

## 共同标准

所有项目都遵循开放Agent Skills标准（SKILL.md格式），YAML frontmatter声明触发条件和依赖，正文是决策框架+参数表+验证规则。一次编写，到处运行。

---

*整理时间: 2026-10-15*
