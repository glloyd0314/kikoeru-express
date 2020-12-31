# Kikoeru
一个同人音声专用的音乐流媒体服务器，详细的使用说明见[**用户文档**](./%E7%94%A8%E6%88%B7%E6%96%87%E6%A1%A3.md)

![截图.png](https://i.loli.net/2020/04/22/hjXW4PdsaoIt97U.png)

### 功能介绍
- 从 DLSite 爬取音声元数据
- 通过标签或关键字快速检索想要找到的音声
- 根据音声元数据对检索结果进行排序
- 可以选择通过 JWT 验证用户或关闭用户认证功能
- 支持在 Web 端修改配置文件和扫描音声库
- 支持为音声库添加多个根文件夹

### 安装部署
```bash
# 安装依赖
npm install

# 启动服务器
npm start

# Express listening on http://localhost:8888
```
本项目还有打包好的 **Windows 系统下可用的 exe 可执行文件**与 **docker 镜像**版本，docker 镜像的使用说明详见[**用户文档**](https://github.com/Watanuki-Kimihiro/kikoeru-express/blob/master/%E7%94%A8%E6%88%B7%E6%96%87%E6%A1%A3.md)

### 技术栈
- axios (网络请求)
- express (构建后端服务)
- sqlite3 (文件型数据库)
- knexjs (操作数据库)
- cheerio (将 html 解析为 jQuery 对象)
- jsonwebtoken (用户认证)
- socket.io (用于将扫描音声库的结果实时传给客户端)
- child_process (nodejs 子进程)
- pkg (打包为可执行文件)


### 项目目录结构
```
├── auth/                    # 用户认证相关路由
├── config/                  # 存放配置文件
├── covers/                  # 存放音声封面
├── database/                # 操作数据库相关代码
├── dist/                    # 存放前端项目 kikoeru-quasar 构建的 SPA
├── filesystem/              # 存放扫描相关代码
├── package/                 # 存放 pkg 打包后的可执行文件
├── scraper/                 # 存放爬虫相关代码
├── sqlite/                  # 存放 sqlite 数据库文件
├── static/                  # 存放静态资源
├── .gitignore               # git 忽略路径
├── api.js                   # 为 express 实例添加路由与 jwt 验证中间件
├── app.js                   # 项目入口文件
├── config.js                # 用于生成与修改 config.json 配置文件
├── Dockerfile               # 用于构建 docker 镜像的文本文件
├── package.json             # npm 脚本和依赖项
└── routes.js                # 主要路由
```


### TODO
- [ ] 添加计划任务，定期更新音声的动态元数据
- [ ] 允许用户手动修改音声元数据
- [ ] 手动添加抓不到元数据的音声
- [ ] 爬取音声的简介信息
- [ ] 添加收藏功能
- [ ] 添加保存歌单功能

### 感谢
本项目的大部分后端代码来自于开源项目 [kikoeru](https://github.com/nortonandrews/kikoeru)
