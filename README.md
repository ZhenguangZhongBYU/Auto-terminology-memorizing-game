# 汽车车身术语记忆游戏
Auto Body Terminology Memorization Game

> 看中文、打英文 —— 基于艾宾浩斯遗忘曲线的汽车车身术语记忆游戏（绿色便携版）
> Type English from Chinese — Ebbinghaus-based Auto Body Terminology Memorization Game (Portable Green Version)
>
> 感谢好朋友杨云曦，Yunxi（Grace) Yang 的技术支持和提供创意。
> Thanks to my friend Yunxi (Grace) Yang for technical support and original ideas.

词库来自 **GB/T 4780《汽车车身术语》（征求意见稿）**，共 **332 条**中英对照术语，
The vocabulary is from GB/T 4780 *Automobile Body Terminology* (Draft for Comment), containing 332 Chinese-English terminology entries,
覆盖车身类别、车身区域、功能界面、功能系统、车身造型、车身色彩、虚拟设计、
covering body classification, body zones, functional interfaces, functional systems, body styling, body color, virtual design,
车身连接、结构术语、车身结构件等 10 大类。
body joints, structural terms, body structural components and other 10 categories.

---

## 特性
## Features

- **固定数量横线**：每个格子 = 1 个字母，一看就知道英文单词的长度，逐字母填入
- **Fixed blank slots**: Each slot = one letter. You can directly see the length of the English word and type letter by letter.
- **艾宾浩斯间隔复习**：错题反复出现、间隔越来越长，直到连续答对 3 次才进入巩固期
- **Ebbinghaus spaced repetition**: Wrong items reappear with growing intervals, entering consolidation phase only after 3 consecutive correct answers.
- **错题背诵学习**（v1.1.0）：答错/跳过时正确答案自动填入横线，停留 18 秒供背诵，带倒计时
- **Review mode for wrong answers (v1.1.0)**: When you answer wrong or skip, the correct answer fills the blanks automatically for 18 seconds of recitation with countdown.
- **可调背诵时长**（v1.2.0）：6 / 10 / 18 / 30 / 60 秒，设置自动保存
- **Adjustable recitation duration (v1.2.0)**: 6 / 10 / 18 / 30 / 60 seconds, settings auto-saved.
- **绿色便携**：免安装、免注册、不写注册表，拷走整个文件夹即用
- **Portable green software**: No installation, no registration, no registry writing. Just copy the whole folder and run.
- **进度持久化**：学习进度自动保存，关闭后随时继续
- **Persistent progress**: Learning progress saves automatically, resume anytime after closing.

---

## 文件结构
## File Structure

```
汽车车身术语记忆游戏/
Auto Body Terminology Memorization Game/
├── 汽车车身术语记忆游戏.exe   游戏主程序（双击运行，v1.2.0）
├── Auto Body Terminology Memorization Game.exe  Main program (double-click to run, v1.2.0)
├── 词汇表.json               词库（UTF-8，可自行增删词条）
├── vocabulary.json           Term bank (UTF-8, you may add or delete entries)
├── 使用说明.txt              用户手册
├── readme.txt                User manual
├── README.md                 本文件
├── README.md                 This document
└── 学习进度.json             进度文件（运行后自动生成）
└── progress.json             Progress file (auto-generated after launch)

游戏源码/
Source Code/
├── CarBodyGame.cs            C# 主程序源码（含算法引擎与界面）
├── CarBodyGame.cs            C# source code (algorithm engine & UI included)
├── 汽车车身术语记忆游戏.exe    开发版可执行文件
├── Auto Body Terminology Memorization Game.exe    Dev build executable
├── 词汇表.json / icon.ico     词库与图标
├── vocabulary.json / icon.ico Term bank and icon
└── build_data.py              词库生成脚本
└── build_data.py              Vocabulary generation script
```

---

## 快速开始
## Quick Start

