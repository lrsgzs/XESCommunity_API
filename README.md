# XESCommunity_API - 学而思编程社区模块化API

## 函数

### def save(Name :str,xml,Cookie :str,headers={},type_='webpy') -> object:
#### 作用
##### 保存作品
#### 参数
##### Name: 作品名
##### xml: 作品内容
##### Cookie: COOKIE
##### headers: 自定义请求头
##### type_: 作品类型 scratch python cpp
#### 返回值
##### 请求变量
#### 示例
```python
save("作品名", 'print(\"hhh\")', ..., {...}, 'python')
```

### def push(res,name='NONE') -> object:
#### 作用
##### 发布作品
#### 参数
##### res: 请求变量
###### 与save配套使用
##### name: 作品名
#### 返回值
##### 请求变量
#### 示例
```python
push(save(...), '作品名')
```

### def report(Cookie :str,Reason :str,reason_detail :int,complaint_reason_url :str,id_ :int) -> object:
#### 作用
##### 举报作品
#### 参数
##### Cookie: COOKIE
##### Reason: 理由
##### reason_detail: 理由类型，1、2、3等
##### complaint_reason_url: （被抄袭）源地址
##### id_: 作品ID
#### 返回值
##### 请求变量
#### 示例
```python
report({...}, '抄袭', 1, 'https://code.xueersi.com/...', 12345678)
```
