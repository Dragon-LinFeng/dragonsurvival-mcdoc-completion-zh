# 安装使用指南

## 前置条件

### 安装 VSCode

下载并安装 [VSCode](https://code.visualstudio.com/)，**并在安装过程中勾选**：
- ✅ 将"通过Code打开"操作添加到Windows资源管理器文件上下文菜单
- ✅ 将"通过Code打开"操作添加到Windows资源管理器目录上下文菜单

### 安装必要插件

安装 VSCode 拓展包：(标识符：`amandin.dpc-pack`)
> `amandin.dpc-pack`默认包含了Spyglass插件，如果你只需要补全服务可以仅安装 Spyglass  
> 标识符: `spgoding.datapack-language-server`

## 部署核心

> 在编写附属时一般会频繁的引用龙之生存Mod的资源，所以补全功能整合包需要一份解压后的龙之生存Mod作为核心

1. 将龙之生存 Mod 中的 `data`、`assets` 文件夹以及 `pack.mcmeta` 文件解压至一个纯英文的路径下（例如：`D:/Minecraft/DragonSurvival-Mod/`）
2. 将补全功能整合包内的所有文件与文件夹直接解压至刚才龙之生存 Mod 解压的根目录中
3. 至此你完成了核心的部署

## 配置依赖链接

### 为数据包链接核心

> 在你完成核心的部署后，接下来要做的就是将核心链接到你的数据包中启用补全功能了

1. 打开**你自己的附属数据包**根目录（即能直接看到数据包 `data` 文件夹的目录）
2. 将位于核心的 `spyglass.json` 文件复制到你的附属数据包根目录中
3. 在 `spyglass.json` 文件的 `$.env.dependencies` 项中添加**核心**的路径
    > 假设部署的核心位于`D:/Minecraft/DragonSurvival-Mod/`（在此路径下能直接看到 `data` 与 `assets` 文件夹）  
    > 那么你需要在此添加`"file:///D:/Minecraft/DragonSurvival-Mod/"`
4. 修改 `spyglass.json` 文件中的 `$.env.mcmetaSummaryOverrides.registries.path` 参数  
   链接核心 `spyglass` 文件夹下的 `registries.json`
    > 假设部署的核心位于`D:/Minecraft/DragonSurvival-Mod/`（在此路径下能直接看到 `spyglass` 文件夹）  
    > 那么你需要在此添加`"file:///D:/Minecraft/DragonSurvival-Mod/spyglass/registries.json"`
5. 修改 `spyglass.json` 文件中的 `$.env.mcmetaSummaryOverrides.commands.path` 参数  
   链接核心 `spyglass` 文件夹下的 `commands.json`
    > 假设部署的核心位于`D:/Minecraft/DragonSurvival-Mod/`（在此路径下能直接看到 `spyglass` 文件夹）  
    > 那么你需要在此添加`"file:///D:/Minecraft/DragonSurvival-Mod/spyglass/commands.json"`
6. 重启 VSCode

### 为资源包链接核心并串联数据包

> 在编写附属时，资源包和数据包一般是分开的。</br>
> 即 资源包位于`resourcepacks/` 而 数据包位于`saves/<世界名称>/datapack/` 的情况。</br>
> 如果不属于这种情况，你可以跳过这一步。

1. **为资源包链接核心**
   - 打开**配套资源包**根目录（即能直接看到资源包 `assets` 文件夹的目录）
   - 将上一步中已经设置好的 `spyglass.json` 文件复制到你的配套资源包根目录中
2. **让资源包与数据包相互链接起来**
   - 打开你**资源包**根目录的`spyglass.json`文件
   - 在 `spyglass.json` 文件的 `$.env.dependencies` 项中添加**配套数据包**的根目录地址
       > 假设配套的**数据包**是`D:/Minecraft/.minecraft/saves/SpeciesCreation/datapack/`路径下的`test_species`文件夹  
       > 那么你需要在此添加`"file:///D:/Minecraft/.minecraft/saves/SpeciesCreation/datapack/test_species"`
   - 打开你**数据包**根目录的`spyglass.json`文件
   - 在 `spyglass.json` 文件的 `$.env.dependencies` 项中添加**配套资源包**的根目录地址
       > 假设配套的**资源包**是`D:/Minecraft/.minecraft/resourcepacks/`路径下的`test_species`文件夹  
       > 那么你需要在此添加`"file:///D:/Minecraft/.minecraft/resourcepacks/test_species"`
3. 重启 VSCode

## 基础使用

1. 用VSCode打开你已链接好核心并串联好的的数据包/资源包根目录
2. 开始编写JSON文件，享受智能补全功能

## 参考 龙之生存本体 or 其他附属数据包

> 在编写自己的附属时你可能会有些不知所措，对此，你可以试着参考其他完整的项目

### **参考龙之生存本体**:
1. 当你安装好核心后直接用VSCode打开根目录即可

### **参考其他附属数据包**:
1. **确认许可**：确保你参考的附属模组允许解压缩用于学习
2. **解压参考模组**：将其解压到英文路径（例如`D:/MinecraftMod/example/`）
3. **配置补全**：按照安装指南的步骤配置 `spyglass.json` 文件
    > 这里有一个小技巧，如果你的核心没有改变位置，你完全可以直接复制之前已经配置好的`spyglass.json`文件，简单的修改一下就能使用了。

## 更新核心

### **更新补全工具包**

 - 打开最初安装的核心位置
 - 将新版本直接解压覆盖所有文件
 - 重启VSCode

### **更新解压的龙之生存mod**

 - 删除旧的 `data`、`assets` 文件夹以及 `pack.mcmeta` 文件
 - 重新解压新的 `data`、`assets` 文件夹以及 `pack.mcmeta` 文件
 - 重启VSCode

[➡️ 遇到问题？查看故障排除指南](TROUBLESHOOTING.md)
