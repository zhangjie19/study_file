# Redis学习

redis支持二进制的五种数据类型 String（字符串）、List（列表）、hash（哈希）、set（集合）、zset（有序集合）



## 1.常用命令

### 1.String

```
set key value 创建k-v数据

get key  获取对应key的数据

flushdb  清空数据库

keys *  查看所有的key

exists key  检查key是否存在

append key value  针对已有的key的value上追加值

strlen key   获取key对应value的长度

```

### 2. List

```mysql
--增加
lpush mylist  value1 value2 ... 向mylist列表左边插入值 追加和新建都用这个命令

rpush mylist  value1 value2 ... 向mylist列表右边插入值 追加和新建都用这个命令

lrange mylist 0 1    查看mylist列表前两个值

linsert mylist  before|after 已有value 新增value  向mylist列表指定值之前或者之后增加value
--查询
exists mylist  查看list是否存在

llen mylist 查看mylist的长度

lindex mylist index  查看mylist对应index下标的值
--修改
lset mylist index value 根据下标修改mylist的值

--删除
lpop mylist  删除mylist左侧的第一个数据

rpop mylist  删除mylist 右侧的第一个数据

lrem mylist count value  mylist 存在多个相同value  该命令删除count个value
```

### 3.set

```
sadd myset  value1 value2 ... 向myset中添加value值

smembers myset  查看myset有哪些value

scard myset 查看myset有多少个value

spop myset 随机删除myset中的一个value

srem myset value  删除myset指定value





```

