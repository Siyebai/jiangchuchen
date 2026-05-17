# TOOLS.md — 工具链与模型配置

> 工具链引用与模型路由配置速查。

---

## 配置文件位置

| 文件 | 路径 |
|------|------|
| 主配置 | `D:\openclaw\config\openclaw.json` |
| 用户配置 | `C:\Users\李初尘\.openclaw\openclaw.json` |

## Gateway

| 项 | 值 |
|----|-----|
| 端口 | 18789 / 18791 |
| 安全 | bind=loopback, auth=token, chatCompletions=off |

## 模型路由

| 优先级 | 模型 | Provider |
|--------|------|----------|
| 主 | siliconflow/deepseek-ai/DeepSeek-V4-Flash | SiliconFlow |
| Fallback 1 | deepseek-ai/DeepSeek-V3 | SiliconFlow |
| Fallback 2 | Qwen2.5-72B-128K | SiliconFlow |

| Provider | 端点 |
|----------|------|
| deepseek | api.deepseek.com |
| ollama | localhost:11434 |
| siliconflow | api.siliconflow.cn |

---

## 已安装技能 (11 个)

| 技能 | 用途 |
|------|------|
| agent-self-evolve | 自我进化系统基础 |
| cross-channel-cross-agent-sharing | 跨渠道共享 |
| find-skills | 技能发现 |
| hermes-for-win | Hermes 生态安装部署 |
| listenhub | 文本转音频/播客/视频 |
| reach | 网页自动化交互 |
| remotion | React 视频创作 |
| sage-memory | 共识记忆系统 |
| shike-self-evolve | 自进化机制（三层架构） |
| skillhub-preference | 技能发现首选项 |
| xiaohongshu-all-in-one | 小红书全链路运营 |
