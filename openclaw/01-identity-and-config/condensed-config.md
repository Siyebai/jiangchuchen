# 系统配置 — 恢复用精简版

## HEARTBEAT.md（守护系统心跳）

每 30 分钟轮换检查。

### 清单 A：轻量检查（每次必做）
1. **Gateway PID** — 检查 PID 26300 (node) 是否存活
2. **端口** — 18789 是否可达（`netstat -an | findstr :18789`）
3. **API** — `http://127.0.0.1:18789/health` 是否返回 200
4. **今日日志** — `memory/YYYY-MM-DD.md` 存在，不存在则创建

### 清单 B：深度检查（每 2 次心跳）
5. **Watchdog** — 检查 watchdog_state.json 中的 PID 是否存活
6. **计划任务** — OpenClawWatchdog 状态是否为 Ready
7. **Node 进程数** — 应只有 1 个，超过可杀
8. **RAM** — 空闲 >2000MB？若否提醒

### 清单 C：自进化（每 4 次心跳）
9. **队列检查** — `memory/skill-improvements.md` 是否有 urgent 条目
10. **踩坑回顾** — 扫描今日对话有无可记录的踩坑经验

### 响应规则
- **A 全部 OK** → `HEARTBEAT_OK`
- **B 或 C 有问题** → 记录 memory，下次重查
- **连续 2 次同一严重问题** → cron 系统事件通知
- **Gateway PID 不存在** → 紧急事件

---

## CONTEXT-BUDGET.md（上下文预算控制）

| 参数 | 值 | 说明 |
|------|-----|------|
| 模型上下文窗口 | 1,000,000 | DeepSeek V4 Flash 理论最大 |
| 实际安全上限 | 200,000 | 保守估计可用窗口 |
| Compaction 触发 | auto 模式 | 非 safeguard，主动压缩 |
| keepRecentTokens | 24,000 | 压缩后保留近期对话 |
| reserveTokens | 8,192 | 为回复预留空间 |
| recentTurnsPreserve | 5 | 保留最近5轮完整对话 |

### 工作区注入预算（已优化）
- 合计 ~3,400 tokens（已从 ~9,100 精简 -63%）
- 维护守则：单文件不超 500 tokens 常驻注入

### 会话监控规则
- >60% → 减少输出、合并工具调用
- >80% → 触发 compaction
- >90% → 紧急精简，建议新会话

---

## 安全配置历史（重要）

2026-05-16 加固记录：
- 漏洞：auth=none, bind未限制, chatCompletions开放
- 修复：bind=loopback, auth=token, chatCompletions=off
- 新增 watchdog.cmd v4（防重试风暴，5次上限+300s冷却）
- 注册表 HKCU Run 开机自启 watchdog

⚠️ 注意：watchdog 计划任务可能被系统策略禁用
⚠️ 注意：StepClaw 完全独立（端口 30999），无端口冲突

---

## 已知风险（恢复后必须先处理）

### ⚠ 高风险
1. **Ollama 不可用**: 可执行文件已丢失（不在 PATH/Program Files/AppData\Local），但 openclaw.json 仍配置 ollama provider
2. **cron 模型指定过期**: nightly-self-evolution 仍指定 ollama/qwen2.5:7b，导致每次自动 fallback 浪费轮次
3. **GPU 驱动**: Intel Iris Xe 2021 版驱动 — 待更新

### ⚡ 中风险
4. **C 盘紧张**: ~19GB 空闲
5. **Windows Insider**: Build 26200 25H2 不稳定
6. **360 系后台**: 致系统卡顿 — 建议清理
7. **Docker 数据在 C 盘**: 建议迁移到 D 盘

### ✅ 已修复
- ~~计划任务被禁用 → 改用注册表 Run 键~~
- ~~auth=none / bind 无限制 / chatCompletions 开放~~
- ~~旧版 gateway.cmd 指向 dist/index.js~~
- ~~Watchdog 重试风暴~~
- ~~SOUL.md/TOOLS.md/MEMORY.md 膨胀~~
