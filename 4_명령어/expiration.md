# Redis 특수 명령어

## Expiration(데이터 만료)
 - 데이터를 특정 시간 이후 만료
 - TTL (데이터 유효시간, Time To Live)
 - 조회시 만료 된 데이터가 조회되지 않음
   - 즉각 삭제 아닌, 만료 표기 이후 백그라운드에서 주기적 삭제

```redis
SET greeting hello
expire greeting 10
TTL greeting

GET greeting

-- set + TTL설정
SETEX greeting 10 hello
```