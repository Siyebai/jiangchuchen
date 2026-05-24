# 启动脚本速查

---

## OpenClaw

| 脚本 | 位置 | 用途 |
|------|------|------|
| gateway.cmd | D:\openclaw\gateway.cmd | 启动 OpenClaw Gateway |
| watchdog.cmd | D:\openclaw\watchdog.cmd | 守护进程（v4）|

### watchdog 行为（v4）
- 检测 Gateway 进程是否存活
- 如死则重启，最多 5 次重试
- 重试间冷却 300s
- 注册表 Run 键：HKCU\Software\Microsoft\Windows\CurrentVersion\Run\OpenClawWatchdog

## Hermes

| 脚本 | 位置 | 用途 |
|------|------|------|
| Hermes 启动 | D:\Hermes\_start_fixed.cmd | 启动整个 Hermes 生态 |

## CCX + Codex

| 脚本 | 位置 | 用途 |
|------|------|------|
| 全部启动 | C:\Users\李初尘\.ccx\start_all.cmd | 启动 CCX + ccswitch + Codex 支持 |
