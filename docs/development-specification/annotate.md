## 注释规范 {docsify-ignore}
- 规范、语义化的代码是最好的注释；
- 注释虽然写起来很痛苦, 但对保证代码可读性至关重要，可降低后期维护的代价

### HTML

#### 单行注释
- 一般用于简单的描述，如某些状态描述、属性描述等；
- 注释内容前后各一个空格字符，注释位于要注释代码的上面，单独占一行。

```HTML
<!-- Comment Text -->
<div>...</div>
```

#### 模块注释
- 一般用于描述模块的名称以及模块开始与结束的位置；
- 注释内容前后各一个空格字符，`<!-- S Modules Name -->` 表示模块开始，`<!-- E Modules Name -->`表示模块结束，模块与模块之间相隔一行。

```HTML
<!-- S Modules A -->	
<div class="mod-a">
  ...
</div>
<!-- E Modules A -->
	
<!-- S Modules B -->	
<div class="mod-b">
  ...
</div>
<!-- E Modules B -->
```

#### 嵌套模块注释
当模块注释内再出现模块注释的时候，为了突出主要模块，嵌套模块不再使用
```HTML
<!-- S Modules Name -->
<!-- E Modules Name -->
```
而改用
```HTML
<!-- /Modules Name -->
```
注释写在模块结尾标签底部，单独一行。

```HTML
<!-- S Modules A -->
<div class="mod-a">
		
  <div class="mod-b">
    ...
  </div>
  <!-- /Modules B -->
  	
  <div class="mod-c">
  	...
  </div>
  <!-- /Modules C -->
		
</div>
<!-- E Modules A -->
```

### CSS

#### 文件注释
- 在样式文件头部注明页面信息描述、作者、创建日期等信息。

```css
/**
 * @desc File Description
 * @author Author Name
 * @date 2018-08-01
 */
```

#### 模块注释
- 模块与模块之间相隔两行；
- 包含模块说明；
- 在组件化开发方案中，一个文件就是一个模块，这时候模块注释可直接写在文件注释内。

```css
/**
 * Module A
 */
.mod-a {}


/**
 * Module B
 */
.mod-b {}
```

#### 单行注释
- 单独占一行，行与行之间相隔一行；
- 包含单行样式说明。

```css
/* 输入框 */
.input-box {}

/* 提交按钮 */
.submit-btn {}
```

### JavaScript
###### 常用标签说明

标签 | 含义 | 示例
:-- |:-- | :--
@author  | 标识开发者信息 | @author 吴胜斌 code@simbawu.com
@class   | 表示这是一个类 | @class
@function| 表示这是一个方法 | @function
@param   | 标记方法参数及参数类型，可重复定义 | @param {number} name  用户昵称
@return  | 标记返回的类型 | @return {string}

###### 类型定义
- 类型定义都是以`{`开始, 以`}`结束；
- 对于基本类型 {string}, {number}, {boolean}，首字母必须小写。

类型定义 | 语法示例 | 解释 
:-- | :-- | :-- 
String | {string} |
Number | {number} |
Boolean | {boolean} |
Object | {Object} |
Function | {Function} |
RegExp | {RegExp} |
Array | {Array} |
Date | {Date} |
单一类型集合 | {Array.<string>} | string 类型的数组
多类型 | {(number｜boolean)}|可能是 number 类型, 也可能是 boolean 类型
允许为null | {?number}|可能是 number, 也可能是 null
不允许为null | {!Object}|Object 类型, 但不是 null
Function类型 | {function(number, boolean)} | 函数, 形参类型
Function带返回值 | {function(number, boolean):string} | 函数, 形参, 返回值类型
参数可选 | @param {string=} name | 可选参数, =为类型后缀
可变参数 | @param {...number} args | 变长参数,  ...为类型前缀
任意类型 | {*} | 任意类型
可选任意类型 | @param {*=} name | 可选参数，类型不限
可变任意类型 | @param {...*} args | 变长参数，类型不限

#### 文件注释
同CSS文件注释

#### 单行注释
- 双斜线后，必须跟一个空格；
- 缩进与下一行代码保持一致。

```javascript
if (condition) {
  // if you made it here, then all security checks passed
  allowed();
}
```

#### Function注释
- 函数简单描述
- 函数类型声明
- 参数类型、名字、解释
- 返回值类型

```javascript
/**
 * 获取用户信息
 * @function
 * @param {string} name 用户名字
 * @param {number} age 用户年龄
 * @return {object}
 */
function getUser(name, age){
  return {name: name, age, age}
}
```
#### Class类注释

```javascript
/**
 * Create a point.
 * @class
 * @param {number} x The x value.
 * @param {number} y The y value.
 */
class Point {
  constructor(x, y) {
    // ...
  }

  /**
   * Get the x value.
   * @return {number} The x value.
   */
  getX() {
    // ...
  }

  /**
   * Get the y value.
   * @return {number} The y value.
   */
  getY() {
    // ...
  }

  /**
   * Convert a string containing two comma-separated numbers into a point.
   * @param {string} str - The string containing two comma-separated numbers.
   * @return {Point} A Point object.
   */
  static fromString(str) {
    // ...
  }
}
```

