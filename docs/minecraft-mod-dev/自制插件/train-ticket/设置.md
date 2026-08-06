# 配置说明

插件配置文件位于 `plugins/TrainTicket/config.yml`。下面是常用配置示例及说明：

```yaml
web:
  port: 2345        # Web 管理面板监听端口，设置为空时不启用

sync:
  stations-url: "https://metro.cqiming.com/api/stations"  # 站点同步地址，留空跳过
  lines-url:    "https://metro.cqiming.com/api/lines"     # 线路同步地址，留空跳过
  interval-seconds: 30  # 自动同步间隔（秒）

economy:
  enabled: true     # 是否启用 Vault 收费

security:
  web-token: ""     # 可选：为 Web 面板设置简单 token（若为空则无认证）
```

注意事项：
- 若 `sync.stations-url` 或 `sync.lines-url` 为空，插件会跳过对应同步。
- Web 面板默认无认证，若公开部署请设置 `security.web-token` 或仅监听 127.0.0.1。
- 修改后需重启服务器使配置生效（当前插件未实现热载入）。