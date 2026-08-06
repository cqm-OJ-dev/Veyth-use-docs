# 数据库与持久化

插件使用 SQLite 存储数据，默认数据库文件：

`plugins/TrainTicket/stations.db`

主要表结构：

- `lines(id, name, raw_json)`：线路信息（id 为远端或自定义 ID）。
- `stations(id, name, line_id, raw_json)`：站点信息。
- `line_prices(line_id, price)`：线路价格。
- `gates(...)`：闸机（检票机）配置。
- `machines(...)`：机器方块（售票机/检票机）位置与类型。
- `tickets(...)`：已发放车票记录（用于撤销或管理）。

迁移注意：早期版本可能缺少某些列，插件会尽量回退查询或在启动时安全处理。备份数据库文件在进行手动修改或迁移前强烈推荐。