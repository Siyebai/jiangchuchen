# CCX + ccswitch-deepseek + Codex 架构

> 安装: 2026-05-18 | 架构: Codex → ccswitch-deepseek(:11435) → CCX(:3000) → DeepSeek/SiliconFlow

---

## 架构图

```
Codex CLI
   ↓ Responses API (streaming/non-streaming)
ccswitch-deepseek (localhost:11435)
   [Responses↔Chat 协议转换]
   ↓
CCX v2.7.4 (localhost:3000)
   [路由 + 负载均衡]
   ↓
┌──────────┬──────────┐
DeepSeek V4   SiliconFlow
```

## 组件位置

| 组件 | 位置 | 端口 |
|------|------|------|
| CCX v2.7.4 | C:\Users\李初尘\.ccx\ccx.exe | 3000 |
| ccswitch-deepseek | C:\Users\李初尘\.ccswitch-deepseek\index.js | 11435 |
| Codex CLI v0.130.0 | npm 全局安装 | — |

## 启动

```bash
# 一键启动所有组件
C:\Users\李初尘\.ccx\start_all.cmd
```

## 验证

- Chat Completions → CCX → DeepSeek/SiliconFlow: ✅
- Responses API → ccswitch → CCX → DeepSeek (非 streaming): ✅
- Responses API → ccswitch → CCX → DeepSeek (streaming/SSE): ✅
- Codex CLI: 已安装可调用 ✅
