# 修改记录 002：Minecraft 26.2 生物审计与 Sulfur Cube 能力

- 修改日期：2026-08-02
- 目标 Minecraft：Java Edition 26.2
- 输入模组：`mob-possession-26.2-1.0.1.jar`
- 输出模组：`mob-possession-26.2-1.0.2.jar`

## 注册表审计

通过读取 Minecraft 26.2 `minecraft-common.jar` 中 `EntityTypes` 的泛型注册字段，并递归检查实体类是否继承 `net.minecraft.world.entity.Mob`，得到 90 个 Mob。

原模组的目标校验使用 `entity instanceof Mob`，因此 90 个 Mob 均可附身；没有发现“完全不能附身”的遗漏。完整列表见根目录 `MOBS_26.2.md`。

Minecraft 26.2 正式版新增的生物是 `sulfur_cube`。原 `1.0.1` 可对其进行通用移动和近战，但没有处理它吸收方块和弹出方块的核心特性，因此将其认定为专用能力缺口。

## 新增能力

### 右键：吸收主手方块/物品

- 读取控制玩家的主手物品。
- 使用 Sulfur Cube 原版 `isEquippableInSlot(..., BODY)` 检查，只接受原版允许吸收的物品。
- 调用原版 `equipItem`，保留原版替换旧内容、掉落旧内容、同步身体装备和吸收音效。
- 成功后消耗主手 1 个物品；无限材料模式由原版 `ItemStack.consume` 处理。
- 成功冷却 10 tick，无有效物品时冷却 5 tick。

### G：弹出已吸收内容

- 检查原版 `readyForShearing()`。
- 调用原版 `shear(...)` 弹出 BODY 槽内容。
- 保留原版弹出音效和 100 tick 自动拾取抑制。
- 成功冷却 20 tick，无内容时冷却 5 tick。

## 实现方式

- 新增 `dev.mobpossession.server.SulfurCubeSupport`。
- 在 `SpecialMobAbilities.use` 和 `useSecondary` 开头接入专用处理。
- 网络包格式、按键格式、Mixin 列表和其他生物能力均未改变。
- 继承并保留 1.0.1 的速度修复：Shift 加速、Ctrl 下降、陆地默认 0.6 倍、三维默认 `max(0.08, 属性 × 0.8)`。

## 验证

- JAR 结构可正常读取。
- `fabric.mod.json` 版本为 `1.0.2`，Minecraft 依赖仍为 `26.2`。
- 新辅助类已包含在 JAR 中。
- 反汇编确认主要/次要能力入口均调用 Sulfur Cube 支持逻辑。
- 反汇编确认 1.0.1 的速度常量仍然存在。
- ASM `CheckClassAdapter` 对新增类和修改后的 `SpecialMobAbilities` 验证通过。

## 实机测试建议

1. 使用 `/summon minecraft:sulfur_cube` 生成成年 Sulfur Cube。
2. 附身后主手持可吸收方块，按右键，确认方块被吸收且数量减少。
3. 按 `G`，确认吸收内容掉落并播放原版弹出音效。
4. 主手持不可吸收物品按右键，确认不会误吞。
5. 再测试普通移动、Shift 加速和 Ctrl 下降，确认 1.0.1 行为未回退。
