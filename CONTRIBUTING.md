# **CMI Github仓库管理协议**

<div align="left">

### `Create: Mechanism and Innovation`(下文称`CMI`)版本号协议

 - `CMI`版本号码由大中小版本号组成

 - `CMI`大、中版本号码由主创`Unknown_Entity_`进行规定。

 - 技术人员每次上传涉及游戏内代码的更新时，须相对当前小版本号进一位再上传。

 - 版本号在[**Global.js**](kubejs/startup_scripts/Global.js)中撰写与修改。

### GitHub仓库修改注释协议

 - GitHub每次进行修改上传(即`push origin`)需要输入该次修改的注释，包含`summary`与`description`。

 - 自本协议生效开始，所有修改的`summary`统一为版本号码。

 - 技术人员在上传的`description`中需使用中文或英语概述该次修改的内容

### 开发规范

 - 所有的类名和Java一样, 大驼峰命名法(单词首字母大写), 例如`GetDateModifyTitle`, `RecipeSchema`

 - 所有的函数名与变量名与Java一样, 小驼峰命名法(单词首字母小写), 例如`getDateModifyTitle`, `recipeSchema`

 - 在每次进行Dev之前先同步一下仓库, 避免改动覆盖或被覆盖

 - 每一个和配方相关的脚本必须进行一次解构, 结构完后才可以进行配方的编写

```js
ServerEvents.recipes((event) => {
	let { create, kubejs, minecraft, namespace... } = event.recipes
})
```

 - 在进行所有的有序配方, 包括`kubejs:shaped`, `minecraft:crafting_shaped`, `create:mechanical_crafting`等一系列包括了`pattern`的配方类型时, 必须按照下方的格式进行修改, 以此除外的所有格式均不接受

```js
kubejs.shaped("minecraft:stone", [
	"AAA",
	"BBB",
	"CCC"
], {
	A: "minecraft:sand",
	B: "minecraft:gravel",
	C: "#forge:ingots/copper"
})
```

- 在注册东西的时候, 统一使用下方格式, 并且链式方法必须换行使用

```js
event.create(`${global.namespace}:id`)
	.tag()
	.texture()
```

### `Code`公有化协议

 - 所有Code在上传至GitHub仓库后，将会视为由`CMI Dev Team`所有成员共同拥有。

 - `Dev Team`所有成员拥有平等的修改与替换相关代码、材质等内容的权利。

 - 实行该权力的成员需要履行将内容优化修改的义务。

### 版本更新与todo协议

 - 主创`Unknown_Entity_`拥有所有版本号的最终解释权，并且拥有下一个版本更新内容的决定权。

 - 每个版本完成后，`Unknown_Entity_`将会汇总下一个版本的计划更新内容并由`Dev Team`成员上传GitHub的`Projects/`[**CMI development follow-up**](https://github.com/users/VechniMetel/projects/1/views/1)。

 - todo list全部完成并优化完毕后，GitHub仓库将会提升一位版本号并等待主创的下一个todo list

### 更新日志记录

 - 每次做出一个修改(看情况区分)需要再[**UpdateLogs.md**](UpdateLogs.md)中写上记录, 格式如下(每一行的`-`前后请记得空一个空格)

```md
## Beta X.x.x
 - 修复了XXX配方阶段不合理
 - 修复了某某Tags不兼容的问题
 - 修复了某物品没有适合的Tags的问题

 - 添加了XXX匠魂材料
 - 添加了XXX配方
 - 添加了XXX体系

 - 删除了XXX配方
 - 删除了XXX的掉落
 - 删除了XXX的一切可获得方式
```

</div>