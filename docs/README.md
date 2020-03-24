# 南博 - typecho 客户端

> 南博 - typecho 客户端的使用说明, 确保照此就做

介绍/下载
====
| key | value  | 
| ------  | ----- |
| 介绍 | [https://krait.cn/nabo.html][1]  | 
| 下载 | https://www.coolapk.com/apk/240898  | 

友人的教程/介绍
=====
**欢迎大家留下你撰写的教程/介绍**

| 类型 | 南博版本  | 文章  |  友人  | 
| ------  | ----- | ----- | ----- |
| 使用/介绍 | v1.3 | [优雅的Typecho安卓客户端nabo][2]  | [风也温柔][3] |
| 介绍 | v1.4 | [Typecho客户端南博APP][4]| [卧眉纹花][5] |
| 介绍 | v1.7 | [Typecho客户端南博APP][6] | [小茶猫][7] |
| 使用 | v1.6 | [Typecho客户端南博APP详细教程][8] | [小茶猫][9] |
| 使用 | v1.5 | [南博-首个优雅的TE手机客户端][10] | [森木志][11] |
| 介绍 | v1.5 | [南博-首页Ty安卓客户端][12] | [奥秘Sir][13] |
| 介绍 | v1.6 | [对南博APP的友好性适配改动][14] | [尚寂新][15] |
| 介绍 | v1.7 | [南博-智慧掌端-Typecho客户端][16]  |  [折颜][17]  | 
| *** | 欢迎提交 | 欢迎提交  |  欢迎提交  | 
| *** | value | value  |  value  | 
| *** | value | value  |  value  | 

根据要求
====

| key | value  | 
| ------  | ----- |
| 原因 | 为了南博更好的发展,南博不再使用官方给的xmlrpc方法  | 
| 解决 | 前往南博官网替换XmlRpc文件  | 
| 下载 |  https://github.com/kraity/typecho-xmlrpc  | 
| 操作 | 获取下载的 XmlRpc.php 文件 | 
| 操作 | 把下载 XmlRpc.php 替换你博客的 /var/Widget/XmlRpc.php  | 
| 附言 | 应和[南博]版本号相同使用。  | 
| 附言 | 不同版本有不同功能和算法。  | 

| key | value  | 
| ------  | ----- |
| step 1 | 安卓手机  | 
| step 2 | 安卓版本不低于 android 7 | 
| step 3 | 下载南博  | 
| step 4 | 安装南博  | 
| step 5 | 打开博客的XmlRpc接口  | 
| step 6 | 启动南博  | 
| step 7 | 输入域名  | 
| step 8 | 点击检测  | 
| step 9 | 若XmlRpc过旧则需更新  | 
| step 10 | 输入账号密码  | 
| step 11 | 等待几秒钟  | 
| step 12 | 进入主页面  | 
| step 13 | 下拉刷新  | 
| step 14 | 欢迎使用  |

*打开博客的XmlRpc接口 (设置->基本->XMLRPC 接口)* 

提示XmlRpc接口不存在?
====
| key | value  | 
| ------  | ----- |
| 版本 | value  | 
| 问题 | 提示XmlRpc接口不存在  | 
| 出错对象 | User-agent、post问题 | 
| 原因 | 博客开启了user-agent过滤和post过滤  | 
| 解决 | **关闭**user-agent过滤和post过滤  | 

为了安全?
====
| key | value  | 
| ------  | ----- |
| 目的 | 为了博客的安全  | 
| 措施 | 南博支持了**密码**经**md5加密**过后**密文**登陆  | 
| 原因 | 众所周知md5加密的密文后一般不可以逆向的  | 
| 获取密文 | 打开数据库  | 
| 对象 | 找到表名`typecho_users`  | 
| 对象 | 找到你博客的账号  | 
| 发现 | 你会发现有 `uid` `name` `password`  ....  | 
| 找到 | `password` 对应的值(全部复制) 比如是: `$P$B7REihLFP0nt5Ed06yw8Cig5IoC1dC/` |
| 加密 | 加密成**32位小写**  |  
| 加密 | 用md5加密上述找到的对应值 比如加密后是`bbe94415259eb11179f167a7f71241ea` | 
| 登陆 | 用上面加密过后的密文,就可以就它登陆南博了  |

| key | value  | 
| ------  | ----- |
| 目的 | 为了更更安全?  | 
| 措施 | 使用上述的密文登陆 | 
| 措施 | 让博客的xmlrpc不支持明文登陆,仅许可密文登陆  | 
| 更新 | 修改`/var/Widget/XmlRpc.php`文件  | 
| 位置 | 按ctrl+f 搜索 `if (preg_match("/^[a-f0-9]{32}$/", $password))`  | 
| 操作 | 找到这个`if(...){....}else{.....}`  | 
| 操作 | 后面的 `else{.....} `  中的`......`改为 `return false;` | 

Markdown
====

| key | value  | 
| ------  | ----- |
| 原因 | 南博编辑器仅支持markdown  | 
| 故然 | 需要告知typecho我们用的markdown编辑  | 
| 前往 | https://example.com/admin/profile.php  | 
| 位置 | 个人信息->撰写设置->在 XMLRPC 接口  | 
| 操作 | 使用 Markdown 语法->打开  | 

评论管理
====
| key | value  | 
| ------  | ----- |
| 需求 | 使用评论回复  |
| 解决 | 关闭评论中的**开启反垃圾保护**  |
| 前往 | 后台->设置->评论->评论提交->开启反垃圾保护  |
| 操作 | 关闭它 | 
| 附言 | 它的上下几项在没有回复成功则也要关闭  | 

新评论通知
====
| key | value  | 
| ------  | ----- |
| 需求 | 当博客有新评论后南博在通知栏弹出通知  |
| 解决 | 开启后,南博会检测是否有通知的权限  |
| 前往 | 如果没有通知权限会弹出是否前往给南博权限  |
| 操作 | 前往赋予南博通知权限 | 
| 附言 | 你可以设置南博通知权限的级别  | 
| 注意 | 需要南博**后台运行**  | 

探索与发现
====

| key | value  | 
| ------  | ----- |
| 版本 | v1.5-1.7  | 
| 更新 | 替换`/var/Widget/XmlRpc.php`文件  | 
| 更新 | 修改`/var/Widget/Upload.php`  | 
| 解决对象 | 解决上传图片失败问题  | 
| 修改位置 | 126行  | 
| 需修改代码 | `if (!file_put_contents($path, $file['bytes'])) {}`  | 
| 目标代码 | `if (!file_put_contents($path, base64_decode($file['bytes']))) {}`  | 

| key | value  | 
| ------  | ----- |
| 版本 | v1.5  | 
| 更新 | 修改`/var/Widget/Comment/Admin.php`  | 
| 解决对象 | 修改后能查看评论者以往的评论  | 
| 加入位置 | 119行  | 
| 加入位置 | `//增加按文章归档功能`这段文字之前  | 
| 加入代码 | `if (isset($this->request->email)) {$select->where('table.comments.mail = ?', $this->request->email);}`  | 

| key | value  | 
| ------  | ----- |
| 版本 | v1.3 - v1.7  | 
| 更新 | 替换`/var/Widget/XmlRpc.php`文件  | 

文件上传
====
**如果图片上传失败,则你没有修改此处**
**这是官方的bug,我已经pr了**
| key | value  | 
| ------  | ----- |
| 版本 | v1.5-1.7  | 
| 通知 | 已修复上传文件限制问题  | 
| 更新 | 修改`/var/Widget/Upload.php`  | 
| 修改位置 | 126行  | 
| 需修改代码 | `if (!file_put_contents($path, $file['bytes'])) {}`  | 
| 目标代码 | `if (!file_put_contents($path, base64_decode($file['bytes']))) {}`  | 


----------


*如果你使用了其他的附件上传插件，则可能无法使用上传图片，应为都没有写byte流写入内容的考虑*
**注意**:新版本需要base64解密 `base64_decode($file['bytes'])`

| key | value  | 
| ------  | ----- |
| 南博版本 | v1.5-1.7  | 
| 插件 | `OssForTypecho`  | 
| 插件名字 | 阿里云OSS上传插件 | 
| 位置 | `https://github.com/jqjiang819/typecho-plugin-ossfile/blob/master/Plugin.php`  | 

```php
//152行 
$result = $ossClient->uploadFile($options->bucket, substr($path,1), $uploadfile);

//改为 
if (isset($file['tmp_name'])) {
    $result = $ossClient->uploadFile($options->bucket, substr($path, 1), $uploadfile);
} else {
    $result = $ossClient->putObject($options->bucket, substr($path, 1), $uploadfile);
}
```

```php
//310行
return isset($file['tmp_name']) ? $file['tmp_name'] : (isset($file['bytes']) ? $file['bytes'] : (isset($file['bits']) ? $file['bits'] : ''));

//改为
return isset($file['tmp_name']) ? $file['tmp_name'] : (isset($file['bytes']) ? base64_decode($file['bytes']) : (isset($file['bits']) ? $file['bits'] : ''));
```

```php
//169行 
'mime' => @Typecho_Common::mimeContentType($path)

//其改为
'mime' => (isset($file['tmp_name']) ? Typecho_Common::mimeContentType($file['tmp_name']) : $file['mime'])
```

----------

| key | value  | 
| ------  | ----- |
| 南博版本 | v1.5-1.7  | 
| 插件 | `Qiniu File`  | 
| 插件名字 | Typecho 的附件上传至七牛云存储中 | 
| 位置 | `https://github.com/licxisky/typecho-Plugin-QiniuFile/blob/master/Plugin.php`  | 

 ```php
//108行   将其删掉
$filename = $file['tmp_name'];
if (!isset($filename)) return false;
``` 

``` php
//116行到127行  
if ($error == null)   .... else return false; 

//将其改为 
if (isset($file['bytes'])) {
        	list($ret, $error) = $upManager->put($token, $option->savepath . $file['name'], base64_decode($file['bytes']));
        	if ($error == null) {
        		return array(
        			'name' => $file['name'], 
        			'path' => $option->savepath . $file['name']  . ($option->imgstyle == '' ? '' : '-' . $option->imgstyle), 
        			'size' => $file['size'], 
        			'type' => $ext, 
        			'mime' => $file['mime']//Typecho_Common::mimeContentType($option->savepath . $file['name'])
        			);
        		
        	} else {
        		return false;
        	}
        	
        	
        } else {
	
	    // 上传文件
        $filename = $file['tmp_name'];
        //if (!isset($filename)) return false;
        list($ret, $error) = $upManager->putFile($token, $option->savepath . $file['name'], $filename);
           if ($error == null) {
        	return array(
        		'name' => $file['name'], 
        		'path' => $option->savepath . $file['name'] . ($option->imgstyle == '' ? '' : '-' . $option->imgstyle), 
        		'size' => $file['size'], 
        		'type' => $ext, 'mime' => Typecho_Common::mimeContentType($filename)
        		);
        		} else {
        	return false;
        
           }
        	
        }
```


----------


| key | value  | 
| ------  | ----- |
| 南博版本 | v1.5-1.7  | 
| 插件 | `cosUploadV5`  | 
| 插件名字 | 针对腾讯云cos v5更新 for Typecho | 
| 位置 | `https://github.com/eocene317/cosUploadV5/blob/master/Plugin.php`  | 
| 位置 | 164行 |
| 位置 | `$file['bytes']` |
| 改为 | `base64_decode($file['bytes'])` |


```php
//176行 
'mime' => @Typecho_Common::mimeContentType(rtrim($options->domain, '/') . '/' .  $newPath)

//其改为
'mime' => (isset($file['tmp_name']) ? Typecho_Common::mimeContentType($file['tmp_name']) : $file['mime'])
```

----------


| key | value  | 
| ------  | ----- |
| 南博版本 | v1.5-1.7  | 
| 插件 | `AliOssForTypecho`  | 
| 插件名字 | AliOssForTypecho | 
| 位置 | `https://github.com/DefectingCat/AliOssForTypecho-/blob/master/Plugin.php`  | 
| 位置 | 第253行 |
| 位置 | `$content = $file['bytes'];` |
| 改为 | `$content = base64_decode($file['bytes']);` |


----------


| key | value  | 
| ------  | ----- |
| 南博版本 | v1.5-1.7  | 
| 插件 | `GitStatic`  | 
| 插件名字 | 用 git 当御用图床的一款 typecho 插件 — GitStatic | 
| 作者 | **@Mumuli**  | 
| 位置 | https://blog.mumuli.cn/148.html  | 
| 位置 | https://github.com/MliKiowa/GitStatic  | 
| 改为 | 不用修改，兼容支持南博 |
| 改为 | 不用修改，兼容支持南博 |
| 改为 | 不用修改，兼容支持南博 |


  [1]: https://krait.cn/nabo.html
  [2]: https://kaygb.top/posts/63.html
  [3]: https://eas1.cn/
  [4]: https://53ic.com/nabo.html
  [5]: https://53ic.com
  [6]: https://www.xiaochamao.com/63.html
  [7]: https://www.xiaochamao.com/
  [8]: https://www.xiaochamao.com/69.html
  [9]: https://www.xiaochamao.com/
  [10]: https://imxxz.cn/archives/typecho-nabo.html
  [11]: https://imxxz.cn/
  [12]: https://blog.say521.cn/archives/236/
  [13]: https://blog.say521.cn/
  [14]: https://shangjixin.com/archives/nabo-app-adapt.html
  [15]: https://shangjixin.com/
  [16]: https://blog.hnxjhf.com/archives/nabo.html
  [17]: https://blog.hnxjhf.com/