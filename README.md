# Qiniu Cloud SDK for PHP

## 安装

* 推荐使用 `composer` 进行安装。可以使用 composer.json 声明依赖，或者运行下面的命令。SDK 包已经放到这里 [`qiniu/php-sdk`][install-packagist] 。
```bash
$ composer require xiaoheiba/qiniu
```
* 直接下载安装，SDK 没有依赖其他第三方库，但需要参照 composer 的 autoloader，增加一个自己的 autoloader 程序。

## 运行环境

| Qiniu SDK版本 | PHP 版本 |
|:--------------------:|:---------------------------:|
|          7.x         |  cURL extension,   5.3 - 5.6,7.0 |
|          6.x         |  cURL extension,   5.2 - 5.6 |

## 使用方法

### 上传
```php
use Qiniu\Storage\UploadManager;
use Qiniu\Auth;
...
    $uploadMgr = new UploadManager();
    $auth = new Auth($accessKey, $secretKey);
    $token = $auth->uploadToken($bucket);
    list($ret, $error) = $uploadMgr->putFile($token, 'key', 'filePath');
...
```

## 测试

``` bash
$ ./vendor/bin/phpunit tests/Qiniu/Tests/
```

