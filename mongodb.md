
# MongoDB

## Nosql同类产品中的优势

## 应用场景

## 客户端操作工具
* Robo 3T
  * 下载地址 https://robomongo.org/download
* 自带的Shell工具
  * mongo
## 最佳实践
* 数据的导入

 mongoimport -h localhost:27017 -d jdhci -c hcisystem ./hcisystem.json
 mongoimport -h localhost:27017 -d jdhci -c hcidevice ./hcidevice.json
 mongoimport -h localhost:27017 -d jdhci -c hcicluster ./hcicluster.json
 mongoimport -h localhost:27017 -d jdhci -c hcicabinet ./hcicabinet.json
* 数据的导出

 mongoexport -h localhost:27017 -d jdhci -c hcisystem -o./hcisystem.json
 mongoexport -h localhost:27017 -d jdhci -c hcidevice -o./hcidevice.json
 mongoexport -h localhost:27017 -d jdhci -c hcicluster -o./hcicluster.json
 mongoexport -h localhost:27017 -d jdhci -c hcicabinet -o./hcicabinet.json
