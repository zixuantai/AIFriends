<p align="center">
  <!-- 建议尺寸: 1280x640px。可以使用 Canva, Figma 或 https://banners.beyondco.de/ 等工具制作 -->
  <img src="https://avatars.githubusercontent.com/u/256310449?v=4" alt="AIFriends" width="80px">
</p>

<div align="center">

# AIFriends

**一 个 虚 拟 朋 友 创 作 分 享 平 台**  
*created by Zixuan Tai*

### 项目地址：https://app7682.acapp.acwing.com.cn/
</div>



## 🖼️ 概览
**AIFriends**是一个虚拟朋友创作分享平台。支持用户创建并分享任意多个虚拟朋友，可以自定义角色音色、性格、简介；支持语音识别、语音合成、语音复刻，可以跟虚拟人物进行语音通话。

## 📚 核心功能
### 1. 用户系统
- 注册登录 : 完整的用户注册和登录功能
- 个人资料 : 用户可以修改个人信息和头像
- JWT认证 : 安全的身份验证机制
### 2. AI角色管理
- 创建角色 : 用户可以创建具有自定义名称、头像和背景的AI角色
- 角色列表 : 查看和管理已创建的AI角色
- 角色编辑 : 修改角色信息和属性
### 3. 对话功能
- 实时对话 : 与AI角色进行实时流式对话
- 语音输入 : 支持语音转文本功能
- 消息历史 : 查看和管理对话历史
### 4. 知识库集成
- 向量存储 : 使用LanceDB存储知识嵌入
- 知识检索 : 基于相似度搜索的知识查询
- 上下文理解 : AI可以结合知识库内容进行回答

## 📦 技术栈
### 前端
- Vue 3 + Composition API : 现代化前端框架，提供响应式界面
- Vite : 快速的前端构建工具
- Tailwind CSS : 实用优先的CSS框架
- Vue Router : 前端路由管理
- Pinia : 状态管理库
- @ricky0123/vad-web : 语音活动检测
- SSE客户端 : 处理流式响应
### 后端
- Django 6.0 : Python Web框架
- Django REST Framework : 构建RESTful API
- JWT认证 : 用户身份验证
- SSE (Server-Sent Events) : 实现流式输出
- LangChain : 大语言模型应用框架
- LangGraph : 构建复杂AI工作流
- DeepSeek API : 大语言模型服务
- LanceDB : 向量数据库
- SQLite : 关系型数据库
- 阿里云语音识别 : 语音转文本服务

## 📁 项目结构

```
AIFriends/
├── backend/              # 后端代码
│   ├── backend/          # Django 项目配置
│   │   ├── __init__.py
│   │   ├── asgi.py
│   │   ├── settings.py   # 项目配置文件
│   │   ├── urls.py       # 主URL配置
│   │   └── wsgi.py
│   ├── web/              # 应用代码
│   │   ├── documents/    # 文档处理和知识库
│   │   │   ├── utils/    # 文档处理工具
│   │   │   └── __init__.py
│   │   ├── migrations/   # 数据库迁移文件
│   │   ├── models/       # 数据模型
│   │   │   ├── __init__.py
│   │   │   ├── character.py  # 角色模型
│   │   │   ├── friend.py     # 好友关系模型
│   │   │   └── user.py       # 用户模型
│   │   ├── templates/    # HTML模板
│   │   ├── views/        # 视图函数
│   │   │   ├── create/   # 创建相关视图
│   │   │   ├── friend/   # 好友相关视图
│   │   │   │   ├── message/  # 消息相关视图
│   │   │   │   │   ├── asr/   # 语音识别
│   │   │   │   │   ├── chat/  # 聊天功能
│   │   │   │   │   ├── memory/ # 记忆功能
│   │   │   ├── homepage/ # 首页视图
│   │   │   ├── user/     # 用户相关视图
│   │   │   └── utils/    # 工具函数
│   │   ├── __init__.py
│   │   ├── admin.py
│   │   ├── apps.py
│   │   ├── tests.py
│   │   └── urls.py       # 应用URL配置
│   ├── manage.py         # Django 管理命令
│   └── requirements.txt  # 后端依赖
├── frontend/             # 前端代码
│   ├── public/           # 静态资源
│   │   └── favicon.ico
│   ├── src/              # 源代码
│   │   ├── assets/       # 静态资源
│   │   ├── components/   # 组件
│   │   │   ├── character/ # 角色相关组件
│   │   │   │   ├── chat_field/ # 聊天字段
│   │   │   │   ├── icons/      # 图标
│   │   │   └── Character.vue   # 角色组件
│   │   ├── js/           # JavaScript 工具
│   │   │   ├── config/   # 配置文件
│   │   │   ├── http/     # HTTP 请求
│   │   │   └── utils/    # 工具函数
│   │   ├── router/       # 路由配置
│   │   ├── stores/       # 状态管理
│   │   ├── views/        # 页面
│   │   │   ├── create/   # 创建页面
│   │   │   ├── error/    # 错误页面
│   │   │   ├── friend/   # 好友页面
│   │   │   ├── homepage/ # 首页
│   │   │   └── user/     # 用户页面
│   │   ├── App.vue       # 根组件
│   │   └── main.js       # 入口文件
│   ├── .gitignore
│   ├── README.md
│   ├── index.html        # HTML 模板
│   ├── jsconfig.json
│   ├── package-lock.json
│   ├── package.json      # 前端依赖
│   └── vite.config.js    # Vite 配置
├── .gitignore
└── README.md             # 项目说明
```

