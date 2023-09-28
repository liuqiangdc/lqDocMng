# 1. 入口主文件
main.go
* 连接数据库
* 加载路由 

# 2. 前端
文件夹views

acount 用户相关
book 知识域相关
commment 评论相关
document 文档
error 报错页面
home 用户的主页
items 知识域广场
label 标签
manager 文档编辑页面
search  搜索页面
settting  后台配置页面
template 模板
widgets 组件（页面头部和底部）

# 3. 后台控制器（后端）
文件夹：controller
# 4. 配置
conf
* MySQL 数据库配置
* 项目名称等基本配置
* 语言配置（变量和语言的对应）

# 5. lib
后端依赖库

# 6. models
模型和数据库对应

# 7. routers
前端页面调整（调整链接）

# 8. static
前端依赖库

# 9. uploads

# 10. utils
第三方工具


# 11. 对应关系

# 12. 表结构说明

## 12.1. md_itemsets
知识域广场
## 12.2. md_books
知识域
* 属于唯一一个md_itemsets。
## 12.3. md_documents
文档
* 属于唯一一个md_documents。
## 12.4. md_document_history
历史文档
## 12.5. md_blogs
知识文件
## 12.6. md_comments
评论
## 12.7. md_attachment
文档和知识文件中可以添加附件
## 12.8. md_label
知识域标签
## 12.9. md_members
用户
## 12.10. md_options
系统配置选项
## 12.11. md_relationship
人员、角色、知识域三者关系表
## 12.12. md_teams
部门/团队
## 12.13. md_team_member
团队和人员关系表
## 12.14. md_team_relationship
团队和知识域关系表
## 12.15. md_templates
模板


