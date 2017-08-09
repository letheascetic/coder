# redis common

## data type

> Redis支持五种数据类型：string（字符串），hash（哈希），list（列表），set（集合）及zset(sorted set：有序集合)。

### string

> SET name "runoob"   # SET name runoob

> GET name

### hash

> HMSET user:1 username runoob password runoob points 200

> HGETALL user:1

### list

> lpush runoob redis

> lpush runoob mongodb

> lpush runoob rabitmq

> lrange runoob 0 10

### set

> sadd runoob redis

> sadd runoob mongodb

> sadd runoob rabitmq

> smembers runoob

### zset (sorted set)

> Redis zset 和 set 一样也是string类型元素的集合,且不允许重复的成员。
不同的是每个元素都会关联一个double类型的分数。redis正是通过分数来为集合中的成员进行从小到大的排序。
zset的成员是唯一的,但分数(score)却可以重复。

> zadd key score member 

> zadd runoob 0 redis

> zadd runoob 0 mongodb

> zadd runoob 0 rabitmq

> zrangebyscore runoob 0 1000




