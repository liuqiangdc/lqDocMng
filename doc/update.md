# 1. 修改首页“MinDoc文档管理系统”

* in file lqDocMng\models\Options.go,at line 140:

old
```
option.OptionValue = "MinDoc文档管理系统"
```
new 
```
随便写个名字
```

* in file lqDocMng\views\widgets\header.tpl,at line 5:

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

# 2. 修改启动方式'./mindoc'

在这个命令就是执行根目录下的`mindoc`文件，可以在生产这个文件的时候，改变名称。生成这个文件的命令是`go build -ldflags "-w" -o mindoc main.go`，改为`go build -ldflags "-w" -o asyouwish main.go`.
然后再根目录启动项目用命令`./asyouwish`