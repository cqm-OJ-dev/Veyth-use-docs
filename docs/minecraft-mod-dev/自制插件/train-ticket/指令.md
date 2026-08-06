# 插件指令参考

下表列出已实现或常见的指令（请根据服务器中实际实现为准）：

- `/setline price <lineId> <price>`
  - 作用：为指定线路设置售票价格。
  - 示例：`/setline price 12 3.5`

- `/setline`（查看线路）
  - 作用：列出当前已知线路及其 ID 与价格（若实现）。

- `/givemachine <type>`
  - 作用：给管理员一台机器方块（售票机或检票机）。
  - 示例：`/givemachine ticket_machine`

- `/syncdata` 或 Web 面板“手动同步”按钮
  - 作用：立即从配置的远程 API 同步线路/站点数据。

注：具体指令名可能与服务器版本略有差异，使用 `plugin.yml` 中声明的命令为准。