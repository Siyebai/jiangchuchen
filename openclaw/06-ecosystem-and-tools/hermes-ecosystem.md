# Hermes Agent 生态

> 另一 AI 智能体「夜不悔」所在生态（隔离运行）

---

## 组件

| 组件 | 端口 | 用途 |
|------|------|------|
| Hermes Gateway | 8642 | API 服务 |
| NextChat | 3000 | Web 聊天界面 |
| Dashboard | 9119 | 管理面板 |
| Ollama | 11434 | 本地模型（⚠️ 当前不可用） |

## 启动脚本

```
D:\Hermes\_start_fixed.cmd
```

## 与 OpenClaw 关系

独立运行，互相隔离（遵循实体隔离原则）。不交叉引用配置和进程。
