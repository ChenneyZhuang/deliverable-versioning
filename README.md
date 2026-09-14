# deliverable-versioning 交付版本纪律

Every team eventually has a folder full of `report_FINAL.xlsx`, `report_FINAL_v2.xlsx`, and `report_FINAL_really.xlsx` — and nobody trusts any of them. This skill is the cure.

每个团队最终都会有一个装满 `report_FINAL.xlsx`、`report_FINAL_v2.xlsx`、`report_FINAL_really.xlsx` 的文件夹——然后没人相信其中任何一个。这个 skill 就是解药。

## Why / 为什么

The chaos has one root cause: **overwriting and ambiguous naming**. A file that was already sent is edited in place; the word "final" is used as a name; and six months later nobody can say which file a decision was based on. The fix is mechanical, not motivational.

混乱只有一个根源：**覆盖 + 命名含糊**。已发出的文件被原地修改；"final" 被拿来当文件名用；六个月后没人说得清哪个决策是基于哪个文件。解法是机械的，不靠自觉。

## The rules / 规则

1. **已发出 = 不可变。** A file that left your hands never gets edited — new content becomes a new file, and the old one stays exactly as sent.
2. **用日期和内容命名，永远不用 final。** The word final always gets violated; a date never does. `proposal_2026-09-14.xlsx` beats `proposal_final_v3.xlsx` forever.
3. **一个权威交付目录。** One directory per project is the source of truth for "what did we actually send"; drafts live elsewhere. 交付目录 = 权威。
4. **台账把一切串起来。** date → filename → count → recipient. "我们发过什么" 是一次查询，不是一场考古。
5. **新版本先查有没有。** Before rebuilding a deliverable, check whether it already exists in the delivery directory — rebuilding creates the second source of truth that rots the first.
6. **替代要留痕。** A superseded file stays in place but gets marked in the ledger; references in docs get updated to point at the current one.

## The test / 一分钟自测

Can you answer, from the delivery directory and ledger alone, without opening chat history: what did we send, to whom, when, and how many rows? If any answer requires scrolling chat — the discipline is missing.

只看交付目录和台账，不翻聊天记录，能不能答出：发过什么、发给谁、什么时候、多少行？任何一问需要翻聊天——纪律就还缺着。

## Install / 安装

```bash
git clone https://github.com/ChenneyZhuang/deliverable-versioning ~/.claude/skills/deliverable-versioning
```

One SKILL.md, zero dependencies. MIT. v0.1.0.

单个 SKILL.md，零依赖。MIT 许可，v0.1.0。
