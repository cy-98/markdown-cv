---
layout: cv
title: "Resume"
lang: en
date: 08 2026
---
## Profile

**Cai Yue** · Full-stack Engineer

🏫 B.S. · China University of Mining and Technology · 2017 - 2021

☎︎ 18747099166

📧 [www.caiyue@qq.com](mailto:www.caiyue@qq.com)

🌐 [github.com/cy-98](https://github.com/cy-98)

## Experience

### Airwallex

*Full-stack Engineer · 2024 - Present*

Focus on platform foundations, testing infrastructure, and full-stack delivery for the financial platform. Own iteration and governance of the company-wide frontend **Foundation** and the **Treasury** management system.

#### Foundation (design system / platform primitives)

- **Component upgrades**: Covered **50+** repositories and **20+** teams company-wide, closed **100+** major version gaps. Shipped every component to the latest release; built progress tracking that auto-detects remaining gaps and opens MRs with AI-assisted coding. Coordinated and supported all teams through migration to the latest component versions.
- **Component maintenance**: Ongoing component refactors and on-call defect fixes; built a bundle-size tracking dashboard.
- **Location service**: Legacy service was unowned, under-observed, and missing complete logs. Restored monitoring/alerting, domain routing, latency metrics, and test environments end-to-end, then completed a **zero-incident** traffic cutover.
- **Agent development**: Contributed to the company’s online coding Agent; deep familiarity with Web Agent flows and internals.
- **Oncall Agent**: Own design-team on-call. Detect feature requests and bug fixes from Slack channels, answer from historical messages and the codebase; ask follow-ups when context is missing, reply promptly, and land the code changes.

#### Treasury / financial platform full-stack delivery

- **Core modules**: Led full-stack delivery for bank accounts, cash visualization, and financial reporting so finance can manage global account funds. Frontend covers fund distribution visualization, idle-cash investment, batch transfers, and Agent offline analysis; backend covers auth, permissions, financial data queries, and form storage. Split the monolith into **5** microservices, isolated unrelated services, rebalanced production resources, and improved end-to-end logging and observability coverage.
- **Agent**: Cleaned unused/legacy dependencies in the Rush monorepo; codified reusable Skills (TDD coding, element design, server-driven UI, local debug & verification, remote E2E, delivery scoring) and a Subagent chain (Planner, developer, tester, deliver, designer), wired into the company online Agent and Slack bot. Using Jira tickets as the entry point, orchestrated a closed loop of Ticket → spec → unit tests → implementation → MR → remote E2E → human review for one-shot delivery from scratch with less instability and less human intervention. Backend engineers can independently ship standard frontend work under shared conventions; product can generate UX prototypes quickly via Slack bot.
- **Team impact**: PMs can use the Agent to produce prototypes that match existing style and interaction patterns. Standard frontend work can be delivered by two partnered backend engineers without frontend involvement. Treasury frontend day-to-day ownership shrank from ~**2** people to **0.5**, saving ~**18** person-months per year. Frontend focus shifted to code review, design, and requirements review.

### ByteDance · TikTok User Growth

*Frontend Engineer · 2021 - 2024*

Cross-platform Web product work, performance and i18n, incentive gameplay engineering, and full-chain In-app automation testing.

#### Cross-platform engineering & In-app quality

- **Cross-platform engineering**: As the team’s cross-platform engineering owner, drove adoption of the next-gen Lynx rendering framework, stood up non-browser host projects covering amount localization and multi-language bundle trimming; improved experience via package size reduction, container keep-alive, data prefetch, and offline support, and built critical-path monitoring. Independently authored experiment reports across countries and pages: core page load time dropped ~**80%** to under 1s, and **page penetration roughly doubled**; contributed Web isomorphic fallback so one codebase runs in both the cross-platform container and the browser.
- **In-app automation**: While In-app Web testing was still immature, covered long incentive flows across cross-platform, deep-link launch, and client containers. Co-built a test data service with QA and backend (auth, real-user simulation, account pool); introduced client test tools and a frontend automation framework, using real-device debugging to define required APIs; scripts handled popup dismissal, risk checks, and client-element messaging for **noise resilience**. Measured impact via effective block rate, production incidents, stability, and case **coverage**.

#### “Hundred Yuan” incentive gameplay

- Split into config / UI / gameplay layers with dependency injection and **xstate**, enabling multi-version, multi-country, multi-audience strategies in parallel.
- Extracted country differences into platform config; decoupled gameplay from UI so themes and assets are configurable.
- Rolled out across 10+ countries starting March 2022, often as Fri–Sun campaigns. 2021 Christmas promo acquired ~**115K** new users with ~**27.2%** retention; gameplay-driven traffic covered ~**44%** of acquisition cost. Brazil launch **DNU 8000+**, steady-state daily **DNU ~2000+**.

## Skills

- **Frontend & engineering**: React, component libraries & design systems, i18n, performance optimization, observability.
- **Architecture & quality**: Cross-platform hosts & Web isomorphic apps, dependency injection; In-app Web testing, client co-debugging, automation, and release pipelines.
- **Productivity & collaboration**: Git workflows; proficient with **Claude** and **Cursor**, Agent session management, and Agent workflow design.

## Personal projects & OSS

- **Raycast community extensions** ([raycast/extensions](https://github.com/raycast/extensions)): Develop and maintain open-source extensions in the Raycast Store.
  - **Visual Studio Code**: Fixed compatibility after VS Code changed the `storage.json` path; later fixed a crash when opening Recent Projects.
  - **Tailwind Cheatsheet**: Built and published a Tailwind CSS cheatsheet extension.
- **Open-source contributions**: Ongoing Issues / PRs to upstream and downstream libraries.
  - **rollup-plugin-dts**: Fixed `*.d.ts` output path issues
  - **XState**: Added options support to `useSpawn`
  - **react-keyframes**: Loop frames and end callback
  - **Keyframes**: Fixed animation not running after adding a step
