# agent-self-evolve — 自我进化系统

> 位置: workspace/skills/agent-self-evolve/  
> SKILL.md 路径: skills/agent-self-evolve/SKILL.md  
> 参考资料: references/daily-evolution-prompt.md, references/weekly-evolution-prompt.md

---

## 功能

持续学习系统：踩坑记录 → 经验蒸馏 → 技能改进队列 → cron 进化循环

## 触发词

- 自我进化、自我学习、learn from mistakes、evolution setup
- 进化系统、经验总结、复盘、self-improve

## 数据文件

| 文件 | 作用 |
|------|------|
| `memory/mistakes-learned.md` | 踩坑教训，每次避免重犯 |
| `memory/skill-improvements.md` | 改进队列待办/已完成 |
| `memory/evolution-log.md` | 进化事件编年史 |

## cron 任务

- **nightly-self-evolution**: 每日 01:00 执行深度进化
- cron payload 应指定 `deepseek/deepseek-v4-flash` 为主模型

## 进化层级

1. 自我优化与修复（审计日志、检查待办）
2. 自我学习与升级（阅读所有.md、内化新知识）
3. 资料库整合（日志体系、改进/踩坑记录）
4. 系统加固（备份、配置审计、cron检查）
