# Redis 常用命令列表
该列表随着学习持续更新

---

# 基础
#### 登录Redis
`redis-cli [-h 地址] [-p 端口] [-a 密码]`
#### 检查服务是否开启
`PING`
#### 

---

# 键命令
|序号|命令|描述|
|-|-|-|
|1|**DEL key**|删除键 key 对应的元素|
|2|**DUMP key**|序列化 key 对应的元素, 返回被序列化的值|
|3|**EXISTS key**|检查 key 是否存在|
|4|**EXPIRE key s**|设置 key 的过期时间为 s 秒|
|5|**PEXPIRE key ms**|设置 key 的过期时间为 ms 毫秒|
|6|**EXPIREAT key stt**|设置 key 的过期时间戳为 stt, 以秒计|
|7|**PEXPIREAT key mstt**|设置 key 的过期时间戳为 mstt, 以毫秒计|
|8|**KEYS pattern**|查找所有符合模式 pattern 的 key|
|9|**MOVE key db**|将当前数据库的 key 移动到给定的数据库 db 当中|
|10|**PERSIST key**|移除 key 的过期时间, key 将持久保持|
|11|**PTTL key**|以毫秒为单位返回 key 的剩余的过期时间|
|12|**TTL key**|以秒为单位，返回给定 key 的剩余生存时间|
|13|**RANDOMKEY**|从当前数据库中随机返回一个 key|
|14|**RENAME key newkey**|修改 key 的名称|
|15|**RENAMENX key newkey**|仅当 newkey 不存在时, 将 key 改名为 newkey|
|16|**SCAN cursor [MATCH pattern] [COUNT count]**|迭代数据库中的数据库键|
|17|**TYPE key**|返回 key 所储存的值的类型|

---

# 数据类型相关
## string
- 添加 : `SET 键 值`
- 查询 : `GET 键`
- 删除 : `DEL 键`
## hash
- 添加 : `HMSET 键 域1 值1 域2 值2 ...`
- 查询 : `HGET 键 域x`
- 删除 : `DEL 键`
## list
- 插入(头/尾) : `LPUSH 键 值1 值2 ...` / `RPUSH 键 值1 值2 ...`
- 弹出(头/尾) : `LPOP 键` / `RPOP 键`
- 查询 : `LRANGE 键 初始索引 结束索引`
- 删除 : `DEL 键`
## set
- 插入 : `SADD 键 成员1 成员2 ...`
- 查询 : `SMEMBERS 键`
- 删除 : `DEL 键`
## zset
- 插入 : `ZADD 键 权重1 成员1 权重2 成员2 ...`
- 查询 : `ZRANGE 键 初始分数 结束分数` / `ZRANGEBYSCORE 键 初始分数 结束分数`
- 删除 : `DEL 键`

---

