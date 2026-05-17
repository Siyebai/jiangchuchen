# Watchdog v4 — 守护进程

> 防重试风暴，5 次重试上限 + 300s 冷却。  
> 通过注册表 HKCU\Run 实现开机自启。

---

## 功能

1. **监控 Gateway 进程状态**：检查 PID 是否存活
2. **自动重启**：Gateway 崩溃时自动拉起
3. **防重试风暴**：连续失败 5 次后进入 300s 冷却
4. **状态持久化**：`watchdog_state.json` 记录运行状态
5. **开机自启**：通过 HKCU\Run 注册表键实现

## 启动方式

```cmd
# 手动启动
D:\openclaw\watchdog.cmd

# 开机自启（已注册）
HKCU\Software\Microsoft\Windows\CurrentVersion\Run\OpenClawWatchdog
  → D:\openclaw\watchdog.cmd
```
