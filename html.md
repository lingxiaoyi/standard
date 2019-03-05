# HTML编码规范

## 一、模板规范

### PC页面模板【参考】

1. 指定文档类型（推荐使用 HTML5 的文档类型申明： &lt;!DOCTYPE html&gt;）
2. 指定文档编码为utf-8
3. 指定兼容方案
4. 编写网站关键字、描述信息、网站标题（[SEO优化](./seo.md)）
5. 页面头部&lt;/head&gt;标签前引入css样式文件，页面底部&lt;/body&gt;标签前引入js文件（提升网站性能和用户体验）

例：

```html
<!-- 推荐使用html5规范 -->
<!DOCTYPE html>　
<!-- 制定文档语言 -->
<html lang="zh-CN">　
<head>
    <!-- 指定编码 -->
    <meta charset="UTF-8">　
    <!-- 兼容模式方案：IE以最高级模式渲染文档；使用Chrome Frame渲染。 -->
    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
    <!-- 网站关键字 -->
    <meta name="keywords" content="关键词">　
    <!-- 网站描述 -->
    <meta name="description" content="描述信息">　
    <!-- 作者信息 -->
    <meta name="author" content="东方头条">
    <!-- 网站标题 -->
    <title>首页</title>　
    <!-- 基础样式（reset等） -->
    <link rel="stylesheet" href="css/base.css">　
    <!-- 公用模块样式 -->
    <link rel="stylesheet" href="css/common.css">　
    <!-- 具体页面样式 -->
    <link rel="stylesheet" href="css/page.css">　
</head>
<body>
    <!-- html code -->
    <div>....</div>
    <p>...</p>
    <!-- /html code -->

    <!-- js库文件 -->
    <script src="js/jquery-1.12.4.min.js"></script>
    <!-- 页面js业务逻辑 -->
    <script src="js/page_index.js"></script>

    <div style="display: none">
        <!-- 统计代码 -->
    </div>
</body>
</html>
```

### 移动页面模板【参考】

```html
<!DOCTYPE html>
<html lang="zh-cn">
<head>
    <!-- 编码 -->
    <meta charset="UTF-8">
    <!-- H5页面窗口自动调整到设备宽度，并禁止用户缩放页面 -->
    <meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,minimum-scale=1,user-scalable=no">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <!-- 当网站添加到主屏幕快速启动方式，可隐藏地址栏，仅针对ios的safari (ios7.0版本以后，safari上已看不到效果) -->
    <meta name="apple-mobile-web-app-capable" content="yes">
    <!-- 将网站添加到主屏幕快速启动方式，仅针对ios的safari顶端状态条的样式 (可选default、black、black-translucent) -->
    <meta name="apple-mobile-web-app-status-bar-style" content="black">
    <!-- 忽略将页面中的数字识别为电话号码 -->
    <meta name="format-detection" content="telephone=no">
    <!-- 忽略Android平台中对邮箱地址的识别 -->
    <meta name="format-detection" content="email=no">
    <!-- 作者 -->
    <meta name="author" content="东方头条">
    <!-- 关键词 -->
    <meta name="keywords" content="关键词">
    <!-- 描述信息 -->
    <meta name="description" content="描述信息">
    <!-- dns预解析 -->
    <link rel="dns-prefetch" href="//mini.eastday.com/" />
    <!-- favicon -->
    <link rel="shortcut icon" href="//mini.eastday.com/toutiaoh5/img/favicon.ico" />
    <link rel="bookmark" href="//mini.eastday.com/toutiaoh5/img/favicon.ico" type="image/x-icon"/>
    <link rel="apple-touch-icon-precomposed" href="//mini.eastday.com/toutiaoh5/img/favicon.ico">
    <!-- 标题 -->
    <title>头条新闻</title>
    <!-- 动态更新html字体大小（使用rem为单位时） -->
    <script src="js/responsive.js"></script>
    <!-- 基础样式（reset等） -->
    <link rel="stylesheet" href="css/base.css">　
    <!-- 公用模块样式 -->
    <link rel="stylesheet" href="css/common.css">　
    <!-- 具体页面样式 -->
    <link rel="stylesheet" href="css/page.css">
</head>
<body>
    <!-- html code -->
    <div>....</div>
    <p>...</p>
    <!-- /html code -->

    <!-- js库文件 -->
    <script src="js/zepto.min.js"></script>
    <!-- 页面js业务逻辑 -->
    <script src="js/page_index.js"></script>

    <div style="display: none">
        <!-- 统计代码 -->
    </div>
</body>
</html>
```

## 二、书写规范

### 1. 缩进与换行【必须】

统一采用`4个空格`作为一个代码缩进层级，不允许使用`2个空格`；

```html
<ul class="news-list">
    <li class="news-item">...</li>
    <li class="news-item">...</li>
</ul>
```

### 2. class和id命名【建议】

