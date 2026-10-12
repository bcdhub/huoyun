# 货运系统

## 🚀 项目简介
这是一套覆盖货主、司机、平台三端的智能货运系统。货主一键发布货源即可快速匹配附近司机，全程轨迹可视、费用透明；司机端实时接单、路线清晰、收益可查；
平台端可统一管理货源、司机、车辆、订单与财务数据。系统运行稳定、扩展灵活，既能快速上线运营，也支持按需定制，为货运物流业务提供可靠的技术底座。

## 🛠️ 技术栈

| 层级 | 技术                                    |
|:---|:--------------------------------------|
| **后端框架** | Spring Boot + MyBatis Plus            |
| **JDK** | Java 8+                               |
| **数据库** | MySQL 5.7+                            |
| **缓存** | Redis                                 |
| **消息队列** | RabbitMQ                              |
| **实时通信** | Netty WebSocket                       |
| **地图服务** | 高德地图                                  |
| **支付** | 微信支付 + 支付宝支付                          |
| **管理后台** | Vue 2.x + Element UI + ECharts        |
| **构建工具** | Maven 3.8+ / Vue CLI 5（webpack 5）     |

## ✨ 核心功能

### 业务流程
- ✅ 用户下单（起点/终点、代驾类型、费用预估）
- ✅ 智能派单（附近司机匹配、抢单机制）
- ✅ 实时定位与轨迹（Netty WebSocket）
- ✅ 行程管理（开始/结束、里程计算）
- ✅ 多渠道支付（微信/支付宝/余额）
- ✅ 订单结算与分润

### 司机管理
- ✅ 司机注册与审核
- ✅ 司机状态管理（在线/离线/接单中）
- ✅ 司机评分与评价系统
- ✅ 司机收入统计与提现

### 运营管理
- ✅ 计价规则配置（起步价+里程费+时长费+夜间溢价）
- ✅ 城市/区域管理
- ✅ 订单监控与统计
- ✅ 财务管理（流水、对账）
- ✅ 数据可视化看板

## 🚀 快速启动

### 环境要求
- JDK 17+
- Maven 3.8+
- MySQL 5.7+
- Redis 5.0+
- RabbitMQ 3.8+
- Node.js 16+（管理后台，推荐 18/20/24）

## ⚙️ 系统特点
- 友好的代码结构及注释，便于阅读及二次开发
- 实现前后端分离，通过token进行数据交互，前端再也不用关注后端技术
- 灵活的权限控制，可控制到页面或按钮，满足绝大部分的权限需求
- 页面交互使用Vue2.x，极大的提高了开发效率
- 引入API模板，根据token作为登录令牌，极大的方便了APP接口开发
- 引入swagger文档支持，方便编写API接口文档


## 🚀 快速启动
- 通过git下载源码
- idea、eclipse需安装lombok插件，不然会提示找不到entity的get set方法
- 创建数据库fast_build，数据库编码为UTF-8
- 执行db/mysql.sql文件，初始化数据
- 修改application-dev.yml，更新MySQL账号和密码
- Eclipse、IDEA运行fastApplication.java，则可启动项目
- Swagger文档路径：http://localhost:8179/fast_build/swagger/index.html
- Swagger注解路径：http://localhost:8179/fast_build/swagger-ui.html


## 📂 项目结构

```
fb-chuxing-server 
├── src/main/java/com/fast
 │ ├── common # 公共模块（注解、切面、异常、工具类、XSS过滤） 
 │ ├── config # 全局配置（Shiro、Redis、MyBatis、Swagger、CORS等） 
 │ ├── datasource # 多数据源支持（动态数据源切换） 
 │ ├── modules # 业务模块 
 │ │ ├── app # APP端用户接口（登录、注册、Token认证） 
 │ │ ├── sys # 系统管理（用户、角色、菜单、字典、日志） 
 │ │ ├── errand # 跑腿/货运订单核心业务 
 │ │ ├── pay # 支付模块（微信支付、回调处理） 
 │ │ ├── chat # �即时通讯模块 
 │ │ ├── chats # 聊天会话管理 
 │ │ ├── carModel # 车辆型号管理 
 │ │ ├── carType # 车辆类型管理 
 │ │ ├── cityArea # 城市区域管理 
 │ │ ├── cityCarType # 城市车型关联 
 │ │ ├── cityInfo # 城市信息管理 
 │ │ ├── banner # 轮播图管理 
 │ │ ├── member # 会员管理 
 │ │ ├── message # 消息推送 
 │ │ ├── oss # 文件存储（阿里云OSS） 
 │ │ ├── invite # 邀请奖励 
 │ │ ├── invoice # 发票管理 
 │ │ ├── reward # 奖励管理 
 │ │ ├── creditRecord # 信用记录 
 │ │ ├── agentMoney # 代理商余额 
 │ │ ├── agentMoneyDetails # 代理商余额明细 
 │ │ ├── goodPrice # 商品价格 
 │ │ ├── goodType # 商品分类 
 │ │ ├── goodWeight # 商品重量 
 │ │ ├── riderLine # 骑手线路 
 │ │ ├── timedtask # 定时任务 
 │ │ ├── userCar # 用户车辆 
 │ │ ├── userExtension # 用户扩展信息 
 │ │ ├── sysUserAddress # 用户地址管理 
 │ │ ├── tbCoupon # 优惠券模块 
 │ │ ├── rechargeConfig # 充值配置 
 │ │ ├── packageTime # 套餐时间 
 │ │ ├── indentTimeRecord # 订单时间记录 
 │ │ ├── gameChat # 游戏聊天 
 │ │ ├── file # 文件上传 
 │ │ ├── common # 业务公共模块 
 │ │ └── utils # 业务工具类 
 │ └── FastApplication.java # 启动类 
 ├── src/main/resources 
 │ ├── mapper # MyBatis XML映射文件 
 │ ├── static/swagger # Swagger静态资源 
 │ ├── weixin # 微信支付证书 
 │ ├── application.yml # 主配置文件 
 │ └── application-prod.yml # 生产环境配置 
 ├── db # 数据库脚本 
 │ └── chuxing.sql # 数据库初始化SQL 
```

### 后端演示

管理后台及司机端演示请联系获取：

- 📞 电话：15596655525
- 💬 微信：15596655525（同号）

> ⚠️ 开源版仅用于学习交流，商用请购买商业版授权。

## 📄 许可证

本项目遵循 **MIT 许可证**，允许商业使用、修改、分发和私有使用。

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

---

**如果这个项目对你有帮助，请点个 Star ⭐ 支持一下！**
