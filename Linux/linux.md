## curl 发送POST请求

JSON格式

```
curl -d '{"APP_ID":"FYU2bxdqAz","TIMESTAMP":"2023-05-19 10:32:00 192","TRANS_ID":"20230519103200192296906","TOKEN":"a97ce46d98c27f0fb641b7e33a0acf5e"}' -H "Content-Type: application/json" -X POST "127.0.0.1:9094/quantity/batchTaskdata"
```

发送文件

```
curl -X POST -F 'image=@/home/user/Downloads/profile.jpg' http://example.com/upload
```

携带参数

```
curl -d "firstname=John&lastname=Andrew" -X POST http://example.com
```

## redis 命令

进入redis

```
redis-cli
```

查询key（模糊查询打*）

```
keys *name*
```

命令行直接查询key信息

```
redis-cli -n 1 keys "*name*"
```

删除key

```
del name
```

模糊删除key

```
redis-cli -n 1 keys "*name*" | xargs redis-cli -n 1 DEL
```

如果上面删除报错可编写一个lua脚本执行

de.lua

```
local key=KEYS[1]
local list=redis.call("keys", key);
for i,v in ipairs(list) do
    redis.call("del", v);
end
```

执行lua脚本

```
redis-cli -n 1 --eval ./de.lua "*name*"
```

## tail 命令

实时查看文件刷新内容

```
tail -f info.log
```



## grep 搜索文件内容

```
grep 'context' info.log
grep 'context1' info.log |grep 'context2'
//搜索目标后的一百行
grep -100A info.log   
//搜索目标前的一百行
grep -100B info.log   
```

