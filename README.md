<p align="center">
  <img src="./assets/banner.png" alt="MarkITwains — Backend / LLM Infrastructure" width="100%">
</p>

<h1 align="center">王某某 · MarkITwains</h1>

<p align="center">
  成都工业学院 · 计算机科学与技术 2028 届　|　后端 / LLM 基础设施　|　坐标成都
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Open%20to-2027%20Summer%20Intern-2ea44f?style=flat-square" alt="Open to 2027 Summer Intern">
  <img src="https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white" alt="Go">
  <img src="https://img.shields.io/badge/C%2FC%2B%2B-00599C?style=flat-square&logo=cplusplus&logoColor=white" alt="C/C++">
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black" alt="Linux">
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker">
</p>

---

> 🔍 **正在找 2027 年暑期实习 / 大三下日常实习**
>
> - **方向**：大模型应用后端 · AI 平台 / 推理服务 · Agent 运行时 · 基础软件
> - **地点**：成都优先
> - **到岗**：每周可到岗 3 天以上，2027-02 起可全职实习

## 关于我

写 Go 和 C，日常在 Linux 上折腾模型服务、网关和 Agent 运行时。关心的问题只有一个：**怎么把大模型跑得稳、跑得省、跑进生产环境。**

- 偏底层：从 SSE 长连接、限流计费，一路做到 vLLM 的显存与 TTFT，喜欢把链路拆开、用数据说话
- 只看真实指标：站点可用率、采集条数、P99 延迟、吞吐、超卖数，而不是"跑通了"
- 手头的项目都跑在容器化的生产形态里，不是玩具 demo

## 项目

### LiteGate — OpenAI 兼容的 LLM 网关

`Go` `Redis` `Docker`　·　自研，v1 开发中

- 统一 OpenAI 协议入口，SSE 流式转发，支持多后端路由与故障转移
- token 级限流与计费，Redis 承载计数器与配额
- **待补数据**：v1 发布后填 —— N 并发 SSE 的 P99 首字节 X ms；接入 vLLM 后吞吐 Y tokens/s

### gov-doc-collector — 中国政府官网政策文档采集器

`Python` `Playwright` `curl_cffi` `MCP`　·　[仓库 →](https://github.com/MarkITwains/GOV-DOC-COLLECTOR)

- 覆盖 61 个部委 / 省级站点，50 个可用（**82%**），已采集 **3380** 条真实政策文档
- 三级反爬降级：`curl_cffi → Playwright → requests`，按站点自动选择开销最小的通道
- 打包为 MCP Server，可接入任意 Agent，把政策检索变成一次工具调用

### Edu-Manager — 高校教务全栈系统

`Go` `Gin` `GORM` `Vue 3`　·　[仓库 →](https://github.com/MarkITwains/EDU-MANAGER)

- 覆盖组织架构、课程与排课、学生选课、成绩管理、数据驾驶舱与权限认证
- 选课链路按高并发抢课设计：Redis 预扣库存 + RabbitMQ 异步落库，规避超卖与数据库热点
- **待补数据**：k6 压测后填 —— 选课接口 N 并发 P99 X ms，超卖 0

### 其他项目

| 项目 | 说明 |
| --- | --- |
| C89 代码生成模型微调 | 基于 Qwen3.6-27B 微调，Pass@1 **待补（before → after）**，用 Valgrind 做内存安全校验 |
| Dify + Ollama 通用 RAG | 负责 Ollama 部署与检索链路 |
| Hermes Agent 部署 | 接入企业微信 / SearXNG / 浏览沙箱 |

## 技术栈

| 方向 | 技术 |
| --- | --- |
| 语言 | Go · C/C++ · Python |
| 基础设施 | Linux · Docker · Redis · MySQL · RabbitMQ · Nginx |
| AI / LLM | vLLM · Ollama · Dify · MCP · LoRA 微调 |

## 正在做（2026-09）

- [ ] LiteGate → LLM Gateway v1：SSE 流式转发、Redis 限流、多后端路由，目标 10 月中发布
- [ ] 用 vLLM 部署 Qwen3.6-27B 量化版，做并发 1 / 8 / 32 的 TTFT、吞吐、显存 benchmark，对比 Ollama
- [ ] 把 gov-doc-collector 的浏览器层升级为带隔离、白名单、审计日志的 Computer Use 沙箱 harness

## 联系

📮 [676006179@qq.com](mailto:676006179@qq.com)　·　📝 [eecs.top](https://eecs.top/)
