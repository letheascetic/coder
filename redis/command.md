# redis command script

### connect to remote redis server

> redis-cli -h host -p port -a password

### Redis keys 命令

###### DEL KEY_NAME

> Redis DEL 命令用于删除已存在的键。不存在的 key 会被忽略。

###### DUMP KEY_NAME

> 序列化给定 key,并返回被序列化的值,如果 key 不存在，那么返回 nil

###### EXISTS KEY_NAME

> 若 key 存在返回 1 ，否则返回 0 。

###### Expire KEY_NAME TIME_IN_SECONDS

> 设置 key 的过期时间。key 过期后将不再可用。

> 设置成功返回 1 。 当 key 不存在或者不能为 key 设置过期时间时(比如在低于 2.1.3 版本的 Redis 中你尝试更新 key 的过期时间)返回 0 。

###### Expireat KEY_NAME TIME_IN_UNIX_TIMESTAMP

> 以 UNIX 时间戳(unix timestamp)格式设置 key 的过期时间。key 过期后将不再可用。

> 设置成功返回 1 。 当 key 不存在或者不能为 key 设置过期时间时(比如在低于 2.1.3 版本的 Redis 中你尝试更新 key 的过期时间)返回 0 。

    EXPIREAT runoobkey 1293840000

###### PEXPIREAT KEY_NAME TIME_IN_MILLISECONDS_IN_UNIX_TIMESTAMP

###### KEYS PATTERN

> 查找所有符合给定模式 pattern 的 key

    redis 127.0.0.1:6379> SET runoob1 redis
    OK
    redis 127.0.0.1:6379> SET runoob2 mysql
    OK
    redis 127.0.0.1:6379> SET runoob3 mongodb
    OK
    redis 127.0.0.1:6379> KEYS runoob*
    1) "runoob3"
    2) "runoob1"
    3) "runoob2"

###### MOVE KEY_NAME DESTINATION_DATABASE

> 将当前数据库的 key 移动到给定的数据库 db 当中.移动成功返回 1 ，失败则返回 0 。

###### PERSIST KEY_NAME

> 移除给定 key 的过期时间，使得 key 永不过期.当过期时间移除成功时，返回 1 。 如果 key 不存在或 key 没有设置过期时间，返回 0 。

###### PTTL KEY_NAME

> 以毫秒为单位返回 key 的剩余过期时间. 

> 当 key 不存在时，返回 -2 。 当 key 存在但没有设置剩余生存时间时，返回 -1 。 否则，以毫秒为单位，返回 key 的剩余生存时间。

###### TTL KEY_NAME

> 以秒为单位返回 key 的剩余过期时间。当 key 不存在时，返回 -2 。 当 key 存在但没有设置剩余生存时间时，返回 -1 。 否则，以秒为单位，返回 key 的剩余生存时间。

###### RANDOMKEY 

> 从当前数据库中随机返回一个 key. 当数据库不为空时，返回一个 key 。 当数据库为空时，返回 nil 。

###### RENAME OLD_KEY_NAME NEW_KEY_NAME

> 修改 key 的名称 .改名成功时提示 OK ，失败时候返回一个错误。
> 当 OLD_KEY_NAME 和 NEW_KEY_NAME 相同，或者 OLD_KEY_NAME 不存在时，返回一个错误。当 NEW_KEY_NAME 已经存在时，RENAME 命令将覆盖旧值。

###### RENAMENX OLD_KEY_NAME NEW_KEY_NAME

> 在新的 key 不存在时修改 key 的名称

> 修改成功时，返回 1 。 如果 NEW_KEY_NAME 已经存在，返回 0 。

###### TYPE KEY_NAME 

> 返回 key 所储存的值的类型.

> 返回 key 的数据类型，数据类型有：

    * none (key不存在)
    * string (字符串)
    * list (列表)
    * set (集合)
    * zset (有序集)
    * hash (哈希表)


### CONFIG 命令

#### CONFIG GET

> CONFIG GET CONFIG_SETTING_NAME

> CONFIG GET loglevel

> CONFIG GET *

#### CONFIG SET

> CONFIG SET CONFIG_SETTING_NAME NEW_CONFIG_VALUE

> CONFIG SET loglevel "notice"





###### FLUSHDB

> 删除当前数据库所有 key



