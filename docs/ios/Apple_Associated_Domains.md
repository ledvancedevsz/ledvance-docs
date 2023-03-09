# Apple associated domains 服务器配置

## 正文

配置服务端

1. 需要一个 **https** 的网站，且无重定向
2. 在服务器根目录下创建 **.well-known** 目录（需要此服务器根目录权限）
3. 创建 **apple-app-site-association** (必须是无扩展名)
4. 步骤 3 中文件内容如下：

``` javascript
{
    "webcredentials": {
        "apps": ["43CR6478ME.com.ledvance.smartunify"]
    }
}
```
5. 把文件放在 **.well-known** 文件中
6. 修改服务器文件配置中，拓展名(*fileExtension*)为 “.” 的 *mimeType* 为 application/json


### 参考文档：
[苹果文档](https://developer.apple.com/documentation/xcode/supporting-associated-domains)、
[实践例子](https://medium.com/@barsh/my-first-date-with-ios-universal-links-90dfabc88bb8)、
[实践例子2](https://www.jianshu.com/p/139760979b4d)