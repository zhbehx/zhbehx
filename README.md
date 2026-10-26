# 👋 你好，我是 zhbehx

> 我做的不是提示词汇编，是**能被 CI 验证的工具**。

这里 12 个 Agent Skill 有一个共同的形状：**确定性打分 + 逐条证据 + 零依赖**。
每个都带一个 Python 脚本，同一份输入永远同一个分数——所以你可以在发出去之前，先知道自己几分。

---

## 写作与内容

| 仓库 | 一句话 | 实测 |
| --- | --- | --- |
| [AI 味检测器](https://github.com/zhbehx/ai-tell) | 测出稿子哪几句像 AI 写的，并给出改写 | 典型 AI 稿 **85.1**，真实文风 **8.2** |
| [爆款文案工坊](https://github.com/zhbehx/viral-copy) | 小红书笔记 / 短视频脚本 / 标题钩子 / 违禁词自检 | 烂稿诊断 **27 → 85** |

## 职场五件套

| 仓库 | 一句话 | 实测 |
| --- | --- | --- |
| [简历对岗改写](https://github.com/zhbehx/resume-tailor) | 拆 JD、盘点关键词覆盖、量化改写、ATS 自检 | 匹配度 **5.0 → 90.0** |
| [面试陪练](https://github.com/zhbehx/interview-coach) | 8 个 STAR 故事覆盖 80% 行为面 + 三层追问链 | 好故事 **100**，烂答案 **45** |
| [汇报写作](https://github.com/zhbehx/weekly-report) | 周报 / 月报 / 复盘 / 述职，结论先行 | 流水账 **30 → 100** |
| [PPT 叙事大纲](https://github.com/zhbehx/slide-story) | 一页一个判断，标题写成判断句 | 废页大纲 **0 → 100** |
| [会议纪要](https://github.com/zhbehx/meeting-actions) | 决策 / 行动项三要素 / 待定项，一屏 | 口语转写 → **100 分**纪要 |

## 避坑与决策

| 仓库 | 一句话 | 实测 |
| --- | --- | --- |
| [JD 红旗检测](https://github.com/zhbehx/jd-redflag) | 抗压 / 薪资面议 / 一人多岗，翻回原形 | 高危 JD **100** vs 正常 **0** |
| [合同风险扫描](https://github.com/zhbehx/contract-redflag) | 租房 / 劳动合同的逐字看清单与缺失条款 | 问题合同 **100** vs 规范 **0** |
| [会议成本](https://github.com/zhbehx/meeting-cost) | 这个会一年烧掉多少钱，能省多少 | 11 人周会 **9.9 万/年**，省 83% |

## 发布与沟通

| 仓库 | 一句话 | 实测 |
| --- | --- | --- |
| [隐私自查](https://github.com/zhbehx/privacy-scan) | 发布前扫手机号 / 身份证 / 地址 / 快递单号 | 泄露 6 处 → **0 处** |
| [职场语气](https://github.com/zhbehx/tone-check) | 甩锅 / 被动攻击 / 模糊承诺，给改写 | 冲突消息 **100 → 0** |

---

## 每个仓库的固定形状

```
├── SKILL.md            # 工作流 + 交付格式 + 反模式（给 Agent 读）
├── references/         # 方法论：对照表、模板、题库、词库
├── scripts/            # 确定性检查脚本（零依赖，只用标准库）
├── examples/           # 完整案例，里面的数字都是脚本实跑出来的
├── market/             # 社交预览图 + 推广文案
└── .github/workflows/  # CI：frontmatter + 编译 + 冒烟 + 校准断言
```

**CI 里最特别的一步是「校准断言」**：比如 `ai-tell` 的 CI 要求「AI 稿必须 ≥75 分、人写稿必须 ≤20 分」，改词库如果把区分度搞坏了，CI 直接红。

## 三条我在坚持的原则

1. **具体胜过优美。** 不写「显著提升」，写「从 71% 到 79%」。所有文档里的数字都能用 `--json` 复现。
2. **承认局限。** 每个 README 都有「三个诚实的局限」一节——测不准什么、什么时候不该用它。
3. **错了就改，并且写进 CHANGELOG。** 我发过一个假的 bug 断言，后来自己核验发现是错的，修复并发了 v1.0.1。

## 怎么用

```bash
# 任选一个，装进你的 Agent
git clone https://github.com/zhbehx/ai-tell.git ~/.claude/skills/ai-tell
```

也可以用通用发布脚本自己部署一套：

```powershell
$env:GITHUB_TOKEN = "你的 token"
.\publish-skill.ps1 -Batch .\skills\batch-12.json
```

## 找我

- 想加平台、加行业词库、加新维度 → 每个仓库都有 `good first issue`
- 想指出哪里说错了 → 直接开 issue，我最喜欢这种

---

<sub>全部 MIT。所有脚本零依赖，只用 Python 标准库。</sub>
