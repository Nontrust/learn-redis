# 설치 

https://redis.io/docs/getting-started/installation/install-redis-on-windows/

이미 설치 되어있는 redis-cli이용 예졍
https://github.com/microsoftarchive/redis/releases/tag/win-3.2.100


```shell
$ redis-cli  
```

```redis
PING
-- PONG
SET test-key test-value 
-- OK
GET test-key
-- "test-value"
DEL test-key
-- (integer) 1
GET test-key
-- (nil)
```