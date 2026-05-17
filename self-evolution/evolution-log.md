# 🧬 进化日志

> 每次自我进化事件的编年记录。

---

## [2026-05-17 01:00] 夜间深度自我进化

**触发**：cron nightly-self-evolution（定时 01:00 执行）

**变更**：
1. 注册表 `HKCU\Run\OpenClawWatchdog` 重建
2. `evolution-metrics.json` 计数修复（total: 2→3, daily: 1→2）
3. `mistakes-learned.md` 从空模板 → 3 条踩坑记录
4. `skill-improvements.md` 从空模板 → 4 项队列 + 3 项已完成
5. `backup/` 新增 5 份最新备份（含 openclaw.json）
6. 创建 05-17 每日日志并更新 MEMORY.md 进化报告

**风险发现**：
- Ollama 占用内存大（空闲 2.7 GB）
- SOUL.md 模型行略滞后于实际配置
- cron 模型指定需优化（本地模型推理深度不足）

**模型**：主流程 DeepSeek V4 Flash
- （cron 指定 ollama/qwen2.5:7b 但自动 fallback）

**预期效果**：系统修复链完整，踩坑/改进文件正式投入使用。

---

## [2026-05-16 17:00] 深度自我进化

**触发**：cron nightly-self-evolution（非标准时间 16:59 执行）

**变更**：
1. 清理 14 个 .bak 冗余文件
2. 新建 `backup/` 目录并备份核心配置文件
3. 创建 05-16 每日日志
4. MEMORY.md 添加自我进化报告
5. 改进队列新增 4 项

**风险发现**：
- Ollama 占 6.2 GB（空闲仅 1.8 GB）
- Watchdog 计划任务消失
- Gateway 404

**模型**：主流程 DeepSeek V4 Flash, qwen2.5:7b 辅助分析

**预期效果**：系统健康报告生成，风险项暴露，待后续修复。

---

## [2026-05-15 10:10] 每日进化

**触发**：cron daily-self-evolution

**变更**：回溯 05-14。确认 05-14 上下文清理、compaction 优化完成。改进队列为空。首次 daily_evolution 计数。

**预期效果**：最小化进化周期，维持系统健康。
