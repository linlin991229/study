# 学习nestjs
## 发现个有趣的问题
在javaScript中除0不会抛出异常而是会得到无穷大的结果====>Infinity
JS中异常为Error

## 请求路径问题
```JavaScript
@Get('list') // 先定义这样请求才不会匹配错路径
@Get(':id')
```

### 配置nestjs 10的热更新
最后发现不用配置，晕！！
### mongodb容器问题
mongodb6.0版本以上
```bash
docker exec -it mongo mongosh admin
```
以下使用
```bash
docker exec -it mongo mongo admin
```
### nestjs各组件功能初步总结

1. `controller`===控制层
2. `provider`===服务层
3. `Modules`===功能模块
4. `Middleware`===应该类似于`Servlet`的过滤器
a.可以修改请求与响应
b.可以结束响应周期
c.有类似于过滤器链的中间件链通过`next()`函数传递
d.若没有调用`next()`请求会被挂起
5. `Exception filter`===将异常集中处理，同异常处理切面
6. pipes===用于转换参数和验证后台接收到底参数相当于参数校验与数据转换
7. guards===卫兵，类似于安全框架校验权限
7. interceptors====AOP
