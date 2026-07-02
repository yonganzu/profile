# yonganzu

具备 AI 应用开发、水文科研计算与 IT 运维实践，持续积累 RAG 系统开发、深度学习时序预测、Windows/Linux 环境部署及故障排查经验。

## 简历资料

- [IT Support Resume Master](resume/IT_Support_Resume_Master.md)

## 项目经历

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

### 水文时序分析与深度学习径流预测

**项目周期：** 2023.11 – 2025.06

**项目类型：** 科研项目

**技术栈：** Python、PyTorch、TensorFlow、Pandas、NumPy、Scikit-learn、XGBoost、MATLAB、ArcGIS

围绕额尔齐斯河流域水文过程与径流变化开展数据处理、统计分析和智能预测研究，参与第三次新疆综合科学考察相关研究工作。

- **数据处理流水线：** 使用 Python、Pandas 与 MATLAB 处理多站点、长时间序列水文气象数据，完成时间索引统一、小时/日/月尺度聚合、缺失与异常值处理、特征构建及 Excel/NetCDF 数据转换。
- **气象数据获取：** 使用 CDS API 批量获取 ERA5 再分析数据，配置代理和认证流程，完成温度等气象变量的自动下载与整理。
- **水文统计分析：** 开展丰水年、平水年与枯水年分类，结合累积距平、Mann–Kendall 趋势检验、小波/MODWT 多尺度分解分析径流趋势、突变与周期特征。
- **预测模型试验：** 使用 XGBoost、LSTM、GRU、Transformer 等模型开展径流预测与对比，围绕样本窗口、特征筛选、张量维度、缺失标签和训练稳定性持续优化数据与模型流程。
- **空间过程建模：** 探索融合 DEM、土地利用和土壤类型的网格神经网络，引入相邻网格状态与基于地形的汇流机制，模拟截流、入渗、蓄水和径流过程。
- **科研工程化：** 编写批处理、可视化和结果导出脚本，处理中文字体、图表排版、并行计算与 GPU 环境配置，提升重复试验和成果整理效率。

### Windows 终端部署与故障排查

**项目类型：** 个人技术实践

**技术关键词：** Windows 10/11、PE、BIOS、UEFI、Secure Boot、TPM、Hyper-V、WSL、PowerShell

- 完成 Windows 10/11 安装部署、Ventoy/启动盘制作、PE 环境维护、驱动安装与系统恢复，熟悉 BIOS/UEFI、Secure Boot、TPM 等基础配置。
- 排查系统启动异常、PIN 失效、驱动冲突、设备 Code 19、资源管理器右键扩展卡顿等问题，使用 Autoruns、注册表、SFC、DISM 与磁盘检查工具定位原因。
- 处理硬盘迁移、硬件更换后的驱动和网络问题，核对 BIOS/DMI 序列号、Windows 激活与厂商驱动识别。
- 配置 Ricoh 等网络打印机，完成 IP/端口确认、局域网发现、驱动安装、打印尺寸与共享问题排查。
- 配置 Hyper-V 外部虚拟交换机、CentOS/Ubuntu 虚拟机及 WSL 开发环境，处理 DHCP、网络连接和 Windows/Linux 文件互通问题。

### Linux / WSL 开发与服务器环境部署

**项目类型：** 个人技术实践

**技术关键词：** Ubuntu、CentOS、WSL、SSH、Docker、Nginx、Python、Conda、systemd

- 在 WSL/Ubuntu 与 CentOS 服务器中搭建 Python、Conda、Jupyter 和 AI 开发环境，处理依赖、代理、CUDA/PyTorch 与虚拟环境问题。
- 使用 SSH 进行远程连接和服务器管理，围绕软件安装、端口、进程、systemd 服务与日志开展故障排查。
- 实践 Docker 跨平台开发与 Linux 容器部署，处理 Windows/WSL 挂载、网络和文件系统差异。
- 配置 Nginx、域名解析与 HTTPS，开展基础服务部署；安装 Intel oneAPI/Fortran 工具链并维护环境变量。
- 在 WSL 中部署和调试 Hermes、OpenClaw 等 Agent 工具，处理 systemd 用户会话、后端选择、API 配置和权限隔离问题。

## 其他工程实践

- 使用 PyInstaller、cx_Freeze 将 Python 数据处理脚本封装为 Windows/Linux 可执行程序，便于无开发环境的终端运行。
- 使用 Go 进行 Linux/ARM 交叉编译，将自动认证程序部署到路由器环境，实践跨平台构建与运行排查。
- 使用 Git、PowerShell、CMD 与 Shell 维护开发环境和批处理流程，处理 Conda、Jupyter、ArcGIS、代理及依赖兼容问题。

## 技能概览

- **AI 与开发：** Python、PyTorch、TensorFlow、RAG、Embedding、向量检索、BM25、Rerank、LLM、Gradio
- **数据与科研计算：** Pandas、NumPy、Scikit-learn、XGBoost、MATLAB、ArcGIS、水文时序分析、深度学习预测
- **系统与运维：** Windows 10/11、Linux、Ubuntu、CentOS、WSL、Hyper-V、SSH、Docker、Nginx、BIOS/UEFI、终端与外设故障排查
- **工程工具：** Git、PowerShell、CMD、Shell、Conda、Jupyter、环境变量与依赖管理、日志分析