1. 双击 `汽车车身术语记忆游戏.exe`；
1. Double-click `Auto Body Terminology Memorization Game.exe`;
2. 屏幕显示中文术语（如「踏平面」），下方横线数量即英文单词字母数；
2. Chinese term appears on screen (e.g. "踏平面"), the number of blanks equals the letter count of the English term;
3. 直接打字填入横线，`Backspace` 退格，`Enter` 提交；
3. Type directly into blanks, `Backspace` to delete, `Enter` to submit;
4. 答对变绿进入下一题；答错变红，正确答案填入横线停留 18 秒供背诵；
4. Turns green for correct answer and proceeds; turns red for wrong answer, correct answer fills blanks for 18 seconds of recitation;
5. 答错的词会按艾宾浩斯间隔在后续反复出现，直到连续答对 3 次。
5. Wrong terms reappear following Ebbinghaus intervals until 3 consecutive correct answers.

### 快捷键
### Hotkeys

| 按键 Key | 功能 Function |
| --- | --- |
| `Enter` | 提交答案 / 背诵学习中提前继续 Submit answer / skip recitation countdown early |
| `Backspace` | 删除最后一个字母 Delete last letter |
| `Esc` | 跳过本题（计为答错，进入背诵学习）Skip this term (marked wrong, enter recitation mode) |
| `Ctrl+H` | 提示（显示下一个字母）Hint (reveal next letter) |

---

## 艾宾浩斯遗忘曲线算法
## Ebbinghaus Spacing Algorithm

艾宾浩斯遗忘曲线表明：新记忆遗忘先快后慢，在「快要遗忘」的时刻复习，
The Ebbinghaus forgetting curve shows new memories fade fast at first then slowly. Reviewing right before forgetting
能把记忆强度拉回高位，且每次复习后的遗忘曲线更平缓。本游戏据此安排间隔：
restores memory strength, and the forgetting curve becomes gentler after each review. Intervals are set as follows:

| 阶段 Stage | 间隔 Interval | 阶段 Stage | 间隔 Interval |
| --- | --- | --- | --- |
| 1 | 2 分钟 2 min | 6 | 2 天 2 d |
| 2 | 10 分钟 10 min | 7 | 4 天 4 d |
| 3 | 30 分钟 30 min | 8 | 7 天 7 d |
| 4 | 12 小时 12 h | 9 | 15 天 15 d |
| 5 | 1 天 1 d | 10 | 30 天 30 d |

**规则：**
**Rules:**

1. 答对一次 → 阶段 +1，下次间隔按上表拉长；
1. One correct answer → Stage +1, next interval extends per the table;
2. 答错一次 → 连对清零、回到第 1 档，**2 分钟后再次出现**；
2. One wrong answer → reset consecutive streak, back to Stage 1, reappear in **2 minutes**;
3. 连续答对 **3 次** → 标记「已掌握」，进入巩固期（第 1 / 3 / 7 天各抽查一次）；
3. **3 consecutive correct answers** → Marked mastered, enter consolidation phase (quizzes on Day 1 / 3 / 7);
4. 巩固期全部通过 → 长期掌握（毕业）；巩固期答错 → 回炉重新学习；
4. Pass all consolidation quizzes → Long-term mastery (graduated); wrong in consolidation → re-learn from scratch;
5. 进度自动保存至 `学习进度.json`。
5. Progress auto-saved to `progress.json`.

---

## 数据文件
## Data Files

### 词汇表.json
### vocabulary.json

```json
{
  "source": "GB/T 4780《汽车车身术语》(征求意见稿)",
  "source": "GB/T 4780 Automobile Body Terminology (Draft for Comment)",
  "version": "1.0",
  "words": [
    { "zh": "踏平面", "en": "pedal plane", "alt": "", "cat": "车身区域" }
  ]
}
```

- `zh` 中文术语、`en` 英文答案、`alt` 同义写法（可为空）、`cat` 分类（可为空）；
- `zh`: Chinese term, `en`: English answer, `alt`: alternative spelling (optional), `cat`: category (optional);
- 保持 UTF-8 编码，注意 JSON 逗号与最外层大括号结构。
- Keep UTF-8 encoding, watch JSON commas and outer brace structure.

