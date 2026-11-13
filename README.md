# AI-Training-Dat
# Social Diagnosis (social_diagnosis_10k.json) 仓库 README

> **项目名称：** Social Diagnosis 10k (`social_diagnosis_10k.json`)  
> **数据规模：** 10,000 条真实社交互动/微信聊天对话样本及深度心理语义分析数据集  

---

## 📖 项目简介 (Introduction)

在现代人际交往中，微信、聊天软件等线上沟通往往充满潜台词。**Social Diagnosis** 是一个专注于**社交关系健康度诊断、情感倾向评估、潜在沟通风险（如情感勒索、人情裹挟、商业诱导、冷暴力）识别**的数据集。

本仓库核心文件 `social_diagnosis_10k.json` 包含了丰富的日常与复杂人际对话样本。每一条样本均经过精细化标注，涵盖情绪类别、情感极性、亲密度评分（Affection Score）、关系趋势、风险等级以及深层潜台词（Subtext）剖析，旨在为**大语言模型（LLM）情感微调、社交心理学研究、AI 恋商/情商助手开发**提供高质量的垂直领域语料。

---

## 🗂️ 数据集结构 (Data Structure)

数据集采用标准 JSON 格式存储，每条记录包含多维度的社交分析标签。以下为典型的数据结构示例：

```json
{
  "conversation": "我：周五晚上有空吗 一起去吃烧烤啊[狗头]\n对方：我不太想吃烧烤 懒得动[苦涩]\n我：那就这么定了啊\n对方：随便吧[苦涩]\n我：别放我鸽子啊[狗头]\n对方：嗯[让我看看]",
  "analysis": {
    "emotion": "客套冷淡",
    "sentiment_polarity": "负面",
    "affection_score": 10,
    "trend": "下降",
    "risk_level": "中风险",
    "risk_and_subtext": "被动回应不展开话题，隐含礼貌性疏远"
  }
}
```

### 字段说明 (Field Descriptions)

* **`conversation`**：对话文本，记录了双方来回的聊天内容（包含常用的 Emoji 表情符号，还原真实微信/社交通讯场景）。
* **`analysis`**：针对该段对话的 AI/人工深度诊断结果，包含：
  * **`emotion`**：主导情绪（如：客套冷淡、过度热络、隐性抱怨、活泼打趣、患得患失等）。
  * **`sentiment_polarity`**：情感极性（正面 / 中性 / 负面）。
  * **`affection_score`**：亲密度/好感度评分（0 - 100 分量化指标）。
  * **`trend`**：关系发展趋势（上升 / 持平 / 下降）。
  * **`risk_level`**：沟通与社交风险等级（无风险 / 低风险 / 中风险 / 高风险）。
  * **`risk_and_subtext`**：潜台词剖析与风险点总结（揭示言语背后的防御机制、利益诉求、情感记账或转化意图）。

---

## 🎯 核心应用场景 (Use Cases)

1. **AI 社交/情商助手 (Social/EQ Copilot)**：帮助大模型理解人类聊天的“弦外之音”，避免直男式回复或盲目踩雷。
2. **风险防范与心理健康监控**：识别高风险对话中的情感勒索（Emotional Blackmail）、杀猪盘/商业诱导、隐性人情施压及社交冷暴力。
3. **情绪分析与 NLP 模型训练**：作为微调（Fine-tuning）语料库，用于训练具备高情商、高共情能力的垂直领域对话模型。

---

## 🚀 快速开始 (Quick Start)

你可以使用 Python 快速加载并分析该数据集：

```python
import json

# 加载数据集
with open("social_diagnosis_10k.json", "r", encoding="utf-8") as f:
    data = json.load(f)

print(f"数据集总样本数: {len(data)}")

# 查看第一条样本
sample = data[0]
print("对话内容：\n", sample["conversation"])
print("\n深度诊断：", sample["analysis"])
```

---

## 🛠️ 贡献与维护 (Contributing)

欢迎通过 Pull Requests 或 Issues 提交更多的对话样本、优化分析维度或修复数据标签。让我们一起用技术解码人际社交的复杂密码！

---

## 📝 许可证 (License)

本项目采用 [MIT License](LICENSE) 开源协议。
