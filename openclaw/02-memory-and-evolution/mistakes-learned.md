# 踩坑与教训 🎓

> 创建: 2026-05-17 | 连续更新中

---

### 记忆系统
- **短篇创作未落盘**: 2026-05-11 创作的《遗物整理师》未保存 → **强制**：任何创作产物立即写入 knowledge-base/

### 系统配置
- **Watchdog注册项丢失**: 计划任务被禁用/注册表Run键消失 → 每次进化 cron 检查 HKCU\Run\OpenClawWatchdog

### Token管理
- **进化主流程不应由本地模型执行**: cron 指定 ollama/qwen2.5:7b → ANSI 乱码、推理不完整 → 进化用 DeepSeek V4 Flash

### 配置维护
- **Ollama状态与配置不同步**: openclaw.json 仍保留失效 ollama provider → 定期清理失效配置
