# 内容列表

## base

### 1. isNumber(data)

判断是否是数值

### 2. isString(data)

判断是否是字符串

### 3. isBoolean(data)

判断是否是布尔值

### 4. isUndefined(data)

判断是否未定义

### 5. isNull(data)

判断是否是null

### 6. isObject(data)

判断是否是对象

### 7. isArray(data)

判断是否是数组

### 8. isFunction(data)

判断是否是函数

## string

### 1. deleteSpace(data)

删除对象或数组字符串项两侧的空白字符

### 2. deleteStrSpace(data)

删除字符串两端的空白字符。这个方法没太大意义，可以直接在字符串上调用 trim 方法。

## array

### 1. fill(arr, value, start, end, replace)

填充数组--返回值是原数组

arr: 要填充的数组

value: 要填充的值

start: 开始填充的位置，可选，默认0

end: 结束填充的位置，可选，默认最后一个元素

replace: 是否替换现有值，可选，默认不替换

## object

### 1. filterProperties(source, reserveProperties)

对对象/数组进行过滤，保留指定的属性。source 是源对象，reserveProperties 是字符串数组，元素是指定的属性名

### 2. transferProperties(source, transferProperties)

对对象/数组进行转换，替换字段名。

## functions

### 1. deleteInfo(self, itemName, uuid, callback)

element ui 增强--删除信息确认框

self: 上下文

itemName: 待删除信息名称，用来显示在弹出框中

uuid: 待删除信息uuid

callback：请求函数

## date

### 1. parseTime(time, cFormat)

时间转换

time: 时间

cFormat: 要转换的格式--默认：'{y}-{m}-{d} {h}:{i}:{s}'

### 2. initDate(time)

将字符串类型的时间‘2019-01-01 01:01:01’转成 date 对象。如果是空字符串，返回值也是空字符串。

time：时间字符串

## validate
> 单独引入的时候用全名，全部引入的时候用简写——省略‘validate’

### 1. validateURL(str)

验证url

### 2. validateLowerCase(str)

验证小写字母

### 3. validateUpperCase(str)

验证大写字母

### 4. validateAlphabets(str)

验证大小写字母

### 5. validateEmail(str)

验证邮箱

### 6. validateMobile(str)

验证手机号

### 7. validatePositiveIntegerNonzero(str)

验证非零正整数

### 8. validateNegativeIntegerNonzero(str)

验证非零负整数

### 9. validatePositiveInteger(str)

验证非负整数

### 10. validateNegativeInteger(str)

验证非正整数

### 11. validatePwd(str)

验证密码（6-20位数字字母）

### 12. validateNotEmpty(str)

验证非空

### 13. validatePhone(str)

验证联系方式（电话或手机）

### 14. validateLongitude(str)

验证经度

### 15. validateLatitude(str)

验证纬度

### 16. validateDate(str)

验证日期

### 17. validateFloatZ(str)

正浮点数验证

### 18. validateNumberZ(str)

验证1-无穷大整数

## tree

### 1. treeSelect(obj, checkedObj, para)

element ui tree 组件增强: 多选框选择-父子联动。

obj: element ui tree 组件 check 事件返回的传递给 data 属性的数组中该节点所对应的对象

checkedObj: element ui tree 组件 check 事件返回的第二个参数：树目前的选中状态对象，包含 checkedNodes、checkedKeys、halfCheckedNodes、halfCheckedKeys 四个属性

para: 自定义参数，包括 single 和 tree 两个属性。single 表明是否单选 true：单选，false：多选。tree 是 tree 组件元素的引用。比如 this.$refs.tree

### 2. treeSelectNoLinkage(obj, checkedObj, para)

element ui tree 组件增强：多选框选择-父子不联动

参数解释同上

### 3. showBack(tree, checked)

element ui tree 组件增强：回显

tree: tree 组件元素的引用。比如 this.$refs.tree

checked: 选中节点或id数组

**可以用 tree 组件的默认选择属性代替此方法**

### 4. findNodeInTree(tree, key, value, childNodeName)

对树进行查找，找到则返回节点，否则返回false。

tree: 树--数据集合，不是元素引用

key：查找键名

value: 查找键值

childNodeName: 子节点名称

### 5. findNodeInTreeDeep(tree, key, value, childNodeName)

对树进行深度查找，找到则返回节点数组，否则返回空数组。

参数解释同上

### 6. setProperty(tree, oldProperty, newProperty, childNodeName, callback)

根据指定属性给树添加属性

tree: 树数据

oldProperty: 旧属性

newProperty：新属性

childNodeName: 子节点名称

callback: 可选参数，转变过程中的回调函数，参数是旧值，返回值是新值

### 7. setPropertyFromParent(tree, parentProperty, childProperty, childNodeName)

给树中的节点添加需要的父属性

tree: 树数据

parentProperty: 父节点属性名称

childProperty: 需要添加的子节点属性名称

childNodeName: 子节点名称

### 8. plainTree(tree, childNodeName)

将树扁平化，返回元素组成的一维数组

tree: 树数据

