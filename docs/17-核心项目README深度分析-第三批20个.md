# 核心项目README级深度分析（第三批20个项目）

> **分析时间：** 2026-10-16
> **累计分析：** 58个项目（第一批20个 + 第二批18个 + 本批20个）
> **说明：** 本批很多教学项目404，实际有效项目约15个

---

## 一、医疗Agent方向（5个）

### 1. Awesome-Medical-Agents（zhcz328）
- **Star：** 37
- **真实是什么：** 医疗Agent精选阅读清单，survey论文配套
- **主题：** 医疗Agent从辅助到自主的临床系统扩展
- **你的机会：** 不是产品，是学习资料

### 2. Awesome-Medical-LLM-Agent（yczhou001）
- **Star：** 45 | **许可证：** MIT
- **真实是什么：** 医疗LLM到通用医疗Agent的演化综述，reasoning as the engine
- **你的机会：** 不是产品，是综述论文配套资源

### 3. xinyu-medical-agent（心语医疗助手）⭐重点
- **Star：** 21 | **许可证：** MIT
- **真实是什么：** 生产级医疗AI助手，不是RAG demo
- **核心功能：** Agentic retrieval、GraphRAG、跨会话记忆、多医院MCP预约、PII加密
- **技术栈：** LangGraph + PostgreSQL(pgvector) + Redis + FastAPI + React
- **你的机会：** 这是最完整的生产级医疗Agent实现！预约流程做了幂等性和槽位锁定，参考它的架构做产品

### 4. LLM-Medical-Agent（TUDB-Labs）
- **Star：** 12 | **许可证：** Apache-2.0
- **真实是什么：** 多Agent医疗数据处理框架，模块化设计
- **特点：** 数据加载Agent + 预处理Agent + 分析Agent，可扩展
- **你的机会：** 参考它的模块化多Agent架构

### 5. golden-medical-agent（machan1119）
- **Star：** 11
- **真实是什么：** FastAPI后端，多通道AI Agent（邮件/SMS/Web聊天）
- **特点：** 目标导向对话，自动识别用户目标（私人支付/保险案例管理/出院），自动存Google Sheets
- **你的机会：** 参考它的多通道接入设计

---

## 二、知识图谱方向（3个）

### 6. OpenCMKG（RuiqingDing）
- **Star：** 31
- **真实是什么：** 开源中文医疗知识图谱，聚合自QAKG+OwnThink+CHIP2021
- **特点：** 三元组文件+实体字典+人工标注对齐文件
- **注意：** 仅用于学术研究，不得商用
- **你的机会：** 研究参考，商用需注意许可

### 7. umls-graph（dhchenx）
- **Star：** 28 | **许可证：** MIT
- **真实是什么：** 基于UMLS构建医学知识图谱，MySQL存储
- **你的机会：** 如果你要做英文医疗知识图谱，这是标准基础

### 8. LMKG（ypr17）⭐重点
- **Star：** 21 | **许可证：** MIT
- **真实是什么：** 大规模多语言多源医学知识图谱
- **规模：** 13种实体类型，17种关系类型，403,784个实体，1,225,097个关系
- **特点：** 有在线Neo4j界面可以直接查询
- **你的机会：** 直接拿数据用，做医学问答或知识库产品

---

## 三、MCP Server方向（3个）

### 9. openevidence-mcp（htlin222）
- **Star：** 78 | **许可证：** Apache-2.0
- **真实是什么：** OpenEvidence MCP的活跃fork，支持Claude Code/Codex CLI/Cursor等
- **特点：** 通过自己的浏览器tab认证，不需要API key；绕过DataDome；BibTeX引用输出；Crossref验证
- **你的机会：** 这是最好用的OpenEvidence MCP实现，直接装在你电脑上用

### 10. openevidence-mcp（bakhtiersizhaev）
- **Star：** 45 | **许可证：** Apache-2.0
- **真实是什么：** 第一个开源OpenEvidence MCP
- **特点：** 多语言文档（俄语/西班牙语/中文/韩语/印地语）
- **你的机会：** 原版实现，htlin222是它的fork