* `class`必须单词全字母小写，单词间以中横线`-`分隔（为了方便代码阅读与维护,用于js操作的class，建议新增一个以`J-`开头作为class名，该class只用于js操作）;
* `id`建议单词全字母小写，单词间以下划线`_`分隔，（为了方便代码阅读与维护,用于js操作的id，建议以`J_`开头作为id名）。

```html
<!-- J_news_list：用于js业务逻辑操作 -->
<ul id="J_news_list" class="news-list">
    <li class="news-item">...</li>
    <li class="news-item">...</li>
</ul>

<!-- J-news-list：用于js业务逻辑操作； news-list：用于样式 -->
<ul class="J-news-list news-list">
    <li class="news-item">...</li>
    <li class="news-item">...</li>
</ul>
```

* `class`必须代表相应模块或部件的内容或功能，不得以样式信息进行命名。

```html
<!-- Good -->
<div class="warn"></div>
<div class="sidebar"></div>

<!-- Bad -->
<div class="red"></div>
<div class="left"></div>
```

### 3. 标签

#### 3.1 标签格式【必须】

* 标签名必须使用小写字母。

```html
<!-- Good -->
<div>lowercase</div>

<!-- Bad -->
<DIV>upcase</DIV>
```

* 空标签不要闭合（`input`  `br`  `img`  `hr`）

```html
<!-- Good -->
<br> <hr>  

<!-- Bad -->
<br /> <hr />  
```

* 标签尽量简洁，不添加不必要的标签。
* 在使用div标签布局可以实现相同需求的情况下，不要使用表格进行布局。  

#### 3.2 标签语义化【待完善】

HTML 标签的使用应该遵循标签的语义（`开发过程中一定要尽量根据上下文语义来选择语义化标签`），标签语义化主要有以下好处：
- 1. 利于SEO（搜索引擎会根据标签的语义确定上下文和权重问题）。
- 2. 去掉样式或者样式丢失时页面结构依然清晰分明。

常用的语义化标签有：  

| 标签 | 描述 |
|:-------|:---------|
| h1 ~ h6  |  标题一 ~ 标题六  |
| p | 段落 |
| b | 加粗 |
| em | 强调 |
| strong | 更强的强调（强调用&lt;em&gt;和&lt;strong&gt;，纯粹加粗用&lt;b&gt;） |
| ul | 无序列表（当涉及到列表的项目，应该用&lt;ul&gt; &lt;li&gt;或&lt;ol&gt; &lt;li&gt;（或者是&lt;dl&gt; &lt;dt&gt; &lt;dd&gt;来布局），而不是用&lt;table&gt;或&lt;p&gt;甚至&lt;span&gt;。）  |
| ol | 有序列表  |
| li | 列表项目  |
| dl | 定义列表 （当我们用带标题的列表时，即可采用&lt;dl&gt; &lt;dt&gt; &lt;dd&gt;自定义列表实现） |
| dt | 定义列表中的项目（即术语部分）  |
| dd | 定义列表中定义条目的定义部分 |
| span | 被用来组合文档中的行内元素 |
| q | 用来标记简短的单行引用 |
| blockquote | 用来标记那些一段或者好几段的长篇引用 |
| cite | &lt;cite&gt;标签既可以与&lt;q&gt; 一起用，也可以与&lt;blockquote&gt;一起用，用来提供引用内容的来源地址。|
| table | 表格 |
| caption | 表格标题 |
| th | 表头单元格 |
| td | 单元格 |
| button | 按钮 |
| input | 用于搜集用户信息; 根据type不同而产生不同作用 |
| textarea | 文本输入控件 |
| label | 为input元素定义标注（标记） |
| ins | 已经被插入文档中的文本 |
| del | 文档中已被删除的文本。 |

> __注意__：如果是开发针对高版本浏览器的项目或者是开发移动端项目，尽量使用html5新增的语义化更好的标签（如：header、footer、article、menu、aside、section、hgroup、nav、figure等）。

### 4. 属性【必须】

* 属性名必须使用`小写字母`。
* 属性值必须用双引号（`""`）包围，不要使用单引号。

```html
<!-- Good -->
<div class="hot-news">...</div>  

<!-- Bad -->
<div class='hot-news'>...</div>  
```

* 布尔类型的属性，建议不添加属性值。

```html
<input type="text" disabled>
<input type="checkbox" value="checkbox" checked>
```

* 自定义属性建议以`xxx-`为前缀，推荐使用`data-`。

```html
<img src="xxx.png" alt="test img" data-width="400" data-height="300">
```

* 属性应该按照特定的顺序出现以保证易读性；
    - class
    - id
    - name
    - data-
    - src, for, type, href, value , max-length, max, min, pattern
    - placeholder, title, alt
    - aria-, role
    - required, readonly, disabled

class是为高可复用组件设计的，所以应处在第一位；

id更加具体且应该尽量少使用，所以将它放在第二位。

### 5. 注释【建议】

* 分块注释，推荐注释写法：

```html
<!-- 头部 start -->
<div class="header">
    <!-- 内容 start -->
    <div class="content">
        此处省略100行...
    </div>
    <!-- 内容 end -->
</div>
<!-- 头部 end -->
```
