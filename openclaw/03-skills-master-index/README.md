# 技能仓库索引

> 安装目录: C:\Users\李初尘\.openclaw\workspace\skills\  
> 核心技能: ~18 个 | 来源: d:\openclaw\node_modules\openclaw\skills\ 和 skillhub/clawhub

---

## 快速恢复

```bash
# 恢复后刷新技能列表
openclaw skills list

# 重新安装关键技能（按需）
clawhub install <skill-name>     # 从 clawhub 安装
skillhub install <skill-name>    # 从 skillhub 安装
```

---

## 技能分类

### ⭐ 核心用户技能（workspace/skills/）

| 技能 | 功能 | 优先级 |
|------|------|--------|
| `agent-self-evolve` | 自我进化系统 — 踩坑记录→学习→改进循环 | **P0** |
| `find-skills` | 技能发现 — 从 skillhub/clawhub 安装新技能 | **P0** |
| `skill-creator` | 创建/编辑/优化 SKILL.md | **P0** |
| `skillhub-preference` | 优先 skillhub，回退 clawhub | **P0** |
| `cross-channel-cross-agent-sharing` | 跨渠道/跨智能体传播新能力 | **P1** |
| `xiaohongshu-all-in-one` | 小红书全链路运营 | **P2** |
| `hermes-for-win` | Hermes Agent Windows 安装/部署 | **P2** |
| `listenhub` | 播客/语音/视频制作 | **P3** |
| `reach` | 网页浏览/表单填写/登录/验证码 | **P3** |
| `remotion` | React 视频制作 | **P3** |
| `sage-memory` | 持久化共识记忆 | **P3** |
| `shike-self-evolve` | 自进化触发词系统 | **P3** |

### ⚙️ 核心内置技能（d:\openclaw\node_modules\openclaw\skills/）

| 技能 | 功能 |
|------|------|
| `browser-automation` | 浏览器自动化 — 多步流程、登录检查、标签管理 |
| `healthcheck` | 主机安全审计 SSH/防火墙/更新/暴露检测 |
| `node-connect` | 节点配对诊断 |
| `openai-whisper-api` | 音频转录（Whisper API）|
| `taskflow` | 多步后台任务编排 |
| `taskflow-inbox-triage` | 收件箱分类/意图路由/回复等待 |
| `weather` | 天气查询 |

---

## 各技能详细说明（按文件名索引）

每个技能对应一个 `.md` 文件，包含：
- 安装来源和方法
- 核心函数/功能列表
- 调用触发词
- 配置要求
