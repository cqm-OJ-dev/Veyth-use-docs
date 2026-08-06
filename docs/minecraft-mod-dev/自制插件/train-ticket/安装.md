# 安装指南

## 要求

- Minecraft 服务器：Paper 或 Spigot，对应的 API 版本（建议与插件编译时的 paper-api 匹配）
- Java 运行环境：Java 11+
- Vault（用于经济扣款）及至少一个 Vault 支持的经济插件（例如 EssentialsX Economy、iConomy 等）
- SQLite JDBC（如果未使用 fat-jar 打包，需要将 sqlite-jdbc 放入服务器的 `plugins/libs` 或 `plugins`）

## 安装步骤

1. 将编译好的插件 jar 放入服务器 `plugins/` 目录。
2. 启动服务器，插件将在 `plugins/TrainTicket/` 下生成 `config.yml` 与（可选的）`stations.db`。
3. 编辑 `config.yml`：设置 `web.port`、`sync` URL 等（参见配置章节）。
4. 重启服务器使配置生效。

## 打包建议

为了避免服务器端手动安装依赖，建议生成包含依赖的 fat-jar（shadowJar）。如果需要我可以帮你在项目里添加或生成 fat-jar。