## 🚀 快速开始
### 前置条件
- Python 3.8 或更高版本
- Node.js 16 或更高版本
- npm 7 或更高版本
- DeepSeek API 密钥
### 安装步骤
1. 克隆项目
   ```
   git clone <repository-url>
   cd AIFriends
   ```
2. 后端安装
   ```
   cd backend
   pip install -r requirements.txt
   python manage.py migrate
   ```
3. 配置环境变量 创建 backend/.env 文件并添加以下内容：
   ```
   API_KEY=your_deepseek_api_key
   API_BASE=https://api.deepseek.com/v1
   ```
4. 启动后端服务
   ```
   python manage.py runserver
   ```
5. 前端安装
   ```
   cd ../frontend
   npm install
   ```
6. 启动前端服务
   
   ```
   npm run dev
   ```
### 访问地址
- 前端: http://localhost:5173
- 后端API: http://127.0.0.1:8000

## ⚙️ 配置说明

### 后端配置

主要配置文件：`backend/backend/settings.py`

- **静态文件配置**：
  - `STATIC_URL = 'static/'`
  - `STATIC_ROOT = BASE_DIR / 'staticfiles'`（生产环境 collectstatic 目标）
  - `STATICFILES_DIRS = [BASE_DIR / 'static']`（开发时前端构建产物在 static/frontend）

- **跨域配置**：
  - `CORS_ALLOWED_ORIGINS`：允许的前端域名
  - 默认允许 `http://localhost:5173`（Vite 开发服务器）

- **JWT 配置**：
  - Access Token 有效期：2 小时
  - Refresh Token 有效期：7 天

### 前端配置

主要配置文件：`frontend/vite.config.js`

- 开发服务器端口：5173
- 构建输出目录：`../backend/static/frontend`（与 Django 静态目录一致）
- `npm run build` 后会自动执行 `scripts/update-django-static.js`，同步 Django 模板中的 js/css 路径

## 📚 相关资源

- [Django 官方文档](https://docs.djangoproject.com/)
- [Vue3 官方文档](https://cn.vuejs.org/)
- [LangChain 文档](https://python.langchain.com/)
- [Django REST Framework 文档](https://www.django-rest-framework.org/)

## 📄 许可证

本项目仅供学习交流使用。

## 🧭 道
- 用户至上 : 所有功能设计以用户体验为中心
- 实时响应 : 对话应该像与人交流一样自然流畅
- 个性化交互 : 每个AI角色都有独特的个性和背景
- 数据安全 : 保护用户隐私和数据安全
- 持续优化 : 不断改进AI模型和系统性能
- 技术选型 : 选择成熟、稳定的技术栈
- 架构设计 : 清晰的分层架构，便于维护和扩展

## 🧩 法
- 一句话目标 : 创建一个用户友好的AI对话系统，支持个性化角色和实时交互
- 非目标 : 不追求过度复杂的功能，保持系统简洁高效
- 模块化开发 : 按职责拆分为前端、后端、AI引擎等模块
- 接口先行 : 先定义好模块间的接口，再实现具体功能
- 代码复用 : 能使用现有库的就不重复造轮子

## 🔮 未来规划
- 多语言支持 : 扩展到更多语言，支持跨语言对话
- 模型扩展 : 集成更多大语言模型，提供更多选择
- 高级个性化 : 更精细的角色定制，包括性格、语气等
- 情感分析 : 理解用户情绪并做出相应的情感回应
- 多模态交互 : 支持图像、视频等多种输入形式
- 移动端适配 : 优化移动端用户体验，提供APP版本

## 🤝 贡献指南
我们欢迎社区贡献，包括但不限于：
- 提交Bug报告和功能建议
- 改进代码和文档
- 开发新功能和集成新模型

请通过GitHub的Issue和Pull Request参与贡献。

## 📞 联系我们
如有任何问题或建议，请通过以下方式联系我们：
- QQ: 2227530410
- Email: zixuantai@163.com

**享受与AI朋友的对话吧！** 🤖💬