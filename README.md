<div align="center">

![紫微斗数 AI 解盘技能](assets/ziwei-banner.png)

</div>

# 紫微斗数 AI 解盘技能 (Zi Wei Dou Shu Chart Reading Skill)

[![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-blue)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Antigravity%20%7C%20Claude%20Code%20%7C%20Hermes-8A2BE2)](#使用方式)
[![Knowledge Base](https://img.shields.io/badge/References-14%20Modules-success)](#知识库架构)

紫微斗数 AI Skill — 一份面向大语言模型（Claude、Antigravity CLI、DeepSeek、GPT 等）的结构化专业解盘指令集与权威知识库。**不是排盘工具，是专业解盘引擎。**

---

## 🌟 核心特色

- **纯解盘引擎定位**：排盘交由专业算法库，AI 专注于执行人类资深命理师的专业推演与多维解读。
- **HARD-GATE 安全防编造机制**：指令集与知识库彻底解耦。AI 回答前必须实时调阅对应的 reference 文件，**不读不答，拒绝幻觉**。
- **正统典籍校准**：知识库全量参考《紫微斗数全书》《紫微斗数全集》《骨髓赋》及主流学术论坛共识，排除了星曜五行颠倒、伪吉格与推运口诀错误。
- **多流派权重融合**：以**三合派（70%）**为骨架，融合**飞星四化（15%）**、**河洛卦象（10%）**与**钦天四化（5%）**，提供兼具格局高度与时空细节的推演。
- **多 Agent 平台即插即用**：原生支持 Google Antigravity CLI / Gemini CLI、Claude Code、Hermes Agent、Cursor、Aider 等主流 AI Agent 平台。

---

## 🏛️ 知识库架构

```
ziwei-doushu/
├── SKILL.md                ← 核心：流程指令 + 决策路由 + 输出模板
├── README.md               ← 本说明文件
└── references/             ← 权威数据层（AI 按需读取，不内联）
    ├── shier-gong.md           十二宫位详解（含空宫借对、夹宫双向效应、财荫/刑忌夹印）
    ├── shisi-zhuixing.md       十四主星详解（五行、阴阳、庙旺陷落、双星同宫特质）
    ├── fuzhu-xing.md           六吉星与辅星详解（左右、昌曲、魁钺、禄存、天马）
    ├── sha-xing.md             六煞星详解（羊陀火铃空劫，火空则发与生克制化）
    ├── sihua.md                四化飞星详解（天干四化表、飞化公式、来因宫定位）
    ├── geju.md                 格局三层判定（石中隐玉、明珠出海、日月并明、铃昌陀武等）
    ├── daxian-liunian.md       大限流年小限推算（含年支三合起小限、身宫命身合参）
    ├── hunyin.md               婚姻感情专题
    ├── shiye-caifu.md          事业财富专题（命财官三方四正与田宅财库）
    ├── jiankang.md             疾厄健康专题（星曜五行病灶与运势应期）
    ├── heluo-guaxiang.md       河洛卦象分析（一六共宗、六条线、气数位）
    ├── qintian-sihua.md        钦天四化分析（体用向心离心自化）
    ├── wuxing-shengke.md       五行生克分析（五行局、通关救应、反侮机制）
    └── xingqing-mingli.md      星情论与历代名人命例
```

---

## 🛡️ 核心推演机制

### 1. 决策路由系统

用户输入命盘或问题后，系统按 14 条路径自动路由读取目标知识库：

```
用户请求
├─ 宫位/三方四正/空宫借对 → references/shier-gong.md
├─ 主星特性/庙旺陷落      → references/shisi-zhuixing.md
├─ 六煞/六吉/辅曜特性      → references/sha-xing.md, fuzhu-xing.md
├─ 四化/来因宫/飞化        → references/sihua.md
├─ 格局评定/吉凶纯度      → references/geju.md
├─ 大限/流年/小限/身宫     → references/daxian-liunian.md
├─ 婚姻感情/桃花          → references/hunyin.md
├─ 事业/财运/创业          → references/shiye-caifu.md
├─ 健康/疾厄/病灶          → references/jiankang.md
├─ 五行生克/五行局        → references/wuxing-shengke.md
└─ 综合解盘                → 多文件组合交叉读取
```

### 2. 双输出模式

| 模式 | 适用场景 | 输出结构 |
|------|----------|----------|
| **Short Mode** | 具体 yes/no 问题、单一事件或时机预测 | 核心结论 → 关键宫位与星曜 → 时机应期 → 实操建议 |
| **Full Mode** | 整体格局分析、全盘深度解读 | 命盘概览 → 命身格局评定 → 三方四正精析 → 专题深挖 → 大限流年推演 → 核心建议 |

### 3. 五步解盘工作流

1. **命宫三方四正分析** — 三合派核心架构，空宫借对宫主星，核定命财官迁基盘。
2. **星曜综合互动** — 主星 + 六吉 + 六煞 + 四化 + 五行生克 + 夹宫（财荫夹印/刑忌夹印等）。
3. **格局三层判定** — 严格依 `required（必备）` → `breaking（破格）` → `bonus（加分）` 逐项核验纯度与九品等级。
4. **时空运势推算** — 生年四化（体）→ 大限四化（十年用）→ 流年太岁与小限（应期）→ 命身合参。
5. **专题多维聚焦** — 三合派 70% 主导，飞星四化、河洛卦象与钦天四化进行交叉验证。

---

## 🔍 知识库正统校准说明

本版本对传统斗数文献及知识库进行了严格的**理论审校与知识点校正**：

1. **星曜五行归正**：
   - **地空**更正为**阴火（丁火）**，**地劫**更正为**阳火（丙火）**（契合“火空则发”古理，排除水属误记）；
   - **天魁（阳火）**、**天钺（阴火）**；**擎羊（阳金）**、**陀罗（阴金）**；**禄存（阴土）**归位。
2. **主星庙旺陷落校准**：
   - **巨门星**：子午入庙（石中隐玉），辰戌落陷（天罗地网）；
   - **天机星**：辰戌庙旺（善荫朝纲），巳亥落陷；
   - **天同星**：子位庙旺（水澄桂萼），午位落陷；
   - **天相星**：明确标出卯酉二宫独坐落陷。
3. **经典格局定义规范**：
   - **明珠出海格**：规范为未宫立命无正曜，卯阳亥阴并明会照（明确区分太阳卯宫坐命的“日出扶桑格”）；
   - **日月同辉格**：规范为日巳月酉或日卯月亥并明（明确区分丑未二宫的“日月同宫格”）；
   - **铃昌陀武格**：明确界定为《骨髓赋》所载之水厄败亡凶格，移除伪吉化概念。
4. **推运法则校准**：
   - **小限起宫**：严格遵循生年三合四墓库起算口诀（寅午戌起辰、申子辰起戌、巳酉丑起未、亥卯未起丑，男顺女逆）。
5. **宫位体系纠偏**：
   - 修正事业宫（官禄宫）三合宫位为【命宫】与【财帛宫】；补齐六外宫之【兄弟宫】分类。

---

## 🚀 安装与使用方式

### 1. Google Antigravity CLI / Gemini CLI

直接将本仓库克隆至全局配置目录或项目 `.agents/` 目录：

```bash
# 全局安装（所有工作区通用）
git clone https://github.com/SuperGODOG/ziwei-doushu.git ~/.gemini/config/skills/ziwei-doushu

# 或项目级安装
git clone https://github.com/SuperGODOG/ziwei-doushu.git .agents/skills/ziwei-doushu
```

在对话中输入关于命盘、十二宫、四化或紫微斗数的问题，Antigravity CLI 将自动按需调阅知识库。

### 2. Claude Code

```bash
git clone https://github.com/SuperGODOG/ziwei-doushu.git ~/.claude/skills/ziwei-doushu
```

### 3. Hermes Agent

```bash
git clone https://github.com/SuperGODOG/ziwei-doushu.git ~/.hermes/skills/ziwei-doushu
```

### 4. 其他 LLM 平台（Web / IDE 扩展）

将 `SKILL.md` 内容作为 System Prompt，并将 `references/` 目录下的 Markdown 文档作为上下文知识库附件上传即可。

---

## 📊 推荐搭配排盘工具

本 Skill 聚焦于精准解盘，推荐使用以下成熟的第三方排盘工具生成命盘后贴给 AI：

- **[iztro](https://github.com/SylarLong/iztro)** — 现代开源紫微斗数排盘 JS/TS 库（另有 Python 版 `iztro-py`）
- **各大专业在线排盘网站** — 导出包含十二宫星曜分布、三方四正、生年四化与大限流年的标准文本/JSON 格式即可。

---

## 🎯 触发词 (Triggers)

> 紫微斗數、紫微、斗數、命盤、排盤、星盤、十二宮、命宮、四化、大限、流年、来因宫、ziwei、purple star、astrolabe

---

## 📄 开源许可

本项目遵循 [CC BY-NC-SA 4.0](LICENSE) 许可协议发布。

---

<div align="center">

*命由天造，运由己生。虽曰天命，岂非人事？紫微斗数是认识自我潜能与时机节奏的智慧系统，而非宿命判决书。*

</div>
