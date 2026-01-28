# LLM Agent Lab 🧪 从零构建多模型智能体

通过一系列模块化 Jupyter Notebook，系统学习如何从 API 调用到构建可协作的 LLM Agent。

本项目通过引用Notebook模块的概念，试图达到目标：

- 🔍 理解底层原理（API 如何工作？Agent 如何思考？）
- 🧩 亲手实现每个组件（记忆、工具、规划、多模型编排）
- 🌐 支持多模型（通义千问、豆包、OpenAI 等），通过统一接口自由切换

🗺️ 学习路线

1. 基础 API 调用 获取 Key，调用 Qwen（OpenAI 兼容模式）

2. 多模型接入 接入豆包（Doubao），抽象统一 LLM 接口

3. Agent 核心组件 实现记忆（Memory）、工具调用（Tools）、简单规划

4. 模型编排（Orchestration） 串行/并行调用多模型，构建协作流程

5. 完整 Agent 示例 能查天气、做计算、联网搜索的智能体

6. 进阶探索 多 Agent 协作、评估、部署到百炼等平台

所有代码均以 .ipynb 形式提供，边学边改，即时反馈。

## 🚀 快速开始

1. 克隆本仓库：
   ```bash
   git clone https://github.com/yourname/llm-agent-lab.git
   cd llm-agent-lab
   ```
2. 创建虚拟环境并激活：
   ```bash
   python -m venv .venv
   source .venv/bin/activate      # Linux/macOS
   # .venv\Scripts\activate       # Windows
   ```
3. 安装依赖：
   ```bash
   pip install -r requirements.txt
   ```
4. 配置 API 密钥：
   ```bash
   cp .env.example .env
   # 编辑 .env，填入你的 Qwen、Doubao 等 API Key
   ```
5. 启动 Jupyter：
   ```bash
   为了让 Notebook 使用你刚创建的虚拟环境（`.venv`），请在打开 notebook 后：
   1. 点击顶部菜单：Kernel → Change kernel
   2. 选择 Python (.venv)
   ```
6. 打开第一个 Notebook
   - 浏览 notebooks/00-overview.md 了解第一部分目标
   - 运行 notebooks/01_setup_qwen_api.ipynb 开始学习！
