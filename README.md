# zhiliao · AI 应用开发

把好奇心做成看得见的作品。三个已上线系统，从后端、客户端、管理端到网关与部署，全部独立完成。

📍 **作品集：https://zhiliaohub.com** 　·　 ✉️ z987645344@gmail.com 　·　 2027 届 

---

## 仓库地图

一套能上线的产品需要后端、客户端、管理端、网关和部署，缺一块就跑不起来。下面是我做的三个产品。

### 1️⃣ 知天 · 企业知识库 Agent 平台　[▶ 在线体验](https://agent.zhiliaohub.com/login.html)

本地优先的知识库 Agent 平台：对话、企业知识库检索、联网搜索、文件处理、任务分解、权限审核、运行诊断在同一条可追踪链路上。后端 FastAPI + LangGraph，模型全量接入 DeepSeek API；检索为 BM25 + 向量混合检索 + 批量重排序，并支持 GraphRAG 图谱增强。

| 仓库 | 说明 | 技术栈 |
|---|---|---|
| [**zhitian**](https://github.com/z987645344-arch/zhitian) | 后端 + 客户网页端 | Python / FastAPI / LangGraph |
| [**zhitian_app**](https://github.com/z987645344-arch/zhitian_app) | Windows 客户端 | Dart / Flutter |
| [**zhitian_admin**](https://github.com/z987645344-arch/zhitian_admin) | 员工 / 审核员 / 开发者管理端 | JavaScript |
| [**zhitian-deploy**](https://github.com/z987645344-arch/zhitian-deploy) | 部署：Compose、备份调度、灾备恢复 | Docker / nginx |
| [**zhiliao-gateway**](https://github.com/z987645344-arch/zhiliao-gateway) | 统一前置网关：域名规范化、TLS 终止 | nginx |

### 2️⃣ 知了hub · 个人作品站　[▶ 在线访问](https://zhiliaohub.com)

访客前台为原生 HTML/CSS/JS（无构建工具，无运行时依赖），Node.js 管理后台在保存时直接生成静态页。

| 仓库 | 说明 | 技术栈 |
|---|---|---|
| [**zhiliaohub**](https://github.com/z987645344-arch/zhiliaohub) | 站点 + 管理后台 | Node.js / Express / SQLite |
| [**zhiliaohub_app**](https://github.com/z987645344-arch/zhiliaohub_app) | 管理端 Android App（设备配对 + TOTP） | Kotlin / AndroidX |

### 3️⃣ 知逸 · Unity 微恐小游戏　[▶ 试玩](https://lab.zhiliaohub.com/u77e5-u9038-0-u2e-3-u2e-0/)

2 个场景、系列动作与音效、推 / 拉交互与场景切换。

| 仓库 | 说明 | 技术栈 |
|---|---|---|
| [**zhiyi**](https://github.com/z987645344-arch/zhiyi) | 游戏工程 | Unity / C# |
| [**zhiyi-unity**](https://github.com/z987645344-arch/zhiyi-unity) | 场景与资源 | Unity |

### 其他作品（不在 GitHub）

- **ComfyUI 中文创作整合包「知了整合包」** —— 在 8GB 显存笔记本上一站式完成图片 / 音乐 / 音效 / 视频的生成与后期。自研节点包把复杂节点收进子图，搭了 00–05 六套中文工作流，5 秒视频生成从 4.3 分钟优化到 2.0 分钟，并打包成可直接分享的整合包。→ [作品页](https://zhiliaohub.com/works.html)

---

## 技术栈

![Python](https://img.shields.io/badge/Python-3.10-3776AB?logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-Agent-1C3C3C)
![Flutter](https://img.shields.io/badge/Flutter-Windows-02569B?logo=flutter&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-Android-7F52FF?logo=kotlin&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker&logoColor=white)
![nginx](https://img.shields.io/badge/nginx-gateway-009639?logo=nginx&logoColor=white)
![DeepSeek](https://img.shields.io/badge/LLM-DeepSeek_API-4D6BFE)

**AI 应用与 Agent**：LangGraph 编排 · RAG（BM25 + 向量混合检索 / 重排序 / GraphRAG）· Prompt 工程 · Function Calling 与工具路由 · Chroma · MCP 协议
**后端与工程**：Python（FastAPI）· Dart（Flutter）· Kotlin（Android 原生 / MethodChannel）· SQL · Git · CI/CD（GitHub Actions）· Docker + nginx + HTTPS
**本地化 AI 部署**：ComfyUI 工作流与自定义节点 · 显存预算调优 · 推理加速（SageAttention / int8 VAE / LoRA）

---

<!-- 这一节是主动说明，不是坦白：贡献者列表本来就是公开的，先说明比被追问强 -->
## 关于实现方式

架构决策、任务拆解、验收标准与运维配置由我负责；应用层的具体实现借助 Claude Code 协同完成。

这一点可以从各仓库的提交记录直接核对，分两层：

- **基础设施层** —— [zhiliao-gateway](https://github.com/z987645344-arch/zhiliao-gateway)（统一网关）与 [zhitian-deploy](https://github.com/z987645344-arch/zhitian-deploy)（部署编排）：**提交作者全部是我本人**，没有 AI 作者的提交。
- **应用层** —— 知天三端与知了hub：**我主导设计与开发，使用 AI 辅助编码**；这些仓库包含 AI 作为提交作者的提交（主要是前端视觉改版），以及带 AI 共同作者行的提交。

我为此建立了 **403 项后端测试**与 **49 项客户端测试**作为约束，所有验证走真实 HTTP 与真实运行结果——**AI 会写出能跑但错的东西，验收这一步不能省。**

我的强项是**把系统真正跑起来并跑稳**：容器最小权限（`cap_drop: ALL` + `NET_BIND_SERVICE` / `SETUID` / `SETGID` / `CHOWN`）、网络分层与隔离、非 root 运行、TLS 与网关路由、加密备份与灾难恢复。

## 联系方式

- 作品集网站：https://zhiliaohub.com
- 邮箱：z987645344@gmail.com

---

## License

本账号下的仓库未附带开源许可证，默认保留全部权利；公开复用前请先联系作者。

---