### 学习进度.json
### progress.json

运行后自动生成，记录每个词条的学习状态（未学 / 学习中 / 巩固中 / 已毕业）、
Auto-generated after launch, records status of each term (unlearned / learning / consolidating / graduated),
连续答对次数、当前阶段、到期时间、答错/答对/提示次数，以及 `settings.learn_seconds` 背诵时长设置。
consecutive correct count, current stage, due time, wrong/correct/hint count and `settings.learn_seconds` recitation duration.
删除该文件即可重新开始。
Delete this file to reset all progress.

---

## 从源码构建
## Build from Source

依赖 Windows 自带 **.NET Framework 4.x** 与 `csc` 编译器，无第三方依赖：
Depends on Windows built-in **.NET Framework 4.x** and `csc` compiler, no third-party libraries:

```powershell
$csc = "C:\Windows\Microsoft.NET\Framework64\v4.0.30319\csc.exe"
& $csc /nologo /target:winexe /optimize+ /codepage:65001 `
  "/win32icon:icon.ico" "/out:汽车车身术语记忆游戏.exe" `
  /r:"C:\Windows\Microsoft.NET\Framework64\v4.0.30319\System.Windows.Forms.dll" `
  /r:"C:\Windows\Microsoft.NET\Framework64\v4.0.30319\System.Drawing.dll" `
  CarBodyGame.cs
```

### 命令行自检
### CLI Self-test

| 参数 Argument | 功能 Function |
| --- | --- |
| `--selftest` | 算法自检（10 项：间隔递增、3 连对、巩固毕业、回炉、词库完整性、JSON 往返等），写《自检报告.txt》 |
| `--selftest` | Algorithm self-test (10 cases: interval escalation, 3-streak, consolidation graduation, reset, vocabulary integrity, JSON serialization etc.), output SelfTestReport.txt |
| `--uitest` | 无头界面自检（驱动真实 UI 路径：答错→背诵学习→填入横线→倒计时→提前继续），写《界面自检报告.txt》 |
| `--uitest` | Headless UI test (simulate real UI flow: wrong → recitation → fill blanks → countdown → skip early), output UITestReport.txt |
| `--smoke` | 打开界面 2 秒后自动关闭（冒烟测试） |
| `--smoke` | Launch UI and auto-close after 2 seconds (smoke test) |

退出码 `0` = 全部通过。
Exit code `0` = All tests passed.

---

## 版本历史
## Version History

- **v1.0.0** — 初版：完整游戏、艾宾浩斯间隔复习、绿色便携 exe
- **v1.0.0** — Initial release: full game logic, Ebbinghaus spaced repetition, portable exe
- **v1.1.0** — 错题背诵学习：答错/跳过时正确答案填入横线停留数秒（可设 3/10/15 秒）
- **v1.1.0** — Wrong answer recitation mode: fill answer for several seconds after wrong/skip (3/10/15s options)
- **v1.2.0** — 背诵时长默认改为 **18 秒**，选项改为 6 / 10 / 18 / 30 / 60 秒
- **v1.2.0** — Default recitation time set to **18s**, options updated to 6 / 10 / 18 / 30 / 60 seconds

---

## 环境要求
## Requirements

- Windows 10 / 11（Windows 自带 .NET Framework 4.x，无需额外安装）
- Windows 10 / 11 (Built-in .NET Framework 4.x, no extra installation needed)
- 绿色便携版：整个文件夹拷贝即用
- Portable version: Copy the whole folder and run directly

## 备注
## Notes

- 词库来源：GB/T 4780《汽车车身术语》(征求意见稿)，仅供学习使用；
- Vocabulary source: GB/T 4780 Automobile Body Terminology (Draft for Comment), for study only;
- 未签名小 exe 可能被个别杀毒软件误报，选择「允许运行」即可。
- Unsigned executable may trigger false positive alerts from some antivirus software, choose "allow to run".

