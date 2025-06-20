# 1. another-mentor

## 1.1. 介绍

another-mentor 是一个个人学习、工作计划智能导师系统，旨在通过分析用户的 Markdown 笔记（作为个人知识的载体），构建一个可查询、可关联的个人知识图谱，并基于用户设定的目标智能生成学习或工作计划及个人发展路线。它利用先进的自然语言处理技术自动抽取关键信息，识别知识点之间的关系，并结合用户的职业目标和个人兴趣推荐个性化的学习资源和建议。

通过 another-mentor，你可以：

- 将分散的 Markdown 笔记整合成个人知识库。
- 自动分析笔记内容，提取关键概念和关系。
- 设定个人学习和发展目标。
- 获取基于你的知识状态和目标的智能学习计划。
- 将计划同步到飞书等工具，获得及时提醒。

## 1.2. 模块划分

### 1.2.1. 用户管理模块

负责用户的注册、登录、权限控制等功能。提供安全的身份验证机制，保护用户数据隐私。

- [ ] 用户账户管理
  - [ ] 用户注册、登录、登出

### 1.2.2. 数据存储模块 NoteVault

支持上传、编辑、删除 Markdown 笔记，以及图文、视频文件的存储。

- [ ] 文件存储
  - [x] 支持多种文件类型（Markdown、图片、视频等）的上传与存储
  - [ ] 文件分块上传与断点续传
  - [x] 文件元数据（如标签、描述、作者、上传时间等）管理
  - [ ] 存储安全与访问权限控制
- [ ] 文件 CRUD 接口
  - [ ] 提供文件的创建、读取、更新、删除（CRUD）RESTful API
  - [x] 支持批量操作与分页查询
  - [x] 文件检索与筛选（按类型、标签、时间等）
- [ ] 文件版本控制
  - [ ] 支持文件的多版本管理与历史记录
  - [ ] 版本回滚与差异对比
  - [ ] 版本元数据管理（如修改人、修改时间、变更说明）
  - [ ] 版本冲突检测与合并策略

### 1.2.3. 笔记分析模块

对笔记内容进行结构化和非结构化分析，包括但不限于关键词提取、主题分类等。

- [ ] 笔记内容解析
  - [ ] Markdown 语法解析与结构化
  - [ ] 支持多语言内容解析
- [ ] 关键词和主题提取
  - [ ] 关键词自动提取与权重排序
  - [ ] 主题分类与标签生成
  - [ ] 实体识别（如人名、地名、专业术语等）
- [ ] 文件属性分析
  - [ ] 统计字数、段落、图片、代码块等属性
  - [ ] 识别笔记中的引用、链接、附件等

### 1.2.4. 知识图谱构建模块

基于笔记分析结果，自动建立知识点之间的关联，形成个人知识图谱，支持高效的知识检索和发现。

- [ ] 知识点识别与链接
  - [ ] 从笔记中抽取知识点、概念、实体
  - [ ] 自动建立知识点之间的关系（如上下位、引用、相关性）
- [ ] 知识网络可视化
  - [ ] 图谱结构可视化展示
  - [ ] 支持节点、关系的交互式操作
- [ ] 高效的知识检索引擎
  - [ ] 支持按关键词、主题、关系等多维度检索
  - [ ] 支持模糊查询与智能推荐

### 1.2.5. 学习/工作计划生成模块

根据用户设定的职业目标和个人兴趣，结合知识图谱中的信息，智能生成个性化的学习或工作计划，帮助用户更好地规划个人发展路径。

- [ ] 目标设定与跟踪
  - [ ] 支持用户自定义学习/工作目标
  - [ ] 目标分解为可执行任务
  - [ ] 目标进度实时跟踪与展示
- [ ] 个性化学习/工作计划生成
  - [ ] 基于知识图谱和用户目标自动生成计划
  - [ ] 支持计划的动态调整与优化
  - [ ] 计划优先级与依赖关系管理
- [ ] 进度监控与反馈
  - [ ] 任务完成情况统计与可视化
  - [ ] 自动提醒与反馈建议

### 1.2.6. 外部接口通信模块

联动飞书、日历等办公软件，为用户提供任务提醒、日程安排等通知功能，确保重要事项不被遗漏。

- [ ] 飞书 API 集成
  - [ ] 任务、日程同步到飞书
  - [ ] 支持消息推送与互动
- [ ] 日历同步与管理
  - [ ] 与主流日历（Google、Outlook、本地等）双向同步
  - [ ] 日程冲突检测与提醒
- [ ] 提醒与通知服务
  - [ ] 多渠道提醒（App、邮件、短信、推送等）
  - [ ] 支持自定义提醒规则
- [ ] 邮件通知系统
  - [ ] 自动发送计划、进度等邮件
  - [ ] 邮件模板与多语言支持

### 1.2.7. 网关模块

统一对外暴露 API 网关，提供远程操作接口。此模块负责请求的路由、组合和协议转换，使得内部服务可以更灵活地扩展和维护。

- [ ] RESTful API 请求路由
  - [ ] 统一入口，路由转发到各业务模块
  - [ ] 支持 API 版本管理
- [ ] gRPC 请求路由
  - [ ] 支持高性能服务间通信
  - [ ] gRPC 服务注册与发现
- [ ] MCP 服务
  - [ ] 支持多协议转换与适配
  - [ ] 服务编排与聚合
- [ ] 请求认证与授权
  - [ ] 支持 JWT/OAuth2 等认证方式
  - [ ] 细粒度权限控制
- [ ] 协议转换与数据适配
  - [ ] REST/gRPC/GraphQL 等协议互转
  - [ ] 数据格式适配与校验

### 1.2.8. 推荐系统模块

根据用户的学习计划从网络中搜索相关的个人博客、视频等内容，为用户提供更加全面和个性化的学习体验。

- [ ] 内容检索与过滤
  - [ ] 网络内容聚合与筛选
  - [ ] 支持多源内容（博客、视频、文档等）
  - [ ] 内容质量与相关性评估
- [ ] 个性化推荐算法
  - [ ] 基于用户兴趣、知识图谱、历史行为的推荐
- [ ] 用户偏好与学习计划分析
  - [ ] 用户兴趣建模与动态调整
  - [ ] 推荐结果与学习计划联动

### 1.2.9. 客户端

- [ ] 命令行工具
  - [ ] 支持常用操作的 CLI 工具
  - [ ] 脚本化与自动化支持
- [ ] Web 管理界面
  - [ ] 丰富的交互式管理界面
  - [ ] 支持知识图谱、计划、笔记等可视化
- [ ] flutter 跨平台应用
  - [ ] 支持 iOS、Android、桌面端
- [ ] VSCode 插件
  - [ ] 集成笔记编辑、知识检索等功能
  - [ ] 支持与本地/云端数据同步
- [ ] QT 客户端
  - [ ] 跨平台桌面应用

### 1.2.10. 监控

- [ ] 服务网格
  - [ ] 服务间流量管理与安全策略
  - [ ] 支持灰度发布、熔断、限流等
- [ ] 监控大屏
  - [ ] 实时监控各模块运行状态
  - [ ] 性能指标、告警、日志可视化

## 1.3. 项目架构
