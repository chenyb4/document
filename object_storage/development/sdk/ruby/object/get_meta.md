### 获取对象元数据
#### 前提条件
用户拥有易云云存储系统提供的 `access_key` 及 `secret_key` 并且该用户拥有目标对象的读取权限。

#### 流程说明
1. 初始化 `Client` 实例；
2. 调用 `head_object` 方法获取对象元数据。

#### 示例
```
# 初始化 Client 实例
client = ...

# 获取对象内容
bucket_name = 'new-bucket'
object_name = 'new-object'
client.head_object(
    bucket: bucket_name,
    key: object_name,
)
```
