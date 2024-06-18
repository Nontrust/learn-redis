# 3. 데이터 타입 알아보기

## Hashes
 - field-value 구조
 - 다양한 속성을 갖는 객체의 데이터를 저장

## 명령어
```redis
-- cli 4버전 이상
HSET lecture name inflearn-redis price 100 language ko
-- cli 4버전 미만
HSET lecture name inflearn-redis
HSET lecture price 100
HSET lecture language ko


HGET lecture name
HMGET lecture price language invalid

HINCRBY lecture price 10
```