# ASF Award Tool Lite

[![Bilibili](https://img.shields.io/badge/bilibili-Chr__-00A2D8.svg?logo=bilibili)](https://space.bilibili.com/5805394)
[![Steam](https://img.shields.io/badge/steam-Chr__-1B2838.svg?logo=steam)](https://steamcommunity.com/id/Chr_)

[![Steam](https://img.shields.io/badge/steam-donate-1B2838.svg?logo=steam)](https://steamcommunity.com/tradeoffer/new/?partner=221260487&token=xgqMgL-i)
[![爱发电][afdian_img]][afdian_link]
[![buy me a coffee][bmac_img]][bmac_link]

## EULA

> 此插件为 ASFAwardTool 的精简版, 免费发布, 暂不开源
>
> 另有完整版以及点数提货平台, 可在爱发电获取 [@chr233][afdian_link]

## 安装方式

### 初次安装 / 手动更新

1. 从 [GitHub Releases](https://github.com/chr233/ASFAwardToolLite/releases) 下载插件的最新版本
2. 插件本体需要配合 [`ASF-Generic`][asf] 使用, 或者使用编译好的 ASF 版本

| 文件名                 | 说明                                         |
| ---------------------- | -------------------------------------------- |
| `ASFAwardToolLite.zip` | 插件本体, 需要配合 [`ASF-Generic`][asf] 使用 |
| `win-x64.zip`          | 自编译版本 ASF, 内置插件, 开箱即用           |
| `linux-x64.zip`        | 自编译版本 ASF, 内置插件, 开箱即用           |
| `linux-arm64.zip`      | 自编译版本 ASF, 内置插件, 开箱即用           |

[asf]: https://github.com/JustArchiNET/ArchiSteamFarm/releases/latest

### 版本区别

| 功能                 | ASFAwardToolLite           | ASFAwardTool Standalone    | ASFAwardTool Server      |
| -------------------- | -------------------------- | -------------------------- | ------------------------ |
| 打赏任务管理         | ✅                         | ✅                         | ✅                       |
| 历史任务查询         | ✅                         | ✅                         | ✅                       |
| 打赏范围             | 个人资料, 指南, 评测, 截图 | 个人资料, 指南, 评测, 截图 | 人资料, 指南, 评测, 截图 |
| 打赏范围             |                            | 艺术作品, 视频, 创意工坊   | 艺术作品, 视频, 创意工坊 |
| 打赏线程             | 单线程                     | 多线程                     | 多线程                   |
| 设置排除打赏项目     | ❌                         | ✅                         | ✅                       |
| 机器人点数概览       | ❌                         | ✅                         | ✅                       |
| 自动停用无点数机器人 | ❌                         | ✅                         | ✅                       |
| 自动发货平台接入     | ❌                         | ❌                         | ✅                       |

> ASFAwardTool 以及点数提货平台可在爱发电获取 [@chr233][afdian_link]
>
> 点数提货平台演示站: [演示平台](https://demo.1vmp.com) | [演示后台](https://demo.1vmp.com/admin) 密码 `123456`

## 捐赠

|               ![img][afdian_qr]                |                   ![img][bmac_qr]                   |                       ![img][usdt_qr]                       |
| :--------------------------------------------: | :-------------------------------------------------: | :---------------------------------------------------------: |
| ![爱发电][afdian_img] <br> [链接][afdian_link] | ![buy me a coffee][bmac_img] <br> [链接][bmac_link] | ![USDT][usdt_img] <br> `TW41eecZ199QK6zujgKP4j1cz2bXzRus3c` |

[afdian_qr]: https://raw.chrxw.com/chr233/master/afadian_qr.png
[afdian_img]: https://img.shields.io/badge/爱发电-@chr__-ea4aaa.svg?logo=github-sponsors
[afdian_link]: https://afdian.com/@chr233
[bmac_qr]: https://raw.chrxw.com/chr233/master/bmc_qr.png
[bmac_img]: https://img.shields.io/badge/buy%20me%20a%20coffee-@chr233-yellow?logo=buymeacoffee
[bmac_link]: https://www.buymeacoffee.com/chr233
[usdt_qr]: https://raw.chrxw.com/chr233/master/usdt_qr.png
[usdt_img]: https://img.shields.io/badge/USDT-TRC20-2354e6.svg?logo=bitcoin

## 更新日志

| ASFAwardToolLite 版本                                                      | 适配 ASF 版本 | 更新说明   |
| -------------------------------------------------------------------------- | :-----------: | ---------- |
| [1.1.2.1](https://github.com/chr233/ASFAwardToolLite/releases/tag/1.1.2.1) |    6.0.4.4    | 第一个版本 |

## 插件配置说明

> 本插件的配置不是必须的, 保持默认配置即可使用大部分功能

ASF.json

```json
{
  //ASF 配置
  "CurrentCulture": "...",
  "IPCPassword": "...",
  "...": "...",
  //Asf Award Tool 配置
  "ASFEnhance": {
    "EULA": true,
    "Statistic": true,
    "PreferBotPoints": 100000,
    "DelayPerAward": 300,
    "DelayPerAwardError": 2000,
    "DelayBeforeCalcAward": 2000,
    "DefaultAwardType": "A"
  }
}
```

| 配置项                   | 类型     | 默认值   | 说明                                                                              |
| ------------------------ | -------- | -------- | --------------------------------------------------------------------------------- |
| `EULA`                   | `bool`   | `true`   | 是否同意 [EULA](#eula)                                                            |
| `Statistic`              | `bool`   | `true`   | 是否允许发送统计数据, 仅用于统计插件用户数量, 不会发送任何其他信息                |
| `PreferBotPoints`        | `long`   | `100000` | 优先使用点数小于此设定值的机器人, 建议适当调大以免频繁切换机器人导致降低打赏速度  |
| `DelayPerAward`          | `int`    | `200`    | 发送一项打赏成功时的延时 (毫秒)                                                   |
| `DelayPerAwardError`     | `int`    | `2000`   | 发送一项打赏出错时的延时 (毫秒)                                                   |
| `DelayBeforeCalcAward`   | `int`    | `2000`   | 一个物品的打赏全部发送完成, 统计打赏数量前的延时 (毫秒), 此值太小会导致漏统计打赏 |
| `DefaultAwardType`       | `string` | `A`      | 默认打赏类型, 打赏类型说明见下                                                    |
| `UpdatePointCachePeriod` | `int`    | `30`     | 在后台更新机器人点数周期 (秒), 设为 0 禁用                                        |

- 打赏类型 (不区分大小写)

  1. `A` 或 `*`: 打赏个人资料 指南 截图 评测
  2. `P`: 个人资料
  3. `G`: 指南
  4. `S`: 截图
  5. `R`: 评测

  打赏类型允许任意组合, 例如 `PGS` 代表打赏 个人资料 指南 和 截图

## 插件指令说明

> `[]` 代表可省略的参数

| 命令                                              | 缩写         | 权限            | 说明                                           |
| ------------------------------------------------- | ------------ | --------------- | ---------------------------------------------- |
| `ASFAWARDTOOL`                                    | `AAT`        | `FamilySharing` | 查看 ASF Award Tool 的版本                     |
| `TASKLIST [任务ID/SteamID]`                       |              | `Master`        | 查找相关的打赏任务, 不指定参数时查显示所有任务 |
| `CREATETASK 被打赏人SteamdId 打赏点数 [打赏类型]` | `ADDTASK`    | `Master`        | 创建打赏任务, 打赏类型省略时使用默认打赏类型   |
| `CANCELTASK`                                      | `STOPTASK`   | `Master`        | 取消当前打赏任务                               |
| `DELETEHISTORYTASK`                               | `DELHISTORY` | `Master`        | 清除历史任务记录                               |
