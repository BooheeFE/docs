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
<div class="modA">
    ...
</div>
<!-- E Modules A -->
	
<!-- S Modules B -->	
<div class="modB">
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
<div class="modA">
		
    <div class="modB">
        ...
    </div>
    <!-- /Modules B -->
    	
    <div class="modC">
    	...
    </div>
    <!-- /Modules C -->
		
</div>
<!-- E Modules A -->
```