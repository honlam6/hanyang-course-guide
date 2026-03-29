# 韩国汉阳大学选课评价系统

[English](./README.en.md) | [한국어](./README.ko.md)

这是一个给汉阳大学学生使用的选课评价、课程表和 AI 辅助选课网站。

- 在线示范：<https://hanyang.eu.cc>
- GitHub 展示建议：[docs/github-metadata.md](./docs/github-metadata.md)
- 系统架构与网站逻辑：[docs/architecture.md](./docs/architecture.md)
- 数据处理说明：[docs/data-source.md](./docs/data-source.md)
- 数据组织概览：[docs/data-model.md](./docs/data-model.md)
- 贡献指南：[CONTRIBUTING.md](./CONTRIBUTING.md)
- 安全说明：[SECURITY.md](./SECURITY.md)

## 示范截图

### Desktop

![Desktop Demo](./docs/images/homepage-desktop.png)

### Mobile

![Mobile Demo](./docs/images/homepage-mobile.png)

## 项目概览

项目当前包含这些能力：

- 课程浏览、搜索、筛选
- 课程详情展示
- 课程表功能
- 时间冲突检测
- 用户提交评价与信息修正
- 管理后台审核
- AI 选课助手

## 核心思路

这个项目的重点，不是把 Everytime 上的内容原样搬到网站里。

更重要的是把分散的课程评价信号做成可以稳定使用的课程画像。

我的做法大致是：

1. 从 Everytime 相关页面整理课程信息和用户评价
2. 将同一门课的多条评价合并理解
3. 用 AI 做课程级汇总，沉淀成统一风格的摘要和结论
4. 再把这些课程画像用于搜索、推荐、问答和前台展示

所以用户最终看到的不是一堆零散原始评论，而是经过整理、归纳和统一表达后的课程信息。

如果你有别的采集或处理方式，也可以按自己的方法实现。

## AI 评价汇总与问答增强

这部分是项目里最关键的一层。

这里的 AI 不是只负责聊天，而是先参与课程评价的汇总，再参与后续问答。

整体上可以理解为：

- 多条用户评价先被汇总成课程级摘要
- 课程摘要进一步被组织成可检索的知识单元
- 用户提问后，系统先做相关内容召回，再生成最终回答
- 接入模型使用的是 Google Gemini API

因此网站的 AI 能力更接近“课程知识增强问答”，而不是一个孤立的聊天框。

## 课程表与冲突检测

网站还包含课程表功能。

用户可以把课程加入课表，系统会根据课程时间自动检测冲突，并在列表与课程表视图中给出提示。课程表也支持导出图片。

## 数据说明

公开仓库里保留的是整体产品逻辑、公开 Web 部分和必要的集成方式说明。

数据组织和处理思路会做概览说明，但不会把核心实现细节展开到操作层。

可参考：

- [docs/data-source.md](./docs/data-source.md)
- [docs/data-model.md](./docs/data-model.md)
- [docs/architecture.md](./docs/architecture.md)

## 本地运行

```bash
npm install
cp .env.example .env
npm run dev
```

默认访问：

- 前台：`http://localhost:3000/`
- 后台：`http://localhost:3000/admin`

数据库初始化：

- 在 Supabase SQL Editor 执行 [`supabase_setup.sql`](./supabase_setup.sql)

## 面向其他韩国高校的适配

这个项目当前是按汉阳大学来设计的，但底层思路并不局限于单一学校。

如果迁移到其他韩国高校，通常需要重新整理学校名称、校区体系、课程分类、数据来源和 AI 汇总策略。

更准确的说法是：

- 当前产品：汉阳大学选课评价系统
- 方法层面：可以扩展到其他韩国高校
