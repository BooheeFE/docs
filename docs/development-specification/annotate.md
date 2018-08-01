## 注释规范 {docsify-ignore}
注释虽然写起来很痛苦, 但对保证代码可读性至关重要，可降低后期维护的代价。

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
