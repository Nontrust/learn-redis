# 3. 데이터 타입 알아보기

## Strings 
 - 문자열, 숫자, serialized object(JSON string) 저장

## 명령어

```redis
-- key value String
SET key value
-- 다수의 Strings
MSET key1 value1 key2 value2 
MGET key1 key2

-- 별도의 integer 타입은 없지만 연산 가능
-- +1
INCR price
-- +n
INCRBY price 10

-- serialize 된 json 을 String 형태로 사용
SET test-json '{"name":"book", "price":100}'
-- 의미 단위별로 ':'로 구분(convention)
SET test-data:book:price 100
```