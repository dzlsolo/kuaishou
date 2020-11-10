## 快手did设备注册,快手sig签名(sign解决,操作太快了，请稍微休息一下)

快手签名计算分析，我们抓包看到sig签名字段，是post请求，32位MD5算法，把?后面的参数和post的参数一起排序，组合计算。

### 1.抓包参数

```
POST /rest/n/user/profile/v2? HTTP/1.1
Connection: close
Accept-Language: zh-cn
User-Agent: kwai-android
Content-Type: application/x-www-form-urlencoded
Host: apissl.gifshow.com
Accept-Encoding: gzip, deflate
 
client_key=5234234&country_code=cn&exp_tag=1_i/293748723479238749&language=zh-Hans-CN%3Bq%3D1&sig=c8a22b77755169b9ecfc63b30e428d32&user=72364723
```
### 2.逆向
通过逆向找到计算加密函数，调试过程略过。

![](./20200426193720667.png)

分析出是md5加密，传入的字符串顺序进行加密。
最近快手升级了风控，多了一个log策略。
而且还需要注册did字段，如果不注册的话，是不能进行抓取的。

### 3.问答交流
如果有什么不懂的可以联系我交流
wx : z990809908
### 4.免责声明
请勿使用本服务于商用或大量抓取
若因使用本服务与快手官方造成不必要的纠纷，本人盖不负责，存粹技术爱好，若侵犯快手贵公司的权益，请告知！

### 5.其他
有抖音、小红书、tiktok、淘宝、等其他技术问题，也可随时交流。

