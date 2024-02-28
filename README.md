[![Build Status](https://github.com/dataabc/weiboSpider/workflows/Python%20application/badge.svg)](https://badge.fury.io/py/weibo-spider)
[![Python](https://img.shields.io/pypi/pyversions/weibo-spider)](https://badge.fury.io/py/weibo-spider)
[![PyPI](https://badge.fury.io/py/weibo-spider.svg)](https://badge.fury.io/py/weibo-spider)

# Weibo Spider

本程序可以连续爬取**一个**或**多个**新浪微博用户（如[胡歌](https://weibo.cn/u/1223178222)、[迪丽热巴](https://weibo.cn/u/1669879400)、[郭碧婷](https://weibo.cn/u/1729370543)）的数据，并将结果信息写入**文件**或**数据库**。写入信息几乎包括用户微博的所有数据，包括**用户信息**和**微博信息**两大类。因为内容太多，这里不再赘述，详细内容见[获取到的字段](#获取到的字段)。如果只需要用户信息，可以通过设置实现只爬取微博用户信息的功能。本程序需设置cookie来获取微博访问权限，后面会讲解[如何获取cookie](#如何获取cookie)。如果不想设置cookie，可以使用[免cookie版](https://github.com/dataabc/weibo-crawler)，二者功能类似。

## 注意事项

1. user_id不能为爬虫微博的user_id。因为要爬微博信息，必须先登录到某个微博账号，此账号我们姑且称为爬虫微博。爬虫微博访问自己的页面和访问其他用户的页面，得到的网页格式不同，所以无法爬取自己的微博信息；如果想要爬取爬虫微博内容，可以参考[获取自身微博信息](https://github.com/dataabc/weiboSpider/issues/113)；
2. cookie有期限限制，大约三个月。若提示cookie错误或已过期，需要重新更新cookie。
