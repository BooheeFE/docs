## 命名规范 {docsify-ignore}
规范、语义化的命名让别人肃然起敬、好感倍增

### 项目
- 字母小写；
- 不能有空格；
- 多个单词采用中划线。
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

### 变量
- 小驼峰：首字母小写；
- boolean 类型的变量使用 is 或 has 开头。
```javascript
let userInfo = 'boohee';
let isReady = false;
```

### 常量
- 全部大写；
- 多个单词采用下划线。
```javascript
const URL = 'http://www.boohee.com';
const MAX_COUNT = 10;
```

### 函数
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

### 类及成员
- 类，大驼峰：首字母大写；
- 私有属性和方法：加下划线（_）前缀。

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