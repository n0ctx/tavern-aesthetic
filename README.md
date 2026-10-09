# Tavern Aesthetic

为角色扮演、互动小说、游戏面板、人物档案和叙事型网页提供沉浸式界面设计指导的 AI Skill。

重点包括作品独有的美术概念、主视觉与信息层级、素材风格统一、中文可读性，以及可操作的实际界面。独立于 SillyTavern 和具体前端框架，优先沿用项目已有实现；有明确视觉需求时，可按需使用现有 AI 生图能力。

## 安装

安装到 Codex 的个人 Skill 目录：

```sh
git clone https://github.com/n0ctx/tavern-aesthetic.git ~/.agents/skills/tavern-aesthetic
```

Claude Code 可安装到 `~/.claude/skills/tavern-aesthetic`。若目标目录已存在，请先检查其中内容，避免覆盖已有安装。

## 使用

在支持 Skill 的 AI 工具中显式调用 `tavern-aesthetic`，并说明题材、页面用途、现有项目路径和具体需求。例如：

> 使用 tavern-aesthetic，为这个互动小说项目设计角色档案页，突出角色的背景与关键操作，并保证中文阅读体验。

本 Skill 适用于沉浸式叙事界面，不因普通网页开发任务自动触发。仅要求设计方案时，不擅自修改代码。

## 文件

- [SKILL.md](SKILL.md)：适用范围、设计流程和交付要求。
- [references/asset-sources.md](references/asset-sources.md)：按需素材来源与许可核对指引。
