# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

这是 ChenDaqian 的 GitHub 个人主页仓库，不是一个传统的软件项目。仓库的核心内容是 README.md 个人资料展示页，通过 GitHub Actions 自动更新开发者统计数据。

## 仓库结构

- `README.md` — 个人主页内容，包含技术栈徽章、GitHub 统计、WakaTime 数据
- `images/` — README 引用的 SVG 徽章和 GIF 动画
- `dist/` — 贡献贪吃蛇动画 SVG 的输出目录（推送到 `output` 分支）
- `.github/workflows/` — 两个自动化工作流
- `ChenDaqian.csproj` — .NET 6.0 项目文件，仅作为占位符，无实际应用代码

## GitHub Actions

| 工作流 | 触发条件 | 作用 |
|--------|----------|------|
| `GenerateSnake.yml` | 每 24 小时 / push 到 main / 手动 | 生成贡献贪吃蛇 SVG，推送到 `output` 分支 |
| `WakeTimeSync.yml` | 每 6 小时 / 手动 | 用 WakaTime API 更新 README 中的编程统计 |

## 分支策略

- `main` — 源代码和 README
- `output` — 自动生成的贪吃蛇动画 SVG（由 Actions 推送，勿手动修改）

## 编辑 README 注意事项

- WakaTime 数据区域（`<!--START_SECTION:waka-->` 到 `<!--END_SECTION:waka-->`）由 Actions 自动覆写，手动编辑会被覆盖
- 贪吃蛇图片引用的是 `output` 分支的 raw URL，修改路径时注意分支名
- 图片资源存放在 `/images/` 目录，使用相对路径引用
