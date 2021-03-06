salesapp 销售管理程序

一个 C 语言程序设计作业

最后更新时间：2021年12月12日

# 功能说明

本程序为适用于小型超商和便利店使用的单机收银程序，具有用户管理，商品管理和收银功能，使用 mariadb 来存储数据。

用户分为管理员、售货员和顾客三类角色，各自可使用的功能如下：

管理员：
- [x] 列出所有用户的信息（除密码）
- [x] 添加、删除任意角色类型的用户
- [x] 启用、禁用任意角色类型的用户
- [x] 修改任意角色类型用户的信息（用户名，密码，姓名）

售货员：
- [x] 收银
- [x] 列出所有商品信息
- [x] 添加、删除、修改商品
- [x] 新建、删除、修改顾客用户

顾客：
- [x] 修改自己的信息

# 开发环境

- OS:windows11
- IDE:codeblocks 20.03 with mingw
- mariadb 版本：10.6.5 x64

github 上的源代码是 UTF-8 编码格式，而开发时使用的是 GBK 编码。编译使用 codeblocks 自带的 mingw，设置连接 mariadb 库，其它编译选项保持默认。

# 使用说明

程序使用了 mariadb 数据库，在未安装 mariadb 的系统上运行需要`libmariadb.dll`在程序同一目录下

# 连接到 mariadb 数据库

mariadb 服务端可架设在本地或云服务器上

连接到远程 mariadb 服务器：  
需自行搭建 mariadb 服务端，在程序中使用域名或 ip 进行连接，使用前需要在程序中对数据库初始化。

使用本地 mariadb 服务器：  
在本机安装 mariadb 服务端，使用前需要在程序中对数据库初始化。

# 数据库结构设计

表 USERS
|名称|类型|属性|
|:----:|:----:|:----:|
|Id|INT|主键，自动增长，非空|
|Role|INT|非空|
|Status|INT|非空|
|Username|TEXT|非空|
|Password|TEXT|非空|
|Name|TEXT|无|

Id 从 1001 开始自动增长

表 GOODS
|名称|类型|属性|
|:----:|:----:|:----:|
|Code|BIGINT|主键，非空|
|Name|TEXT|非空|
|PurchasePrice|FLOAT|无符号|
|Price|FLOAT|无符号|

# 待完善

- 添加更多顾客功能
- VIP 顾客结算打折