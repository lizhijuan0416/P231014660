# 项目 README

## 项目简介

本项目是一个基于 Next.js 的应用程序，整合了本学期的多个课程练习，并着重实现了 QAnything 问答服务以及 WakaTime API 的集成与数据展示。项目致力于提供一个统一的平台来展示学习成果，并通过组件化开发和良好的代码实践来提升可维护性。

## QAnything 集成路径与实现细节

本项目选择 **路径二：API 自行开发** 的方式集成 QAnything 问答服务。选择此路径的原因是为了更深入地理解 QAnything API 的工作原理，实现更灵活的前端交互，并为未来可能的高级定制功能（如流式输出、特定主题问答）打下基础。

### 实现细节：

1.  **API 调用**：通过 Next.js 的 API Routes (`/api/qanything`) 作为中间层，代理对 QAnything 后端服务的请求，以避免客户端直接暴露 API Key，并处理跨域问题。所有对 QAnything 的调用都经过后端封装和安全管理。
2.  **前端交互**：开发了独立的聊天界面组件 (`src/app/chat/page.tsx` 和 `src/components/chat/chat-interface.tsx`)，实现了用户输入、问题发送、回答展示以及加载/错误状态处理等功能。支持文本输入和基于 QAnything 返回结果的展示。
3.  **安全性**：QAnything 的 API Key 作为环境变量在服务器端进行管理和使用，确保敏感信息不会泄露到客户端。

**QAnything 运行截图**：

![image-20250630231704981](/Users/night/Documents/Codes/SaltyFish/250530-qanything-all/250530-qanything-1/assets/image-20250630231704981.png)

![image-20250630231712472](/Users/night/Documents/Codes/SaltyFish/250530-qanything-all/250530-qanything-1/assets/image-20250630231712472.png)

![image-20250630231719848](/Users/night/Documents/Codes/SaltyFish/250530-qanything-all/250530-qanything-1/assets/image-20250630231719848.png)

![image-20250630231728780](/Users/night/Documents/Codes/SaltyFish/250530-qanything-all/250530-qanything-1/assets/image-20250630231728780.png)

![image-20250630231740027](/Users/night/Documents/Codes/SaltyFish/250530-qanything-all/250530-qanything-1/assets/image-20250630231740027.png)

![image-20250630231613627](/Users/night/Documents/Codes/SaltyFish/250530-qanything-all/250530-qanything-1/assets/image-20250630231613627.png)

## WakaTime API 集成与展示

项目集成了 WakaTime API 以获取个人编码时长数据，并在应用的页脚全局展示。这不仅展示了 API 集成的能力，也为用户提供了一个直观的个人开发数据概览。

### 实现细节：

1.  **API Key 管理**：WakaTime API Key 同样作为环境变量 (`WAKATIME_API_KEY`) 进行管理，通过 Next.js 的 API Routes (`/api/wakatime/stats/[range]/route.ts` 和 `/api/wakatime/user/route.ts`) 在服务器端安全地调用 WakaTime API。
2.  **数据获取与展示**：前端组件 (`src/components/wakatime-stats.tsx`) 调用后端 API Routes 获取编码时长数据，并在应用的全局页脚 (`src/app/layout.tsx` 或类似全局布局文件) 中清晰、准确、格式良好地展示累计编码时长。

**WakaTime API 集成与展示截图**：

![image-20250630231627941](/Users/night/Documents/Codes/SaltyFish/250530-qanything-all/250530-qanything-1/assets/image-20250630231627941.png)

## Next.js 项目结构

本项目基于 `create-next-app` 初始化，遵循 Next.js 推荐的项目结构，并对课程练习进行了合理的组织和整合。

