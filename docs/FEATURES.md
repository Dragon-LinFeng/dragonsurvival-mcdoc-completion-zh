
# 功能特性详情

## 数据包JSON补全

其中`资源数据映射`由于Spyglass的`identifier`功能仍未完善，所以无法精确匹配文件

| 支持的功能        | 功能对应的路径                  |
| ----------------- | ------------------------------- |
| 资源数据映射      | data/<命名空间>/dragon_ability  |
| 能力/技能         | data/<命名空间>/dragon_ability  |
| 身体类型/子物种   | data/<命名空间>/dragon_body     |
| 龙表情            | data/<命名空间>/dragon_emote_set|
| 物种缺陷/缺陷     | data/<命名空间>/dragon_penalty  |
| 物种数据          | data/<命名空间>/dragon_species  |
| 成长阶段          | data/<命名空间>/dragon_stage    |
| 自定义弹射物      | data/<命名空间>/projectile_data |
| 龙之生存自定义标签| data/<命名空间>/tags/dragonsurvival |

## 资源包JSON补全

其中`生物模型`仅添加引用

| 支持的功能        | 功能对应的路径                     |
| ----------------- | ---------------------------------- |
| 自定义龙魂图标    | assets/<命名空间>/custom_soul_icons|
| 生物模型          | assets/<命名空间>/geo              |
| 默认组件          | assets/<命名空间>/skin/default_parts|
| 皮肤组件          | assets/<命名空间>/skin/parts       |

## 龙生Mod新增实体NBT

限于精力，只支持用于数据包制作的自定义弹射物

| 支持的实体          | 实体对应的ID                        |
| ------------------- | ----------------------------------- |
| 自定义箭类弹射物    | dragonsurvival:generic_arrow_entity |
| 自定义火球类弹射物  | dragonsurvival:generic_ball_entity  |

## 龙生Mod新增/修改的游戏内容

其中`生物ID`仅添加用于数据包制作的自定义弹射物

| 支持的功能      | 功能对应的ID              |
| --------------- | ------------------------- |
| 生物属性        | attribute                 |
| 生物ID          | entity_type               |
| 实体子谓词      | entity_sub_predicate_type |
| 药水效果        | mob_effect                |
| 粒子效果        | particle_type             |
| 成就触发器      | trigger_type              |
