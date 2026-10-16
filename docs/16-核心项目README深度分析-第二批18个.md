# 核心项目README级深度分析（第二批18个项目）

> **分析时间：** 2026-10-16
> **累计分析：** 38个项目（第一批20个 + 本批18个）
> **本批方向：** 医疗大模型、知识图谱、Agent、MCP Server、数据标准、中医药

---

## 一、医疗大模型方向（4个）

### 1. HuatuoGPT-II（港大FreedomIntelligence）
- **Star：** 3000+ | **许可证：** Apache-2.0 | **发表：** COLM 2024
- **真实是什么：** 港大华佗GPT二代，中文医疗对话大模型，7B/13B/34B三个版本
- **特点：** 专家评估和执业医师考试中超过GPT-4；训练数据全部开源
- **你的机会：** 这是中文医疗大模型里最成熟的开源模型之一，你要做医疗AI产品可以直接用它做底座

### 2. Med-R1（医疗版DeepSeek-R1）
- **Star：** 26
- **真实是什么：** 医疗版DeepSeek-R1，用RL训练让医疗LLM深度推理
- **特点：** 14B参数超过Qwen2.5-72B和Claude-3.5-Sonnet；只有4000条训练数据
- **你的机会：** 如果你要做医疗深度推理产品，这个模型可以直接用LoRA微调

### 3. Open-Medical-Reasoning-Tasks
- **Star：** 132 | **许可证：** MIT
- **真实是什么：** 医疗推理任务合集，Open Life Science AI社区维护
- **你的机会：** 不是产品，是数据集和任务定义。你训练或评估医疗模型时用这个

### 4. MedAGI（KAUST）
- **Star：** 41 | **许可证：** BSD-3
- **真实是什么：** 医疗AGI统一框架，低成本统一多个专科医疗LLM
- **特点：** 支持皮肤、X光、病理等多个专科，用MiniGPT-4架构
- **你的机会：** 如果你要做多专科医疗AI产品，这个框架可以参考

---

## 二、医疗Agent方向（4个）

### 5. Landmark-of-medical-agent（NUS）
- **Star：** 186
- **真实是什么：** 医疗Agent全景survey + MedMASLab多模态多Agent系统框架
- **特点：** 有小红书笔记推广，说明社区活跃度高
- **你的机会：** 不是产品，是综述+框架。做医疗Agent前先看这个survey理清全貌

### 6. Multilevel_Decomposition_Medical_Agent
- **Star：** 78 | **许可证：** Apache-2.0
- **真实是什么：** 规则问答+LLM+RAG双引擎医疗问答系统
- **核心功能：** 18类规则问题模板 + LLM智能问答；三路召回（Aho-Corasick实体识别 × Neo4j多跳 × ChromaDB向量检索）；支持MiniMax/SiliconFlow/Ollama/Qwen/DeepSeek
- **你的机会：** 这是最完整的中文医疗问答系统实现！直接参考它的架构做产品

### 7. MedicalAgentX-Agentic-RAG
- **Star：** 39 | **许可证：** MIT
- **真实是什么：** 医疗智能诊断助手，输入症状→AI团队查文献→分析推理→给出诊断建议
- **特点：** 用EvoAgentX工作流框架，模拟医生团队协作
- **你的机会：** 参考它的多Agent协作架构做辅助诊断产品

### 8. MedAgent（kyle103/medical_agent）⭐重点
- **Star：** 23 | **许可证：** MIT
- **真实是什么：** 合规医疗问答系统，核心设计理念是"AI辅助+知识库决策+合规兜底"
- **关键设计：** 药物相互作用与化验单异常判断100%来自结构化知识库，LLM只做意图识别和文本润色；所有输出强制追加免责声明
- **你的机会：** 这就是你要的合规方案！LLM做理解，知识库做决策，完全符合医疗合规要求

---

## 三、知识图谱方向（3个）

### 9. medical_knowledge_graph_app（pen-ho）
- **Star：** 350
- **真实是什么：** 医药知识图谱自动问答系统，带前端交互（ECharts力引导图）
- **特点：** 4377个症状，99492个三元组；BERT+CRF做实体识别；SBERT做实体链接；支持多症状疾病交集查询
- **你的机会：** 比基础教程多了前端和NLP优化，直接拿来做Demo

### 10. MedicalKG（yeeeqichen）
- **Star：** 93
- **真实是什么：** 医疗知识图谱构建实战，爬百度百科医疗数据，MongoDB存储+Neo4j图谱
- **特点：** 完整教程：Scrapy爬虫→MongoDB→Neo4j→可视化
- **你的机会：** 学习如何从0构建医学知识图谱的教程

