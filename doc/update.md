# 1. 修改语言配置
在`\conf\lang\zh-cn.ini`中修改相应配置的中文名称。

# 2. 修改首页“MinDoc文档管理系统”
在文件`\views\widgets\header.tpl`第5行

old
```
<a href="{{.BaseUrl}}/" class="navbar-brand" title="{{.SITE_NAME}}">
    {{if .SITE_TITLE}}
    {{.SITE_TITLE}}
    {{else}}
    {{.SITE_NAME}}
    {{end}}
</a>
```
new
```
<a href="{{.BaseUrl}}/" class="navbar-brand" title="{{.SITE_NAME}}">
    随便写个名字
</a>
```

# 3. 修改底部文字链接，不跳转
在文件`lqDocMng\views\widgets\footer.tpl`整个文件修改
old
```
<div class="footer">
    <div class="container">
        <div class="row text-center border-top">
            <span><a href="https://www.iminho.me" target="_blank">{{i18n .Lang "common.official_website"}}</a></span>
            <span>&nbsp;·&nbsp;</span>
            <span><a href="https://github.com/mindoc-org/mindoc/issues" target="_blank">{{i18n .Lang "common.feedback"}}</a></span>
            <span>&nbsp;·&nbsp;</span>
            <span><a href="https://github.com/mindoc-org/mindoc" target="_blank">{{i18n .Lang "common.source_code"}}</a></span>
            <span>&nbsp;·&nbsp;</span>
            <span><a href="https://www.iminho.me/wiki/docs/mindoc/" target="_blank">{{i18n .Lang "common.manual"}}</a></span>
        </div>
        {{if .site_beian}}
        <div class="row text-center">
            <a href="https://beian.miit.gov.cn/" target="_blank">{{.site_beian}}</a>
        </div>
        {{end}}
    </div>
</div>

```
new 
```
<div class="footer">
    <div class="container">
        <div class="row text-center border-top">
            <span>{{i18n .Lang "common.official_website"}}</span>
         </div>
    </div>
</div>
```

# 4. 修改提示
在文件`views\widgets\ie.tpl`16行：
old 
```
  <p class="from">来自MinDoc的提醒</p>
```
new 
```
<p class="from">来自LayKbms的提醒</p>
```

# 5. 文档新建中的提示修改: 本知识文件使用 MinDoc 上传发表

# 6. 修改知识域编辑模式下显示`本知识文件使用 MinDoc 上传发表`
在文件`lqDocMng\views\document\default_read.tpl`159行
old
```
 {{i18n $.Lang "doc.doc_publish_by"}} <a href="https://www.iminho.me" target="_blank">MinDoc</a> {{i18n $.Lang "doc.doc_publish"}}
```
new
```
    {{i18n $.Lang "doc.doc_publish_by"}} LayKbms {{i18n $.Lang "doc.doc_publish"}}
```

# 7. 文档新建里的模板修改: 删除模板后的链接
在文件`\views\document\template_normal.tpl`中
old1
```
很多文字。。。。
```
new
```
# LayKbms 模板演示

```

# 8. 修改`Powered by Mindoc`
使用vscode全局搜索`Powered by Mindoc`,然后替换为`Powered by LayKbms`

# 9. 阅读者显示异常
在`MemberResult.go`文件中，64行
old
```
m.RoleName = i18n.Tr(lang, "common.obverser")
```
new 
```
m.RoleName = i18n.Tr(lang, "common.observer")
```

# 10. 修改启动方式'./mindoc'

在这个命令就是执行根目录下的`mindoc`文件，可以在生产这个文件的时候，改变名称。生成这个文件的命令是`go build -ldflags "-w" -o mindoc main.go`，改为`go build -ldflags "-w" -o asyouwish main.go`.
然后再根目录启动项目用命令`./asyouwish`