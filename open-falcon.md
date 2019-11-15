# Open-falcon监控

# 组件介绍

HostGroup
1、host表中的机器从哪里来呢？agent有个heartbeat(hbs)的配置，agent每分钟会发心跳给hbs，把自己的ip、hostname、agent version等信息告诉hbs，hbs负责写入host表。如果host表中没数据，需要检查这条链路是否通畅。
2、Open-Falcon心跳服务-HBS
  https://blog.csdn.net/qq_27384769/article/details/79576232
  
