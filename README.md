# 给阿嬷的情书 — 侨批生成器 (Letters to Ama)

大白话 → 正宗侨批（银信 / 批信）格式转换器。一个受电影《给阿嬷的情书》深度启发的多平台 AI Skill，将日常口语化内容转换为承载百年华侨情感的传统书信。

---

## 功能特性

| 功能 | 说明 |
|------|------|
| 📝 大白话转换 | 将口语化输入自动转换为规范的侨批七段式格式 |
| 🎭 双年代风格 | 支持 `historical`（民国风，1930s–1950s 半文半白）与 `modern`（现代白话） |
| 🏮 四地域韵味 | 潮汕 / 闽南 / 客家 / 通用，自动融入方言韵味与地方意象 |
| 🎬 电影级还原 | 深度参考《给阿嬷的情书》真实道具台词，还原最地道的侨批文字温度 |
| 💬 智能交互 | 未指定参数时自动引导用户选择风格、地域与关系对象 |
| 🔀 多平台支持 | 同时提供 Lingma Agent、Claude Code、OpenAI Codex 三种格式 |

---

## 工作流程

```
┌─────────────────────────────────────────────────────────────┐
│                     用户请求示例                              │
│   "老爸，我在新加坡打工挺好的，寄了五百块回去，               │
│    你们拿去买点好吃的。弟弟妹妹读书怎么样了？"               │
└─────────────────────────────────────────────────────────────┘
│
▼
┌─────────────────────────────────────────────────────────────┐
│                   确认用户偏好（若未指定）                    │
│   • 年代风格：historical / modern                            │
│   • 地域韵味：潮汕 / 闽南 / 客家 / 通用                       │
│   • 关系对象：父母 / 妻子 / 丈夫 / 友人 / 兄弟姐妹            │
└─────────────────────────────────────────────────────────────┘
│
▼
┌─────────────────────────────────────────────────────────────┐
│                   按七段式结构生成侨批                       │
│   称谓 → 开篇问安 → 汇银说明 → 正文 → 嘱托询问 → 祝颂语 → 署名日期 │
└─────────────────────────────────────────────────────────────┘
│
▼
┌─────────────────────────────────────────────────────────────┐
│                      输出最终结果                             │
│   • qiaopi 代码块包裹的完整书信                               │
│   • 风格说明（年代 / 地域 / 关键转换点）                      │
└─────────────────────────────────────────────────────────────┘
```

---

## 安装

### 方式一：Lingma Agent（推荐）

1. 将 `.lingma` 目录复制到你的项目根目录：
   ```bash
   git clone https://github.com/your-username/letters-to-ama.git
   cd letters-to-ama
   cp -r .lingma /path/to/your/project/
   ```

2. 重启 Lingma Agent，通过 `/letters-to-ama` 触发使用。

### 方式二：Claude Code

1. 将本仓库 Clone 到 Claude Code Skill 目录：
   ```bash
   cd ~/.claude-code/skills/
   git clone https://github.com/your-username/letters-to-ama.git
   ```

2. 或在对话中直接要求安装：
   ```
   安装 letters-to-ama skill: https://github.com/your-username/letters-to-ama
   ```

### 方式三：OpenAI Codex

1. 将 `codex/instructions.md` 复制到你的项目 `.codex` 目录：
   ```bash
   mkdir -p /path/to/your/project/.codex
   cp codex/instructions.md /path/to/your/project/.codex/instructions.md
   ```

2. Codex CLI 会自动加载该指令文件。

---

## 使用方式

### 方式一：命令式调用

```
/letters-to-ama 老爸，我在新加坡做工挺好的，这个月发了工资，寄五百块回去，你们拿去买点好吃的
```

Agent 会自动询问年代风格、地域韵味和关系对象，然后生成一封完整的侨批。

### 方式二：对话式调用

```
用户：帮我写一封侨批，答谢朋友海滨的来信

Agent：
1. 【询问】年代风格选 historical 还是 modern？
2. 【询问】地域韵味偏好？潮汕 / 闽南 / 客家 / 通用
3. 【询问】海滨是你的什么人？友人 / 同学 / 同事
4. 【生成】输出完整侨批
```

---

## 目录结构

```
letters-to-ama/
├── README.md                          # 本文档
├── SKILL.md                           # Claude Code Skill 说明
├── .lingma/
│   └── skills/
│       └── letters-to-ama/            # Lingma Agent Skill 原生格式
│           ├── SKILL.md               # Lingma Skill 主文件
│           └── examples.md            # 示例与电影原文参考汇编
└── codex/
    └── instructions.md                # OpenAI Codex 指令格式
```

---

## 文件说明

| 文件 | 适用平台 | 说明 |
|------|---------|------|
| `SKILL.md` | Claude Code | Skill 定义文件，包含触发条件、执行流程与参数说明 |
| `.lingma/skills/letters-to-ama/SKILL.md` | Lingma Agent | Skill 主文件，含完整书写规范、七段式结构、风格指南 |
| `.lingma/skills/letters-to-ama/examples.md` | 全平台参考 | 7 个完整示例 +《给阿嬷的情书》侨批原文参考汇编 |
| `codex/instructions.md` | OpenAI Codex | 指令文件，放入 `.codex/` 目录即可生效 |

---

## 侨批七段式结构

```
1. 称谓      → 收信人尊称
2. 开篇问安  → 思念与问候
3. 汇银说明  → 金额、币种、托送方式（可穿插正文）
4. 正文      → 近况、家事、工作、子女
5. 嘱托询问  → 叮咛、问题、盼回信
6. 祝颂语    → 祝福安康
7. 署名日期  → 发信人、地点、日期
```

---

## 参考来源

- 电影《给阿嬷的情书》道具台词与广州华侨博物馆道具展
- 小红书用户整理的电影信件内容
- 岭南古籍出版社侨批相关文献

---

## License

MIT

---

## 贡献

欢迎提交 Issue 和 Pull Request！