### 11. AMG-RAG（Agentic Medical Graph-RAG）
- **Star：** 42 | **许可证：** MIT
- **真实是什么：** 自动构建+持续更新医学知识图谱，集成推理和外部证据检索
- **特点：** 实体提取带置信度评分（1-10）；双向关系分析；PubMed+Wikipedia+向量库多源证据；实时图谱更新
- **你的机会：** 如果你要做动态更新的医学知识库产品，这个框架可以参考

---

## 四、MCP Server方向（5个）⭐重点

### 12. omophub-mcp（OMOPHub）
- **Star：** 6
- **真实是什么：** OMOP医学术语MCP Server，11M+概念：SNOMED CT、ICD-10、RxNorm、LOINC
- **特点：** npm包，TypeScript，支持Claude/Cursor/VS Code
- **你的机会：** 这是医学术语查询的标准工具！做医疗AI产品时需要术语映射就用它

### 13. medical-codes-mcp-server（cyanheads）
- **Star：** 2 | **许可证：** Apache-2.0
- **真实是什么：** 美国医学编码MCP Server：ICD-10-CM、ICD-10-PCS、HCPCS Level II、RxNorm
- **特点：** 离线索引，6个工具，支持STDIO和Streamable HTTP
- **你的机会：** 如果你要做面向美国市场的医疗产品，这个直接用

### 14. medical-mcp-server（kieran-heidi）
- **Star：** 1
- **真实是什么：** 医学指南MCP Server，搜索NICE/RACGP/WHO/CDC指南全文
- **特点：** 不需要API Key，用DuckDuckGo搜索；站点特定解析；生产就绪Railway部署
- **你的机会：** 这就是你仝学的MCP版本！给药企做指南查询工具

### 15. MCP-Medical（sqlshep）
- **Star：** 1 | **许可证：** MIT
- **真实是什么：** 医疗MCP聊天应用，连接PubMed/WHO/RxNorm/FDA
- **特点：** 用Gemini on Vertex AI做自然语言回答，带登录界面
- **你的机会：** 参考它的架构做医疗AI聊天产品

### 16. awesome-medical-mcp-server（shanggqm）
- **Star：** 4 | **许可证：** MIT
- **真实是什么：** 医学计算器MCP Server合集，为AI医疗助手提供精准医疗计算工具
- **你的机会：** 做医疗AI时需要医学计算器就从这里找

---

## 五、数据标准与互操作（1个）

### 17. google/cql
- **Star：** 115 | **许可证：** Apache-2.0
- **真实是什么：** Google做的临床质量语言（CQL）执行引擎，用Go写的
- **特点：** FHIR数据查询执行；定义质量指标、临床决策支持、队列分析
- **你的机会：** 如果你要给药企做真实世界研究（RWE）或者医疗质量评估，这个是标准工具

---

## 六、中医药方向（1个）

### 18. zyAI（中医AI问诊系统）
- **Star：** 14
- **真实是什么：** 中医AI问诊系统，开放平台，中医生可以提交自己的经验
- **特点：** 疫情期间开发，支持微信小程序；有在线Demo（jtkf.com/ai）
- **你的机会：** 如果你想做中医AI方向，这个是参考架构——医生经验录入+AI诊断

---

## 七、本批关键发现总结

### 最有价值的新发现：

| 项目 | 为什么重要 | 你的机会 |
|------|-----------|---------|
| **MedAgent（kyle103）** | 合规设计完美：LLM做理解，知识库做决策 | 直接参考做你的医疗AI产品，完全合规 |
| **Multilevel_Decomposition_Medical_Agent** | 最完整的中文医疗问答系统实现 | 参考架构，规则+LLM+RAG双引擎 |
| **omophub-mcp** | 11M+医学术语，标准工具 | 做医疗AI时术语映射直接用 |
| **medical-mcp-server（kieran-heidi）** | NICE/RACGP/WHO/CDC指南全文搜索 | 仝学的MCP版本，给药企用 |
| **google/cql** | Google官方FHIR查询引擎 | 给药企做真实世界研究工具 |

### 按你的优先级排序：

**第一优先级（直接能用的技术组件）：**
1. **omophub-mcp** — 医学术语查询，标准工具
2. **HuatuoGPT-II** — 中文医疗大模型底座
3. **Multilevel_Decomposition_Medical_Agent** — 中文医疗问答系统完整实现

**第二优先级（参考架构做产品）：**
4. **MedAgent（kyle103）** — 合规设计参考
5. **medical-mcp-server（kieran-heidi）** — 指南查询MCP
6. **google/cql** — 真实世界研究工具

**第三优先级（学习和参考）：**
7. **Landmark-of-medical-agent** — 医疗Agent全景survey
8. **AMG-RAG** — 动态知识图谱框架
9. **zyAI** — 中医AI参考

---

*累计分析：38个项目README | 整理时间：2026-10-16*
