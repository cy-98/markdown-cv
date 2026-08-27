---
layout: cv
title: "个人简历"
date: 08 2026
---
## 个人简介

**才越** · 前端工程师

🏫 本科 · 中国矿业大学 · 2017 - 2021

☎︎ 18747099166

📧 [www.caiyue@qq.com](mailto:www.caiyue@qq.com)

🌐 [github.com/cy-98](https://github.com/cy-98)

## 工作经历

### Airwallex

*前端工程师 · 2024 - 至今*

围绕平台前端、测试基础设施和金融平台交付效率，负责公司级 **Foundation** 与 **Treasury（资金管理）** 的迭代与治理。

#### Foundation（设计系统 / 平台基础能力）

- **组件升级**：覆盖全公司 **50+** 仓库、**20+** 团队，完成 **100+** 个 major 和当时所有 minor, fix 版本对齐；搭建进度跟踪流程，自动查找追踪版本缺口并且AI编码提MR。通过沟通协调和人力支持完成全部团队迁至最新组件版本。
- **组件维护**：持续组件重构与 oncall 缺陷修复，并搭建 bundle size 追踪看板。
- **DateTime**：根据设计师 spec 设计并落地自用 date-time 库，在符合国际标准的前提下适配不同精度、不同格式的时间展示。
- **Location 服务**：主导无人维护的 client-geolocation-service 迁移。旧服务缺少观测、日志不完整；将监控告警、域名路由、请求耗时、测试环境等完整链路逐项补齐后完成**0 故障**切流。

#### Treasury / 金融平台交付

- **核心模块**：主导设计和实现银行账户、现金可视化与财务报表，为财务团队提供资金实时视图与多维度分析。
- **Agent 基建**：清理无用,老旧依赖，建立 Agent context 工程并沉淀 Skill，接入公司在线 Agent 与 Slack bot。
- **Agent 工作流**：以 Jira ticket 为基础，根据用户即时输入或需求文档一次性完成建立 Ticket，功能开发、E2E测试，代码提交与人验收。
- **团队收效**：后端开始承包大部分前端需求；产品可通过 Slack bot 快速产出 UX 原型。前端人力由1.5人力节约为0.5人力。

### 字节跳动 · TikTok User Growth

*前端工程师 · 2021 - 2024*

跨端 Web 业务、性能与国际化、激励玩法工程化，以及 In-app 全链路自动化测试建设。

#### 跨端工程与 In-app 质量

- **跨端工程**：推动团队接入新一代跨端渲染框架 Lynx，搭建 Lynx 容器的前端工程，覆盖数字本地化与多语言；通过包体缩减、容器保活、数据预取、离线化优化体验，并搭建关键路径监控。带领开发小组完成核心页面迁移：加载时长下降约 **80%**、达秒开，**用户渗透率翻倍**；参与 Web 同构降级，使同一套工程可运行于跨端容器与浏览器。
- **In-app 自动化**：引入客户端测试工具与前端自动化框架，覆盖跨端、唤端与客户端容器的激励长链路，与 QA、服务端共建测试数据服务（鉴权、真实用户模拟、账号池）；脚本层实现弹窗关闭、风控校验等**抗干扰**。建立错误拦截数、稳定性与 case **覆盖率**等评估指标。

#### 激励百元玩法

- 以配置 / UI / 玩法三层拆分，结合依赖注入与 **xstate**，支持多版本、多国家、多人群策略并行上线。
- 将国家差异抽至平台配置，玩法与 UI 解耦，换肤与素材可配置。
- 自 **2022 年**起以现金、商品激励等形式在**十余个国家**陆续上线，支撑周期性活动与玩法导量。
  
## 技能与工具
- **前端与工程化**：React、组件库与设计系统、国际化（i18n）、性能优化、Observability（可观测性）。
- **架构与质量**：跨端宿主与 Web 同构、依赖注入；In-app Web 测试、客户端联调、自动化测试与发布流水线。
- **提效与协作**：Git 工作流；熟悉 **Claude** 与 **Cursor**，熟悉 Agent session 管理，Agent 工作流设计。

## 个人经历

- **Raycast 社区插件**（[raycast/extensions](https://github.com/raycast/extensions)）：参与 Raycast Store 开源扩展的开发与维护。
  - **Visual Studio Code**：修复 VS Code 新版本 `storage.json` 路径变更导致的兼容性问题（[PR #1630](https://github.com/raycast/extensions/pull/1630)，已合并）；后续提交 Recent Projects 打开崩溃修复（[PR #9449](https://github.com/raycast/extensions/pull/9449)）。
  - **Tailwind Cheatsheet**：独立开发 Tailwind CSS 速查扩展并提交上架 PR（[PR #1667](https://github.com/raycast/extensions/pull/1667)）。
- **开源社区贡献**：向上下游依赖库持续提交 Issue / PR。
  - **rollup-plugin-dts**：修复 `*.d.ts` 输出路径问题（[PR #177](https://github.com/Swatinem/rollup-plugin-dts/pull/177)，已合并）。
  - **XState**：`useSpawn` 支持 options 参数（[PR #3419](https://github.com/statelyai/xstate/pull/3419)）。
  - **react-keyframes**：loop frames 与 end callback（[PR #78](https://github.com/vercel/react-keyframes/pull/78)）。
  - **Keyframes**：修复 add step 后动画不运行（[PR #25](https://github.com/mitchas/Keyframes/pull/25)）。