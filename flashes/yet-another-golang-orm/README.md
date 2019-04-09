# Silk项目介绍

Silk是一个新的golang orm框架。为了提高开发效率，减少开发上容易出现的问题，同时又兼顾性能，Silk诞生了。
Silk的特点是，可以通过自带的命令行工具生成各个模型文件，然后直接在项目中调用模型文件的方法即可。几乎无需看文档就可以上手使用，同时又是ide友好的结构体的方式进行调用，出错率大大降低，同时代码也更加可维护。

使用：

```
silk.Open("sqlite3", "test.db")

user := models.NewUsers()
user.Id = 1
user.Name = "张三"
user.Save()
fmt.Println(user.Id, user.Name)

newUser := models.NewUsers().WhereId(1).First()
fmt.Println(newUser.Id, newUser.Name)
```

例子见：https://github.com/goctopus/silk/blob/master/example/main.go

## 进度

- [ ] 模型文件对外接口的补充和优化
- [ ] 适配各种驱动（pg,mysql,mssql,sqlite）的语法
- [ ] 性能测试
- [ ] 命令行工具开发（读取数据库配置，获取各个表格信息，生成模型文件）
- [ ] [collection数据结构](https://laravel.com/docs/5.8/eloquent-collections)
