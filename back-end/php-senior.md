## 常用扩展

### cURL
cURL（Client URL 库）是 Daniel Stenberg 创建的 libcurl 库，能够连接通讯各种服务器、使用各种协议。

#### 用法
```php
// 初始化 cURL 句柄
$ch = curl_init();
// 设置参数
curl_setopt($ch, CURLOPT_URL, 'example.com');
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
// 执行请求
$output = curl_exec($ch);
// 关闭　cURL 句柄
curl_close($ch);
```

使用 cURL 主要是这四步，难点就是 cURL 的参数设置，PHP 提供了很多的参数选项，以预定义常量的给出。

[参数选项查看](http://php.net/manual/zh/curl.constants.php)

#### 应用场景
- 访问 API 获取结果
- 网页爬虫
- 图片或其他资源下载

### GD（Graphics Draw）
在 PHP 中，如果有图像生成和处理的需求，那么 GD 库无疑是最好的选择之一。图像相关函数众多，如果一个一个去记忆，那么效率是低下的，个人觉得较好的学习方式就是结合实例。

> 创建带文字的图片

```php
header('Content-type: image/png');
$str = 'Hello';
$im = imagecreatefrompng('btn.png');
$orange = imagecolorallocate($im, 220, 210, 60);
$px = (imagesx($im) - 7.5 * strlen($string)) / 2;
imagestring($im, 3, $px, 9, $string, $orange);
imagepng($im);
imagedestroy($im);
```
PS：如果需要在图片上增加中文，那么需要使用 imagettftest() 函数。

> 使用 Alpha 通道为图像加水印

```php
// 加载水印以及要加水印的图像
$stamp = imagecreatefrompng('stamp.png');
$im = imagecreatefromjpeg('photo.jpeg');

// 设置水印图像的外边距，并且获取水印图像的尺寸
$marge_right = 10;
$marge_bottom = 10;
$sx = imagesx($stamp);
$sy = imagesy($stamp);


// 利用图像的宽度和水印的外边距计算位置，并且将水印复制到图像上

imagecopy($im, $stamp, imagesx($im) - $sx - $marge_right, imagesy($im) - $sy - $marge_bottom, 0, 0, imagesx($stamp), imagesy($stamp));

// 输出图像并释放内存
header('Content-type: image/png');
imagepng($im);
imagedestroy($im);
```
PS：imagecopy() 与 imagecopymerge()，这两个的函数功能基本上一样，但后者可以设置水印图片的透明度。
