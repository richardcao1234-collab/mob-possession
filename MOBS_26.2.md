# Minecraft Java 26.2 生物完整审计

## 审计结论

Minecraft Java 26.2 的 `EntityTypes` 注册表中共有 **90 个实体类型继承 `Mob`**。Mob Possession 的附身目标判定是 `entity instanceof Mob`，因此原 `1.0.1` 已能附身这 90 个生物，没有遗漏可附身的 Mob。

功能审计发现的缺口不是“不能附身”，而是 26.2 新增的 `sulfur_cube` 只有通用移动和近战，没有对应其原版特性的主动能力。`mob-possession-26.2-1.0.2.jar` 已补充：

- 右键：从控制者主手吸收一个符合原版 `sulfur_cube_swallowable` 标签的方块/物品。
- `G`：弹出当前吸收的方块/物品。

## 完整列表

以下列表直接从本机 Minecraft 26.2 `minecraft-common.jar` 的 `EntityTypes` 泛型注册字段和类继承关系生成，不包括玩家、盔甲架、人体模型、载具、投射物、展示实体和掉落物，因为它们不继承 `Mob`。

| # | Entity ID | 中文说明 | 1.0.2 状态 |
|---:|---|---|---|
| 1 | `allay` | 悦灵 | 已支持 |
| 2 | `armadillo` | 犰狳 | 已支持 |
| 3 | `axolotl` | 美西螈 | 已支持 |
| 4 | `bat` | 蝙蝠 | 已支持 |
| 5 | `bee` | 蜜蜂 | 已支持 |
| 6 | `blaze` | 烈焰人 | 已支持 |
| 7 | `bogged` | 沼骸 | 已支持 |
| 8 | `breeze` | 旋风人 | 已支持 |
| 9 | `camel` | 骆驼 | 已支持 |
| 10 | `camel_husk` | 骆驼尸壳 | 已支持 |
| 11 | `cat` | 猫 | 已支持 |
| 12 | `cave_spider` | 洞穴蜘蛛 | 已支持 |
| 13 | `chicken` | 鸡 | 已支持 |
| 14 | `cod` | 鳕鱼 | 已支持 |
| 15 | `copper_golem` | 铜傀儡 | 已支持 |
| 16 | `cow` | 牛 | 已支持 |
| 17 | `creaking` | 嘎枝 | 已支持 |
| 18 | `creeper` | 苦力怕 | 已支持 |
| 19 | `dolphin` | 海豚 | 已支持 |
| 20 | `donkey` | 驴 | 已支持 |
| 21 | `drowned` | 溺尸 | 已支持 |
| 22 | `elder_guardian` | 远古守卫者 | 已支持 |
| 23 | `ender_dragon` | 末影龙 | 已支持 |
| 24 | `enderman` | 末影人 | 已支持 |
| 25 | `endermite` | 末影螨 | 已支持 |
| 26 | `evoker` | 唤魔者 | 已支持 |
| 27 | `fox` | 狐狸 | 已支持 |
| 28 | `frog` | 青蛙 | 已支持 |
| 29 | `ghast` | 恶魂 | 已支持 |
| 30 | `giant` | 巨人 | 已支持 |
| 31 | `glow_squid` | 发光鱿鱼 | 已支持 |
| 32 | `goat` | 山羊 | 已支持 |
| 33 | `guardian` | 守卫者 | 已支持 |
| 34 | `happy_ghast` | 快乐恶魂 | 已支持 |
| 35 | `hoglin` | 疣猪兽 | 已支持 |
| 36 | `horse` | 马 | 已支持 |
| 37 | `husk` | 尸壳 | 已支持 |
| 38 | `illusioner` | 幻术师 | 已支持 |
| 39 | `iron_golem` | 铁傀儡 | 已支持 |
| 40 | `llama` | 羊驼 | 已支持 |
| 41 | `magma_cube` | 岩浆怪 | 已支持 |
| 42 | `mooshroom` | 哞菇 | 已支持 |
| 43 | `mule` | 骡 | 已支持 |
| 44 | `nautilus` | 鹦鹉螺 | 已支持 |
| 45 | `ocelot` | 豹猫 | 已支持 |
| 46 | `panda` | 熊猫 | 已支持 |
| 47 | `parched` | Parched | 已支持 |
| 48 | `parrot` | 鹦鹉 | 已支持 |
| 49 | `phantom` | 幻翼 | 已支持 |
| 50 | `pig` | 猪 | 已支持 |
| 51 | `piglin` | 猪灵 | 已支持 |
| 52 | `piglin_brute` | 猪灵蛮兵 | 已支持 |
| 53 | `pillager` | 掠夺者 | 已支持 |
| 54 | `polar_bear` | 北极熊 | 已支持 |
| 55 | `pufferfish` | 河豚 | 已支持 |
| 56 | `rabbit` | 兔子 | 已支持 |
| 57 | `ravager` | 劫掠兽 | 已支持 |
| 58 | `salmon` | 鲑鱼 | 已支持 |
| 59 | `sheep` | 羊 | 已支持 |
| 60 | `shulker` | 潜影贝 | 已支持 |
| 61 | `silverfish` | 蠹虫 | 已支持 |
| 62 | `skeleton` | 骷髅 | 已支持 |
| 63 | `skeleton_horse` | 骷髅马 | 已支持 |
| 64 | `slime` | 史莱姆 | 已支持 |
| 65 | `sniffer` | 嗅探兽 | 已支持 |
| 66 | `snow_golem` | 雪傀儡 | 已支持 |
| 67 | `spider` | 蜘蛛 | 已支持 |
| 68 | `squid` | 鱿鱼 | 已支持 |
| 69 | `stray` | 流浪者 | 已支持 |
| 70 | `strider` | 炽足兽 | 已支持 |
| 71 | `sulfur_cube` | Sulfur Cube | 已支持；1.0.2 新增专用能力 |
| 72 | `tadpole` | 蝌蚪 | 已支持 |
| 73 | `trader_llama` | 行商羊驼 | 已支持 |
| 74 | `tropical_fish` | 热带鱼 | 已支持 |
| 75 | `turtle` | 海龟 | 已支持 |
| 76 | `vex` | 恼鬼 | 已支持 |
| 77 | `villager` | 村民 | 已支持 |
| 78 | `vindicator` | 卫道士 | 已支持 |
| 79 | `wandering_trader` | 流浪商人 | 已支持 |
| 80 | `warden` | 监守者 | 已支持 |
| 81 | `witch` | 女巫 | 已支持 |
| 82 | `wither` | 凋灵 | 已支持 |
| 83 | `wither_skeleton` | 凋灵骷髅 | 已支持 |
| 84 | `wolf` | 狼 | 已支持 |
| 85 | `zoglin` | 僵尸疣猪兽 | 已支持 |
| 86 | `zombie` | 僵尸 | 已支持 |
| 87 | `zombie_horse` | 僵尸马 | 已支持 |
| 88 | `zombie_nautilus` | 僵尸鹦鹉螺 | 已支持 |
| 89 | `zombie_villager` | 僵尸村民 | 已支持 |
| 90 | `zombified_piglin` | 僵尸猪灵 | 已支持 |

## “支持”的范围

“已支持”表示可以被选中、附身、从其视角控制、移动、跳跃/游泳/飞行并使用统一近战。具有 `RangedAttackMob` 接口的实体还会走通用远程攻击分支；1.0.5 中骷髅系拥有沿玩家准星射箭的专用分支，远程生物会显示准星与参考预测轨迹；苦力怕、末影人、恶魂、守卫者、凋灵等实体也具有额外专用分支。并非每个生物都拥有独立右键技能。

## 非 Mob 实体

26.2 还注册了玩家、盔甲架、人体模型（`mannequin`）、船、矿车、投射物、展示实体等。它们不继承 `Mob`，也没有 Mob AI/MoveControl，不属于本次 90 个生物清单。强行将其纳入当前控制架构需要另外设计 LivingEntity/载具控制系统，不能视为简单漏项。
