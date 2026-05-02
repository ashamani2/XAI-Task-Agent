# XAI-Task-Agent

> AI驱动的多Agent任务编排系统，用于研发效能自动化 | 小米AI激励计划技术验证项目

## 项目简介

XAI-Task-Agent 是一套基于大模型的多Agent协作系统，旨在解决研发团队日常工作中的重复性任务痛点。通过任务调度Agent、执行Agent、汇总Agent的协作，实现从意图识别到任务执行的完整闭环。

## 解决的核心问题

- **日报/周报撰写耗时**：工程师每天花费15-20分钟手动汇总工作，Agent可自动生成结构化日报
- **任务意图理解模糊**：通过长链推理，将"帮我整理一下今天的代码工作"等模糊指令解析为可执行步骤
- **多步骤任务编排困难**：传统脚本难以处理需要逻辑推理的任务链，Agent系统可动态拆解并执行

## 技术架构

用户指令 → 调度Agent(意图识别+任务拆解) → 执行Agent(调用工具链) → 汇总Agent(结构化输出)

- **底层模型**：DeepSeek 系列（支持切换至 Claude、GPT 系列）
- **核心技术**：长链推理、多Agent协作、Prompt Engineering
- **开发语言**：Python 3.9+

## 快速开始

### 1. 克隆仓库
git clone https://github.com/ashamani2/XAI-Task-Agent.git
cd XAI-Task-Agent

### 2. 安装依赖
pip install -r requirements.txt

### 3. 配置API Key
在 main.py 中将 your-deepseek-api-key-here 替换为你的 DeepSeek API Key。
申请地址：https://platform.deepseek.com/

### 4. 运行演示
python main.py

## 运行效果

演示模式下，系统将展示完整的Agent推理链路：

- 接收模糊指令
- 调度Agent进行意图识别
- 执行Agent生成结构化日报
- 输出完整日报，展示Token消耗统计

## 后续规划

- 接入小米生态智能设备控制场景
- 实现多Agent间的异步消息队列通信
- 增加代码审查、接口文档自动生成模块
- 支持Claude、GPT等多模型切换
