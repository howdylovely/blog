# Open-falcon监控

# 资料
```text
在线视频：
http://www.jikexueyuan.com/course/2242.html
在线文档：
http://book.open-falcon.com/zh_0_2
Open-falcon API 文档：
http://api.open-falcon.com/
SNMP协议的资料：
https://blog.csdn.net/bbwangj/article/details/80981098
H3C交换机SNMP配置：
https://www.cnblogs.com/airoot/p/7919295.html
```

# 组件介绍

## HostGroup
* 依赖
  agent、hbs
1、host表中的机器从哪里来呢？agent有个heartbeat(hbs)的配置，agent每分钟会发心跳给hbs，把自己的ip、hostname、agent version等信息告诉hbs，hbs负责写入host表。如果host表中没数据，需要检查这条链路是否通畅。
2、Open-Falcon心跳服务-HBS
  https://blog.csdn.net/qq_27384769/article/details/79576232
  
## Nodata 
```text
1、上报中断时，通知用户。
2、配置了Nodata后，如果有数据上报中断的情况，Nodata配置中的默认值就会被上报。我们可以针对这个默认值，设置报警；只要收到了默认值，就认为发生了数据上报的中断（如果你设置的默认值，可能与正常上报的数据相等，那么请修改你的Nodata配置、使默认值有别于正常值）。
```

## agent
* 依赖
   hbs
   push Transfer //自动采集数据
   v1/push //接受用户手工数据（shell、python）
```text
特点：
自发现、自动去采集
支持插件
```

## HBS
* 数据来源
  CMDB
  自动收集agent发的心跳信息会把hostname、ip、agent version、plugin version等信息告诉HBS，HBS负责更新host表。



