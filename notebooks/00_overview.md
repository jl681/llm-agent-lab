从零构建多模型 LLM Agent 的动手实验室  
不依赖 LangChain，不追求黑盒封装，只关注原理、控制力与可扩展性。

## 项目初心

我想学如何真正构建一个 LLM Agent。  
但大多数教程要么：

- 直接扔给我一行 AgentExecutor.from_agent_and_tools(...)，说“看，它能用了！”——可我根本不知道背后发生了什么；
- 要么一上来就讲 AutoGen、LangGraph，却跳过了最基础的问题：“API 怎么调？模型怎么换？记忆怎么加？”

于是，我决定从最底层开始，亲手实现每一个组件。这个 repo 就是我一路踩坑、验证、重构的学习笔记。

## 完整学习路线

| 序号 | Notebook 文件名                       | 核心目标                          | 关键能力 / 知识点                                                          |
| ---- | ------------------------------------- | --------------------------------- | -------------------------------------------------------------------------- |
| 1    | `01_setup_qwen_api.ipynb`             | 调通通义千问（Qwen）              | 阿里云百炼平台、DashScope 兼容 API、`qwen-max` 调用                        |
| 2    | `02_setup_doubao_api.ipynb`           | 调通豆包（Doubao）                | 火山方舟（Ark）平台、Model ID（`doubao-seed-1-8-251228`）、开通模型服务    |
| 3    | `03_unified_llm_interface.ipynb`      | 统一多模型调用接口                | 抽象基类 `BaseLLM`、OpenAI SDK 封装、模型无关调用                          |
| 4    | `04_simple_model_orchestration.ipynb` | 实现多模型编排                    | 串行流水线（Pipeline）、并行调用、模型路由（Router）、并行投票（Ensemble） |
| 5    | `05_agent_with_memory.ipynb`          | 为 Agent 添加对话记忆             | 消息历史管理、Token 长度截断、上下文保持                                   |
| 6    | `06_agent_with_tools.ipynb`           | 让 Agent 使用外部工具             | 工具注册、函数调用、安全执行、工具描述（为自动选择铺垫）                   |
| 7    | `07_react_agent.ipynb`                | 实现 ReAct 推理框架               | Thought-Action-Observation 循环、自主规划、多步推理、防死循环机制          |
| 8    | `08_multi_agent_collaboration.ipynb`  | 多 Agent 协作解决问题（可选进阶） | 角色分工（Writer/Reviewer）、消息传递、协作协议                            |

## 设计原则

1. 透明 > 便捷，宁可多写几行代码，也要看清每一层逻辑。
2. 模块化 Notebook，每个 .ipynb 聚焦一个核心概念，可独立运行、可组合使用。
3. 国产模型优先更便捷地使用大模型
   重点支持通义千问、豆包等国内主流模型，适配真实开发环境。
4. 无重型框架依赖，仅用 openai SDK + 标准库，避免被 LangChain 等绑定。

## 环境要求

- Python ≥ 3.9
- 依赖：openai>=1.40.0, python-dotenv, jupyter
- 账号：
  - 阿里云百炼（获取 QWEN_API_KEY）
  - 火山引擎 Ark（获取 ARK_API_KEY，并开通 doubao-seed-1-8-251228）

## 详细配置指南见：`guides` 目录

## 如何使用本项目？

1. 从 01_setup_qwen_api.ipynb 开始，按顺序学习
2. 每个 notebook 都包含：
   - 原理解释
   - 可运行代码
   - 错误处理提示
3. 鼓励你：
   - 修改参数尝试不同效果
   - 替换模型测试兼容性
   - 在基础上构建自己的 Agent

🌱 你不是在调用一个 Agent，你是在成为它的建筑师。
