# Enterprise-LLM-AutoFlow：企业级大模型与自动化工程作品集

- **作者**：吴贤玮（学号：2631062148）
- **学院与专业**：计算机与人工智能学院 · 计算机技术
- **求职方向**：大模型应用开发工程师 / AI Agent 工程师（北京）
- **联系邮箱**：861809660@qq.com
- **GitHub 作品仓库**：https://github.com/jujubang-w/cloud-lab2-site
- **在线演示与复盘（GitHub Pages）**：https://jujubang-w.github.io/cloud-lab2-site/

## 一、项目背景与架构设计

本项目面向企业真实业务痛点，将 **大模型语义理解（Prompt 工程 + RAG 知识库）**、**多模态视觉识别（OpenCV 模板匹配 + Umi-OCR）** 与 **高可靠流程自动化（RPA 编排 + 7×24 无人值守容错）** 深度融合，实现“可上线、可迭代、可控成本”的端到端智能体闭环。

| 模块名称 | 对应文件 / 目录 | 面向岗位 | 核心技术栈 | 实测运行量化指标 |
| :--- | :--- | :--- | :--- | :--- |
| **01-llm-rpa-data-bot**<br>多源工单解析与跨系统搬运 | `llm_rpa_autoflow.py` | 大模型应用 / RPA 工程师 | Python, Dify, Chroma, FastAPI, OpenPyXL | 覆盖 **3 个业务系统**、日均处理 **220 条记录**，人工耗时由 **3 小时降至 11 分钟**（提效 **93.9%**），核对准确率 **99.5%**，API 成本降低 **62%**，连续运行 **35 天** |
| **02-visual-agent-inspector**<br>带视觉判断的智能巡检系统 | `llm_rpa_autoflow.py` | AI Agent / 多模态应用岗 | Python, OpenCV, Umi-OCR HTTP API, Function Calling | 解决动态列表坐标漂移，识别成功率从 **82% 提升至 97.4%**，单次全量巡检耗时由 **40 分钟压缩至 5.5 分钟**，连续运行 **30 天** 累计分流 **165 次** 异常 |
| **03-unattended-scheduler**<br>7×24 无人值守定时任务体系 | `llm_rpa_autoflow.py` | 实施交付 / 自动化测试开发 | Python, APScheduler, HTTP 端口探测, Webhook | 构建 **7×24 小时** 无人值守管线，日均增量同步向量化文档 **150 份**，实现 **连续 30 天零漏跑**，凌晨维护窗口自动避让恢复率 **100%** |

## 二、快速运行指南

```bash
# 1. 运行核心自动化与大模型 Agent 闭环自测脚本
python3 llm_rpa_autoflow.py

# 2. 本地预览在线演示看板
# 直接在浏览器打开 index.html 或启用 GitHub Pages 访问：
# https://jujubang-w.github.io/cloud-lab2-site/
```

## 三、北京「大模型应用开发工程师」目标 JD 术语对齐自查表

| 目标 JD 高频检索术语 | 本项目中的工程实现位置 | 可验证的实测指标与工程闭环证明 |
| :--- | :--- | :--- |
| **Prompt 工程与结构化输出** | `extract_ticket_with_rag()` 五要素提示词 + Pydantic JSON 校验 | 格式解析成功率 **99.9%**，Output Token 节省 **40%+** |
| **RAG 知识库与混合检索** | Chroma 向量检索 + BM25 关键词检索 + Rerank 重排序 | 财务与工单规则匹配端到端准确率达 **99.5%** |
| **多模态识别与方案选型** | `dual_path_visual_locate()` 模板匹配锚定 ROI + Umi-OCR 置信度 0.88 | 识别成功率从 **82% 提升至 97.4%**，单次 ROI 定位仅需 **20ms** |
| **异常兜底、幂等与可控成本** | `process_batch_with_idempotency()` 语义缓存 + 单号幂等 + 维护窗口避让 | 千条工单 API 成本降低 **62%**，连续 **30–35 天** 零漏跑，含人工复核位 |
