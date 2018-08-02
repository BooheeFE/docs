## 命名规范 {docsify-ignore}
规范、语义化的命名让别人肃然起敬、好感倍增

### 项目
- 字母小写；
- 不能有空格；
- 多个单词采用中划线（-）。
```
vue-cli
create-react-app
```

### 文件夹
- 参照项目名规则；
- 有复数结构时，采用复数命名法。
```
images
data-models
```

### 文件
- 参照文件夹名规则；
- 特殊文件全大写。
```
README
LICENSE
CHANGELOG
```

### HTML
- HTML标签名、属性名统一用小写
```HTML
<div class="boohee" data-name="boohee">Boohee</div>
```

### CSS

#### 类名
- 在常规方案，比如vue、小程序等中，参考项目名规则；
- 在CSS Modules方案中，由于中划线（-）不能作为变量名，采用小驼峰；

```css
/**
 * 常规方案
 */
.boohee {}

.boohee-user {}


/**
 * CSS Modules
 */
.boohee {}

.booheeUser {}
```

#### SCSS
- SCSS中的变量、函数、混合、placeholder采用小驼峰式命名。

```css
/* 变量 */
$colorBlack: #000;

/* 函数 */
@function pxToRem($px) {
    ...
}

/* 混合 */
@mixin centerBlock {
    ...
}

/* placeholder */
%myDialog {
    ...
}
```

常用class名推荐

ClassName |	含义
:-- | :--
about | 关于
account | 账户
arrow | 箭头图标
article | 文章
aside | 边栏
audio | 音频
avatar | 头像
bg,background | 背景
bar | 栏（工具类）
branding | 品牌化
crumb,breadcrumb | 面包屑
btn,button | 按钮
caption | 标题，说明
category | 分类
chart | 图表
clearfix | 清除浮动
close | 关闭
col,column | 列
comment | 评论
community | 社区
container | 容器
content | 内容
copyright | 版权
current | 当前态，选中态
default | 默认
description | 描述
details | 细节
disabled | 不可用
entry | 文章，博文
error | 错误
even | 偶数，常用于多行列表或表格中
fail | 失败（提示）
feature | 专题
fewer | 收起
field | 用于表单的输入区域
figure | 图
filter | 筛选
first | 第一个，常用于列表中
footer | 页脚
forum | 论坛
gallery | 画廊
group | 模块，清除浮动
header | 页头
help | 帮助
hide | 隐藏
hightlight | 高亮
home | 主页
icon | 图标
info,information | 信息
last | 最后一个，常用于列表中
links | 链接
login | 登录
logout | 退出
logo | 标志
main | 主体
menu | 菜单
meta | 作者、更新时间等信息栏，一般位于标题之下
module | 模块
more | 更多（展开）
msg,message | 消息
nav,navigation | 导航
next | 下一页
nub | 小块
odd | 奇数，常用于多行列表或表格中
off | 鼠标离开
on | 鼠标移过
output | 输出
pagination | 分页
pop,popup | 弹窗
preview | 预览
previous | 上一页
primary | 主要
progress | 进度条
promotion | 促销
rcommd,recommendations | 推荐
reg,register | 注册
save | 保存
search | 搜索
secondary | 次要
section | 区块
selected | 已选
share | 分享
show | 显示
sidebar | 边栏，侧栏
slide | 幻灯片，图片切换
sort | 排序
sub | 次级的，子级的
submit | 提交
subscribe | 订阅
subtitle | 副标题
success | 成功（提示）
summary | 摘要
tab | 标签页
table | 表格
txt,text | 文本
thumbnail | 缩略图
time | 时间
tips | 提示
title | 标题
video | 视频
wrap,wrapper | 容器，包，一般用于最外层

### JavaScript

#### 变量
- 小驼峰：首字母小写；
- boolean 类型的变量使用 is 或 has 开头。
```javascript
let userInfo = 'boohee';
let isReady = false;
```

#### 常量
- 全部大写；
- 多个单词采用下划线。
```javascript
const URL = 'http://www.boohee.com';
const MAX_COUNT = 10;
```

#### 函数
- 小驼峰；
- 前缀为动词。

动词 | 含义 | 返回值
:--  |:--   | :--
can  | 判断是否可执行某个动作（权限） | 返回一个布尔值。true：可执行；false：不可执行
has  | 判断是否含有某个值 | 返回一个布尔值。true：含有此值；false：不含有此值
get  | 获取某个值 | 返回一个非布尔值
set  | 设置某个值 | 无返回值、返回是否设置成功或者返回链式对象
is   | 判断是否为某个值 | 返回一个布尔值。true：为某个值；false：不为某个值

```javascript
// 是否可阅读
function canRead() {
    return true;
}

// 获取名字
function getName(name) {
    return name;
}
```

#### 类及成员
- 类，大驼峰：首字母大写；
- 私有属性和方法：加下划线（*_*）前缀。

```javascript
class UserInfo(name) {
    let _name = name;
    
    this.getName() {
        return _name;
    }
}
```

### 特殊字符
```
Android
iOS
```

### 图片
图片命名建议以以下顺序命名：  
业务（可选）+ 模块名称（可选）+ 功能类别（必选） + 精度（可选） + 版本（可选）

###### 业务
- 淘宝：tb-
- 微信：wx-
- 京东：jd-
- ...

###### 模块名称
- 商品列表：goodsList-
- 商品信息：goodsInfo-
- 用户头像：userAvatar-

###### 功能类别
- 图标：icon-
- LOGO：logo-
- 按钮：btn-
- 背景: bg-
- ...

###### 图片精度
- 普请：@1x
- Retina：@2x | @3x
- ...

###### 版本
- 初始版本不需要加
- 第二版本：1
- 第二版本：2
- ...
```
tb-goodsList-btn.png // 淘宝商品列表按钮
boohee-logo@1x.png //普通清晰度度logo
pro-guide-bg.png // 付费版引导背景图
pro-guide-bg-1.png // 付费版引导背景图
```