
# 普通业务的错误日志格式
```text
日志前缀+日志内容
```

# 日志前缀
```text
[时间][Request_id]App_name.错误类型.具体的错误类型

```

# 日志内容
```text
err_code 错误码
message 错误内容
file 操作文件
line 错误行
```


ECHO golang框架的格式
http://go-echo.org/middleware/logger/

Gin 日志格式
gin.DebugPrintRouteFunc = func(httpMethod, absolutePath, handlerName string, nuHandlers int) {
		log.Printf("endpoint %v %v %v %v\n", httpMethod, absolutePath, handlerName, nuHandlers)
}