childNodeName: 子节点名称

### 9. treeNodeNumber(tree, childNodeName)

统计树有多少个节点

tree: 树数据

childNodeName: 子节点名称

### 10. deleteEmptyChildNode(tree, childNodeName)

删除空的子节点--此方法不一定有用

tree: 树数据

childNodeName: 子节点名称

### 11. getLastLevel(tree, childNodeName, key, value)

获取树中最后一级的节点

tree: 树数据

childNodeName: 子节点名称，可选，默认 ‘children’

key: 筛选键名，可选

value: 筛选键值，可选

## UI
> 组件需要单独引入
> - 一次性引入全部组件：
```
import ui from 'tiny-utils.js/UI'
Object.keys(ui).map(item => {
  Vue.component(item, ui[item])
})
```
> 这种情况，组件标签格式类似这种：`<tu-svg-icon />`
> - 单独引入某个组件
```
import SvgIcon from 'tiny-utils.js/UI/SvgIcon'
Vue.component('SvgIcon', SvgIcon)
```

### 1. SvgIcon

svg 图标组件。项目需要安装 svgo 和 svg-sprite-loader 包，配置 webpack 文件。

属性：

|名称|值|说明|
|-|-|-|
|icon-class|String|svg 图标名称，不需要后缀|
|class-name|String|样式类名|

### 2. Book

电子书组件。需要依赖于`kim-vue-touch`包。需要说明的是，这个组件并没有真正解决文本分页问题。此外，这个组件……慎用。并没有进行严格测试，可能有bug。

属性：

|名称|值|说明|
|-|-|-|
|text|String|需要显示的文本|
|title|String|文本标题，显示在封面上，封面配置在下面。|
|percent|Number|阅读进度。为0时代表在封面，超过100时在封底。|
|width|Number|电子书宽度，单位为px。|
|height|Number|电子书高度，宽度为px。|
|single|Boolean|显示模式，true为单页，false为双页。默认双页。|
|pagePadding|[Number, Array]|页面padding。数组需要四个值，否则可能与预想的不同。此外，底部padding的值也是页码区域的高度。|
|showPageNumber|Boolean|是否显示页码。默认显示。|
|pageSeparator|String|页码分割线。默认：‘ / ’。比如：1 / 2|
|fontSize|Number|字体大小。单位px。默认16。|
|lineHeight|Number|行高。单位px。默认24。这个效果比较迷，某些行高会导致页面错位。|
|color|String|文字颜色。默认‘#333’|
|background|String|页面背景。默认‘seashell’。可以是css颜色值，也可以是有效的图片路径。|
|cover|String|封面配置。默认不显示。如果是长度不为零的空字符串，会显示封面和标题，默认背景为灰色。如果是非空字符串（图片路径），标题则不显示，显示指定图片。|
|backCover|String|封底配置。和封面差不多。|

事件：

|名称|参数|说明|
|-|-|-|
|pageChange|(Object)|初始化和页码改变时触发。对象有三个值：page--当前页；total--总页数；percent--进度。|


## directive
> 指令需要单独引入。
> - 一次引入全部指令：
```
import directives from 'tiny-utils.js/directive'
Object.keys(directives).map(item => {
  Vue.directive(item, directives[item])
})
```
> 这种情况，指令名称格式类似这种：v-tu-loading。
> - 单独引入某条指令
```
import loading from 'tiny-utils.js/directives/loading'
Vue.directive('tuLoading', loading)
```

### 1. v-tu-loading

加载动画指令。默认白色背景，紫色加载圆圈。可自定义样式覆盖。外层样式名是‘.tu-loading’，内部圆圈样式名是‘.tu-loading-round’，加载文字样式名是‘.tu-loading-text’。

tu-loading-text: 在元素上设置此属性，则显示加载文字，而不是圆圈。比如：tu-loading-text="Loading……".

### 2. v-tu-waves

点击波纹指令。默认透明黑色。波纹样式名是‘.tu-waves-ripple’, 波纹动画样式名是‘.z-active’--实际是‘.tu-waves-ripple.z-active’。

指令的值是个对象，内容为配置项：

|属性|值|说明|
|-|-|-|
|el|Object|波纹作用元素|
|type|String|扩散类型，'hit': 点击处扩散，'center': 中心扩散|
|color|String|波纹颜色，比如：'purple'|

### 3. v-tu-bubble

文字气泡指令（并不清楚应该叫什么，暂时先这样）。文字样式名是‘.tu-bubble’，动画时的样式是‘.tu-bubble-hidden’。

指令的值是个对象，内容为配置项：

|属性|值|说明|
|-|-|-|
|text|Array|文字数组，比如：['tiny', 'utils', 'js]|
|color|Array|颜色数组，比如：['red', 'purple', 'blue']|
|duration|Number|动画持续时间，单位是毫秒|
|delay|Number|动画延迟时间，单位是毫秒|
|distance|Number|动画时间内运动距离，单位是像素|
|offset|Array|文字偏移位置，元素是数字，单位是像素。分别是 x 轴，y 轴。|