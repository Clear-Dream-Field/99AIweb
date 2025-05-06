# AI Web 4.2.0 稳定版

可商业化 AI Web 应用（免授权，无后门，非盗版，完整安装包安装即用，支持 Docker 快速部署）。


## 页面预览
![QQ20250506-201027](https://github.com/user-attachments/assets/8e2b99aa-c6bf-46a7-b7e2-069db3086883)

**应用广场**
![QQ20250506-200605](https://github.com/user-attachments/assets/429a578c-cb4f-41e0-8ae7-8c7ae91acf06)

**AI绘画、AI音乐、AI视频等多应用插件**
![QQ20250506-200620](https://github.com/user-attachments/assets/5c22435b-b223-494d-91ad-f8e42138c727)
![QQ20250506-200828](https://github.com/user-attachments/assets/af886858-18e4-4cab-979b-a32872e4073b)

**用户签到**
![QQ20250506-200848](https://github.com/user-attachments/assets/a8756402-dfd0-4e15-9015-199835a5677b)

**用户中心**
![QQ20250506-200905](https://github.com/user-attachments/assets/721a1dfb-5660-43ed-91a4-308680c8dea6)

**密码重置**
![QQ20250506-200917](https://github.com/user-attachments/assets/59a34c0f-e79f-48d6-8bd7-a6b4f5251f3e)

**内容显示**


## 更新日志

## 稳定版 v4.2.0

### 更新内容 v4.2.0
- 全新UI界面更简洁，前端重构。
- 前端适配 `<think></think>` 标签格式的深度思考显示
- 剔除使用外部联网插件，改用 API 方式调用联网搜索
- 联网插件已支持多种方式（需自行登录以下网站，获取对应的 Key）：
  - [智谱 web-search-pro](https://bigmodel.cn)
  - [博查 web-search](https://open.bochaai.com)
  - [Tavily](https://app.tavily.com/home)

### 注意事项 v4.2.0

- 升级前请做好数据库备份，本次升级项目结构有所调整，使用本地存储的文件，需自行迁移
- 本次升级内容较少，思考推理模型搭配其他模型混合调用、联网搜索详情显示、UI 优化等升级



## 安装部署

推荐使用 Docker 环境来编译和部署镜像，或者直接在 Node.js 环境中进行安装。虽然安装文档可能不是非常详细，但绝对够用。如果在安装或配置过程中遇到任何问题，优先使用 AI助手  货交流群内提出问题，以获得更多帮助和支持。

## Docker 部署 （推荐）

1. **安装 Docker 及 Docker-compose**

   - 使用[Docker 官网](https://www.docker.com/)提供的一键安装链接安装Docker及Docker-compose。 
   
     ```shell
     curl -fsSL https://get.docker.com | bash -s docker
     ```
    
2. **服务管理**

   - 后台启动服务

     ```bash
     docker-compose up -d
     ```

   - 查看日志

     ```bash
     docker-compose logs
     ```
     
   - 停止服务

     ```bash
     docker-compose down
     ```
   - 重新构建并启动服务

     ```bash
     docker-compose up -d --build
     ```

3. **访问项目**
   - 在浏览器中访问 `http://localhost:9520`，如果配置了 nginx 反向代理，则通过配置的域名访问。

## Node.js + PM2 部署

### 环境准备

1. **安装 Node.js 环境**

   推荐使用 `nvm` (Node Version Manager) 来安装 Node.js。

   - 首先，安装 `nvm`，你可以从 `nvm` 的 GitHub 仓库找到安装指南:
     [nvm GitHub 仓库](https://github.com/nvm-sh/nvm)

   - 按照仓库中的安装说明进行操作，安装完成后，重启你的终端或命令行界面。

   - 安装 Node.js 版本 20.0 或更高版本:

     ```bash
     nvm install 20
     nvm use 20
     ```

   - 验证 Node.js 安装成功及版本:

     ```bash
     node -v
     ```

   使用这种方法安装 Node.js，可以确保你的开发环境中 Node.js 的版本管理更为灵活和方便。

2. **安装 PM2 / PNPM**

   - 使用 npm 安装 PM2：

     ```bash
     npm install pm2 -g
     ```

   - 使用 npm 安装 pnpm：

     ```bash
     npm install -g pnpm
     ```

   - 确认`PM2`, 和 `pnpm` 都已正确安装并且可以运行：

     ```bash
  
     pm2 -v
     pnpm -v
     ```

   - 这一步确保所有必需的工具和软件已正确安装，并且它们的版本符合项目需求。

### 配置项目

1. **配置环境变量**

   - 复制`.env.example`文件为`.env`。
   - 根据需要修改`.env`文件中的配置项。

2. **安装项目依赖**
   - 运行命令：`pnpm install`(若安装缓慢可尝试使用国内源)。
   - 这将根据`package.json`文件安装所有必需的依赖。

### 启动项目

1. **启动服务**

   - 使用命令：`pnpm start`
   - 这将启动项目，并默认在 9520 端口监听。

2. **访问项目**
   - 在浏览器中访问 `http://localhost:9520`，如果配置了 nginx 反向代理，则通过配置的域名访问。

### 项目升级

1. **拉取更新**

   - 拉取新的整合包。

2. **删除旧进程**

   - 删除旧的 PM2 进程。

3. **安装依赖**

   - 运行命令：`pnpm install` 以安装 `package.json` 中定义的必需依赖。

4. **启动服务**

   - 使用命令：`pnpm start` 来启动项目，它将默认在 9520 端口监听。

## 管理平台

- **管理端地址**：`/admin`

- **普通管理员账号**：`admin` 

- **超级管理员账号**：`super`

- **密码**：`123456`

普通管理员，可以预览后台非敏感信息，默认不激活。请使用超级管理员账号登入后台，并及时修改密码。


