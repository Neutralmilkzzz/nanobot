<div align="center">
  <p>
    <a href="README.md">English</a> | <b>简体中文</b>
  </p>
</div>

<div align="center">
  <img src="nanobot_logo.png" alt="nanobot" width="500">
  <h1>nanobot: 超轻量级个人 AI 助手</h1>
  <p>
    <a href="https://pypi.org/project/nanobot-ai/"><img src="https://img.shields.io/pypi/v/nanobot-ai" alt="PyPI"></a>
    <a href="https://pepy.tech/project/nanobot-ai"><img src="https://static.pepy.tech/badge/nanobot-ai" alt="Downloads"></a>
    <img src="https://img.shields.io/badge/python-≥3.11-blue" alt="Python">
    <img src="https://img.shields.io/badge/license-MIT-green" alt="License">
    <a href="./COMMUNICATION.md"><img src="https://img.shields.io/badge/Feishu-Group-E9DBFC?style=flat&logo=feishu&logoColor=white" alt="Feishu"></a>
    <a href="./COMMUNICATION.md"><img src="https://img.shields.io/badge/WeChat-Group-C5EAB4?style=flat&logo=wechat&logoColor=white" alt="WeChat"></a>
  </p>
</div>

🐈 **nanobot** 是一款受 [Clawdbot](https://github.com/openclaw/openclaw) 启发的**超轻量级**个人 AI 助手。

⚡️ 仅用约 **4,000** 行代码即可实现核心 Agent 功能 —— 比 Clawdbot 的 43w+ 行代码缩小了 **99%**。

## 📢 最新动态

- **2025-02-01** 🎉 nanobot 正式发布！欢迎试用 🐈 nanobot！

## nanobot 核心特性：

🪶 **超轻量级**：仅约 4,000 行代码 —— 在保留核心功能的同时，体积比 Clawdbot 缩小了 99%。

🔬 **适合研究**：代码整洁、可读性强，非常易于理解、修改和扩展，是 AI 智能体研究的理想起点。

⚡️ **极速响应**：极小的开销意味着更快的启动速度、更低的资源占用以及更迅速的开发迭代。

💎 **易于使用**：一键部署，开箱即用。

## 🏗️ 架构设计

<p align="center">
  <img src="nanobot_arch.png" alt="nanobot architecture" width="800">
</p>

## ✨ 功能亮点

<table align="center">
  <tr align="center">
    <th><p align="center">📈 24/7 实时市场分析</p></th>
    <th><p align="center">🚀 全栈软件工程师</p></th>
    <th><p align="center">📅 智能日常管理</p></th>
    <th><p align="center">📚 个人知识助手</p></th>
  </tr>
  <tr>
    <td align="center"><p align="center"><img src="case/search.gif" width="180" height="400"></p></td>
    <td align="center"><p align="center"><img src="case/code.gif" width="180" height="400"></p></td>
    <td align="center"><p align="center"><img src="case/scedule.gif" width="180" height="400"></p></td>
    <td align="center"><p align="center"><img src="case/memory.gif" width="180" height="400"></p></td>
  </tr>
  <tr>
    <td align="center">发现 • 洞察 • 趋势</td>
    <td align="center">开发 • 部署 • 扩展</td>
    <td align="center">规划 • 自动化 • 组织</td>
    <td align="center">学习 • 记忆 • 推理</td>
  </tr>
</table>

## 📦 安装指南

**通过 PyPi 安装**

```bash
pip install nanobot-ai
```

**从源码安装** (推荐开发使用)

```bash
git clone https://github.com/HKUDS/nanobot.git
cd nanobot
pip install -e .
```

## 🚀 快速开始

> [!TIP]
> 请在 `~/.nanobot/config.json` 中设置你的 API Key。
> 获取方式：[OpenRouter](https://openrouter.ai/keys) (LLM) · [Brave Search](https://brave.com/search/api/) (可选，用于联网搜索)
> 你也可以将模型更改为 `minimax/minimax-m2` 以降低成本。

**1. 初始化**

```bash
nanobot onboard
```

**2. 配置** (`~/.nanobot/config.json`)

```json
{
  "providers": {
    "openrouter": {
      "apiKey": "sk-or-v1-xxx"
    }
  },
  "agents": {
    "defaults": {
      "model": "anthropic/claude-opus-4-5"
    }
  },
  "webSearch": {
    "apiKey": "BSA-xxx"
  }
}
```


**3. 开始聊天**

```bash
nanobot agent -m "2+2 等于几？"
```

只需 2 分钟，你就能拥有一个可以工作的 AI 助手。

## 💬 聊天应用

随时随地通过 Telegram 或 WhatsApp 与你的 nanobot 对话。

| 渠道 | 设置难度 |
|---------|-------|
| **Telegram** | 简单 (仅需 Token) |
| **WhatsApp** | 中等 (需扫码) |

<details>
<summary><b>Telegram</b> (推荐)</summary>

**1. 创建机器人**
- 打开 Telegram，搜索 `@BotFather`
- 发送 `/newbot`，按照提示操作
- 复制 Token

**2. 配置**

```json
{
  "channels": {
    "telegram": {
      "enabled": true,
      "token": "你的_BOT_TOKEN",
      "allowFrom": ["你的_USER_ID"]
    }
  }
}
```

> 可以通过 Telegram 上的 `@userinfobot` 获取你的用户 ID。

**3. 运行**

```bash
nanobot gateway
```

</details>

<details>
<summary><b>WhatsApp</b></summary>

需要 **Node.js ≥18**。

**1. 关联设备**

```bash
nanobot channels login
# 使用 WhatsApp 扫描 QR 码 → 设置 → 已关联设备
```

**2. 配置**

```json
{
  "channels": {
    "whatsapp": {
      "enabled": true,
      "allowFrom": ["+1234567890"]
    }
  }
}
```

**3. 运行** (需要两个终端)

```bash
# 终端 1
nanobot channels login

# 终端 2
nanobot gateway
```

</details>

## ⚙️ 配置说明

<details>
<summary><b>完整配置示例</b></summary>

```json
{
  "agents": {
    "defaults": {
      "model": "anthropic/claude-opus-4-5"
    }
  },
  "providers": {
    "openrouter": {
      "apiKey": "sk-or-v1-xxx"
    }
  },
  "channels": {
    "telegram": {
      "enabled": true,
      "token": "123456:ABC...",
      "allowFrom": ["123456789"]
    },
    "whatsapp": {
      "enabled": false
    }
  },
  "tools": {
    "web": {
      "search": {
        "apiKey": "BSA..."
      }
    }
  }
}
```

</details>

## CLI 命令参考

| 命令 | 描述 |
|---------|-------------|
| `nanobot onboard` | 初始化配置与工作区 |
| `nanobot agent -m "..."` | 与 Agent 对话 |
| `nanobot agent` | 进入交互式聊天模式 |
| `nanobot gateway` | 启动网关服务 |
| `nanobot status` | 显示当前状态 |
| `nanobot channels login` | 关联 WhatsApp (扫码) |
| `nanobot channels status` | 显示渠道状态 |

<details>
<summary><b>定时任务 (Cron)</b></summary>

```bash
# 添加任务
nanobot cron add --name "daily" --message "早上好！" --cron "0 9 * * *"
nanobot cron add --name "hourly" --message "检查状态" --every 3600

# 列出任务
nanobot cron list

# 删除任务
nanobot cron remove <job_id>
```

</details>

## 📁 项目结构

```
nanobot/
├── agent/          # 🧠 核心 Agent 逻辑
│   ├── loop.py     #    Agent 循环 (LLM ↔ 工具执行)
│   ├── context.py  #    Prompt 构建
│   ├── memory.py   #    持久化记忆
│   ├── skills.py   #    技能加载器
│   ├── subagent.py #    后台任务执行
│   └── tools/      #    内置工具 (包括 spawn)
├── skills/         # 🎯 预装技能 (github, weather, tmux...)
├── channels/       # 📱 WhatsApp 集成
├── bus/            # 🚌 消息路由
├── cron/           # ⏰ 定时任务
├── heartbeat/      # 💓 主动唤醒
├── providers/      # 🤖 LLM 提供商 (OpenRouter 等)
├── session/        # 💬 对话会话管理
├── config/         # ⚙️ 配置管理
└── cli/            # 🖥️ 命令行工具
```

## 🗺️ 路线图

- [ ] **多模态** —— 听觉与视觉支持 (图片, 语音, 视频)
- [ ] **长期 memory** —— 永不遗忘重要的上下文信息
- [ ] **更强的推理** —— 多步规划与自我反思能力
- [ ] **更多集成** —— Discord, Slack, 邮件, 日历
- [ ] **自我进化** —— 从反馈和错误中不断学习

**想帮忙吗？** 选一个感兴趣的项目并 [提交 PR](https://github.com/HKUDS/nanobot/pulls)！

## 🤝 参与贡献

欢迎提交 PR！代码库设计简洁，非常易读。 🤗

<p align="center">
  <em> 感谢关注 ✨ nanobot!</em><br><br>
  <img src="https://visitor-badge.laobi.icu/badge?page_id=HKUDS.nanobot&style=for-the-badge&color=00d4ff" alt="Views">
</p>
