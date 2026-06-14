# ai_coding_project

这是我自己的 vibe coding 试验场。

我把它当成一个长期实验：

1. 用真实需求驱动项目，而不是只做教程式 demo。
2. 允许失败，并记录为什么失败。
3. 把过程和结论写清楚，给未来的自己和面试官看。

仓库地址：

- https://github.com/maoshanwen/ai_coding_projects

## 这个仓库想表达什么

这不是一个“全都成功”的作品集，而是一个真实的工程成长记录：

1. 有些项目解决了我每天真会用的问题。
2. 有些项目方向判断对了，但工程投入和产出不划算，所以停止。
3. 有些项目虽然结果一般，但留下了值得复用的方法论。

我希望面试官看到的是：

1. 我会独立定义问题。
2. 我会做工程取舍。
3. 我能从失败里抽象出可迁移的认知。

## 项目总览（目的 + 设计 + 结果）

### 1) green_diary

目标：做一个我自己愿意每天使用的写作工具。

背景：我平时用 CSDN 写记录，但外观和交互不够顺手，所以做了自己的版本。

功能设计：

1. Flask + SQLite 的轻量架构，启动成本低。
2. Markdown 编辑、预览、发布、回收站恢复。
3. 支持图片上传，方便知识记录。
4. 保持可扩展，后续可加“插入当前时间”等我常用功能。

运行示例：

```bash
cd green_diary
pip install -r requirements.txt
python app.py
```

访问：

- 首页：http://127.0.0.1:5000/
- 编辑器：http://127.0.0.1:5000/editor

结果与思考：这是当前对我最有帮助的项目之一，能直接服务我的日常输出。

### 2) clone_web

目标：从“好看的网页截图”反推设计结构，辅助我自己的页面设计。

背景：我发现很多 AI 生成网页风格相似，所以想做一个“截图理解 + 页面生成/修改”的流程。

功能设计：

1. FastAPI + SQLite，支持会话与版本管理。
2. 支持多截图输入，首版生成后可继续对话修改。
3. 前端可视化预览，形成最小闭环。

运行示例：

```bash
cd clone_web
pip install -r requirements.txt
uvicorn app.main:app --reload
```

结果与思考：

1. 在配色、排版层面有帮助。
2. 在动效细节和审美把控上仍不够稳定。
3. 目前暂停深入，把精力放到更高收益方向。

### 3) face

目标：做一个有个人风格的“非露脸内容创作”换脸/特效工具。

背景：现有很多 App 模板化太强，我想做可控度更高的版本。

功能设计：

1. 前端实时处理框架（画布、参数面板、录制）。
2. 关键点检测和变形层接口预留，便于后续替换模型。
3. 先做可运行骨架，再做效果迭代。

运行示例：

```bash
cd face
npm install
npm run dev
```

结果与思考：不接入更强模型时，效果上限明显，方向暂缓。

可公开效果图（素材示意）：

![face input](face/public/photo/face.png)
![face style sample](face/public/photo/fairy2.png)

### 4) happy_me

目标：把“科研任务”和“竞赛任务”拆成双 Agent，自动抓取信息并产出建议。

背景：我希望把重复的信息收集和初步分析自动化，减少低价值手工劳动。

功能设计：

1. FastAPI 统一任务入口。
2. Celery + Redis 异步执行。
3. 双路由：research / contest。
4. 多源数据连接器 + 聚类分析。

运行示例：

```bash
cd happy_me
pip install -e '.[dev]'
./scripts/run_api.sh
./scripts/run_worker.sh
```

结果与思考：

1. 竞赛侧的数据与流程价值较高。
2. 科研侧能产出很多结论，但人工审阅成本太高。
3. 后续将重点迁移到更聚焦的竞赛深挖。

### 5) tx_happy

目标：做一个 auto-research 风格的竞赛增强系统，把天池/Kaggle 优秀方案迁移到腾讯 baseline。

我做过的尝试：

1. 13 个单点创新。
2. 10 组组合创新。

关键复盘：

1. 在“每日评测次数受限”的环境下，很难找到全局最优，通常只能得到局部最优。
2. 尝试次数越多，理论上越接近最优，但时间和算力成本会快速上升。
3. 大模型预判和剪枝很关键，但前提是高质量数据源和足够深入的推理能力。
4. 即便短期每次都小涨点，也要持续评估长期 ROI（训练/评测成本 vs 人工经验）。

运行示例：

```bash
cd tx_happy
bash run.sh
```

### 6) let_code_ai

目标：做一个我刷题时“截图即出题解”的小工具，减少在多个页面来回找资料的时间。

功能设计：单文件快速原型，强调实用效率。

运行示例：

```bash
cd let_code_ai
python ai_let_code.py
```

延伸思考：我认为工程能力不该只靠刷题定义，更应包括架构理解、调试能力、部署和协作。

## 我的方法论（这部分比结果更重要）

1. 先做最小可运行闭环，再追求完整功能。
2. 把失败当成显式资产，写清楚“为什么不做了”。
3. 每个项目都保留可复现实例，确保可讲、可演示、可继续迭代。

## 隐私与数据边界

为了避免个人数据泄漏，仓库默认不上传：

1. .env 与密钥文件。
2. 本地数据库（如 green_diary 的 database.db）。
3. 本地上传目录（如 green_diary/static/uploads）。

提交前我会做最小检查：

```bash
git status --short
git diff --name-only --cached
```

## 分支策略

- main
- proj/clone_web
- proj/face
- proj/green_diary
- proj/happy_me
- proj/let_code_ai
- proj/tx_happy

## 快速开始

```bash
git clone https://github.com/maoshanwen/ai_coding_projects.git
cd ai_coding_projects
git checkout main
```
