---
title: 竞品分析 Agent
emoji: 🔍
colorFrom: red
colorTo: blue
sdk: streamlit
sdk_version: "1.35.0"
python_version: "3.10"
app_file: app.py
pinned: false
---

# 🔍 竞品分析 Agent

基于 LangGraph ReAct Agent 的智能竞品分析工具，支持实时联网搜索，自动生成 11 章专业竞品调研报告。

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://huggingface.co/spaces/kktaro/competitoragent-web)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

---

## 📋 目录

- [项目简介](#项目简介)
- [能做什么](#能做什么)
- [工作原理](#工作原理)
- [报告结构](#报告结构)
- [快速开始](#快速开始)
- [部署方式](#部署方式)
- [技术栈](#技术栈)

---

## 项目简介

竞品分析 Agent 是一个智能化的竞品调研工具，通过 AI Agent 自动收集竞品信息、分析市场数据、生成结构化报告。无论是产品经理、市场分析师还是创业者，都可以快速获取专业级的竞品洞察。

**在线体验**: [https://huggingface.co/spaces/kktaro/competitoragent-web](https://huggingface.co/spaces/kktaro/competitoragent-web)

---

## 能做什么

### 1. 📊 查看预置 Demo 报告（无需 API Key）

我们已经为你生成了 3 份 2026 年 Q1 最新数据的竞品分析报告：

| Demo 报告 | 竞品 | 数据时间 |
|-----------|------|----------|
| **AI 对话产品** | 豆包 vs Kimi vs DeepSeek | 2026 Q1 |
| **AI 写作工具** | Notion AI vs 飞书 AI vs 语雀 | 2026 Q1 |
| **项目管理 SaaS** | 飞书 vs 钉钉 vs Jira | 2026 Q1 |

每份报告包含 **11 个章节**，**4000+ 字**，涵盖市场分析、产品拆解、商业模式、SWOT 对比等专业内容。

### 2. 🔍 自定义竞品分析（需要 API Key）

输入你想分析的竞品和赛道，AI Agent 会：

1. **实时搜索** - 自动搜索竞品的公开信息
2. **网页抓取** - 提取官网、新闻、评测的关键数据
3. **智能分析** - 基于收集的信息进行结构化分析
4. **生成报告** - 输出 11 章专业竞品调研报告

**使用示例：**
- 竞品：「小米汽车、特斯拉、蔚来」
- 赛道：「智能电动汽车」
- 输出：完整的竞品分析报告

### 3. 💾 导出 Word 文档

生成的报告支持一键下载为 Word 格式，方便二次编辑和分享。

---

## 工作原理

### 技术架构

```
┌─────────────────────────────────────────────────────────────┐
│                        用户界面 (Streamlit)                   │
├─────────────────────────────────────────────────────────────┤
│                    LangGraph ReAct Agent                     │
│  ┌──────────────┐    ┌──────────────┐    ┌──────────────┐  │
│  │   搜索工具    │◄──►│   LLM 推理   │◄──►│  网页抓取    │  │
│  │(DuckDuckGo)  │    │(GPT/Claude  │    │   工具      │  │
│  └──────────────┘    │  兼容接口)   │    └──────────────┘  │
│                      └──────────────┘                       │
└─────────────────────────────────────────────────────────────┘
```

### Agent 工作流程

```
阶段一：信息搜集
├── 搜索竞品 1 的公开信息
├── 抓取竞品 1 官网内容
├── 搜索竞品 2 的公开信息
├── 抓取竞品 2 官网内容
├── 搜索竞品 3 的公开信息
└── 抓取竞品 3 官网内容

阶段二：报告生成
├── 分析市场背景与趋势
├── 拆解各竞品核心能力
├── 对比商业模式与定价
├── 评估增长策略与用户画像
├── SWOT 优劣势分析
└── 输出机会点与策略建议
```

### 核心能力

- **实时联网搜索** - 基于 DuckDuckGo 搜索最新公开信息
- **网页内容抓取** - 自动提取网页正文内容
- **多轮推理** - LangGraph 驱动的多步骤 Agent 工作流
- **结构化输出** - 固定 11 章报告格式，确保内容完整性

---

## 报告结构

每份报告包含以下 11 个章节：

| 章节 | 内容 |
|------|------|
| **一、报告概述** | Executive Summary，核心结论与关键趋势 |
| **二、市场与赛道分析** | 市场规模、增速、竞争格局、趋势判断 |
| **三、竞品选择与分层** | 竞品定位分析与选择逻辑 |
| **四、核心能力拆解** | 每个竞品的 9 个维度详细分析（定位、功能、技术、定价、用户规模等） |
| **五、商业模式分析** | 收费方式、客单价、付费转化路径、收入来源 |
| **六、增长与分发策略** | 获客渠道、增长策略、分发方式 |
| **七、用户与场景分析** | 用户画像、核心场景、使用频率 |
| **八、优劣势对比** | SWOT 分析 + 综合能力对比矩阵 |
| **九、关键差异与壁垒** | 核心竞争壁垒与护城河分析 |
| **十、机会点与策略建议** | 市场机会与可执行建议 |
| **十一、数据附录** | 所有数据来源与引用链接 |

**报告特点：**
- ✅ 4000+ 字深度内容
- ✅ 所有数据标注来源
- ✅ 表格对比关键指标
- ✅ 支持导出 Word 格式

---

## 快速开始

### 本地运行

```bash
# 1. 克隆仓库
git clone https://github.com/kk-taro/competitoragent-web.git
cd competitoragent-web

# 2. 安装依赖
pip install -r requirements.txt

# 3. 运行应用
streamlit run app.py
```

### 使用自定义分析

1. 打开侧边栏（左上角箭头）
2. 填写 API Key（支持 OpenAI 兼容接口）
3. 输入 Base URL 和模型名称
4. 在「自定义分析」标签页输入竞品和赛道
5. 点击「开始分析」

**支持的模型：**
- OpenAI GPT-4/GPT-3.5
- 阿里云通义千问
- DeepSeek
- 月之暗面 Kimi
- 其他 OpenAI 兼容接口

---

## 部署方式

### 部署到 Hugging Face Spaces

1. Fork 本仓库
2. 创建新的 Hugging Face Space（选择 Streamlit 模板）
3. 将代码推送到 Space
4. 自动部署完成

### 部署到 Streamlit Cloud

1. 访问 [share.streamlit.io](https://share.streamlit.io)
2. 连接 GitHub 仓库
3. 选择主文件 `app.py`
4. 点击 Deploy

---

## 技术栈

| 技术 | 用途 |
|------|------|
| **Streamlit** | Web 应用框架 |
| **LangGraph** | Agent 工作流编排 |
| **LangChain** | LLM 应用开发框架 |
| **DuckDuckGo Search** | 实时网络搜索 |
| **python-docx** | Word 文档导出 |
| **OpenAI 兼容接口** | 大模型调用 |

---

## 项目结构

```
.
├── app.py                    # 主应用文件
├── requirements.txt          # 依赖列表
├── README.md                 # 项目说明
├── .streamlit/
│   └── config.toml          # Streamlit 配置
└── skills/                  # PM 方法论技能库
    ├── claude-skills/
    │   └── competitive-analysis/
    └── lenny-pm-skills/
```

---

## 数据来源说明

Demo 报告数据来源于：
- 各公司官方披露与财报
- 行业研究报告（艾瑞咨询、IDC、QuestMobile 等）
- 权威媒体（36kr、极客公园、机器之心等）

数据更新时间：**2026年Q1**

---

## License

MIT License

---

## 贡献

欢迎提交 Issue 和 PR！

如有问题或建议，请在 [GitHub Issues](https://github.com/kk-taro/competitoragent-web/issues) 中反馈。
