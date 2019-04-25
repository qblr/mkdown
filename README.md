# 骑兵利刃 mkdown

## 基本

mkdown 的目标是实现「易读易写」，最大灵感来源其实是纯文字的电子邮件格式。

* mkdown 是一种用来写作的轻量级标记语言，
* mkdown 的重点在于，它能让文件更容易阅读、编写，
* 兼容 HTML 且自动转换，例如 `<` 和 `&` 自动转为 `&lt;` 和 `&amp;`。

## 境界

最高境界：笔下是语法，心中格式化。

## 字体

* 使用星号`*`和底号`_`表示`<em>`标签。

例如：

***

```
*斜体（星号）*

_斜体（下划线）_
```

*斜体（星号）*

_斜体（下划线）_

***

* 使用双星号`**`和双底号`__`表示`<strong>`标签。

例如：

***

```
**强调（星号）**

__强调（下划线）__
```

**强调（星号）**

__强调（下划线）__

***

## 段落

* 段落的前后要有空行，所谓的空行是指没有文字内容（要点：不能有空格符）。

例如：

***

```
一行文字
又一行文字

空行后再来一行文字
```

一行文字
又一行文字

空行后再来一行文字

***

## 标题

* 生成`<h1>`-`<h6>`标签，是通过在文字前面加上同等个数`#`符号来实现。
* 出于美观，也可以使用对称的闭合式标题符号。

例如：

```
# 一口井 h1
## 二口井 h2
### 三口井 h3
#### 四口井 h4
##### 五口井 h5
###### 六口井 h6
```

## 列表

* `*`，`-`，`+`这三个符号效果都一样，这3个符号被称为mkdown列表符号。而有序列表则使用数字接着一个英文句点（数字大小并不会影响输出序列）。

例如：

***

```
* 全星号1
* 全星号2
* 全星号3

***

- 全减号1
- 全减号2
- 全减号3

***

+ 全加号1
+ 全加号2
+ 全加号3

***

1. 有序列表项 一
1. 有序列表项 二
1. 有序列表项 三

***


- [x] 复选框列表项 一
- [x] 复选框列表项 二
- [ ] 复选框列表项 三

***

- [ ] TODO列表
    - [ ] 支持子列表嵌套
    - [ ] TODO列表列表项 一
    - [x] TODO列表列表项 二
        - [x] TODO列表列表项 三
        - [x] TODO列表列表项 四
- [ ] TODO列表列表项 五
    - [ ] TODO列表列表项 六
    - [x] TODO列表列表项 七
```

* 全星号1
* 全星号2
* 全星号3

***

- 全减号1
- 全减号2
- 全减号3

***

+ 全加号1
+ 全加号2
+ 全加号3

***

1. 有序列表项 一
1. 有序列表项 二
1. 有序列表项 三

***


- [x] 复选框列表项 一
- [x] 复选框列表项 二
- [ ] 复选框列表项 三

***

- [ ] TODO列表
    - [ ] 支持子列表嵌套
    - [ ] TODO列表列表项 一
    - [x] TODO列表列表项 二
        - [x] TODO列表列表项 三
        - [x] TODO列表列表项 四
- [ ] TODO列表列表项 五
    - [ ] TODO列表列表项 六
    - [x] TODO列表列表项 七

***

```
兼容：`复选框` 和 `TODO列表` 的 `复选框` 部分服务商不兼容，会直接显示 `[x]` `[]`，不过没关系。
```

## 引用

* `>`符号表示引用，可简写于第一行，也可以每一行都添加。
* 区块的引用可以嵌套，只需要在层次数上加上同等数量的`>`符号。
* 引用内可以使用其他mkdown语法，包括标题、列表、代码区块等。

例如：

***

```
>    第一行  
>    第二行（要点：换行问题，第一行的后面只有2个 ` ` （空格）才能兼容所有平台）
>    >    引用中的引用
```

>    第一行  
>    第二行（要点：换行问题，第一行的后面只有2个 ` ` （空格）才能兼容所有平台）
>    >    引用中的引用

