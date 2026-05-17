# 🛡️ 安全加固记录

> 2026-05-16 Gateway 安全漏洞修复全记录。

---

## 发现的问题

### 🔴 根本原因 #1：计划任务已禁用
Watchdog 无法通过计划任务开机自启。

### 🔴 根本原因 #2：旧版入口
旧 `gateway.cmd` 指向 `dist/index.js`（旧版），新版入口为 `openclaw.mjs gateway run`。

### 🔴 安全漏洞（三连）
| 漏洞 | 危害 |
|------|------|
| `auth=none` | 无认证，任何人可调用 API |
| `bind` 未限制 | 绑定所有网络接口，暴露公网 |
| `chatCompletions=on` | 外部可访问聊天补全端点 |

---

## 修复操作

### 配置修复
```json
{
  "bind": "loopback",
  "auth": "token",
  "chatCompletions": "off"
}
```

### gateway.cmd 新增启动参数
```cmd
openclaw.mjs gateway run --bind loopback --auth token
```

### Watchdog v4
- 防重试风暴：5 次重试上限 + 300s 冷却
- 注册表 HKCU\Run 开机自启

### 其他
- 清理旧日志文件
- 确认 StepClaw（端口 30999）完全独立，无端口冲突

---

## 当前安全状态

| 措施 | 状态 |
|------|------|
| bind=loopback | ✅ 仅本地访问 |
| auth=token | ✅ 需 Bearer Token |
| chatCompletions=off | ✅ 外部无法调用 |
| Watchdog HKCU.Run | ✅ 开机自启 |
| Watchdog 计划任务 | ⚠️ 已被系统策略禁用 |
