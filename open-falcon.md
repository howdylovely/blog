# Open-falcon监控

# 组件介绍

## HostGroup
1、host表中的机器从哪里来呢？agent有个heartbeat(hbs)的配置，agent每分钟会发心跳给hbs，把自己的ip、hostname、agent version等信息告诉hbs，hbs负责写入host表。如果host表中没数据，需要检查这条链路是否通畅。
2、Open-Falcon心跳服务-HBS
  https://blog.csdn.net/qq_27384769/article/details/79576232
  
## Nodata 
```text
1、上报中断时，通知用户。
2、配置了Nodata后，如果有数据上报中断的情况，Nodata配置中的默认值就会被上报。我们可以针对这个默认值，设置报警；只要收到了默认值，就认为发生了数据上报的中断（如果你设置的默认值，可能与正常上报的数据相等，那么请修改你的Nodata配置、使默认值有别于正常值）。
```
