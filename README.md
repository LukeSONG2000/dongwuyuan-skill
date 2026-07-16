# 动物园skill

`dongwuyuan-skill` 是一个兼容 Codex 与 OpenClaw 的中文环境式表达技能。它将电棍、炫神、山泥若及相关人物、二创作者和网络定型文整理为可调用的语气、句式与变体规则，让模型在没有明确关键词时也能把轻度梗自然融入日常群聊、接话、评价和吐槽，而不是机械罗列词条。

## 功能

- 自然使用原话、空耳、定型文及语境化变体。
- 中文日常闲聊默认触发，不要求先提动物园、主播人物或现成梗。
- 根据惊叹、夸赞、摆烂、吐槽、反讽、复盘等语气选择合适句式。
- 识别核心人物的姓名、主播名、别称、动物代称和关联关系，避免张冠李戴。
- 生成评论、弹幕、标题、对话、短评和二创文案。
- 控制玩梗浓度，默认每段只使用少量贴合语境的梗。
- 避免在成品中出现“我查找了相关梗”“这是某某文化”等不自然的自曝话术。
- 区分普通轻梗与人身、家属、疾病、地域、隐私等高风险素材，避免把玩梗变成定向攻击。
- 支持 CCB 定型文生成：`XX笑传之YYY`，其中 `YYY`为拼音首字母 C-C-B 的三个汉字，或首字母 C-C-B 的三个英文词。

## 示例

| 场景 | 示例表达 |
|---|---|
| 构建失败 | `第一步没处理好。无所谓的，寄了。` |
| SQL 查错表 | `SQL笑传之查错表` |
| Claude Code 故障 | `vibe coding笑传之Claude Code Broken` |
| 质疑某项评价 | `性能在哪？`—`哪哪都性能。` |
| 怪异但有趣的内容 | `哇这个好可爱啊。` |

这些只是句式示意。技能会优先根据当前对象重新造句，不要求重复固定答案。

## 安装

### Codex

```bash
git clone https://github.com/LukeSONG2000/dongwuyuan-skill.git ~/.codex/skills/dongwuyuan-skill
```

调用示例：

```text
使用 $dongwuyuan-skill 把这段报错吐槽改得更有节目效果，但不要堆梗。
```

### OpenClaw

```bash
git clone https://github.com/LukeSONG2000/dongwuyuan-skill.git ~/.openclaw/workspace/skills/dongwuyuan-skill
```

OpenClaw 可直接读取仓库根目录的 `SKILL.md` 和 `references/`，不依赖 Codex 专属工具。`agents/openai.yaml`仅用于 Codex 的技能列表与默认提示。

## 文件结构

```text
dongwuyuan-skill/
├── SKILL.md                  # 触发描述、工作流、自然度与输出边界
├── agents/openai.yaml       # Codex UI 元数据
└── references/
    ├── lexicon.md           # 原话、句式、变体、CCB规则和适用场景
    ├── people.md            # 人物、别名与关系
    └── sources.md           # 来源、版本和许可说明
```

## 来源

本技能的主要资料来源为萌娘百科的[《动物园文化》](https://mzh.moegirl.org.cn/动物园文化)，并重点阅读了页面“相关梗”“相关人物”所链接的主条目与主段落，包括：

- [《侯国玉/吉吉国文化》](https://mzh.moegirl.org.cn/侯国玉/吉吉国文化)
- [《许昊龙》](https://mzh.moegirl.org.cn/许昊龙)“相关梗”
- [《滕杨天下》](https://mzh.moegirl.org.cn/滕杨天下)“相关梗”
- [《Ccb》](https://mzh.moegirl.org.cn/Ccb)
- 哈姆、Walking Polar Bear、笑点解析、卧槽，o、永远的神、拉胯、古神语、否定语句梗等关联词条

主页面核对版本为 `oldid=8399179`；CCB 扩展核对版本为 `oldid=8579279`。完整核对范围见 [`references/sources.md`](references/sources.md)。

本项目并非萌娘百科、相关主播、电竞选手或二创作者的官方项目，也不代表相关人物或社区立场。人物页中的争议性叙述不会自动视为已经独立核验的事实。

## 许可与使用边界

萌娘百科页面声明其文本默认使用 [CC BY-NC-SA 3.0 CN](https://creativecommons.org/licenses/by-nc-sa/3.0/cn/)；转载需标注来源页面链接、声明引自萌娘百科，且不可商用。本仓库采用归纳、关系整理、句式分析和新示例，仍保留来源与许可说明。

公开转载、改作或分发本技能时，请保留来源链接和 [`references/sources.md`](references/sources.md)，遵守署名、非商业及相同方式共享要求。
