# 常见问题与排障

1. 读取线路失败: [SQLITE_ERROR] no such column: position
   - 原因：旧版数据库缺少 position 列（插件曾一度使用排序字段）。
   - 解决：已在插件中移除对 position 的依赖；若仍有错误，重启服务器并确认 `plugins/TrainTicket/stations.db` 未被锁定，或删除并重建数据库（会丢失本地站点/票据数据）。

2. 缺少 org.json 或 sqlite-jdbc 类错误
   - 原因：未使用 fat-jar，服务器缺少依赖。
   - 解决：生成包含依赖的 fat-jar，或把缺失的依赖 jar 放入 `plugins/libs/` 或服务器 classpath。

3. Vault 扣款失败或余额不足提示
   - 检查 Vault 是否安装并有可用 Economy 提供者；确认经济插件（如 EssentialsX）运行正常。

4. 网页面板无法访问
   - 检查 `web.port` 是否正确、服务器防火墙或提供商端口是否开放；若端口为空则面板未启用。

5. 面板需要认证/安全
   - 临时建议：只在内网使用或通过反向代理做认证。可请求我添加 token/password 认证功能。