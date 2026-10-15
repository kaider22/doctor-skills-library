# GitHub医疗AI开源资源评审报告

> **评审时间：** 2026-10-15
> **搜索轮次：** 18轮GitHub搜索
> **收录项目：** 35个高质量项目
> **评审标准：** 与你创业方向（慢病随访/循证问答/药企工具/减重运营）的匹配度

---

## 一、评审分级标准

| 级别 | 含义 | 数量 |
|------|------|------|
| ⭐⭐⭐ 直接可用 | 可以直接拿来做产品底层，或直接集成到MVP | - |
| ⭐⭐ 参考价值 | 技术方案/架构可以参考，或者数据集可以直接用 | - |
| ⭐ 研究跟踪 | 偏学术/前沿，暂时不直接用，但值得关注 | - |

---

## 二、按创业方向分类评审

### 方向1：慢病管理AI随访（高血压/减重）

| 项目 | Star | 许可证 | 描述 | 评审 |
|------|------|--------|------|------|
| **openhospital** | 635 | GPL-3.0 | 开源EHR系统，完整的医院管理软件 | ⭐⭐ 参考：看它的患者管理模块设计，不直接用（许可证传染性强） |
| **SynthEHR** | 38 | GPL-3.0 | 合成EHR数据生成工具 | ⭐⭐⭐ 直接可用：生成模拟患者数据做Demo，不需要真实PHI |
| **ehrshot-benchmark** | 234 | Apache-2.0 | EHR基础模型少样本学习基准 | ⭐ 研究跟踪：偏学术，了解EHR模型能力边界 |
| **awesome-ehr-deeplearning** | 430 | CC0 | EHR深度学习论文合集 | ⭐ 研究跟踪：需要时查论文用 |
| **kyle103/medical_agent** | 23 | - | 轻量化健康管理工具：用药安全+化验单解读+就诊记录归档 | ⭐⭐⭐ 直接可用：和你的随访产品场景高度重合，可以参考架构 |
| **omophub-mcp** | 6 | MIT | OMOP医学术语MCP Server，11M+概念 | ⭐⭐⭐ 直接可用：给药企/商保做数据报告时，标准化术语映射 |

---

### 方向2：循证医学问答（仝学）

| 项目 | Star | 许可证 | 描述 | 评审 |
|------|------|--------|------|------|
| **HuatuoGPT** | 1333 | Apache-2.0 | 华佗GPT，开源医疗大模型 | ⭐⭐⭐ 直接可用：可以本地部署做底层模型，或对比效果 |
| **HuatuoGPT-o1** | 1364 | - | 医疗推理版，o1风格 | ⭐⭐⭐ 直接可用：复杂医学推理场景，比普通LLM强 |
| **HuatuoGPT-Vision** | 403 | - | 多模态医疗VLM | ⭐⭐ 参考：如果做化验单/影像解读可以参考 |
| **HuatuoGPT-3** | 25 | Apache-2.0 | 最新版，RL-only领域适配 | ⭐⭐⭐ 直接可用：最新版，效果更好 |
| **OpenClaw-Medical-Skills** | 3064 | - | 869个医学Skill库 | ⭐⭐⭐ 直接可用：你已经收录了，继续维护 |
| **Awesome-Medical-LLM-Agent** | 45 | - | 医疗LLM到医疗Agent演进资源合集 | ⭐⭐ 参考：了解技术演进路线 |
| **MedicalAgentsBench** | 87 | MIT | 医疗Agent基准测试框架 | ⭐⭐ 参考：用来测试你的产品效果 |

---

### 方向3：药企数字化工具（MSL/医学事务）

