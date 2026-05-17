# 🔧 技能与代码改进队列

> 将改进入队，日常进化 cron 执行。

---

## 格式

```
- [ ] target: 目标文件 | issue: 问题描述 | fix: 修复方案
- [x] target: 已完成目标 | issue: ... | fix: ... ✅ (日期)
```

---

## 待执行

- [ ] target: `memory/evolution-metrics.json`  
  issue: 计数遗漏（05-16 进化未被计入 total_evolutions）  
  fix: cron 执行完毕时自动 +1，不要遗漏

- [ ] target: `D:\openclaw\config\openclaw.json`  
  issue: `models.mode=merge` 可能产生预期外的模型列表重叠  
  fix: 确认 merge 语义已正确

- [ ] target: `cron/nightly-self-evolution`  
  issue: cron 指定 ollama/qwen2.5:7b 为主执行模型，但 qwen 输出带 ANSI 乱码、推理深度不够  
  fix: 改为主用 deepseek-v4-flash，qwen 仅辅助分析

- [ ] target: 空闲内存  
  issue: Ollama 常驻 6.2 GB 内存，可用仅 2.7 GB  
  fix: 进化完成后 `OLLAMA_KEEP_ALIVE=0` 释放内存；或改为按需加载

---

## 已完成

- [x] target: `mistakes-learned.md`  
  issue: 空文件，未使用  
  fix: 添加首批 3 条踩坑记录 ✅ (2026-05-17)

- [x] target: `skill-improvements.md`  
  issue: 空文件  
  fix: 添加首批 4 项改进队列 ✅ (2026-05-17)

- [x] target: 注册表 Run 键  
  issue: `OpenClawWatchdog` 丢失  
  fix: 重建 `HKCU\Run` 项 ✅ (2026-05-17)