***

## 代码

* <code>\`</code>是表示inline代码，4个<code> </code>（空格）来表示缩进式代码段，分别对应HTML的`<code>`，`<pre>`标签。也可以使用<code>\`\`\`</code>来表达围栏式代码块（**GFM语法**，部分编辑器不支持），并指定他的语言类型，实现语法高亮。围栏式代码块可以大量减少缩进的使用，大规模的代码块使用非常方便。

例如：

***

inline代码

```
`sort()` inline代码
```

`sort()` inline代码

***

普通的缩进式代码块。

```
    <?php
        $myArray = array('a' => 'Dog', 'b' => 'Cat');
        sort($myArray);
        print_r($myArray);
    ?>
```

    <?php
        $myArray = array('a' => 'Dog', 'b' => 'Cat');
        sort($myArray);
        print_r($myArray);
    ?>

***

带语法高亮的围栏式代码块（**GFM语法**，部分编辑器不支持）。

```
\`\`\`php
<?php
    $myArray = array('a' => 'Dog', 'b' => 'Cat');
    sort($myArray);
    print_r($myArray);
?>
\`\`\`
```

```php
<?php
    $myArray = array('a' => 'Dog', 'b' => 'Cat');
    sort($myArray);
    print_r($myArray);
?>
```

***

## 链接

* mkdown支持两种形式的链接语法：行内式和参考式两种形式。

例如：

***

行内式链接，是在方括号后面接圆括号即可。

```
[site](http://localhost "站点标题")
```

[site](http://localhost "站点标题")

***

参考式链接，是在链接文字的括号后面加上另一个方括号，在第二个方括号里面要填入用以辨识链接的标记。

```
[site][9527]

[9527]: http://localhost "站点标题"
```

[site][9527]

[9527]: http://localhost "站点标题"

***

## 图片

* mkdown使用一种和链接很相似的语法来标记图片，只是多了一个`!`在最前面，同样也允许两种样式：行内式和参考式。
* 目前为止，mkdown还没有办法指定图片的宽高，如果你需要的话，你可以使用普通的`<img>`标签。

例如：

***

行内式链接，是在方括号后面接圆括号即可。

```
![github](https://assets-cdn.github.com/images/modules/logos_page/GitHub-Logo.png "GitHub")
```

![github](https://assets-cdn.github.com/images/modules/logos_page/GitHub-Logo.png "GitHub")

***

参考式链接，是在链接文字的括号后面加上另一个方括号，在第二个方括号里面要填入用以辨识链接的标记。

```
![github][GH]

[GH]: https://assets-cdn.github.com/images/modules/logos_page/GitHub-Logo.png "GitHub"
```

![github][GH]

[GH]: https://assets-cdn.github.com/images/modules/logos_page/GitHub-Logo.png "GitHub"

***
  
使用普通的`<img>`标签

```
<img width="200px" src="https://assets-cdn.github.com/images/modules/logos_page/GitHub-Logo.png" alt="Github">
```

<img width="200px" src="https://assets-cdn.github.com/images/modules/logos_page/GitHub-Logo.png" alt="Github">

***

## 分隔线

* 使用三个以上的`*`、`-`来建立一个分隔线，行内不能有其他字符。

例如：

***

```

***

```

上文

***

下文

***

## 表格

* mkdown使用`|`和`-`来绘制表格，`:`可控制左对齐、右对齐及居中。

例如：

***

```
| unset         | left          | center        | right         |
| ------------- |:------------- |:-------------:| -------------:|
| align: unset  | align: left   | align: center | align: right  |
| 123           | 123           | 456           |   789         |
| 123456        | 123456        | 456789        | others        |
```

| unset         | left          | center        | right         |
| ------------- |:------------- |:-------------:| -------------:|
| align: unset  | align: left   | align: center | align: right  |
| 123           | 123           | 456           |   789         |
| 123456        | 123456        | 456789        | others        |

***
