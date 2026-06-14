# ai_coding_project

这是一个多项目 AI Coding 工作区，用来沉淀我在不同产品形态下的技术探索：

- Web 自动化与抓取
- AI 交互应用与前后端联动
- 数据/训练/评估流程化
- 从原型到可演示项目的工程化实践

远程仓库：

- https://github.com/maoshanwen/ai_coding_projects

## 我想解决什么问题

把 AI 项目从“单次脚本”升级成“可迭代产品”时，常见痛点是：

1. 场景分散，代码风格和技术栈不统一。
2. 演示材料不完整，别人难以快速理解价值。
3. 数据与隐私边界不清晰，容易误提交本地数据。

这个仓库的目标是把以上问题标准化：

1. 每个子项目都明确目的、设计思路和可运行入口。
2. 每个子项目都有独立演示文档（DEMO.md）。
3. 通过分支策略和忽略规则控制代码与数据边界。

## 项目设计总览

| 项目 | 目的 | 功能设计（核心模块） | 演示入口 |
|---|---|---|---|
| clone_web | 自动化采集与结构化处理网页内容 | 配置管理、数据模型、技能编排、工作流执行、前端静态页 | [clone_web/DEMO.md](clone_web/DEMO.md) |
| face | 人脸相关前端交互与引擎验证 | 前端 UI、引擎层、模型资源、后端服务协作 | [face/DEMO.md](face/DEMO.md) |
| green_diary | 轻量日记应用与内容管理实践 | Flask 应用、模板渲染、编辑器、上传能力、数据持久化 | [green_diary/DEMO.md](green_diary/DEMO.md) |
| happy_me | 面向任务的 AI 服务与离线数据流程 | API、任务队列、数据构建、评估脚本、文档沉淀 | [happy_me/DEMO.md](happy_me/DEMO.md) |
| let_code_ai | 轻量代码生成/解题实验入口 | 单文件快速原型、输入处理、结果输出 | [let_code_ai/DEMO.md](let_code_ai/DEMO.md) |
| tx_happy | 独立仓库形态的训练与分析流程 | 数据集、训练器、评估模块、运行脚本 | [tx_happy/DEMO.md](tx_happy/DEMO.md) |

## 如何展示每个项目（建议结构）

每个项目的 DEMO.md 建议固定包含以下 6 部分：

1. 目标与业务场景
2. 系统设计图（模块与数据流）
3. 快速启动命令
4. 关键演示步骤（3 到 5 步）
5. 演示图（截图或录屏链接）
6. 已知问题与下一步计划

建议每个项目至少放 2 张图：

1. 架构/流程图
2. 结果页或关键输出截图

## 分支策略

- 主分支：main
- 每个项目对应一个开发分支：
  - proj/clone_web
  - proj/face
  - proj/green_diary
  - proj/happy_me
  - proj/let_code_ai
  - proj/tx_happy

建议流程：

1. 从 main 切到对应项目分支。
2. 只修改该项目目录下内容。
3. 提交后推送分支并发起 PR 合并到 main。

## 数据与隐私边界（重点）

默认不上传本地私有数据，尤其是：

1. .env 与密钥类文件
2. 本地数据库文件
3. 本地上传图片与日志文件

提交前建议执行：

```bash
git status --short
git diff --name-only --cached
```

## 快速开始

```bash
git clone https://github.com/maoshanwen/ai_coding_projects.git
cd ai_coding_projects
git checkout main
```
