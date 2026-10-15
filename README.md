# 医生技能库 · Doctor Skills Library

面向临床医生与医学AI产品的开源Skill知识库，收集、整理和评估可用于临床工作流的AI Agent Skill。

## 目录结构

```
doctor-skills-library/
├── README.md
└── docs/
    ├── 01-医生用AI必装的5个Skill推荐.md      # 抖音@阿尔法猎手 入门精选
    └── 02-OpenClaw-Medical-Skills-869个.md   # 港大HKUDS生态开源全家桶
```

## 核心定位

> 把AI当成规培生——它干文书和检索，你干诊断和决策。

## Skill速览

| 类别 | 数量 | 来源 |
|------|------|------|
| 入门精选（临床日常5件套） | 5 | 抖音@阿尔法猎手 |
| 全家桶（临床+科研+生信） | 869 | FreedomIntelligence / OpenClaw Medical Skills |

## 已收录内容

### 入门级：医生日常5个Skill
- `medical-scribe-dictation` — 口述转SOAP结构化病历
- `tencent-health-ai-clinical-assistant` — 辅助诊断+鉴别诊断
- `medication-advisor` — 用药安全+相互作用审查
- `medical-guidelines-hub` — 权威指南知识库
- `medical-lit` — PubMed文献检索+证据分级

### 进阶级：OpenClaw Medical Skills（869个）
- **临床文书**：SOAP、出院小结、病例报告(CARE)、H&P
- **临床决策**：CDS文档、GRADE证据分级、队列分析
- **指南检索**：NCCN / AHA / ADA / NICE / WHO / CPIC 等12+来源
- **用药安全**：DDI预测、药物警戒、罕见病鉴别
- **科研全流程**：文献综述、药物重定位、精准肿瘤、试验匹配
- **生信流水线**：RNA-seq、scRNA-seq、GWAS、VCF注释、PRS计算

## 兼容工具

所有Skill遵循开放Agent Skills标准（SKILL.md格式），兼容：
- Claude Code
- Cursor
- Codex CLI
- Windsurf
- GitHub Copilot
- 任何MCP兼容工具

## 快速安装

```bash
# 通过 skills-hub CLI 安装单个Skill
npx @skills-hub-ai/cli install <skill-slug>

# 浏览全部869个OpenClaw Medical Skills
curl https://skills-hub.ai/api/v1/skills?source=openclaw-medical
```

## 开源仓库

- [OpenClaw Medical Skills (GitHub)](https://github.com/FreedomIntelligence/OpenClaw-Medical-Skills) — 869个医学Skill，MIT协议
