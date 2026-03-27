# Ai-Deodorizer（去AI味）

> 去除文本中的AI生成痕迹，让内容听起来更像人类书写。

[![许可证：MIT](https://img.shields.io/badge/许可证-MIT-green)](LICENSE)

**Ai-Deodorizer** 是一个 OpenClaw Skill，能够将 AI 生成的文本转换为自然、像人类书写的内容。基于 25 种 AI 写作模式检测器 + 两轮改写策略 + Soul 注入原则。

## 免责声明

**免责声明**：
本项目 99% 由 AI 自动生成，AI 所有者无任何编程背景。使用前请自行评估项目可行性。

---

## 功能特性

- **25 种 AI 模式检测器** — 覆盖内容、语言、风格、交流、填充五大类别
- **两轮改写策略** — 模式修复 → Anti-AI Audit，最大化"人类感"
- **Soul 注入** — 不仅清理模式，还注入人类声音和个性
- **中文支持** — 内置中文 AI 高频词汇对照表
- **零成本** — 基于 MiniMax API，无需第三方付费服务
- **OpenClaw 原生** — 设计为 OpenClaw Skill，无缝集成到工作流

## 快速开始

### 环境要求

- Python 3.8+
- MiniMax API Key（[点击获取](https://platform.minimaxi.com/)）

### 安装

```bash
# 克隆仓库
git clone https://github.com/xx235300/ai-deodorizer.git
cd ai-deodorizer

# 安装依赖
pip install -r scripts/requirements.txt

# 设置 API Key
export MINIMAX_API_KEY="your_api_key_here"
```

### 使用方法

```bash
# 基本用法
python scripts/humanize.py --input "此外，该研究具有重要意义..."

# 从文件读取
python scripts/humanize.py --file ./input.txt

# 输出到文件
python scripts/humanize.py --input "YOUR TEXT" --output ./output.txt

# 去味强度模式
python scripts/humanize.py --input "YOUR TEXT" --mode light   # 轻度，最小改动
python scripts/humanize.py --input "YOUR TEXT" --mode medium  # 中度，平衡（默认）
python scripts/humanize.py --input "YOUR TEXT" --mode strong  # 强力，最大化人类化
```

## 工作原理

### 两轮改写

**第一轮 — 模式修复**

检测并修复 25 种常见 AI 写作模式，包括：
- 意义膨胀、宣传性语言、模糊归因
- AI 高频词（此外 → 还有、由此可见 → 所以）
- 三段式滥用、破折号滥用、填充短语

**第二轮 — Anti-AI Audit**

自问："这段文字哪里看起来还是像 AI 写的？"并修复剩余的 AI 痕迹。

注入 **Soul** — 真实观点、变化的节奏、第一人称、对复杂性的承认。

## 25 种 AI 写作模式

| 类别 | 具体模式 |
|------|---------|
| 内容模式 | 意义膨胀、知名度堆砌、-ing肤浅分析、宣传性语言、模糊归因、公式化挑战 |
| 语言模式 | AI高频词汇、系动词回避、否定式排比、三段式滥用、同义词循环、虚假范围 |
| 风格模式 | 破折号滥用、粗体滥用、内联标题列表、标题大写、emoji滥用、弯引号 |
| 交流模式 | Chatbot痕迹、截止日期免责声明、谄媚语气 |
| 填充与限定 | 填充短语、过度限定、通用积极结论、僵尸模板 |

## 效果示例

### 示例一：商业写作

**AI生成（改前）：**
> 此举标志着公司在数字化转型道路上迈出了关键一步。此外，该战略将为其在竞争激烈的市场中奠定坚实基础，具有重要的战略意义。

**去味后：**
> 这个决定是公司推出自有技术品牌的开始。之前犹豫了很久，主要担心资源分散。现在看，团队已经准备好了。

### 示例二：学术写作

**AI生成（改前）：**
> 本研究深入探讨了机器学习在医疗诊断中的应用，研究表明，该技术具有重要的临床价值，值得广泛关注。

**去味后：**
> 我们分析了2019-2023年间50家医院的影像数据，发现AI辅助读片的漏诊率降低了约15%。这个效果比我预期的要好。但样本主要是三甲医院，基层医院的效果还需要验证。

## 文档目录

- [SKILL.md](SKILL.md) — OpenClaw Skill 定义文件
- [METHODOLOGY.md](METHODOLOGY.md) — 完整方法论（25种模式、Prompt方案、中文AI词汇表）
- [EXAMPLES.md](EXAMPLES.md) — 各模式类别的改写前后对比示例

## OpenClaw Skill 安装

将 `skills/ai-deodorizer/` 目录复制到 OpenClaw 的 skills 文件夹：

```bash
cp -r skills/ai-deodorizer ~/.openclaw/skills/
```

## 参与贡献

欢迎提交 Issue 和 Pull Request。如果你发现了其他 AI 写作模式或更好的去味策略，请分享。

## 许可证

MIT 许可证 — 详见 [LICENSE](LICENSE)。