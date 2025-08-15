# Shuidao Blog System - PHP+MySQL 前后端不分离解决方案

## 系统概述
这是一个基于PHP+MySQL的前后端不分离博客系统，包含用户系统、内容管理、内容展示和后台管理等完整功能。系统采用MVC架构设计，确保代码结构清晰、易于维护和扩展。

## 技术栈
- **后端**: PHP 7.4+
- **数据库**: MySQL 8.0+
- **前端**: HTML5, CSS3, JavaScript, Bootstrap 5, Font Awesome
- **认证**: JWT (JSON Web Token)
- **编辑器**: Markdown支持

## 核心功能
### 用户系统
- 注册/登录（JWT认证）
- 用户角色（读者/作者/管理员）
- 个人资料管理（头像、昵称、简介等）
- 密码修改

### 内容管理
- 文章发布/编辑/删除（Markdown编辑器支持）
- 文章分类与标签管理
- 评论与回复功能
- 文章封面上传

### 内容展示
- 文章列表（分页+过滤）
- 文章详情页（包含点赞/收藏）
- 热门文章/最新文章推荐
- 分类与标签导航

### 后台管理
- 仪表盘数据统计（用户、文章、评论等）
- 用户管理（权限控制）
- 内容审核与分类管理
- 系统设置

## 项目结构
```
blog-system/
├── config/              # 配置文件
├── controllers/         # 控制器
├── database/            # 数据库相关
├── lib/                 # 核心类库
├── middlewares/         # 中间件
├── models/              # 数据模型
├── public/              # 公共资源
│   ├── css/             # CSS样式
│   ├── js/              # JavaScript
│   └── uploads/         # 上传文件
├── routes/              # 路由
├── utils/               # 工具函数
├── views/               # 视图文件
│   ├── admin/           # 后台视图
│   ├── article/         # 文章相关视图
│   ├── layout/          # 布局文件
│   └── user/            # 用户相关视图
├── .htaccess            # Apache配置
├── index.php            # 应用入口
└── README.md            # 项目说明
```

## 安装指南
### 环境要求
- PHP 7.4+（推荐PHP 8.0+）
- MySQL 8.0+
- Apache或Nginx服务器
- 启用PHP扩展：pdo_mysql, json, mbstring, openssl, fileinfo

### 安装步骤
1. **克隆项目**
   ```bash
   git clone https://github.com/shuidaobenzun/sdblog.git
   ```

2. **创建数据库**
   - 登录MySQL：`mysql -u root -p`
   - 创建数据库：`CREATE DATABASE blog_system;`
   - 导入初始化脚本：`USE blog_system; SOURCE database/init.sql;`

3. **配置环境**
   - 复制`config/config.php.example`为`config/config.php`
   - 修改数据库连接信息和其他配置项

4. **设置权限**
   - 确保`uploads/`目录可写
   - 确保`public/`目录可访问

5. **配置Web服务器**
   - Apache：启用`mod_rewrite`模块，使用`.htaccess`文件
   - Nginx：配置伪静态规则

6. **访问系统**
   - 前台地址：`http://yourdomain.com/`
   - 后台地址：`http://yourdomain.com/admin`
   - 默认管理员账号：`admin@example.com`，密码：`admin123`（请登录后修改密码）

## 使用说明
### 用户指南
1. **注册/登录**：访问首页点击右上角的注册/登录按钮
2. **发布文章**：登录后点击导航栏的"写文章"按钮
3. **个人中心**：点击右上角头像下拉菜单中的"个人资料"
4. **收藏文章**：在文章详情页点击"收藏"按钮

### 管理员指南
1. **后台管理**：登录后点击右上角头像下拉菜单中的"后台管理"
2. **文章管理**：在后台导航栏选择"文章管理"
3. **用户管理**：在后台导航栏选择"用户管理"
4. **分类管理**：在后台导航栏选择"分类管理"
5. **系统设置**：在后台导航栏选择"系统设置"

## 安全建议
1. 定期备份数据库
2. 不要使用默认管理员账号和密码
3. 限制后台管理地址的访问权限
4. 定期更新系统和依赖库
5. 启用HTTPS

## 扩展建议
1. 添加文章定时发布功能
2. 实现文章全文搜索
3. 集成第三方社交登录
4. 添加文章订阅功能
5. 实现多主题切换

## 常见问题
1. **无法上传图片**：检查`uploads/`目录权限是否正确
2. **登录失败**：检查数据库连接是否正确，用户名密码是否匹配
3. **文章无法显示**：检查文章状态是否为"已发布"
4. **后台无法访问**：检查是否具有管理员权限

## 联系方式
如有问题或建议，请联系：[525637945@qq.com](mailto:525637945@qq.com)

© 2025 Shuidao Blog System. All rights reserved.
