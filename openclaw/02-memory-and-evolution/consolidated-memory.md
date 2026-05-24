# 记忆仓库 — 2026-05-24 快照

> 用户：李初尘（思夜白） | 时区: Asia/Shanghai | 首次对话: 2026-05-13

---

## 机器硬件

| 组件 | 规格 |
|------|------|
| CPU | i5-11320H 4C8T |
| RAM | 15.8 GB |
| SSD | KIOXIA NVMe 512G |
| 磁盘 | C: 146.5G (~19G free) D: 329G (301G free) |
| GPU | Intel Iris Xe (2021 驱动 — 待更新) |
| OS | Win11 Insider Preview Build 26200 25H2 |

---

## 配置演化时间线

### 初始设置（2026-05-13）
- 主模型: siliconflow/deepseek-ai/DeepSeek-V4-Flash
- Fallback: deepseek-ai/DeepSeek-V3 → Qwen2.5-72B-128K
- thinkingDefault: off | contextInjection: always | timeoutSeconds: 120
- compaction: auto 模式, keepRecentTokens=24000

### 系统加固（2026-05-16）
- 发现 3 个安全漏洞: auth=none, bind 无限制, chatCompletions 开放
- 修复: bind=loopback, auth=token, chatCompletions=off
- 新增 watchdog.cmd v4（5次重试上限+300s冷却）
- 注册表 HKCU Run 开机自启

### 行为缺陷修复（2026-05-13）
- ✅ 强制报告规则写入 AGENTS.md
- ✅ 后台进程轮询端口确认
- ✅ 每3个工具调用内报告进度

### CCX + Codex 安装（2026-05-18）
- CCX v2.7.4: 路由 DeepSeek/SiliconFlow
- ccswitch-deepseek: Responses→Chat 转换代理
- Codex CLI v0.130.0: npm 全局安装
- 端口: CCX on 3000, ccswitch on 11435

### Hermes 生态
- API: 8642 | NextChat: 3000 | Dashboard: 9119
- 启动脚本: D:\Hermes\_start_fixed.cmd

---

## 日志体系（连续 10 天：05-10 ~ 05-19）

| 日期 | 重要事件 |
|------|---------|
| 05-10 | 首次对话建立 |
| 05-11 | 创作《遗物整理师》→ 丢失教训 → 强制落盘规则建立 |
| 05-13 | 系统诊断、行为修复 |
| 05-14 | 上下文清理、compaction 优化完成 |
| 05-15 | 每日进化首次执行、CONTEXT-BUDGET.md 创建 |
| 05-16 | 系统加固（安全修复、watchdog、注册表）、深度进化 |
| 05-17 | 夜间深度进化、踩坑/改进文件启用、备份体系建立 |
| 05-18 | 清理 17 个 OCR 脚本 + 6 张截图 + 6 份旧日志 + 旧报告 |
| 05-18 | CCX + ccswitch-deepseek + Codex 安装 |
| 05-19 | 深度进化（确认 Ollama 不可用）、备份更新 |

### 2026-05-23 新增创作
- 知乎中短篇写作工作流系统 v1~v4
- 李白小说创作系统 v1.0（完整版）
- 扫榜报告（知乎短篇热梗分析）
- 选题A 策划文档 + 初稿
- 风格样章 3 篇

---

## 踩坑记录（截至 2026-05-19）

### 记忆系统
- **短篇创作未落盘**: 2026-05-11 创作的《遗物整理师》丢失 → 强制：所有创作产物生成后立即写入 knowledge-base/

### 系统配置
- **Watchdog注册项丢失**: 计划任务被禁用/注册表Run项消失 → 每次进化检查 HKCU\Run 中 OpenClawWatchdog，丢失则重建

### Token管理
- **进化主流程不应由本地模型执行**: cron 指定 ollama/qwen2.5:7b 作执行模型，但输出带 ANSI 乱码、推理不完整 → 进化 cron 用 DeepSeek V4 Flash

### 配置维护
- **Ollama与实际状态不同步**: openclaw.json 仍保留 ollama provider（localhost:11434），但 ollama 可执行文件已不存在 → 定期清理失效配置

---

## 改进队列（截至 2026-05-19）

### 待执行
- [ ] **空闲内存**: Ollama不可用，但openclaw.json仍保留ollama provider → 清理配置或重装Ollama
- [ ] **cron模型指定**: nightly-self-evolution仍指定ollama/qwen2.5:7b → 改为deepseek/deepseek-v4-flash

### 已完成
- [x] mistakes-learned.md 空→首条踩坑记录 (05-17)
- [x] skill-improvements.md 空→改进队列 (05-17)
- [x] 注册表Run键重建 (05-17)
- [x] cron模型 ollama/qwen2.5:7b 问题确认 (05-19)
- [x] openclaw.json merge模式检查 (05-19)
- [x] backup过期修复 (05-19)
