# LLM Agent Lab 🧪

通过一系列 Jupyter Notebook，从零学习如何使用大语言模型（如通义千问、豆包等）构建智能 Agent。

## 🎯 目标

- 学习 LLM API 调用
- 封装多模型统一接口
- 实现带记忆、工具调用、多 Agent 协作的系统

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
6. 打开 notebooks/01_setup_qwen_api.ipynb 开始学习！
