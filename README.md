# 给阿嬷的情书 — 侨批生成器 (Letters to Ama)

一个 [Lingma Agent](https://lingma.aliyun.com/) Skill，将口语化的大白话转换为正宗的侨批（银信 / 批信）格式。

## 功能

- **输入**：日常口语、大白话内容（如"老爸，我在新加坡打工挺好的，寄了五百块回去"）
- **输出**：符合侨批七段式格式的传统书信，支持多种年代风格与地域韵味

## 特色

- **年代风格**：可选 `historical`（民国风，1930s–1950s 半文半白）或 `modern`（现代白话，保留侨批结构）
- **地域韵味**：潮汕 / 闽南 / 客家 / 通用
- **深度参考电影《给阿嬷的情书》**：大量引用影片真实道具与台词，还原最地道的侨批文字温度
- **智能交互**：未指定风格时会先询问用户偏好

## 安装

1. 将本仓库内容复制到你的项目根目录：
   ```bash
   git clone https://github.com/your-username/letters-to-ama.git
   cd letters-to-ama
   cp -r .lingma /path/to/your/project/
   ```

2. 确保目录结构如下：
   ```
   your-project/
   └── .lingma/
       └── skills/
           └── letters-to-ama/
               ├── SKILL.md
               └── examples.md
   ```

3. 重启 Lingma Agent，即可通过 `/letters-to-ama` 触发使用。

## 使用方法

在对话中直接输入：

```
/letters-to-ama 老爸，我在新加坡做工挺好的，这个月发了工资，寄五百块回去，你们拿去买点好吃的
```

Agent 会自动询问年代风格、地域韵味和关系对象，然后生成一封完整的侨批。

## 文件说明

| 文件 | 说明 |
|------|------|
| `SKILL.md` | Skill 主文件，包含完整的书写规范、七段式结构、风格指南和交互逻辑 |
| `examples.md` | 示例与参考汇编，包含 7 个完整示例和电影《给阿嬷的情书》侨批原文参考 |

## 参考来源

- 电影《给阿嬷的情书》道具台词与广州华侨博物馆道具展
- 小红书用户整理的电影信件内容
- 岭南古籍出版社侨批相关文献

## License

MIT
