## 本项目实现的最终作用是基于JSP校园论坛管理系统
## 分为2个角色
### 第1个角色为管理员角色，实现了如下功能：
 - 帖子管理
 - 数据查看
 - 版块管理
 - 用户管理
 - 管理员登录
### 第2个角色为用户角色，实现了如下功能：
 - 个人资料管理
 - 发表回复
 - 发表帖子
 - 最新版块
 - 查看公告
 - 用户注册
 - 用户登录
 - 用户首页
## 数据库设计如下：
# 数据库设计文档

**数据库名：** school_bbs

**文档版本：** 


| 表名                  | 说明       |
| :---: | :---: |
| [bbs_user](#bbs_user) |  |
| [club](#club) |  |
| [club_admin](#club_admin) |  |
| [club_type](#club_type) |  |
| [mail_server](#mail_server) |  |
| [post](#post) |  |
| [post_type](#post_type) |  |
| [reply](#reply) |  |
| [system_admin](#system_admin) |  |
| [user_info](#user_info) |  |

**表名：** <a id="bbs_user">bbs_user</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | userName |   varchar   | 255 |   0    |    N     |  Y   |   ''    |   |
|  2   | passwd |   varchar   | 64 |   0    |    N     |  N   |   ''    |   |

**表名：** <a id="club">club</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | clubName |   varchar   | 255 |   0    |    N     |  Y   |       | 俱乐部名字  |
|  2   | clubIcon |   varchar   | 64 |   0    |    N     |  N   |   ''    |   |
|  3   | clubDescribe |   varchar   | 2048 |   0    |    N     |  N   |   ''    |   |
|  4   | clubTypeId |   int   | 10 |   0    |    Y     |  N   |   0    |   |

**表名：** <a id="club_admin">club_admin</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | userName |   varchar   | 255 |   0    |    N     |  Y   |       | 用户名  |
|  2   | clubName |   varchar   | 255 |   0    |    N     |  Y   |       | 俱乐部名字  |

**表名：** <a id="club_type">club_type</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | clubTypeId |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | clubType |   varchar   | 64 |   0    |    N     |  N   |   ''    |   |

**表名：** <a id="mail_server">mail_server</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | emailServerId |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | domain |   varchar   | 255 |   0    |    N     |  N   |   ''    |   |

**表名：** <a id="post">post</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | postId |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | postTitle |   varchar   | 80 |   0    |    N     |  N   |   ''    |   |
|  3   | postContent |   varchar   | 2048 |   0    |    Y     |  N   |   NULL    |   |
|  4   | postTime |   timestamp   | 19 |   0    |    N     |  N   |   current_timestamp()    |   |
|  5   | lastTime |   timestamp   | 19 |   0    |    N     |  N   |   '2023-01-1414:41:43'    |   |
|  6   | userName |   varchar   | 255 |   0    |    N     |  N   |       | 用户名  |
|  7   | clubName |   varchar   | 255 |   0    |    N     |  N   |       | 俱乐部名字  |
|  8   | postTypeId |   int   | 10 |   0    |    N     |  N   |   0    |   |

**表名：** <a id="post_type">post_type</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | postTypeId |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | postType |   varchar   | 64 |   0    |    N     |  N   |   ''    |   |
|  3   | color |   varchar   | 16 |   0    |    Y     |  N   |   NULL    | 颜色  |

**表名：** <a id="reply">reply</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | replyId |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | replyContent |   varchar   | 512 |   0    |    N     |  N   |       |   |
|  3   | replyTime |   timestamp   | 19 |   0    |    N     |  N   |   current_timestamp()    |   |
|  4   | postId |   int   | 10 |   0    |    N     |  N   |       | 帖子ID  |
|  5   | userName |   varchar   | 255 |   0    |    N     |  N   |       | 用户名  |

**表名：** <a id="system_admin">system_admin</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | adminName |   varchar   | 16 |   0    |    N     |  Y   |   ''    |   |
|  2   | passwd |   varchar   | 64 |   0    |    N     |  N   |   ''    |   |

**表名：** <a id="user_info">user_info</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | userName |   varchar   | 255 |   0    |    N     |  Y   |   ''    |   |
|  2   | nickname |   varchar   | 255 |   0    |    N     |  N   |   '用户'    |   |
|  3   | head |   varchar   | 64 |   0    |    N     |  N   |   ''    |   |
|  4   | emailAccount |   varchar   | 64 |   0    |    N     |  N   |   ''    |   |
|  5   | emailServerId |   int   | 10 |   0    |    N     |  N   |   1    |   |

**运行不出来可以微信 javape 我的公众号：源码码头**