| 项目 | Star | 许可证 | 描述 | 评审 |
|------|------|--------|------|------|
| **Awesome-Agentic-Clinical-Dialogue** | 412 | - | 临床对话医疗Agent资源合集 | ⭐⭐ 参考：找文献检索/学术内容生成的技术方案 |
| **Meissa** | 65 | Apache-2.0 | 多模态医疗Agent，基于轨迹行为 | ⭐⭐ 参考：药企医学部需要多模态内容生成 |
| **MedicalAgentX-Agentic-RAG** | 39 | MIT | 诊断助手系统，RAG+文献查阅 | ⭐⭐⭐ 直接可用：架构可以直接参考，做文献问答产品 |
| **Multilevel_Decomposition_Medical_Agent** | 78 | - | 知识图谱+多层级拆解医疗Agent | ⭐⭐ 参考：复杂医学问题拆解思路 |
| **InspectOMOP** | 15 | AGPL-3.0 | OMOP CDM数据提取工具 | ⭐⭐ 参考：给药企做真实世界研究数据提取 |

---

### 方向4：医疗文书/病历Agent

| 项目 | Star | 许可证 | 描述 | 评审 |
|------|------|--------|------|------|
| **phlox** | 109 | MIT | 开源本地优先AI医疗Agent（桌面+Web） | ⭐⭐⭐ 直接可用：架构可以参考，本地优先部署适合医疗场景 |
| **Merlin** | 489 | MIT | 3D VLM for CT扫描（Stanford） | ⭐ 研究跟踪：影像方向，暂时不直接用 |
| **RETFound** | 685 | - | 视网膜眼底照片视觉基础模型 | ⭐ 研究跟踪：影像方向 |
| **GMAI-VL** | 102 | Apache-2.0 | 通用多模态医学VLM+550万数据集 | ⭐ 研究跟踪：多模态方向，未来扩展用 |

---

### 方向5：数据集/资源合集（通用底座）

| 项目 | Star | 许可证 | 描述 | 评审 |
|------|------|--------|------|------|
| **Awesome-Medical-Healthcare-Dataset-For-LLM** | 333 | MIT | 医疗LLM数据集/模型/论文合集 | ⭐⭐⭐ 直接可用：找训练数据和评测数据 |
| **awesome-medical-ai-cn** | 35 | CC0 | 国内医疗AI开源项目合集 | ⭐⭐⭐ 直接可用：找国内竞品和合作方 |
| **Medical-AI-Guide** | 43 | MIT | 医学AI科研指南 | ⭐⭐ 参考：写技术文档/白皮书用 |
| **medical-ai-course-materials** | 245 | MIT | 日本医学AI课程讲义 | ⭐ 研究跟踪：系统学习用 |
| **medical-ai-research-foundations** | 220 | Apache-2.0 | Google Medical AI研究基础 | ⭐ 研究跟踪：Google的研究方向 |

---

### 方向6：EHR/数据标准（底层基础设施）

| 项目 | Star | 许可证 | 描述 | 评审 |
|------|------|--------|------|------|
| **vindr-lab** | 377 | MIT | 医学AI数据平台（越南） | ⭐⭐ 参考：看它怎么做数据集管理平台 |
| **monai-deploy** | 122 | Apache-2.0 | MONAI医学影像部署框架 | ⭐ 研究跟踪：影像部署方向 |
| **Landmark-of-medical-agent** | 186 | - | 医疗Agent地标项目合集 | ⭐⭐ 参考：找更多Agent项目 |
| **mast** | 36 | - | Medical AI Superintelligence Test | ⭐ 研究跟踪：评测框架 |
| **AutoMedBench** | 13 | MIT | 医疗Agent自进化后训练基准 | ⭐ 研究跟踪：训练方向 |
| **Healthcare_GYM** | 10 | Apache-2.0 | 医疗Agent训练环境（GYM） | ⭐ 研究跟踪：强化学习训练Agent |

---

## 三、重点项目深评（Top 10）

### 1. HuatuoGPT系列（FreedomIntelligence）
- **仓库：** github.com/FreedomIntelligence/HuatuoGPT
- **总Star：** 合计3000+
- **为什么重要：** 国内最好的开源医疗大模型，港大FreedomIntelligence团队（就是OpenClaw那个团队）
- **你能怎么用：**
  - 仝学循证问答的底层模型可以用HuatuoGPT-3做对比
  - 不需要自己从头训练医疗模型
  - Apache-2.0许可证，可以商用

