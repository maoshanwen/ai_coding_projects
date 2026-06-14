# ai_coding_project

多项目 AI Coding 工作区，统一接入远程仓库：

- `git@github.com:maoshanwen/ai_coding_projects.git`

## 项目清单

- `clone_web`
- `face`
- `green_diary`
- `happy_me`
- `let_code_ai`
- `tx_happy`

## 分支策略

- 主分支：`main`
- 每个项目对应一个开发分支：
  - `proj/clone_web`
  - `proj/face`
  - `proj/green_diary`
  - `proj/happy_me`
  - `proj/let_code_ai`
  - `proj/tx_happy`

建议流程：

1. 从 `main` 切到对应项目分支。
2. 只修改该项目目录下内容。
3. 提交后推送分支并发起 PR 合并到 `main`。

## 演示文档约定

每个项目目录包含 `DEMO.md`，用于记录：

- 运行环境
- 启动命令
- 核心功能演示步骤
- 截图或录屏链接
- 已知问题

## 快速开始

```bash
git clone git@github.com:maoshanwen/ai_coding_projects.git
cd ai_coding_projects
git checkout main
```

如果你是首次从本地推送本仓库：

```bash
git add .
git commit -m "chore: initialize monorepo docs and branch strategy"
git push -u origin main
```
