---
name: trick投稿
about: 给 https://tricking.io 投递一个新的trick。

---

# trick标题

## 描述

用一段简单的文字完整描述这个trick。

我们描述要达到的目的是：大佬无需查看详情，就能通过阅读描述知道这个知识点的内容和复现方法。所以，请把所有重要信息在描述里说清楚，切记，描述并不是一段含糊不清只是引导性的文字。

## 详情

一段支持Markdown的文章，长度不限。

## 代码

给出一段代码（或伪代码），因为这段代码中的错误，即可导致这个trick。

例如：

```php
<?php
$tag = $_GET['tag'];
$pattern = "|<{$tag}>(.*?)</{$tag}>|i";
$data = preg_replace($pattern, '\1', $_GET['html']);
echo $data;
```
