# 🎬 Hollywood cut (Film Fusion)

**Film Fusion** 是一款基于 Gemini AI 的电影感静态剧照生成工具。它能够将您上传的人物照片与经典电影场景深度融合，生成具有专业电影质感的幕后照或剧照。

![Demo Simulation](logo.jpg)

## ✨ 精选特性

- **克莱因蓝 + 爵士西部风格**: 采用极具视觉冲击力的设计语言，带给您沉浸式的电影片场体验。
- **经典电影融合**: 支持自定义电影名称，智能重构光影与构图。
- **胶片质感**: 模拟柯达 Vision3 500T 胶片效果。
- **安全保障**: 采用 Serverless Proxy 技术，API Key 存储在服务器环境变量中，不会泄露到前端代码。

## 🚀 快速开始

### 1. 本地运行 (开发环境)

1. 克隆本项目。
2. 复制 `.env.example` 并重命名为 `.env`。
3. 在 `.env` 中填入您的 `GEMINI_API_KEY` (可以在 [Google AI Studio](https://aistudio.google.com/) 免费获取)。
4. 使用 Vercel CLI 运行 (推荐):
   ```bash
   npx vercel dev
   ```
5. 打开浏览器访问 `http://localhost:3000`。

### 2. 部署到生产环境 (Vercel)

本项目已设计好适用于 Vercel 的部署工作流：

1. **推送代码到 GitHub**:
   您可以将代码提交到名为 `hollywood-cut` 的新仓库。
2. **连接 Vercel**:
   在 Vercel 控制台导入该 GitHub 仓库。
3. **配置环境变量**:
   在 Vercel 项目设置中，添加 `Environment Variable`:
   - `GEMINI_API_KEY`: 您的 Gemini API Key。
4. **Action!**:
   Vercel 会自动部署，并为您分配一个二级域名。

## 🛠 技术方案与安全建议

- **前端**: Vanilla JS + React (via CDN) + Tailwind CSS + Framer Motion。
- **后端**: Vercel Serverless Functions (`api/generate.js`)。
- **安全检查**:
  - [x] 所有 API 调用已重构为通过后端 Proxy 转发。
  - [x] 代码库中没有任何硬编码的 API Key 或个人敏感信息。
  - [x] `.env` 文件已包含在 `.gitignore` 中，防止意外提交。

## 📅 工作流设计 (CI/CD)

我们推荐使用 Github Actions 进行自动化检查：

- **自动 lint**: 提交代码时自动运行。
- **自动部署**: 推送到 `main` 分支时自动同步到生产环境。

---
Enjoy your cinematic creation! 🍿
