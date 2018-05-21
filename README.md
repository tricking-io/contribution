# 梧桐百科投稿指南

[梧桐百科][2]是一个碎片化安全知识学习平台，我们将细小的知识点（tricks）写入卡片，以卡片的形式让学习者对知识的认识程度更加深刻。

我们接受用户投稿，大家可以把自己觉得优秀的碎片化知识发送给我们：[投稿地址][1]。

## 投稿步骤

第一步搜索，可能你的知识点已经被梧桐百科收录。

另外，要区分“碎片化知识”和“博客文章”的区别。我们只接受细小的知识点投稿，如果是一个漏洞、一个渗透测试案例等完整的文章，请将其中的知识点拆分出来投稿。如：“PHP某某函数在某某情况下可以导致某某漏洞”，这一类属于知识点；“我通过某某函数编写缺陷获取了某某网站的webshell”，这属于完整的渗透测试文章。

投稿方式：**通过[这个页面][1]在本repo下新建一个issue。**

投稿前，请先阅读下列内容。

你需要填写的内容包括4部分：

1. 标题
2. 描述
3. 详情
4. 代码

其中，标题、描述都不支持Markdown语法，只有详情支持Markdown语法，代码部分支持任意程序语言。

### 标题

可以是比较吸引人的句子，不要过长，最好能够囊括该trick所涉及的函数、作用、影响等，如`preg_replace 利用 \0 截断执行代码`。

### 描述

用一段简单的文字完整描述这个trick。

我们描述要达到的目的是：**大佬无需查看详情，就能通过阅读描述知道这个知识点的内容和复现方法**。所以，请把所有重要信息在描述里说清楚，切记，**描述并不是一段含糊不清只是引导性的文字**。

例如：

> 有些情况下，我们可控`preg_replace`的第一个参数（正则表达式）中的部分内容。
> 
> 在PHP5.4.7以前，`preg_replace`的第一个参数可以利用\0进行截断，并将正则模式修改为e。众所周知，e模式的正则支持执行代码，此时将可构造一个任意代码执行漏洞。

### 详情

详情部分的受众是所有用户。比如，某人阅读描述部分，无法准确获知这个trick，就需要阅读详情。详情部分是一段支持Markdown的文章，长度不限。

Markdown语法请阅读：[https://guides.github.com/features/mastering-markdown/](https://guides.github.com/features/mastering-markdown/)。

梧桐百科的详情有如下特点：

1. 下划线不用转义
2. 自动识别链接
3. 粘贴上传图片

### 代码

代码的目的是：**给出一段代码（或伪代码），因为这段代码中的错误，即可导致这个trick。**

例如：

```php
<?php
$tag = $_GET['tag'];
$pattern = "|<{$tag}>(.*?)</{$tag}>|i";
$data = preg_replace($pattern, '\1', $_GET['html']);
echo $data;
```

代码段比较随意，无需非常严格而能运行。只是一个最简单地能够复现该trick的环境。

当然，某些trick无法用一段简单的代码复现，所以也可以留空。

[1]: https://github.com/tricking-io/contribution/issues/new?template=trick--.md
[2]: https://tricking.io/
