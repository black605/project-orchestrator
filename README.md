# 项目主控 · Project Orchestrator

一个适用于 Codex 的中文 Skill。你在一个主控聊天里描述想做什么，由主控理解目标、拆分任务、协调执行聊天，并从实际交付入口验收。第一版包含设计阶段的交互原型与视觉风格分工，适合从想法推进到可评审设计稿或可操作原型。

## 安装

这是公开仓库，无需登录 GitHub。把下面这句话复制到 Codex：

> 请从 https://github.com/black605/project-orchestrator 安装 project-orchestrator 到我的 Codex 用户级 skills 目录，保留已有的本地修改，并验证 SKILL.md 和 references/design.md 可读取。

也可以在已安装 Git 的 macOS 或 Linux 终端执行：

```sh
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
git clone https://github.com/black605/project-orchestrator.git "${CODEX_HOME:-$HOME/.codex}/skills/project-orchestrator"
```

安装后打开新的 Codex 聊天，输入 `$project-orchestrator` 并描述想做的项目。

## 第一次启动

通用说法：“用 $project-orchestrator 启动这个项目。我想做【想做的事】。请根据实际目标决定怎么分工、用什么形式交付。我授权你按需新建本项目的执行聊天，并向它们派发和跟进任务。”

下面是设计项目的一个例子。

> 用 $project-orchestrator 启动项目。我想做一个给学生练习图形推理的小游戏，第一轮能试玩一道题。你做主控，按需新建原型和风格聊天，我授权你在这个项目内向它们派活、跟进和要求返工。

主控先读取项目资料，明确首个交付物和验收方式。原型聊天负责作答、反馈和重试，风格聊天负责题板与素材。主控协调资源接入，打开试玩入口验证，再把可用版本和待决定的问题带回当前聊天。跨聊天调度需要当前 Codex 环境提供相应工具，并获得用户对目标和范围的授权。

## 后续迭代

- **只改一个体验细节**　直接说“答错时先给提示，让学生再试一次”。主控定位当前版本，安排修改并复验。
- **复用已有聊天**　说“原型和风格沿用这个项目现有的两个聊天，我授权你向它们派发并跟进”。主控核对聊天身份后继续工作。
- **固定项目约定**　说“把本项目采用的分工和验收方式合并进 AGENTS.md”。以后在这个项目里可以直接描述目标。
- **增加产品阶段**　说“沿用当前主控，下一步梳理首版范围和优先级”。先用真实交付明确产品职责，再决定是否提炼成跨项目可复用的阶段说明。

[通用主控规则](SKILL.md) · [设计阶段的输入、交付与验收](references/design.md)
