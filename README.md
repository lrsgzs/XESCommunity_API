<!-- html部分-开始 -->
<div>
    <script>
(function() {
    var link = document.createElement('link');
    link.type = 'image/x-icon';
    link.rel = 'shortcut icon';
    link.href = './favicon.ico';
    document.getElementsByTagName('head')[0].appendChild(link);
}());
    </script>
</div>
<!-- html部分-结束 -->

# XESCommunity_API - 学而思编程社区模块化API

## 函数

### def save(name :str, xml, cookies: str, headers={}, type_='webpy', projectid=3) -> object:
#### 作用
##### 保存作品
#### 参数
##### name: 作品名
##### xml: 作品内容（代码）
##### cookie: COOKIE（用户凭证）
##### headers: 自定义请求头
##### type_: 作品类型 scratch python cpp
##### projectid: 写代码的时候编辑器的id（没什么用）
#### 备注
##### name就是新作品名 比如叫做hellopython
##### xml就是代码 比如print('helloworld!')
##### cookies就是用户凭证，可以去百度什么意思
##### 其他的没什么用
#### 返回值
##### 请求变量
#### 示例
```python
save("作品名", 'print(\"hhh\")', ..., {...})
```

### def publish(res:str, cookies: str, headers: dict = {}, description='', thumbnail="https://static0.xesimg.com/talcode/assets/py/default-python-thumbnail.png", name='NONE', tags='') -> object:
#### 作用
##### 发布作品
#### 参数
##### res: 请求变量
##### name: 作品名
##### description 作品描述
##### thumbnail 封面链接
##### tags 作品标签
###### 不推荐使用（可能出现严重错误）
#### 备注
##### res就是save的请求变量（如果你直接填入的话会报错）
###### 正确示例：
```python
res = save(...)
publish(res.save, ...)
```
##### cookies就是用户凭据，不作说明
##### description就是作品简介
##### thumbnail就是封面图片（没有限制文件格式，但如果上传了一些奇怪的格式就显示不出来）
##### name就是作品名字
##### tags就是标签 以空格分界（没有限制内容，可以自定义）
#### 返回值
##### 请求变量
#### 示例
```python
publish(save(...), '作品名', ..., {...}, '作品简介', '封面网址', 'xxx xxx xxx')
```

### def raw_publish(ID, cookies: str, headers: dict = {}, thumbnail="https://static0.xesimg.com/talcode/assets/py/default-python-thumbnail.png", description='', name='NONE', tags='') -> object:
#### 作用
##### 发布作品（推荐使用）
#### 参数
##### ID:作品ID 该ID必须属于自己
##### name: 作品名
##### description 作品描述
##### thumbnail 封面图片
##### tags 作品标签
###### 不推荐使用（可能出现严重错误）
#### 备注
##### ID就是作品id 如果你的作品列表中已经有这个作品了就能提交 即使他已经发布了
##### cookies就是用户凭据，不作说明
##### description就是作品简介
##### thumbnail就是封面图片（没有限制文件格式，但如果上传了一些奇怪的格式就显示不出来）
##### name就是作品名字
##### tags就是标签 以空格分界（没有限制内容，可以自定义）
#### 返回值
##### 请求变量
#### 示例
```python
publish(12345678, ..., {...}, '封面网址', '作品简介', '作品名', 'xxx xxx xxx')
```


### def cancel_publish(ID, cookies):
#### 作用
##### 取消发布
#### 参数
##### ID：要取消发布的作品ID
##### cookies就是用户凭据，不作说明
#### 返回值
##### 
#### 示例
```python
cancel_publish(12345678, ...)
```


### def report(cookies: str, reason: str, reason_detail: int, complaint_reason_url: str, ID: int) -> object:
#### 作用
##### 举报作品
#### 参数
##### cookie: COOKIE
##### reason: 理由
##### reason_detail: 理由类型，1、2、3等
##### complaint_reason_url: （被抄袭）源地址
##### ID: 作品ID
#### 备注
##### cookies就是用户凭据，不作说明
##### reason就是理由 应该不用我多说了
##### reason_detail举报原因
```
1骗赞刷赞
2未成年人不宜
3人身攻击
4抄袭他作
5违法违规
6垃圾广告
7危险病毒
8其他
```
##### ID就是作品ID
#### 返回值
##### 请求变量
#### 示例
```python
report(..., '抄袭', 4, 'https://code.xueersi.com/...', 12345678)
```
