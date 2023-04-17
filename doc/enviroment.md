# 1. 工具

## 1.1. editor and development

vscode

## 1.2. compile language
 
go

## 1.3. database

### 1.3.1. mysql
 
* uesrname root
* password 123456

# 2. 配置

## 2.1. 代码

* 下载代码并解压至本地目录，如`D:\projects\github\lqDocMng`。（路径不包含中文）

## 2.2. 环境变量

* 右键‘我的电脑’-属性-高级系统设置-环境变量-新建。
* 变量名：`ZONEINFO`;
* 变量值：`D:\projects\github\lqDocMng\lib\time\zoneinfo.zip`;（路径为自己电脑的路径）

## 2.3. 配置数据库

* 启动数据库。启动MySqlWorkBench
* 连接数据库。

```
管理员身份，进入mysql目录`C:\Program Files\MySQL\MySQL Server 8.0\bin`;
链接数据库`mysql -u root -p`
输入密码`123456`
```
* 新建数据库。执行`CREATE DATABASE laykbms_db  DEFAULT CHARSET utf8mb4 COLLATE utf8mb4_general_ci;`
CREATE DATABASE laykbms_db  DEFAULT CHARSET utf8mb4 COLLATE utf8mb4_general_ci;
mysqldump laykbms_db -u root -p123456  | mysql laykbms_db -u root -p123456
* 配置数据库连接。

```
请将刚才解压目录下 conf/app.conf.example 重名为 app.conf。同时配置如下节点：
#数据库配置
db_adapter=mysql
#mysql数据库的IP
db_host=127.0.0.1
        
#mysql数据库的端口号一般为3306
db_port=3306

#刚才创建的数据库的名称
db_database=laykbms_db

#访问数据库的账号和密码
db_username=root
db_password=123456
```

* 初始化数据库。

```
在 MinDoc 根目录下使用命令行执行如下命令，用于初始化数据库：
mindoc_windows_amd64.exe install
稍等一分钟，程序会自动初始化数据库，并创建一个超级管理员账号：admin 密码：123456
```

# 3. 依赖

## 3.1. Go 离线安装依赖包

进入项目根目录(`D:\projects\github\lqDocMng\`);可以在文件管理器中右键选择`Git Bash Here`。

* 替换国内代理。`go env -w GOPROXY=https://goproxy.cn`
* 下载依赖包。在`go.mod`文件所在位置（`D:\projects\github\lqDocMng\`）使用`go get –d`下载依赖包.
* 如果提示不是最新包，可按照最新包下载`go get github.com/gomodule/redigo@latest`

# 4. 编译执行

继续在项目根目录执行:

## 4.1. go包安装
`go mod tidy -v`

## 4.2. 编译(sqlite需要CGO支持)

`go build -ldflags "-w" -o laykbms main.go`

## 4.3. 执行

`./laykbms`

# 5. 正常开发

* 保证数据库软件是打开的（打开mysql workBench，然后链接数据库）
* 源码根目录下，git bash 页面下执行`./mindoc`
* 浏览器访问页面
* 修改代码后保存代码。
* 先停止之前的服务（ctrl+c）
* 再次启动服务执行`./mindoc`

# 6. 页面文字配置

在`conf\lang\zh-cn.ini`目录下。

# 7. 参考

[1]. https://doc.gsw945.com/docs/mindoc-docs/mindoc-windows.md