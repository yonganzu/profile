# yonganzu

兼具 IT 运维与 AI 应用开发实践，持续积累 Windows 终端维护、Linux 环境部署、Python 自动化与 RAG 系统开发经验。

## 项目经历

### Windows 终端部署与故障排查

**项目类型：** 个人技术实践

**技术关键词：** Windows 10/11、PE、BIOS、UEFI、Secure Boot、TPM、Hyper-V、WSL、PowerShell

- 完成 Windows 10/11 安装部署、启动盘制作、PE 环境维护、驱动安装与系统恢复，熟悉 BIOS/UEFI、Secure Boot、TPM 等基础配置。
- 排查系统启动异常、PIN 失效、驱动冲突、设备 Code 19、资源管理器右键卡顿等问题，并通过驱动回退、注册表检查和系统修复定位原因。
- 配置 Hyper-V 与 WSL/Ubuntu 开发环境，处理虚拟化、网络连接和 Windows/Linux 文件互通问题。
- 开展 PC 硬件装配与维护实践，覆盖存储、内存、驱动及外设问题；完成打印机安装、共享与基础网络配置。
- 使用 PowerShell、CMD 和系统管理工具收集状态、验证修复结果并沉淀排障步骤。

### Linux / WSL 开发与服务器环境部署

**项目类型：** 个人技术实践

**技术关键词：** Ubuntu、WSL、Linux、SSH、Docker、Python、Git、服务部署

- 在 WSL/Ubuntu 与 Linux 服务器中搭建 Python 开发环境，完成依赖安装、虚拟环境配置及应用运行验证。
- 使用 SSH 进行远程连接和基础服务器管理，围绕软件安装、端口配置、进程与服务状态开展故障排查。
- 实践 Docker 基础使用和 Linux 应用部署，接触 Hermes、OpenClaw 等 Agent 项目的环境搭建与运行验证。
- 结合日志、网络连通性和服务状态定位启动失败、端口不可用及依赖异常等常见问题。
- 将 Windows、WSL 和远程 Linux 环境串联为统一开发链路，为 Python 与 AI 项目提供可复用的运行环境。

### 手搓 RAG：检索增强生成知识库系统

**项目周期：** 2026.05 – 2026.06

**项目角色：** 独立开发

**项目地址：** [github.com/yonganzu/my-rag](https://github.com/yonganzu/my-rag)

**技术栈：** Python 3.13、Gradio 6、FAISS、BM25、RRF、BGE Reranker、DashScope、Ollama、Sentence Transformers

从零实现完整的 RAG（Retrieval-Augmented Generation）链路，不依赖 LangChain、LlamaIndex 等现成 RAG 框架，覆盖文档解析、文本分块、向量化、混合检索、重排序、提示词构建、模型生成与多轮对话管理，并持续迭代至 v1.3.0。

- **模块化 RAG 架构：** 将文档加载、Embedding、向量数据库、检索器、LLM 调用和生成管线拆分为独立模块；通过统一接口与工厂模式支持 FAISS、内存向量库和自动降级。
- **混合检索与重排序：** 独立实现 BM25 关键词检索和向量语义检索，使用 RRF 合并结果；提供 none、vector、keyword、LLM、BGE 五种重排序策略，并支持展示检索片段与来源文件。
- **查询理解与召回增强：** 实现历史融合、同义词扩展、HyDE 和 Multi-Query；针对代词、上下文引用和话题延续实现规则/LLM 双策略查询改写。
- **多轮对话管理：** 将 ConversationManager 注入 RAGPipeline，由后端根据 user_id 与 conversation_id 获取、修剪和持久化上下文，并隔离用户数据。
- **云端与本地模型切换：** 统一封装 DashScope、Ollama 和本地 Transformers 接口；Embedding 支持 API 与 Sentence-BERT，本地重排序支持 BGE，可通过 `.env` 切换方案并实现纯本地运行。
- **知识库应用能力：** 使用 Gradio 构建 Web 界面，支持多格式文档上传、变更检测、增量向量化、向量库持久化和历史会话管理；实现 PBKDF2 登录认证、多角色管理与文档级访问控制。
- **测试与评估：** 为检索、重排序、多轮对话、权限过滤和管线元数据编写专项测试及评估脚本，并维护规格文档和版本化更新日志。

## 技能概览

- **系统与运维：** Windows 10/11、Linux、Ubuntu、WSL、Hyper-V、SSH、Docker、BIOS/UEFI、终端与外设故障排查
- **AI 与开发：** Python、RAG、Embedding、向量检索、BM25、Rerank、LLM、Gradio
- **工程工具：** Git、PowerShell、CMD、环境变量与依赖管理、日志分析
