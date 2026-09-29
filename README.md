# 中文去 AI 味｜Chinese Writing Humanizer

Review AI-written Chinese and suggest edits to remove formulaic phrasing while preserving the author's voice.

AI 写的中文一眼就能看出来：排比堆砌、过度总结、假大空转折。这个 skill 帮你审中文文章，逐条指出哪里读着机械、为什么影响表达、可以怎么改。公众号、产品介绍、工作文档、故事和随笔都能拿来过一遍；长文会自动分工审阅，目标是让文字更像你本人写的。

## 哪些文字可以拿来过一遍

- **AI 帮忙写过的初稿**：“帮我去 AI 味，保留我的观点和语气。”找出助手腔、套话和不必要的总结，让你真正想说的东西更清楚。
- **产品介绍和 README**：“这段介绍太像宣传稿了，帮我看看哪里该改。”把空泛的赞美换成读者能理解的具体用途，把有个性的说法留下来。
- **工作文档与长文章**：“检查一下这篇文章的 AI 感，先给我修改建议。”通读全文，看看是不是每段都一个节奏、每节都强行收尾，再逐条讨论怎么改。
- **故事、随笔和个人表达**：“帮我看看哪些描写像套模板，别把我的语气改没了。”关注空转的比喻、假具体和人物标签，让原本有意思的句子继续有意思。

每项建议都对应原文，你可以选轻改、标准或重改，决定哪些地方值得动。

## 它检测什么

信号库（[references/ai-taste-signals.md](references/ai-taste-signals.md)）来自跨中英文社区的持续调研，51 条信号分六类：

- **句式与词汇**：「不是A而是B」对照句、三项排比、公文连接词、伪口语风格宣誓、开场寒暄、收尾套话、企业黑话与技术玄学词
- **结构与节奏**：总分总八股、显式顺序串联、段落均匀配重、小标题清单化、强行升华式收束
- **标点与排版**：破折号密度、双引号强调过密、顿号堆砌、Markdown 装饰、全半角漂移、不合理的精确数字
- **修辞与描写**：比喻空转、左分支修饰语堆叠、感官套模板、对话伴随动作、人物标签工具化
- **内容与姿态**：正确的废话、经验缺席与假具体、安全中立抹平立场、案例完美选择零成本、谄媚式肯定
- **生成痕迹**：助手元话语残留、AI 身份自述、提示词流程标记、禁项回声、参考文献空壳、日期版本错配

每条信号都带**可执行的判断门槛**和**误判豁免**——给不出门槛的观察不收进库，避免审阅位凭感觉报问题。词表只作召回入口，命中关键词不等于成立。

## 它怎么给建议

- **双层报告**：达到信号库门槛的进正式建议；未达阈值但命中信号形式的（比如全文仅有的一个破折号）进观察项清单（O 编号，默认不改、可单选）——不再有被静默丢弃的"疑似AI味"
- **质量净收益三档**：第1档＝改了会让文章体验和质量明显变好；第2档＝改前改后各有优点，但改了会降低AI味；第3档＝改掉能降AI味，但原版质量更好。默认只推荐处理第1、2档，第3档留给明确要彻底去AI味的场景
- **改写幅度可选**：轻改（最小替换）/ 标准（默认推荐）/ 重改（允许跨句重组、全文节奏统一）。幅度与处理范围互相独立，选"重改"不会自动扩大要改的条目

## 设计原则

- **宁可漏报，不要误报**——误报会摧毁你对工具的信任
- **不虚构作者经历**——缺细节的地方向你要真实素材，不代写假故事
- **保留作者语气**——目标是像你本人写的，不是像"标准自然中文"
- 长文可以分段扫描，结构与节奏类信号仍按全文判断

## 安装

### Claude Code

```bash
git clone https://github.com/ruodou233/de-ai-taste.git ~/.claude/skills/de-ai-taste
```

### Codex / 其他 Agent

克隆到对应的 skill 目录，或在 prompt 中引用 `SKILL.md` 全文即可。

## 更新

AI 的写作癖好随模型迭代变化（破折号是 ChatGPT 系的癖好，「量子纠缠」式玄学词是 DeepSeek 系的），信号库会随之定期更新。Watch/Star 本仓库获取更新。

## 反馈与作者

这个 skill 我长期维护。如果你有修改方案、发现问题、或者改出了更好的版本，欢迎通过以下任一渠道找到我：

- GitHub：本仓库提 issue 或 PR
- 小红书：错误乱码
- 微信公众号：能工智人错误乱码
- B站：若逗道人

## 相关 Skill 推荐

<!-- 本表由维护脚本生成，勿手工编辑 -->
- [domain-explorer](https://github.com/ruodou233/domain-explorer)：速通新领域：入门、转行、选课题，先把来龙去脉和各路说法弄明白<br>Get up to speed on a new topic through its history, competing approaches, expert debates, and practical experience.
- [improve-product-plan](https://github.com/ruodou233/improve-product-plan)：想做成一个作品？把应用、工具、自动化和游戏想法打磨成能开工的方案<br>Plan product requirements and MVP scope, then produce a development spec with milestones and acceptance criteria.

完整目录见 [GitHub 主页](https://github.com/ruodou233)。

## License

MIT
