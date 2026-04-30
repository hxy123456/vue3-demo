# HomeView 页面文档

## 概述

HomeView 是 Vue3 项目的首页视图，作为应用的主入口页面，展示 Vue 官方提供的欢迎引导内容。

## 文件结构

```
HomeView.vue
├── TheWelcome.vue
│   ├── WelcomeItem.vue (×5)
│   │   ├── IconDocumentation.vue
│   │   ├── IconTooling.vue
│   │   ├── IconEcosystem.vue
│   │   ├── IconCommunity.vue
│   │   └── IconSupport.vue
```

## 组件说明

### HomeView.vue

- **路径**: `src/views/HomeView.vue`
- **功能**: 首页容器组件，渲染 `<main>` 标签并加载 TheWelcome 组件
- **依赖**: `TheWelcome` 组件

### TheWelcome.vue

- **路径**: `src/components/TheWelcome.vue`
- **功能**: 欢迎页内容组件，包含 5 个 WelcomeItem 卡片
- **依赖**: `WelcomeItem`, 5 个图标组件
- **特殊方法**: `openReadmeInEditor()` — 通过 `/__open-in-editor` API 在编辑器中打开 README.md

### WelcomeItem.vue

- **路径**: `src/components/WelcomeItem.vue`
- **功能**: 可复用的欢迎项卡片组件，提供三个插槽：
  - `icon` — 图标插槽
  - `heading` — 标题插槽
  - `default` — 内容插槽
- **样式特性**:
  - 移动端：垂直排列，图标 32×32px
  - 桌面端（≥1024px）：带时间线样式，图标 50×50px 绝对定位，左右有连接线

## 页面内容

| 序号 | 标题 | 图标 | 内容说明 |
|------|------|------|----------|
| 1 | Documentation | IconDocumentation | Vue 官方文档链接，提供入门所需信息 |
| 2 | Tooling | IconTooling | 工具链介绍：Vite（构建）、VSCode + Vue Official（IDE）、Vitest + Cypress/Playwright（测试） |
| 3 | Ecosystem | IconEcosystem | 生态工具：Pinia（状态管理）、Vue Router（路由）、Vue Test Utils（测试）、Vue Dev Tools（调试）、Awesome Vue（资源合集） |
| 4 | Community | IconCommunity | 社区支持：Vue Land（Discord）、StackOverflow、@vuejs.org（Bluesky/X） |
| 5 | Support Vue | IconSupport | 赞助支持：成为 Vue Sponsor |

## 外部链接

- Vue 官方文档: https://vuejs.org/
- Vite 文档: https://vite.dev/guide/features.html
- VSCode: https://code.visualstudio.com/
- Vue Language Tools: https://github.com/vuejs/language-tools
- Vitest: https://vitest.dev/
- Cypress: https://www.cypress.io/
- Playwright: https://playwright.dev/
- Pinia: https://pinia.vuejs.org/
- Vue Router: https://router.vuejs.org/
- Vue Test Utils: https://test-utils.vuejs.org/
- Vue Dev Tools: https://github.com/vuejs/devtools
- Awesome Vue: https://github.com/vuejs/awesome-vue
- Vue Land (Discord): https://chat.vuejs.org
- StackOverflow Vue: https://stackoverflow.com/questions/tagged/vue.js
- Vue Bluesky: https://bsky.app/profile/vuejs.org
- Vue X: https://x.com/vuejs
- Vue Sponsor: https://vuejs.org/sponsor/

## 响应式设计

- **移动端**: WelcomeItem 垂直排列，图标小尺寸（32px），无时间线
- **桌面端（≥1024px）**: WelcomeItem 带时间线连接线，图标大尺寸（50px）绝对定位左侧，形成引导流程视觉效果