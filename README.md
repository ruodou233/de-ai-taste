# de-ai-taste 中文去AI味审阅 Skill

AI 写的中文一眼就能看出来：排比堆砌、过度总结、假大空转折。这个 skill 逐条检测这些 AI 味痕迹并给出具体修改建议，长文自动走并行子代理模式，改完的文字读起来像人写的。

## 它检测什么

信号库（[references/ai-taste-signals.md](references/ai-taste-signals.md)）来自跨 20 个中英文平台的社区研究，覆盖四类信号：

- **句式模式**：「不是A而是B」对比句、三段论、chatbot 开场白和结尾套话
- **表达模式**：机械味、破折号滥用、宏大隐喻、均匀段落、正确的废话
- **词汇标记**：技术玄学词、企业黑话、四字成语堆砌
- **AI身份泄露**：「作为一个大型语言模型」、谄媚式肯定

## 设计原则

- **宁可漏报，不要误报**——误报会摧毁你对工具的信任
- **不虚构作者经历**——缺细节的地方向你要真实素材，不代写假故事
- **保留作者语气**——目标是像你本人写的，不是像"标准自然中文"
- 长文自动切换并行子代理模式：便宜模型分段扫描 + 强模型通读全文 + 最强写作模型终审汇总

## 安装

### Claude Code

```bash
git clone https://github.com/ruodou233/de-ai-taste.git ~/.claude/skills/de-ai-taste
```

### Codex / 其他 Agent

克隆到对应的 skill 目录，或在 prompt 中引用 `SKILL.md` 全文即可。

## 使用

对你的 Agent 说「帮我去AI味」「检查一下这篇文章的AI感」，并给出文章即可。

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
- [domain-explorer](https://github.com/ruodou233/domain-explorer)：速通新领域的核心技巧：四线并行采集，几分钟建立全景认知
- [improve-product-plan](https://github.com/ruodou233/improve-product-plan)：AI 产品经理帮你把模糊想法打磨成可落地的实现方案
- [wisdom-roundtable](https://github.com/ruodou233/wisdom-roundtable)：拉一桌 AI 专家并行辩论，重大决策不再只听一面之词

完整目录见 [GitHub 主页](https://github.com/ruodou233)。

## License

MIT
