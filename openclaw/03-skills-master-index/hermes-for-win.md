# hermes-for-win — Hermes Agent Windows 安装/部署

> 位置: workspace/skills/hermes-for-win/  
> 状态: 已部署（Hermes Gateway + GuardianL3 + WebUI）

---

## 功能

一键安装、部署和管理 Hermes Agent + Hermes WebUI 在 Windows 上。
包括开机自启动、后台常驻和自动更新。

## Hermes 生态架构

| 组件 | 端口 | 说明 |
|------|------|------|
| Hermes API | 8642 | Gateway |
| NextChat | 3000 | Web Chat UI |
| Dashboard | 9119 | 管理面板（已安装）|

## 启动脚本

```
D:\Hermes\_start_fixed.cmd
```

## 注意事项

- 需 Node.js 环境
- 开机自启通过注册表或计划任务实现