### 2. OpenClaw-Medical-Skills
- **仓库：** github.com/FreedomIntelligence/OpenClaw-Medical-Skills
- **Star：** 3064
- **你已经收录了**，继续维护

### 3. phlox
- **仓库：** github.com/bloodworks-io/phlox
- **Star：** 109, MIT
- **为什么重要：** 本地优先的开源医疗Agent，桌面+Web端，2026年10月还在更新
- **你能怎么用：** 参考它的架构做你的随访/问答产品，本地优先=数据不出本地，合规友好

### 4. SynthEHR
- **仓库：** github.com/HicServices/SynthEHR
- **Star：** 38, GPL-3.0
- **为什么重要：** 合成EHR数据生成，不需要真实患者数据
- **你能怎么用：** 做Demo、做产品测试、做模型训练数据，完全合规

### 5. MedicalAgentX-Agentic-RAG
- **仓库：** github.com/yuanxiaochenAC/MedicalAgentX-Agentic-RAG
- **Star：** 39, MIT
- **为什么重要：** 医疗诊断助手，RAG架构，输入症状→查文献→分析推理→给建议
- **你能怎么用：** 架构直接参考，你的仝学循证问答产品就是这个思路

### 6. kyle103/medical_agent
- **仓库：** github.com/kyle103/medical_agent
- **Star：** 23
- **为什么重要：** 轻量化健康管理工具：用药安全+化验单解读+就诊记录归档
- **你能怎么用：** 和你的慢病随访产品场景高度重合，参考它的功能设计

### 7. Awesome-Medical-Healthcare-Dataset-For-LLM
- **仓库：** github.com/onejune2018/Awesome-Medical-Healthcare-Dataset-For-LLM
- **Star：** 333, MIT
- **为什么重要：** 医疗LLM数据集大全，找训练数据和评测数据用
- **你能怎么用：** 选合适的数据集做产品评测

### 8. awesome-medical-ai-cn
- **仓库：** github.com/JuneYaooo/awesome-medical-ai-cn
- **Star：** 35
- **为什么重要：** 国内医疗AI开源项目合集，找竞品和合作方
- **你能怎么用：** 了解国内谁在做类似的事

### 9. omophub-mcp
- **仓库：** github.com/OMOPHub/omophub-mcp
- **Star：** 6, MIT
- **为什么重要：** OMOP医学术语MCP Server，11M+概念标准化映射
- **你能怎么用：** 给药企/商保做数据报告时，术语标准化，直接接入

### 10. Awesome-Agentic-Clinical-Dialogue
- **仓库：** github.com/xqz614/Awesome-Agentic-Clinical-Dialogue
- **Star：** 412
- **为什么重要：** 临床对话医疗Agent资源大全
- **你能怎么用：** 找患者沟通/随访对话的技术方案

---

## 四、关键发现总结

### 4.1 可以直接拿过来用的（不需要从头做）
1. **医疗大模型底座：** HuatuoGPT-3（Apache-2.0，可商用）
2. **医学Skill库：** OpenClaw-Medical-Skills（869个，已收录）
3. **合成患者数据：** SynthEHR（做Demo用，合规）
4. **医学术语标准化：** omophub-mcp（OMOP 11M+概念）
5. **医疗Agent参考架构：** phlox + MedicalAgentX-Agentic-RAG

### 4.2 国内值得关注的竞品/合作方
- FreedomIntelligence团队（港大HKUDS）— 华佗GPT + OpenClaw
- 清华AIR — Agent Hospital（全AI医患仿真）
- 智源BAAI — Cardiac Agent（心脏MRI多模态）
- uni-medical — GMAI-VL通用多模态医学VLM

### 4.3 还没找到的资源（后续继续搜）
- 药企MSL数字化工具的开源项目（这个方向商业价值高，开源少）
- 慢病随访的完整开源产品（偏商业，开源少）
- GLP-1减重运营的工具链（太新，还没开源）
- 中文医学术语知识库的MCP server

---

*评审时间：2026-10-15 | 基于GitHub 18轮搜索结果*
