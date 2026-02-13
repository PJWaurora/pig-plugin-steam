# pig-plugin-steam

> Steam 状态查询与监控插件 - [pig-sender](https://github.com/PJWaurora/pig-sender) QQ 机器人模块

## 功能

- **Steam 账号绑定** — 群成员可通过 `@机器人 绑steam <SteamID/链接>` 绑定自己的 Steam 账号
- **个人状态查询** — `@机器人 steam` 生成精美的个人 Steam 状态卡片图片
- **他人状态查询** — `@机器人 steam @某人` 查看指定成员的 Steam 状态
- **群组批量查询** — `@机器人 steam状态` 查看本群所有已绑定成员的 Steam 在线状态
- **自动状态监控** — 后台定时轮询，当绑定用户上线/下线/切换游戏时自动推送通知
- **图片渲染** — 使用 PIL 原生渲染深色主题状态卡片，包含头像、在线状态、游戏信息等

## 配置

在 `config.json` 中配置以下参数：

| 参数 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `steam_api_key` | string | `""` | Steam Web API 密钥（必填） |
| `auto_monitor` | boolean | `true` | 是否启用自动状态监控 |
| `monitor_interval` | number | `120` | 监控轮询间隔（秒） |
| `db_path` | string | `/app/data/steam.db` | 绑定数据库路径 |

## 使用方法

```
@机器人 绑steam <SteamID/自定义URL>  # 绑定 Steam 账号
@机器人 steam                       # 查看自己的状态
@机器人 steam @某人                  # 查看他人状态
@机器人 steam状态                    # 查看群组所有人状态
@机器人 steam帮助                    # 显示帮助
```

## 依赖

- `aiohttp` — 异步 HTTP 请求
- `Pillow` — 图片渲染
- Steam Web API Key — 从 [Steam 开发者页面](https://steamcommunity.com/dev/apikey) 获取

## 许可

MIT
