# MEMORY.md — 长期记忆

> 机器规格、软件配置、系统加固记录、小说设定（概览）、待办事项。  
> 完整内容请参见各子文件及每日日志 `daily-logs/` 目录。

---

## 硬件规格

| 组件 | 型号/规格 |
|------|----------|
| CPU | Intel i5-11320H 4C8T |
| RAM | 15.8 GB |
| SSD | KIOXIA NVMe 512G |
| GPU | Intel Iris Xe（2021 驱动 — 待更新） |
| OS | Windows 11 Insider Preview Build 26200 (25H2) |

## 软件配置

| 组件 | 值 |
|------|-----|
| OpenClaw 主模型 | siliconflow/deepseek-ai/DeepSeek-V4-Flash |
| Fallback | deepseek-ai/DeepSeek-V3 → Qwen2.5-72B-128K |
| Thinking 默认 | off |
| Context Injection | always |
| Timeout | 120s |
| Compaction | auto, keepRecentTokens=24000 |
| Gateway 端口 | 18789/18791, bind=loopback, auth=token |

## Hermes 生态

| 组件 | 端口 |
|------|------|
| API | 8642 |
| NextChat | 3000 |
| Dashboard | 9119 |
| Ollama | 11434 |
| 启动脚本 | `D:\Hermes\_start_fixed.cmd` |

---

## 已知风险 & 待办

| 优先级 | 事项 | 说明 |
|--------|------|------|
| 🔴 | C 盘空间不足 | 19 GB 空闲，需清理 |
| 🔴 | GPU 驱动过旧 | 2021 版 Intel Iris Xe，待更新 |
| 🟡 | Insider 不稳定 | Win11 25H2 Preview，考虑退出 |
| 🟡 | 360 后台占用 | 待清理 |
| 🟡 | Docker 数据迁移 | 从 C 盘迁至 D 盘 |
| 🟡 | Ollama 内存占用 | 常驻 6.2 GB，进化完成后释放 |
| 🟢 | 系统卡死根因已定位 | C 盘不足 + GPU 驱动旧 + Insider 不稳定 + 360 后台 + 启动项过多 |