```
250530-qanything-1/
├── docs/
├── public/
├── src/
│   ├── app/                # 应用程序路由和布局
│   │   ├── agents/         # Agent 相关页面
│   │   ├── api/            # API Routes，包括 QAnything 和 WakaTime 代理
│   │   │   ├── wakatime/
│   │   │   └── ...
│   │   ├── chat/           # 聊天问答页面
│   │   ├── homework/       # 整合的课程练习页面
│   │   ├── favicon.ico
│   │   ├── globals.css
│   │   ├── layout.tsx      # 全局布局
│   │   └── page.tsx        # 首页
│   ├── components/         # 可复用 UI 组件
│   │   ├── agent/
│   │   ├── chat/
│   │   ├── knowledge-base/
│   │   ├── navigation.tsx
│   │   ├── ui/
│   │   └── wakatime-stats.tsx
│   ├── hooks/              # 自定义 React Hooks
│   ├── lib/                # 工具函数和客户端库
│   ├── services/           # 服务层逻辑
│   └── types/              # TypeScript 类型定义
├── next.config.ts
├── package.json
├── postcss.config.mjs
├── README.md
├── tsconfig.json
└── ...
```

-   **`src/app/`**: 包含所有路由页面 (`page.tsx`) 和共享布局 (`layout.tsx`)。每个课程练习和主要功能都有独立的路由。
-   **`src/api/`**: Next.js API Routes，用于后端逻辑，如 QAnything 和 WakaTime API 的代理。
-   **`src/components/`**: 存放可复用的 React 组件，按照功能模块（如 `chat`、`agent`、`knowledge-base`）进行组织。
-   **`src/hooks/`**: 包含自定义 React Hooks，用于封装可复用的状态逻辑。
-   **`src/lib/`**: 存放通用的工具函数和客户端服务，例如 API 客户端。
-   **`src/services/`**: 包含业务逻辑服务层。

## 旧作业整合方式

本学期所有课程练习都已整合到此 Next.js 应用中，每个练习都有独立的路由。例如，`src/app/homework/page.tsx` 可以作为所有练习的导航页，点击后可跳转到具体的练习页面。每个练习都被视为一个独立的组件或一组组件，以实现组件化开发的思想。

**Next.js 组织课程练习作业的运行截图**：

![image-20250630231645215](/Users/night/Documents/Codes/SaltyFish/250530-qanything-all/250530-qanything-1/assets/image-20250630231645215.png)



## 项目运行指南

请按照以下步骤在本地运行本项目：

### 1. 克隆仓库

```bash
git clone <您的GitHub仓库地址>
cd 250530-qanything-1
```

### 2. 安装依赖

本项目使用 `uv` 进行包管理。请确保您已安装 `uv`。

```bash
uv install
```

### 3. 配置环境变量

在项目根目录创建 `.env.local` 文件，并配置 QAnything 和 WakaTime 的 API Key：

```env
# QAnything API 配置 (根据您的实际 QAnything 服务地址填写)
QANYTHING_API_BASE_URL=http://your_qanything_host:port
QANYTHING_API_KEY=your_qanything_api_key

# WakaTime API 配置
WAKATIME_API_KEY=your_wakatime_api_key
```

### 4. 运行开发服务器

```bash
uv run npm run dev
```

项目将在 `http://localhost:3000` 启动。

### 5. 构建生产版本 (可选)

```bash
uv run npm run build
uv run npm run start
```

### 6. 访问应用

在浏览器中打开 `http://localhost:3000` 即可访问应用程序。

## GitHub 仓库管理

所有代码和文档都通过 Git 进行版本控制，并托管在公开的 GitHub 仓库中。项目保持良好的 Commit 习惯，每次提交都有清晰、有意义的提交信息，以便于版本追踪和代码审计。

## 评分标准对应

-   **LLM 问答服务集成 (QAnything - 路径二)**：本项目严格按照路径二要求，自行开发 API 接口，确保 API Key 安全管理，并实现完整的前端交互功能。
-   **WakaTime API 集成与展示**：成功调用 WakaTime API，安全管理 API Key，并在页面中清晰展示编码时长。
-   **Next.js 应用与课程练习整合**：项目结构规范，课程练习成功整合到 Next.js 应用中，并合理设计了路由。体现了组件化开发思想。
-   **README.md 文档质量**：本文档详尽说明了项目各方面信息，并提供了运行指南。
-   **代码质量与 GitHub 规范**：代码风格一致，可读性强，有基本的错误处理。所有代码托管在 GitHub，具备清晰的 Commit 记录。
