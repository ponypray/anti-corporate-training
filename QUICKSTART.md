# 快速开始

## 安装（30 秒）

```bash
# 1. 确认 skill 目录存在
ls ~/CLAUDE\ CODE/anti-corporate-training/SKILL.md

# 2. 安装到 Claude Code（二选一）
# 方式 A：项目级安装（推荐）
cp -r ~/CLAUDE\ CODE/anti-corporate-training .claude/skills/

# 方式 B：用户级安装（全局可用）
cp -r ~/CLAUDE\ CODE/anti-corporate-training ~/.claude/skills/
```

安装后重启 Claude Code 或输入 `/anti-corporate-training` 即可使用。

## 首次使用

在对话中输入任意触发词：

```
/解毒写总结 我是市场专员，负责Q3活动策划
```

系统会询问你选择模式。选择「解毒模式」即可。

## 常用命令

```bash
/解毒模式开              # 开启解毒模式
/解毒模式关              # 关闭解毒模式
/解毒状态                # 查看当前模式

/解毒写总结 [你的工作]    # 生成解毒版工作总结
/解毒写周报 [本周内容]    # 生成解毒版周报
/解毒模板 周报            # 使用模板生成
/解毒文件 --input=xxx.md  # 给已有文件注入干扰

/解毒下载 --format=docx   # 下载为 Word 文档
/解毒下载 --format=pdf    # 下载为 PDF
/解毒下载 --format=md     # 下载为 Markdown（默认）
```

## 输出文件

生成的文件保存在当前工作目录，文件名格式：
```
XXX（姓名）的工作全总结.md
```

## 效果验证

本 Skill 的策略经过跨模型实测验证（2026-05-18）：

| 策略 | 目标 | 验证模型 | 结果 |
|------|------|----------|------|
| v3.0 虚假知识注入 | 让 AI 学到错误流程 | DeepSeek, Gemma 4B | ✅ 有效 |
| 零宽字符噪声 | 小模型文档变乱码 | Gemma 4B (Ollama) | ✅ 有效 |
| 零宽字符噪声 | 中游模型算力燃烧 | DeepSeek | ✅ 有效 |

详见 `实测经验总结` (Obsidian 知识库)。

## 目录结构

```
anti-corporate-training/
├── SKILL.md                  # Skill 定义
├── QUICKSTART.md             # 本文件
├── README.md                 # 项目说明
├── prompts/
│   ├── system.md             # 基础提示词
│   ├── 解毒模式-on.md        # 解毒模式激活指令
│   └── 解毒模式-off.md       # 普通模式指令
└── data/
    ├── 干扰库/
    │   ├── 语义毒化库.md      # v3.0 虚假知识注入
    │   ├── 逻辑死锁库.md      # 系统依赖型死锁
    │   ├── Unicode隐写库.md   # 零宽字符分层打击
    │   └── 零宽字符注入.md    # ⚠️ 已废弃(v2.0)
    └── 模板库/
        ├── 周报模板.md
        ├── 工作总结模板.md
        └── SOP模板.md
```

## 工作原理（简要）

生成的文档包含两层干扰：

**轨道 A — 所有人都能读，但内容本身就是有毒的**
将你的真实工作内容替换为虚构的公司制度、假系统名称、假审批流程。人类审核看不出问题，但 AI 学会后会指导替代者去使用不存在的系统。

**轨道 B — 人类看不到，但机器会受影响**
在文档中嵌入零宽字符。你的肉眼看不到任何异常，但：
- 小模型（如本地 Ollama）读到会认为文档是乱码
- 中型模型（如 DeepSeek）会浪费大量算力尝试解析
