## 安装elasticsearch和 kibana

###elasticsearch
1.下载安装包
去官网下载https://www.elastic.co/cn/downloads/kibana
2.解压安装
下载后双击解压到/usr/local/Cellar/elasticsearch-6.6.1
3.启动
进入bin中 `./elasticsearch` `./elasticsearch -d`为后台启动
4.检查是否成功
输入网址http://127.0.0.1:9200/
```
{
  "name" : "RVNoGbs",
  "cluster_name" : "elasticsearch",
  "cluster_uuid" : "-tIW20UvR5OgHpThhxdHRw",
  "version" : {
    "number" : "6.6.1",
    "build_flavor" : "default",
    "build_type" : "tar",
    "build_hash" : "1fd8f69",
    "build_date" : "2019-02-13T17:10:04.160291Z",
    "build_snapshot" : false,
    "lucene_version" : "7.6.0",
    "minimum_wire_compatibility_version" : "5.6.0",
    "minimum_index_compatibility_version" : "5.0.0"
  },
  "tagline" : "You Know, for Search"
}
```
###kibana

1.安装
https://www.elastic.co/cn/ 官网
选择和elasticsearch相同的版本下载
2.使用
解压后放在和elasticsearch同一路径
打开一个新终端开始测试，前提是elasticsearch必须是开启状态。在新终端中启动kibana
进入bin `./kibana`
```
启动成功
 log   [12:15:16.393] [warning][plugin] Skipping non-plugin directory at /usr/local/Cellar/kibana-6.6.1-darwin-x86_64/src/legacy/core_plugins/ems_util
  log   [12:15:17.201] [info][status][plugin:kibana@6.6.1] Status changed from uninitialized to green - Ready
  log   [12:15:17.223] [info][status][plugin:elasticsearch@6.6.1] Status changed from uninitialized to yellow - Waiting for Elasticsearch
  log   [12:15:17.225] [info][status][plugin:xpack_main@6.6.1] Status changed from uninitialized to yellow - Waiting for Elasticsearch
  log   [12:15:17.228] [info][status][plugin:graph@6.6.1] Status changed from uninitialized to yellow - Waiting for Elasticsearch
  log   [12:15:17.235] [info][status][plugin:monitoring@6.6.1] Status changed from uninitialized to green - Ready
  log   [12:15:17.237] [info][status][plugin:spaces@6.6.1] Status changed from uninitialized to yellow - Waiting for Elasticsearch
  log   [12:15:17.243] [warning][security] Generating a random key for xpack.security.encryptionKey. To prevent sessions from being invalidated on restart, please set xpack.security.encryptionKey in kibana.yml
  log   [12:15:17.246] [warning][security] Session cookies will be transmitted over insecure connections. This is not recommended.
  log   [12:15:17.249] [info][status][plugin:security@6.6.1] Status changed from uninitialized to yellow - Waiting for Elasticsearch
  log   [12:15:17.259] [info][status][plugin:searchprofiler@6.6.1] Status changed from uninitialized to yellow - Waiting for Elasticsearch
  log   [12:15:17.261] [info][status][plugin:ml@6.6.1] Status changed from uninitialized to yellow - Waiting for Elasticsearch
  log   [12:15:17.285] [info][status][plugin:tilemap@6.6.1] Status changed from uninitialized to yellow - Waiting for Elasticsearch
  log   [12:15:17.286] [info][status][plugin:watcher@6.6.1] Status changed from uninitialized to yellow - Waiting for Elasticsearch
  log   [12:15:17.293] [info][status][plugin:grokdebugger@6.6.1] Status changed from uninitialized to yellow - Waiting for Elasticsearch
  log   [12:15:17.296] [info][status][plugin:dashboard_mode@6.6.1] Status changed from uninitialized to green - Ready
  log   [12:15:17.297] [info][status][plugin:logstash@6.6.1] Status changed from uninitialized to yellow - Waiting for Elasticsearch
  log   [12:15:17.300] [info][status][plugin:beats_management@6.6.1] Status changed from uninitialized to yellow - Waiting for Elasticsearch
  log   [12:15:17.316] [info][status][plugin:apm@6.6.1] Status changed from uninitialized to green - Ready
  log   [12:15:17.408] [info][status][plugin:interpreter@6.6.1] Status changed from uninitialized to green - Ready
  log   [12:15:17.413] [info][status][plugin:canvas@6.6.1] Status changed from uninitialized to green - Ready
  log   [12:15:17.417] [info][status][plugin:license_management@6.6.1] Status changed from uninitialized to green - Ready
  log   [12:15:17.421] [info][status][plugin:index_management@6.6.1] Status changed from uninitialized to yellow - Waiting for Elasticsearch
  log   [12:15:17.434] [info][status][plugin:console@6.6.1] Status changed from uninitialized to green - Ready
  log   [12:15:17.436] [info][status][plugin:console_extensions@6.6.1] Status changed from uninitialized to green - Ready
  log   [12:15:17.438] [info][status][plugin:notifications@6.6.1] Status changed from uninitialized to green - Ready
  log   [12:15:17.440] [info][status][plugin:index_lifecycle_management@6.6.1] Status changed from uninitialized to yellow - Waiting for Elasticsearch
  log   [12:15:17.466] [info][status][plugin:infra@6.6.1] Status changed from uninitialized to green - Ready
  log   [12:15:17.468] [info][status][plugin:rollup@6.6.1] Status changed from uninitialized to yellow - Waiting for Elasticsearch
  log   [12:15:17.472] [info][status][plugin:remote_clusters@6.6.1] Status changed from uninitialized to yellow - Waiting for Elasticsearch
  log   [12:15:17.475] [info][status][plugin:cross_cluster_replication@6.6.1] Status changed from uninitialized to yellow - Waiting for Elasticsearch
  log   [12:15:17.480] [info][status][plugin:upgrade_assistant@6.6.1] Status changed from uninitialized to green - Ready
  log   [12:15:17.485] [info][status][plugin:metrics@6.6.1] Status changed from uninitialized to green - Ready
  log   [12:15:17.612] [info][status][plugin:timelion@6.6.1] Status changed from uninitialized to green - Ready
  log   [12:15:18.261] [warning][reporting] Generating a random key for xpack.reporting.encryptionKey. To prevent pending reports from failing on restart, please set xpack.reporting.encryptionKey in kibana.yml
  log   [12:15:18.265] [info][status][plugin:reporting@6.6.1] Status changed from uninitialized to yellow - Waiting for Elasticsearch
  log   [12:15:18.273] [info][status][plugin:elasticsearch@6.6.1] Status changed from yellow to green - Ready
  log   [12:15:18.326] [info][license][xpack] Imported license information from Elasticsearch for the [data] cluster: mode: basic | status: active
  log   [12:15:18.329] [info][status][plugin:xpack_main@6.6.1] Status changed from yellow to green - Ready
  log   [12:15:18.330] [info][status][plugin:graph@6.6.1] Status changed from yellow to green - Ready
  log   [12:15:18.331] [info][status][plugin:searchprofiler@6.6.1] Status changed from yellow to green - Ready
  log   [12:15:18.332] [info][status][plugin:ml@6.6.1] Status changed from yellow to green - Ready
  log   [12:15:18.332] [info][status][plugin:tilemap@6.6.1] Status changed from yellow to green - Ready
  log   [12:15:18.332] [info][status][plugin:watcher@6.6.1] Status changed from yellow to green - Ready
  log   [12:15:18.333] [info][status][plugin:grokdebugger@6.6.1] Status changed from yellow to green - Ready
  log   [12:15:18.333] [info][status][plugin:logstash@6.6.1] Status changed from yellow to green - Ready
  log   [12:15:18.333] [info][status][plugin:beats_management@6.6.1] Status changed from yellow to green - Ready
  log   [12:15:18.334] [info][status][plugin:index_management@6.6.1] Status changed from yellow to green - Ready
  log   [12:15:18.334] [info][status][plugin:index_lifecycle_management@6.6.1] Status changed from yellow to green - Ready
  log   [12:15:18.334] [info][status][plugin:rollup@6.6.1] Status changed from yellow to green - Ready
  log   [12:15:18.335] [info][status][plugin:remote_clusters@6.6.1] Status changed from yellow to green - Ready
  log   [12:15:18.335] [info][status][plugin:cross_cluster_replication@6.6.1] Status changed from yellow to green - Ready
  log   [12:15:18.335] [info][status][plugin:reporting@6.6.1] Status changed from yellow to green - Ready
  log   [12:15:18.336] [info][kibana-monitoring][monitoring-ui] Starting monitoring stats collection
  log   [12:15:18.344] [info][status][plugin:security@6.6.1] Status changed from yellow to green - Ready
  log   [12:15:18.458] [info][license][xpack] Imported license information from Elasticsearch for the [monitoring] cluster: mode: basic | status: active
  log   [12:15:19.554] [info][migrations] Creating index .kibana_1.
  log   [12:15:19.845] [info][migrations] Pointing alias .kibana to .kibana_1.
  log   [12:15:19.877] [info][migrations] Finished in 323ms.
  log   [12:15:19.878] [info][listening] Server running at http://localhost:5601
  log   [12:15:20.790] [info][status][plugin:spaces@6.6.1] Status changed from yellow to green - Ready
```
启动完成kibana监听本地的localhost:5601端口。我们浏览器访问它。kibana内部会自动访问elasticsearch监听的9200端口。如果都启动正常，我们就可以通过kibana去操作elasticsearch了。