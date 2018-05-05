#### `HTML` 是什么

`HTML：（Hype Text Markup Language）` 超文本标记语言，又称标签语言，可以类比成一个容器，把内容放在容器中，通过操作这些容器的属性来达到不同目的。

#### `HTML` 的元素和属性

元素就是 **标签** ，而属性就是 **标签** 的自身特性，不同的 **标签** 自然有不同的属性，大多也比较容易理解，主要是从生活场景中衍生而来，对 `HTML` 的元素和属性 W3C 组织也是在不断的完善和定义，或有增删。

#### `meta` 标签

从属性的角度来看，分为 **必须属性** 和 **可选属性**

**必须属性：** `content` 并非一定要有，但是一旦出现 **可选属性**，就需要 `content` 来作说明

**可选属性：** 表示不一定要出现

> 1.`http-equiv` 是添加 http 头部内容，对一些自定义的，或者需要额外添加的 http 头部内容，需要发送到浏览器中，我们就可以是使用这个属性。例如我们不想使用 js 来重定向，用 http 头部内容控制，那么就可以这样控制：
>
> ```
> <meta http-equiv="Refresh" content="5;url=http://www.xxx.cn" />
> ```
>
> 在页面中加入这个后，5 秒钟后就会跳转到指定页面

> 2.`name` 是供浏览器进行解析，对于一些浏览器兼容性问题
>
> ```
> <meta name="renderer" content="webkit">
> ```
>
> 这个 meta 标签的意思就是告诉浏览器，用 webkit 内核进行解析，当然前提是浏览器有 webkit 内核才可以，不然就是没有意义的啦。当然看到这个你可能会有疑问，这个 renderer 是从哪里冒出来的，我要怎么知道呢？这个就是在对应的浏览器的开发文档里就会有表明的，例如这个[renderer 是在 360 浏览器](http://se.360.cn/v6/help/meta.html)里说明的。

**`charset`** 声明文档使用的字符编码，解决乱码问题，用于首行,以下两种方法都可以

```
<meta charset="utf-8">
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
```

**百度禁止转码** 百度会自动对网页进行转码，这个标签是禁止百度的自动转码

```
<meta http-equiv="Cache-Control" content="no-siteapp" />
```

**SEO 优化部分**

```
<!-- 页面标题<title>标签(head 头部必须) -->
<title>your title</title>
<!-- 页面关键词 keywords -->
<meta name="keywords" content="your keywords">
<!-- 页面描述内容 description -->
<meta name="description" content="your description">
<!-- 定义网页作者 author -->
<meta name="author" content="author,email address">
<!-- 定义网页搜索引擎索引方式，robotterms 是一组使用英文逗号「,」分割的值，通常有如下几种取值：none，noindex，nofollow，all，index和follow。 -->
<meta name="robots" content="index,follow">
```

**`viewport`** 主要是影响移动端页面布局的，例如：

```
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

* width viewport 宽度(数值/device-width)
* height viewport 高度(数值/device-height)
* initial-scale 初始缩放比例
* maximum-scale 最大缩放比例
* minimum-scale 最小缩放比例
* user-scalable 是否允许用户缩放(yes/no)

**`meta`** 标签更多内容，查看 [此链接](https://blog.csdn.net/yc123h/article/details/51356143)

#### 表单标签

> **`form`** 能够将包裹的内容提交到后台，`action` 属性用来指定提交地址，`method` 指定提交方式

> **`input`** 需指定 `name` 属性，服务端才能获取到对应的 `value`，根据 `type` 决定类型
>
> ```html
>  <input type="text" placeholder="文本框" />
>  <input type="password" placeholder="密码框" />
>  <input type="radio" checked="true" />
>  <input type="checkbox" checked="true" />
>  <input type="button" value="按钮" />
>  <input type="submit" value="提交按钮" />
>  <input type="reset" value="重置按钮" />
> ```

> **`select`** 下拉列表，列表内容用 `option` 标签来设置， `value` 值只有在后台有用，使用 `selected` 表示默认选项
>
> ```html
> <select name="country">
>    <option value="none">--选择国家--</option>
>    <option value="cn" select="select">中国</option>
>   <option value="usa">美国</option>
>    <option value="en">英国</option>
> </select>
> ```

> **`textarea`** 本域标签，用来输入大量文本的的标签，`cols` 表示列，`rows` 表示行

> **`fieldset`** 可给表单加外框，外框上的文字可用 `legend` 标签指定
>
> ```html
> <form>
>  <fieldset>
>    <legend>健康信息</legend>
>    身高：<input type="text" />
>    体重：<input type="text" />
>  </fieldset>
> </form>
> ```

> **`label`** 用于给各元素定义快捷键，`for` 属性指定快捷键起作用的表单元素，其值必须与该表单元素的 **id** 值相同 `accessKey` 指定快捷键，要与 **Alt** 合用，例：
>
> ```html
> <label for=”user” accessKey=”u”>user name</label>
> <input type=”text” id=”user” />
> ```
>
> 若将 `label` 标签加到 `<tr>` 标签上，`for` 属性指向该 `<tr>` 里的文本框，在这行的任意位置点击鼠标，文本框都将获得焦点。

#### 一些需要注意的

**特殊符号**

| 大于号＞ | 小于号＜ | 与符号& | 双引号" | 空格    | 注册符 ® | 版权符 © | TM 符 ™  |
| -------- | -------- | ------- | ------- | ------- | -------- | -------- | -------- |
| \&lt;    | \&gt;    | \&amp;  | \&quot; | \&nbsp; | \&reg;   | \&copy;  | \&trade; |

头标签`<head>`中 `base` 标签：`href` 指定页面中所有超链接的目录，可本地，也可网络，结尾一定要用斜杠/表示目录，只作用于 **相对路径** 文件。 `target` 指定打开方式

> ```html
> <base target="_blank|_self|_parent|_top|framename">
> ```
>
> `href` 的详细描述见[此链接](https://blog.csdn.net/hjb2722404/article/details/72967051)
