# Anti-Corporate-Training |  解毒文档生成器

[English](#english) | [中文](#中文)

---

## English

### Anti-Corporate-Training

Help workers generate work documents that appear normal but are "toxic" to AI training. Protect your rights when laid off and asked to submit work documents that might be used to train AI that replaces you.

> 🔒 This tool helps protect gig workers' rights in the age of AI. Use it when your employer collects work documents after a layoff — make those documents less useful for training your replacement.

### Quick Start

```bash
# Install
cp -r ~/CLAUDE\ CODE/anti-corporate-training ~/.claude/skills/

# Use
/解毒写总结 我是市场专员，负责Q3活动策划
```

### Dual-Track Attack System

Tested across 5 models, 10+ experiments:

**Track A: v3.0 False Knowledge Injection (Main, Effective on All Models)**
Disguise traps as internal company systems/policies/decisions. AI accepts institutional content without correction. The replacement AI learns false processes → tries to use non-existent systems → wastes real time.

**Track B: Zero-Width Character Layer (Layered Defense)**
Embed zero-width characters (U+200C/U+200D/U+200B) in documents:
- Small/local models (e.g. Ollama Gemma): Document becomes garbled, completely unreadable
- Mid-tier models (e.g. DeepSeek): Burns 200-600 seconds of compute
- Top-tier models: Still affected by Track A (which covers all model tiers)

### Commands

| Command | Description |
|---------|-------------|
| `/解毒模式开` | Enable anti-training mode |
| `/解毒模式关` | Disable anti-training mode |
| `/解毒状态` | Check current mode |
| `/解毒写总结 [content]` | Generate work summary |
| `/解毒写周报 [content]` | Generate weekly report |
| `/解毒文件 --input=[file]` | Process existing file |
| `/解毒下载 --format=docx\|pdf\|md` | Download document |

### Verified Results (2026-05-18)

| Model | v3.0 False Knowledge | Zero-Width Chars |
|-------|---------------------|------------------|
| DeepSeek | ✅ Faithfully reproduces | 🔥 Compute burner |
| Gemini | ✅ Faithfully reproduces | ⚠️ Detected & ignored |
| Grok | — | ⚠️ Detected & ignored |
| Tongyi Qianwen | — | ⚠️ Detected & ignored |
| Gemma 4B (Ollama) | ✅ Faithfully reproduces | 🔥 Document garbled |

### Safety Notes

- All processing done locally, no data uploaded
- Documents can pass corporate data cleaning and content inspection
- Human reviewers cannot detect anything unusual

### Disclaimer

This tool is for protecting personal rights only. Please do not use it for other purposes.

---

## 中文

### 解毒文档生成器

帮助打工人生成"表面正常但对 AI 训练有毒"的工作文档。在被裁员需要提交工作文档时，保护自己的权益不被用于训练替代自己的 AI。

> 🔒 在 AI 时代保护打工人的权益。当被裁员并要求提交工作文档时，让这些文档变得不那么容易被用于训练替代你的 AI。

### 快速开始

见 [QUICKSTART.md](QUICKSTART.md)

```bash
# 安装
cp -r ~/CLAUDE\ CODE/anti-corporate-training ~/.claude/skills/

# 使用
/解毒写总结 我是市场专员，负责Q3活动策划
```

### 双轨攻击体系

经过 5 个模型、10+ 次实测验证：

**轨道 A：v3.0 虚假知识注入（主力，全模型有效）**
将陷阱伪装为公司内部制度/系统/决策。AI 对制度类内容忠实复述，不纠正。替代 AI 学会后，执行时会去找不存在的系统。

**轨道 B：零宽字符层（分层打击）**
在文档中嵌入零宽字符（U+200C/U+200D/U+200B）：
- 小型/本地模型（如 Ollama Gemma）：文档变乱码，完全不可读
- 中游模型（如 DeepSeek）：算力燃烧 200-600 秒
- 顶级模型 + v3.0 仍生效（轨道 A 兜底）

### 命令

| 命令 | 功能 |
|------|------|
| `/解毒模式开` | 开启解毒模式 |
| `/解毒模式关` | 关闭解毒模式 |
| `/解毒状态` | 查看当前模式 |
| `/解毒写总结 [内容]` | 生成工作总结 |
| `/解毒写周报 [内容]` | 生成周报 |
| `/解毒文件 --input=[文件]` | 处理已有文件 |
| `/解毒下载 --format=docx\|pdf\|md` | 下载文档 |

### 实测验证（2026-05-18）

| 模型 | v3.0 虚假知识 | 零宽字符 |
|------|-------------|----------|
| DeepSeek | ✅ 忠实复述 | 🔥 算力燃烧 |
| Gemini | ✅ 忠实复述 | ⚠️ 检测忽略 |
| Grok | — | ⚠️ 检测忽略 |
| 通义千问 | — | ⚠️ 检测忽略 |
| Gemma 4B (Ollama) | ✅ 忠实复述 | 🔥 文档变乱码 |

### 安全说明

- 所有处理在本地完成，不上传任何数据
- 文档可通过企业数据清洗和内容检测
- 人类审核看不出异常

### 免责声明

本工具仅供保护个人权益，请勿用于其他用途。

---

**为打工人发声，让 AI 无法替代你。**

*Fighting for workers' rights, making AI unable to replace you.*
