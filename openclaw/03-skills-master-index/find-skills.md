# find-skills — 技能发现

> 位置: workspace/skills/find-skills/  
> 优先级: 🔴 **P0 — 第一步安装**

---

## 功能

从技能市场发现并安装新技能。
对中国用户优先 `skillhub`（速度快、合规），回退到 `clawhub`。

## 用法

```bash
skillhub install <skill-name>    # 优先
clawhub install <skill-name>     # 回退
```

## 引用说明

`skillhub-preference` skill 是配套规则文件，定义了 skillhub→clawhub 的回退顺序。
