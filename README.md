<div align="center">

# Mob Possession / 生物附身

从生物视角直接控制 Minecraft 原版 Mob 的 Fabric 模组

![Minecraft](https://img.shields.io/badge/Minecraft-1.21%E2%80%9326.2-62B47A?style=flat-square)
![Fabric](https://img.shields.io/badge/Loader-Fabric-DBD0B4?style=flat-square)
![Version](https://img.shields.io/badge/Mod_Version-1.0.5-4C8BF5?style=flat-square)
![Java](https://img.shields.io/badge/Java-21%20%7C%2025-E76F00?style=flat-square)
![License](https://img.shields.io/badge/License-MPL--2.0-blue?style=flat-square)

</div>

Mob Possession 允许玩家附身到视线内的原版生物，从该生物的相机视角控制移动、跳跃、游泳、飞行、近战和专用能力，同时保留原版物理、碰撞、尺寸、属性、环境伤害与生物特性。附身期间会暂停该生物的主动 AI，避免它自行锁定或攻击其他生物。

Minecraft Java 26.2 中注册的 **90 种 Mob 均可附身**。苦力怕、末影人、恶魂、凋灵、监守者、守卫者、唤魔者、Sulfur Cube 等生物还具有单独实现的主动能力。

> 当前推荐版本：所有支持的 Minecraft 版本均使用对应的 `1.0.5` JAR。同一个游戏实例中只能安装一个对应版本的 JAR。

[功能亮点](#功能亮点) · [安装](#安装) · [版本选择](#版本选择) · [默认按键](#默认按键) · [远程瞄准](#远程瞄准与预测轨迹) · [90 种生物手册](MOB_OPERATIONS_26.2.md) · [许可证](#许可证)

## 功能亮点

- 对准 24 格内的存活生物即可附身。
- 直接使用生物视角，不生成替身实体。
- 支持陆地、水中和空中三维移动。
- 支持近战、原版远程攻击和生物专用能力。
- 附身期间暂停目标的主动 AI，避免生物自行锁定、追击或攻击。
- 骷髅系可以像玩家使用弓一样，根据准星方向自由射箭。
- 远程生物附身时显示准星和仅控制者可见的预测轨迹。
- 烈焰人支持空格上升、Ctrl 下降和 Shift 加速飞行。
- 右键或 `G` 可以持续按住，冷却结束后自动再次响应。
- 退出后恢复玩家原来的位置、视角、游戏模式、隐身和无敌状态。
- 服务端验证距离、视线、目标状态和控制输入。
- 一个生物同一时间只能由一名玩家控制。
- 提供 Minecraft 1.21 至 26.2 的多个 Fabric 构建。

## 安装

1. 安装与 Minecraft 版本匹配的 Fabric Loader。
2. 安装对应版本的 Fabric API。
3. 从 GitHub Releases 下载与游戏版本匹配的一个 JAR。
4. 将 JAR 放入 Minecraft 实例的 `mods` 文件夹。
5. 客户端和服务器安装相同版本后启动游戏。

单人游戏需要在客户端安装。多人游戏建议客户端和服务器都安装，并确保双方使用完全相同的模组 JAR；仅在服务器安装无法提供按键、附身相机、准星等客户端功能。

运行环境：

- Minecraft 1.21.x：Java 21 或更高版本。
- Minecraft 26.x：Java 25 或更高版本。
- 模组必须与 Minecraft 版本完全匹配。

不要同时安装多个版本的 Mob Possession，否则 Fabric 会检测到重复的 `mob_possession` 模组 ID。

## 版本选择

| Minecraft | 直接下载 | Fabric Loader | Java |
|---|---|---:|---:|
| 1.21–1.21.1 | [`mob-possession-1.21-1.0.5.jar`](https://github.com/richardcao1234-collab/mob-possession/releases/download/v1.0.5/mob-possession-1.21-1.0.5.jar) | 0.16+ | 21+ |
| 1.21.2–1.21.3 | [`mob-possession-1.21.2-1.0.5.jar`](https://github.com/richardcao1234-collab/mob-possession/releases/download/v1.0.5/mob-possession-1.21.2-1.0.5.jar) | 0.16+ | 21+ |
| 1.21.4 | [`mob-possession-1.21.4-1.0.5.jar`](https://github.com/richardcao1234-collab/mob-possession/releases/download/v1.0.5/mob-possession-1.21.4-1.0.5.jar) | 0.16+ | 21+ |
| 1.21.5 | [`mob-possession-1.21.5-1.0.5.jar`](https://github.com/richardcao1234-collab/mob-possession/releases/download/v1.0.5/mob-possession-1.21.5-1.0.5.jar) | 0.16+ | 21+ |
| 1.21.6–1.21.8 | [`mob-possession-1.21.8-1.0.5.jar`](https://github.com/richardcao1234-collab/mob-possession/releases/download/v1.0.5/mob-possession-1.21.8-1.0.5.jar) | 0.16+ | 21+ |
| 1.21.9–1.21.10 | [`mob-possession-1.21.9-1.0.5.jar`](https://github.com/richardcao1234-collab/mob-possession/releases/download/v1.0.5/mob-possession-1.21.9-1.0.5.jar) | 0.16+ | 21+ |
| 1.21.11 | [`mob-possession-1.21.11-1.0.5.jar`](https://github.com/richardcao1234-collab/mob-possession/releases/download/v1.0.5/mob-possession-1.21.11-1.0.5.jar) | 0.16+ | 21+ |
| 26.1 | [`mob-possession-26.1-1.0.5.jar`](https://github.com/richardcao1234-collab/mob-possession/releases/download/v1.0.5/mob-possession-26.1-1.0.5.jar) | 0.19.3+ | 25+ |
| 26.2 | [`mob-possession-26.2-1.0.5.jar`](https://github.com/richardcao1234-collab/mob-possession/releases/download/v1.0.5/mob-possession-26.2-1.0.5.jar) | 0.19.3+ | 25+ |

## 默认按键

按键可以在 Minecraft“控制”设置中的“生物附身”分类修改。

| 按键 | 功能 |
|---|---|
| `R` | 附身目标；再次按下退出 |
| `WASD` | 移动 |
| 空格 | 跳跃；水生/飞行生物上升 |
| `Ctrl` | 水生/飞行生物下降 |
| `Shift` | 加速 |
| 鼠标左键 | 近战攻击 |
| 鼠标右键 | 主要生物能力 |
| `G` | 次要生物能力 |

普通陆地生物默认使用其移动速度属性的 35%，按住 Shift 后提高到 70%。水生和飞行生物使用较慢的平滑三维移动，按住 Shift 后提高 35%。

烈焰人也属于飞行控制：空格上升、Ctrl 下降、WASD 飞行，按住 Shift 加速。

## 能力示例

| 生物 | 鼠标右键 | `G` |
|---|---|---|
| 骷髅、流浪者、沼骸等骷髅系 | 沿玩家准星方向射箭，无需锁定实体 | — |
| 苦力怕 | 开始爆炸倒计时 | — |
| 末影人 | 搬运合法方块；方块无效时向前传送，失败会快速重试 | 强制向前传送 |
| 恶魂 | 发射恶魂火球 | — |
| 监守者 | 释放音爆 | — |
| 守卫者/远古守卫者 | 锁定目标并启动激光 | — |
| 唤魔者 | 召唤尖牙 | 召唤临时恼鬼 |
| 潜影贝 | 发射追踪弹；无目标时传送 | 随机传送 |
| 凋灵 | 发射普通凋灵之首 | 发射危险凋灵之首 |
| Sulfur Cube | 吸收主手中允许的方块/物品 | 弹出吸收内容 |

更多操作请查看 [90 种生物操作手册](MOB_OPERATIONS_26.2.md)。

## 远程瞄准与预测轨迹

附身具有远程攻击能力的生物时，模组会显示原版屏幕中央准星，并通过末地烛粒子给出参考轨迹：

- 骷髅、流浪者、沼骸、Parched 和凋灵骷髅直接沿玩家准星射箭，不需要先锁定实体。
- 箭矢轨迹会计算初速度、阻力和重力下坠。
- 烈焰人、恶魂、旋风人、末影龙和凋灵显示近似直线轨迹。
- 通用远程生物也会显示辅助轨迹，但药水、弩箭、唾沫等特殊弹种可能与预测线存在少量差异。
- 轨迹每 5 tick 刷新一次，只发送给当前控制玩家，其他玩家不会看到辅助线。

预测轨迹用于瞄准参考，不会自动锁定目标或改变弹丸碰撞结果。

## 文档

- [Minecraft 26.2 全部 90 种生物操作与功能](MOB_OPERATIONS_26.2.md)
- [Minecraft 26.2 生物注册表与覆盖审计](MOBS_26.2.md)
- [开发变更记录](docs/changelog/)

## 下载与发布文件

普通玩家只需要从仓库的 **Releases** 页面下载一个与 Minecraft 版本匹配的 `1.0.5` JAR。不要下载 `_tools`、反编译目录或多个 Minecraft 版本的 JAR，也不要同时安装历史版本。

发布者创建 `v1.0.5` Release 时，应把“版本选择”表中的 9 个 JAR 作为 Release 附件，而不是全部提交到 Git 历史中。Release 说明应明确指出：

```text
When this release is published, the corresponding source code will be available from the `v1.0.5` tag in this repository.
Licensed under MPL-2.0.
```

## 版本变化

### 1.0.5

- 将 1.0.3/1.0.4 的 AI、技能响应、速度、末影人和骷髅瞄准修复适配到全部支持版本。
- 烈焰人改为三维飞行控制：空格上升、Ctrl 下降、Shift 加速。
- 附身远程生物时强制显示原版准星。
- 为骷髅系、通用远程生物、烈焰人、恶魂、旋风人、末影龙和凋灵显示仅控制玩家可见的预测轨迹。
- 骷髅、流浪者、沼骸、Parched 和凋灵骷髅均可沿玩家准星自由射箭，并保留各自原版箭矢生成逻辑。

### 1.0.4

- 仅面向 Minecraft 26.2。
- 普通骷髅改为玩家手动瞄准：右键直接沿准星方向射箭，不再要求准星先锁定活体目标。
- 使用骷髅自己的弓、箭矢生成逻辑、伤害与射击音效，射击冷却为 20 tick。

### 1.0.3

- 仅面向 Minecraft 26.2。
- 附身期间暂停生物主动 AI、清空攻击目标并停止自主导航。
- 按住右键或 `G` 时，技能会在冷却结束后自动响应，不再吞掉冷却期间的按键。
- 修复末影人对准无效方块或瞬移失败时看似无响应的问题。
- 再次降低移动速度：陆地默认 35%，Shift 加速 70%；三维基础速度改为 `max(0.05, 属性 × 0.5)`。

### 1.0.2

- 仅面向 Minecraft 26.2。
- 为 Sulfur Cube 增加右键吸收和 `G` 弹出能力。
- 保留 1.0.1 的速度与按键修复。

### 1.0.1

- 降低附身后的默认移动速度。
- 将加速键改为 Shift。
- 将水生/飞行生物下降键改为 Ctrl。

### 1.0.0

- 首次构建。
- 添加基础附身、移动、网络同步和生物能力。

详细记录见 [`docs/changelog`](docs/changelog/) 目录。

## 多人游戏与安全性

- 实际附身、攻击和能力均由服务器执行。
- 服务器会重新验证目标距离、视线、存活状态和目标占用状态。
- 移动轴和视角数据经过范围限制。
- 当前没有权限节点或配置文件；服务器安装后，所有正确安装客户端模组的玩家都可以使用附身功能。
- 恶魂、苦力怕、凋灵、末影龙和唤魔者等能力可能破坏世界，建议先在测试存档使用。

## 已知限制

- 退出附身后，玩家返回附身前的位置，而不是目标生物的当前位置。
- 附身会话只保存在内存中，服务器重启后不会恢复。
- 1.0.5 会在附身期间暂停主动 Goal/Brain AI；少数直接写在实体普通 tick 中的特殊行为仍可能继续运行。
- 并非所有生物都有独立的右键或 `G` 能力；没有专用能力的生物仍支持移动和左键攻击。
- 玩家、盔甲架、人体模型、载具、投射物和展示实体不继承 `Mob`，不属于可附身目标。

## 许可证

本项目采用 [Mozilla Public License 2.0](https://www.mozilla.org/MPL/2.0/)，SPDX 标识为 `MPL-2.0`。发布源码时应保留许可证通知；发布 JAR 时应同时说明对应源代码的获取方式。提交第三方代码、资源或衍生内容前，请自行确认许可证兼容性。

## 免责声明

本项目不是 Mojang Studios 或 Microsoft 的官方项目，也未获得其认可。Minecraft 是 Microsoft 旗下 Mojang Studios 的商标。
