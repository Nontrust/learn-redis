# 3. 데이터 타입 알아보기

## Sorted Set => ZSets
 - Unique String + score(정렬 순서)
   - Unique 한 Set 기능 + score속성 으로 정렬
   - score 가 동일할 시 lexicographically(사전 편찬 순) 정렬

## 명령어
```redis
-- set key score member
ZADD points 10 TeamA 10 TeamB 50 TeamC

-- get range
ZRANGE points 0 -1
-- get range + score
-- redis cli 버전별 차이
ZRANGE points 0 -1 REV WITHSCORES
ZREVRANGE points 0 -1 withscores

-- get index
ZRANK points TeamA
```