### 11. fhir-mcp-server（quiquemz）
- **Star：** 3 | **许可证：** MIT
- **真实是什么：** C#写的FHIR MCP Server，支持FHIR R4
- **特点：** CRUD操作、搜索、合成数据生成、可视化
- **你的机会：** 如果你用.NET技术栈，这个直接用

---

## 四、医学编码与FHIR方向（4个）

### 12. medical-code-translator（sunghoyim）
- **真实是什么：** 疾病名称转标准医学编码工具，用于临床研究队列识别
- **特点：** Jupyter notebook实现，有数据映射和验证流程
- **你的机会：** 给药企做真实世界研究时，把疾病名称转成ICD编码

### 13. medical-code-search（timmcca-be）
- **真实是什么：** 医学编码全文搜索工具（ICD-10、CPT）
- **特点：** "Bring your own codes"，避免版权问题
- **你的机会：** 参考它的设计做编码搜索工具

### 14. fhir-former（UMEssen）
- **Star：** 5 | **许可证：** MIT
- **真实是什么：** FHIR数据Transformer模型，预训练+下游任务
- **特点：** 支持ICD编码、医学影像分析、再入院预测、死亡率预测
- **你的机会：** 如果你要做FHIR数据预测分析，这个框架可以参考

### 15. fast-fhir（archit-kapoor）
- **Star：** 2 | **许可证：** MIT
- **真实是什么：** 高性能Python FHIR R5解析库，C扩展
- **特点：** 比标准库快100倍
- **你的机会：** 处理大规模FHIR数据时用这个

---

## 五、临床决策支持与EHR方向（2个）

### 16. agentic-rag-medical-cdss（LiangRan2003）
- **Star：** 1
- **真实是什么：** 感染科辅助诊疗智能体，Agentic RAG架构
- **特点：** 解决传统RAG在严肃医疗场景中的幻觉问题；多智能体协同
- **你的机会：** 参考它的Agentic RAG架构做CDSS产品

### 17. ehr-dashboard（clinikapi）
- **Star：** 0 | **许可证：** MIT
- **真实是什么：** 开源临床EHR仪表板，基于ClinikAPI
- **核心功能：** 患者注册、图表、生命体征、预约、处方、实验室、 encounter
- **特点：** FHIR R4标准兼容；有React组件库
- **你的机会：** 参考它的EHR前端设计

---

## 六、其他方向（2个）

### 18. medkit-app（bedriyan）
- **Star：** 333
- **真实是什么：** 浏览器端ER+门诊临床训练模拟器，你扮演医生
- **特点：** 语音优先AI患者模拟；Claude Opus 4.7做评分；引用NICE/ESC/AHA/GINA/GOLD指南评分
- **你的机会：** 参考它的OSCE训练模式做医学教育产品

### 19. ami-chatbot-simulation（sonhyean-eda）
- **真实是什么：** Streamlit护理教育虚拟患者chatbot
- **你的机会：** 简单参考，功能比较基础

---

## 七、本批关键发现总结

### 最有价值的新发现：

| 项目 | 为什么重要 | 你的机会 |
|------|-----------|---------|
| **xinyu-medical-agent** | 最完整的生产级医疗Agent实现 | 参考架构做你的产品 |
| **LMKG** | 40万实体120万关系的医学知识图谱 | 直接拿数据用 |
| **openevidence-mcp（htlin222）** | 最好用的OpenEvidence MCP | 直接装在你电脑上用 |
| **medkit-app** | 333星的AI患者模拟器 | 参考OSCE训练模式做教育产品 |

### 累计分析58个项目后的全局结论：

**你现在手里已经有了：**
1. **模型底座：** HuatuoGPT-II（中文医疗大模型）
2. **知识图谱：** LMKG（40万实体）+ CMKG（多模态中文）
3. **术语工具：** omophub-mcp（11M+医学术语）
4. **文献检索：** OpenEvidence MCP + PubMed MCP
5. **合规架构：** MedAgent（LLM做理解，知识库做决策）
6. **产品参考：** phlox（医疗scribe）+ xinyu-medical-agent（生产级Agent）

**你现在可以开始做MVP了。**

---

*累计分析：58个项目README | 整理时间：2026-10-16*
