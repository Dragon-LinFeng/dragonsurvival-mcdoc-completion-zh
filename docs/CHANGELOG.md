# 更新日志

此处包含了该项目的所有变更历史，对于未进行git控制的版本(v2.0.0之前)可在这里找到:
- [蓝奏云](https://wwq.lanzouo.com/b014wp9spg) 密码:5bzn

---

## v2.0.4 - 2026-02-17
> 该版本适用于 [DragonSurvival-1.21.1-v2.0.52-11.12.2025-all](https://www.curseforge.com/minecraft/mc-mods/dragons-survival/files/7320820) 版本及以上

- 更改了部分注释，让它们更符合自己的作用

- 数据包部分
   - 添加食物列表中漏掉的 `retain_effects` 参数
   - 通过确认源代码纠正大部分概率参数错误的默认值提示
   - 将 `dragon_ability` 中 技能等级贴图的数量设为必须大于1，以同步游戏的警告
   - 将 `dragon_ability` 中`Sound`与`Animations`的looping键进行拆分，looping键只在passive与channeled类的技能中可用
   - 修复 `projectile_data` 中 `general_data.entity_hit_condition` 值的错误，他应该接受 LootCondition 或 [LootCondition] 不接受空元素 {}

## v2.0.3 - 2025-12-17

> 该版本适用于 [DragonSurvival-1.21.1-v2.0.52-11.12.2025-all](https://www.curseforge.com/minecraft/mc-mods/dragons-survival/files/7320820) 版本及以上  

### **错误修复**:

- 为整个工具中缺少默认值提示的可选布尔项增加了默认值提示

- 资源包部分
   - 重新调整了部分值的说明，使其更清晰

- 数据包部分
   - 修正了 projectile_data 缺失的 `is_impact_projectile` 参数
   - 修正了 `data_maps` 中物种会对标签报错的问题
   - 修正了 `dragon_ability` 中错误的 `probability` 必选项，已更改为可选项
   - 修正了 `dragon_ability` 中 entity_effect 下的 dragonsurvival:cooldown_recovery 行为的 `abilities` 项使用的错误参数id`dragonsurvival:ability`，已更改为正确的 `dragonsurvival:dragon_ability`
   - 修正了 `dragon_ability` 中 entity_effect 下的 dragonsurvival:cooldown_recovery 行为的 `action_type` 项存在的错误参数 `add`, 已更改为 `reduce`

### **新增功能**:

- 数据包部分
   - 对于 `dragon_ability` 新增接口支持
      - `dragonsurvival:passive` 触发器新增选项
         - `dragonsurvival:on_block_break` 当破坏方块时触发
         - `dragonsurvival:on_key_pressed` 当按下按键时触发
         - `dragonsurvival:on_key_released` 当松开按键时触发
      - `dragonsurvival:block_vision` 让指定方块生成粒子进行标记
         - 增加参数 `particle_rate`粒子速率 、 `color_shift_rate`颜色变化速率
         - 为参数`colors`增加新的内容可以为颜色设置透明度
         - 为参数`display_type`增加了新的类型 `simple_shader`在方块表面简单的覆盖一层着色
      - `dragonsurvival:item_conversion` 转换物品实体的物品类型
         - 为 `item_conversions.items_to` 增加新参数 `conversion_rate`转换量、`particles`粒子

## v2.0.2 - **紧急修复** - 2025-11-30

> 该版本适用于 [DragonSurvival-1.21.1-v2.0.49-29.11.2025-all](https://www.curseforge.com/minecraft/mc-mods/dragons-survival/files/7274907) 版本及以上  

- **修复**: 
   - 实体子谓词 `dragonsurvival:dragon_predicate` 中 `ability_levels` 参数的数据应为列表包裹的struct, 这里错误的设为了struct。这会导致包含该错误的谓词失效

## v2.0.1 - 2025-11-30

> 本次更新适用于 [DragonSurvival-1.21.1-v2.0.49-29.11.2025-all](https://www.curseforge.com/minecraft/mc-mods/dragons-survival/files/7274907) 版本及以上  

### **新增功能**

   - 资源包部分
     - 对于 `parts` 增加了新的可选参数 `is_glowing`
   
   - 数据包部分
     - 对于谓词
       - `dragonsurvival:dragon_predicate` 子谓词
         - 增加了 `ability_levels` 检查技能/能力等级
     - 对于命令
       - `dragon-ability` 增加了 `query` 查询语句
     - 对于 `dragon_ability` 新增接口支持
       - `dragonsurvival:damage` 的更改错误的在上一个版本过早的提交;
       - `dragonsurvival:damage` 简化了 `expression` 参数的描述直接指向[链接](https://ezylang.github.io/EvalEx/references/references.html)

## v2.0.0 - 2025-11-26

> 本次更新适用于 [DragonSurvival-1.21.1-v2.0.48-23.11.2025-all](https://www.curseforge.com/minecraft/mc-mods/dragons-survival/files/7253527) 版本及以上  
> 
> ⚠️由于增加了新的资源索引，并且改进了核心的更新管理方法，如果你从**上一个版本**甚至**更早的版本**进行了更新，请务必重新安装该工具包

### **新增资源包支持**
   - 新增资源包支持: 增加了对资源包的补全提示支持
   - `spyglass.json`文件更新: 为资源包部分增加了新的资源索引(详见该文件的`$.env.customResources`参数)

### **更新安装方法**

   - 重新划分安装步骤，为了:
     - 支持资源包补全提示功能
     - 方便版本更新，减少所需步骤

### **新增功能**

   - 资源包部分
     - `custom_soul_icons` 自定义龙魂图标支持
     - `geo` 对模型的引用支持
     - `skin/default_parts` 皮肤-默认组件支持
     - `skin/parts` 皮肤组件支持

   - 数据包部分
     - 对于 `dragon_penalty` 新增接口支持:
       - `dragonsurvival:modifier` 添加[生物属性](https://zh.minecraft.wiki/w/属性)修改
       - `dragonsurvival:effect_modification` 修改状态效果的持续时间和等级
       - `dragonsurvival:run_function` 运行函数
     - 对于 `dragon_ability` 新增新接口支持：
       - `entity_effect` 部分:
         - `dragonsurvival:damage` 造成伤害 - 新增参数:
            - `scale` 伤害缩放属性
            - `expression` 计算最终伤害值的数学公式
            - `use_claw` 是否在造成伤害时临时装备龙爪上的工具
         - `dragonsurvival:summon_entity` 召唤实体 - 补齐参数:
            - `nbt` 调整召唤实体的nbt
         - `dragonsurvival:mana_recovery` 恢复魔法值 - 补齐参数:
            - `probability` 触发概率
         - `dragonsurvival:experience` 调整玩家经验值
         - `dragonsurvival:cooldown_recovery` 能力/技能冷却时间恢复
       - `block_effect` 部分:
         - `dragonsurvival:summon_entity` 召唤实体 - 新增参数:
            - `nbt` 调整召唤实体的nbt

   - 默认资源部分
     - 对于 `mob_effect` 新增效果
       - `dragonsurvival:empowered_soul` 灵魂充盈
       - `dragonsurvival:exhausted_soul` 灵魂枯竭

## v2.0.0-alpha.1 - 2025-11-21

1. **新增资源包支持**
   - 由于这是一个新功能，你需要完全重新安装该工具包
2. **更新安装方法**
   - 重新划分安装步骤以适配资源包补全提示支持
3. **新增功能**
   - 资源包部分
     - `custom_soul_icons` 自定义龙魂图标支持
     - `geo` 对模型的引用支持
     - `skin/default_parts` 皮肤-默认组件支持
     - `skin/parts` 皮肤组件支持
   - 数据包部分
     - 对于 `dragon_penalty` 新增接口支持:
       - `dragonsurvival:modifier` 添加[生物属性](https://zh.minecraft.wiki/w/属性)修改
       - `dragonsurvival:effect_modification` 修改状态效果的持续时间和等级
       - `dragonsurvival:run_function` 运行函数

## v1.3.0 - 2025-11-19

1. **更新安装方法**
   - 已更新了新的安装方法，你可以删除旧的安装按照新方法重新安装一次
   - 相比于旧的方法：
      - **更便捷**：更新补全包只需要在核心位置覆盖安装一次，不用全部项目都操作一遍，这样就不用担心各个附属项目中该工具的版本不一致乱糟糟的了
      - **更方便**：出现了新的附属，你希望解包他并用该工具进行参考，或者你新建了一个项目，你只需要按照教程中**将补全功能链接到新的附属数据包**的步骤简单的复制替换一下即可生效
      - **更稳定**：旧的方法有时候会因为链接龙生 Mod 导致嵌套调用，龙生 Mod 会因此变得无法进行补全
2. **错误修复**
   - 重新编写了 `dragon_ability` 中 `dragonsurvival:harvest_bonus` 的参数描述，让它们更易懂些
   - 为 `dragon_body` 添加了缺少的 `texture_size` 参数
   - 修正了 `dragon_ability` 中 `entity_effect` 下的 `dragonsurvival:effect_removal` 错误地将 `categories` 指定为元组，已替换为列表
   - 修正了 `dragon_ability` 中 `entity_effect` 下的 `dragonsurvival:effect_removal` 错误地将 `max_amount` 与 `maximum_effect_level` 指定为必选
   - 修正了 `dragon_ability` 中 `entity_effect` 下的 `dragonsurvival:use_item` 错误地将 `sound` 与 `valid_entities` 指定为必选
   - 添加了 `dragon_stage` 中 `destruction_data` 项缺失的键：
      - `block_predicate` - 决定龙行走时能够破坏的方块
         - `entity_predicate` - 决定龙行走时碾压伤害作用的实体
3. **新增功能**
   - 对于 `dragon_ability` 新增新接口支持：
      - `block_effect` 部分:
         - `dragonsurvival:use_item` - 使用物品
         - `dragonsurvival:explosion` - 造成爆炸
         - `dragonsurvival:block_harvest` - 方块采集
      - `entity_effect` 部分:
         - `dragonsurvival:mana_recovery` - 恢复魔法值
   - 对于 `predicate` 新增新接口支持：
      - 实体子谓词 `dragonsurvival:custom_predicates`
         - `looking_at_block` - 用于判断实体是否看向特定的方块

## v1.2.2 - 2025-10-28

- 更改了部分注释，让它们更符合自己的作用
- 修复了最近一次 `vanilla-mcdoc-main` 仓库更新导致粒子相关的注册罢工的问题：
  - 将 `use ::java::data::enchantment::SpawnParticlesEntityEffect` 更换成了 `use ::java::data::enchantment::effect::SpawnParticlesEntityEffect`
- 增加了对 `DragonSurvival-1.21.1-v2.0.37-21.10.2025` 中为 DragonPredicate 中添加的新的 `isFlying` 谓词支持，这用于检测龙是否被视为飞行

## v1.2.1 - 2025-10-8

- 更改了部分注释，让它们更符合自己的作用
- 新增了对龙之生存命令的支持

## v1.2.1-alpha.1 - 2025-10-1

- 新增了对龙之生存命令的支持

## v1.2.0 - 2025-09-30

- 更改了部分注释，让它们更符合自己的作用
- 将 `data_map.mcdoc` 的内容修改回了官方的样例，之前的文件缺少了一些没有注意到的细节问题，也不够规整，不方便维护
- ⚠️ 这次更改需要删除 `mcdoc` 文件夹重新解压，不然会出现重定义错误

## v1.1.4 - 2025-9-29

- 更改了部分注释，让它们更符合自己的作用
- 修改了 `dragon_ability.mcdoc` 中错误的 `BlockPredicate` 引用，应该引用自 `::java::data::worldgen::feature::block_predicate::BlockPredicate`

## v1.1.3 - 2025-09-28

- 增加了对 `max_duration` 键的支持，用于限制 `channeled` 类技能的持续时间
- 增加了对 `DragonSurvival-1.21.1-v2.0.36-26.09.2025-all` 新内容 `trigger_point` 键的支持（[来源](https://www.curseforge.com/minecraft/mc-mods/dragons-survival/files/7036245)），会根据 `$.activation.activation_type` 的内容自动补全与提示
- 修复了 `projectile_data` 中 `$.general_data.common_hit_effects[*]`、`$.general_data.ticking_effects[*]`、`$.type_data.on_destroy_effects[*]` 的 `.general_data.effects[*].effect` 项出现的补全错误（表现为 `world_effect`、`block_effect`、`entity_effect` 从预期的单选变为多选，且内联内容无法正常跳转）
- 去除了大部分引用 `enum(string)` 项的 `#[id]` 标签，让这些项可以在补全时给出提示（你需要在进行补全时将鼠标悬停至给出项上，点击项右侧的 `>` 符号）

## v1.1.2 - 2025-09-23

- 增加了对缺少的 `data\<命名空间>\data_maps\dragonsurvival\dragon_species\end_platforms.json` 的补全支持
- 更改了 `mcdoc\data\data_maps\dragonsurvival\dragon_species\dragon_species.mcdoc` 中物种 ID 的结构体内容，现在各类 JSON 的内容只能独立存在，但是由于 Spyglass 的 `identifier` 功能仍未完善，还不能精确到 JSON 文件

## v1.1.1 - 2025-09-20

- 将 `dragonsurvival:generic_arrow_entity` 与 `dragonsurvival:generic_ball_entity` 的 MCDoc 移动到了独立的文件夹中
- 添加了对龙之生存成就触发器的补全功能
- 添加了龙之生存 Mod 数据内这些资源的 ID 自动补全，详见 `spyglass/registries.json`：
  - `attribute` - 生物属性
  - `entity_type` - 生物 ID
  - `entity_sub_predicate_type` - 实体子谓词
  - `mob_effect` - 药水效果
  - `particle_type` - 粒子效果
  - `trigger_type` - 成就触发器
- 修正了一些键错误的描述信息
- 修正了实体 `dragonsurvival:generic_ball_entity` 的 NBT 数据补全，先前的版本错误地使用了 `use ::java::world::entity::projectile::arrow::ArrowBase` 的内容，并缺少了一些 NBT 项
- 修改了 `必看.txt` 的内容

## v1.1.1-alpha.1 - 2025-09-17

- 添加了龙之生存 Mod 数据内这些资源的 ID 自动补全，详见 `spyglass/registries.json`：
  - `attribute` - 生物属性
  - `entity_type` - 生物 ID
  - `entity_sub_predicate_type` - 实体子谓词
  - `mob_effect` - 药水效果
  - `particle_type` - 粒子效果
  - `trigger_type` - 成就触发器
- 修改了 `必看.txt` 的内容

## v1.1.0 - 2025-09-16

⚠️ 如果你从**上一个版本**甚至**更早的版本**进行了更新，请务必进行如下操作，不会损坏你的项目！

1. 将龙之生存 Mod 中的 `data`、`assets` 文件夹以及 `pack.mcmeta` 文件解压至一个纯英文的路径下（例如：`D:/Minecraft/DragonSurvival-Mod/`）
2. 在 `spyglass.json` 文件的 `$.env.dependencies` 项中添加上一步解压的路径（⚠️ 路径仅接受 `/`，不接受 `\`）（例如：`"file:///D:/Minecraft/DragonSurvival-Mod/"`，在此路径下你能直接看到 `data` 与 `assets` 文件夹）
3. 重启 VSCode

🤔 如果你的数据包存在配套的资源包，请你进行如下操作以启用**配套资源文件名补全**与 **`Ctrl + 左键` 文件跳转**功能：

1. 获取你的资源包路径，下面是案例：（⚠️ 路径仅接受 `/`，不接受 `\`）
   - 假设是文件夹：`"D:/Minecraft/.minecraft/versions/SpeciesCreation/resourcepacks/TestSpecies/"`（在此路径下你能直接看到 `assets` 文件夹）
   - 假设是压缩包：`"D:/Minecraft/.minecraft/versions/SpeciesCreation/resourcepacks/TestSpecies.zip"`
2. 在 `spyglass.json` 文件的 `$.env.dependencies` 项中添加路径，下面是案例：（⚠️ 路径仅接受 `/`，不接受 `\`）
   - 假设是文件夹：`"file:///D:/Minecraft/.minecraft/versions/SpeciesCreation/resourcepacks/TestSpecies/"`
   - 假设是压缩包：`"file:///D:/Minecraft/.minecraft/versions/SpeciesCreation/resourcepacks/TestSpecies.zip"`
3. 重启 VSCode

🫤 如果**配套资源文件名补全**与 **`Ctrl + 左键` 文件跳转**不工作，请你执行以下操作：

1. 在工作区按下 `Ctrl + Shift + P`
2. 搜索 `Spyglass: Reset Project Cache` 并执行
3. 等待项目缓存重置完成
4. 重启 VSCode

😅 如果你看不懂，那么请你先去**了解**或**搜索**以下内容：

1. 计算机的**文件路径**或**文件夹路径**如何表示
2. 如何解压缩压缩包（Mod 文件可以直接用压缩软件打开）
3. **JsonPath**（如果你看不懂类似 `$.env.dependencies` 这样的结构）
4. **JSON** 如何在**列表**或**数组**中填入字符串

其他更新

- 添加了更多的资源跳转链接
- 继续补齐了更多的键的悬停注释
- 为需要 [谓词、自定义字体、码位字符串、等级依赖函数、伤害类型、生物属性] 的键添加了指向 Wiki 的链接
- 为龙之生存的实体子谓词 `dragonsurvival:custom_predicates` 添加了缺少的 `player_hunger` 与 `health_percentage` 项
- 修改了 `必看.txt` 的内容

## v1.0.3 - 2025-09-14

继续补齐了更多的悬停注释
为龙之生存的实体子谓词`dragonsurvival:custom_predicates`添加了缺少`player_hunger`与`health_percentage`项

## v1.0.2 - 2025-09-13

⚠️ 需要在更新后进行如下操作，该操作主要用于重置旧的数据缓存，不会损坏你的项目！

1. 在工作区按下 `Ctrl + Shift + P`
2. 搜索 `Spyglass: Reset Project Cache` 并执行
3. 等待项目缓存重置完成
4. 重启 VSCode

其他更新

- 新增了对标签目录 `tags\dragonsurvival` 下资源的 `Ctrl + 右键` 跳转
- 修复了 `data/dragonsurvival/dragon_species` 中对正确资源的错误提示

## v1.0.1 - 2025-09-12

- 修复了缺少的 `dragon_ability`、`dragon_body`、`dragon_emote_set`、`projectile_data` 项的资源跳转
- 将 `dragon_ability.mcdoc` 中错误的必填数据改为选填
- 新增了 `dragon_ability.mcdoc`、`projectile_data.mcdoc` 中的提示信息
- 新增了 `tags/dragonsurvival` 路径下标签文件的项目提示

## v1.0.0 - 2025-09-11

- 初始版本
