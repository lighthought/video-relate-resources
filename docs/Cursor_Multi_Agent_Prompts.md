## Cursor 多 Agent 产品开发提示词

### No.1 PM 创建 PRD
```
@bmad/pm.mdc 请你基于 @ReadMe.md 创建一个 PRD
```


### No.2 UX-expert 创建 UX 规范
```
@bmad/ux-expert.mdc 帮我基于这个 @PRDXXXX.md 和 参考的Figma设计，输出前端的 UX Spec 和关键页面的提示词
@figmaxxx/design/xxx
```


### No.3 架构师技术选型
```
@bmad/architect.mdc 请你基于最新的 @PRDxxx.md 和 UX 专家输出到 @design/ 目录下的设计文档，思考下整个项目的技术选型，先不要做架构设计和代码层面的思考。只做技术选型。
```

### No.4 架构师设计架构
```
@bmad/architect.mdc 帮我把整体架构设计, 前端架构设计, 后端架构设计, 数据模型设计(可以用 sql 脚本代替)，API 设计文档，都输出到 @architect/ 目录下。注意，不要输出实际的代码尤其是函数实现，设计阶段没有必要。
```

### No.5 po输出用户故事
```
@bmad/po.mdc  基于 @PRDxxx.md 和 @architect/ 创建 Epics（史诗）和 Stories（用户故事）。先不要考虑安全、合规这些外延的点。每个 Epics 一个文档，输出到 @stories 目录下。
```
调整用户故事 ``-------- blabla -----``

### No.6 dev实现后端用户故事
```
@bmad/dev.mdc 帮我基于架构师的设计 @Backend_Architecture.md 依次实现 @epic3-backend-services-stories.md 中的用户故事。  
我已经建好了后台的目录 @backend/ ，请你帮我在这个文件夹内实现。  
后台的实现架构，你用文件 MCP 参考下之前我实现的项目：xxx\backend。  
不要一次性实现所有的用户故事，一个一个来。
实现完一个，我们一起确认下验收的标准是否都达到了，达到了以后，更新用户故事文档，勾上对应的标准。 
然后再询问我，是否继续。不要每次生成多余的总结文档，你可以总结做了什么事，但是不要新增不必要的说明文件。
```

### No.7 dev循环...
```
@bmad/dev.mdc 很好。继续下一个用户故事. 
``` 
``-------- blabla 修bug -----``

### No.8 dev实现前端用户故事
```
@bmad/dev.mdc 开始在 @frontend/ 目录下实现 Epic2 前端用户界面系统。  
1. 前端基础框架搭建，可以用 MCP 参考这个项目 xxx\frontend；  
2. 以架构师对前端的架构设计 @Frontend_Architecture.md 为主要标准；  
3. 遵守 UX 专家对前端部分的设计约束： @UX_Design_System.md 、 @Page_Design_Specifications.md ;  
4. 一个个用户故事来，先实现 Story 2.1: 项目基础架构搭建  
实现完一个，我们一起确认下验收的标准是否都达到了.  
5. 验收标准达到了以后，更新用户故事文档，勾上已经完成的标准。  
6. 不要每次生成多余的总结文档，你可以总结做了什么事，但是不要新增不必要的说明文件。  
7. 最后再询问我，是否继续下一个用户故事。
```
### No.9 dev循环...
```
@bmad/dev.mdc 很好。继续下一个用户故事.  
```
``-------- blabla 修bug -----``

### No.10 dev容器化部署
```
@bmad/dev.mdc 请你帮我在根目录下实现 docker 容器化部署的脚本。服务和依赖如下：
1. 后端：xxx-backend，依赖 redis 和 postgres, 使用这个 @Dockfile，如果有需要调整你帮我调整下内容；
2. 前端: xxx-frontend, 依赖 backend, 使用 nginx 加载，在 nginx.conf 文件中通过配置把 API 代理到后端 /api 指向类似 http://backend:8080/api
```
``-------- blabla 解决部署问题 -----``
