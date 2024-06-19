# 3. 데이터 타입 알아보기

## Bitmaps
 - **실제 데이터 타입X**
 - String에 binary operation을 적용
 - 2^32승 만큼 표현 가능( 적은 메모리로 바이너리 상태값 저장 )
   
## 명령어

```redis
-- 로그인 기록
SETBIT user:log-in:23-01-01 123 1
SETBIT user:log-in:23-01-01 456 1

SETBIT user:log-in:23-01-02 123 1

-- 230101의 로그인 수를 Count
BITCOUNT user:log-in:23-01-01

-- result에 230101과 230102에 로그인 기록을 and 연산으로 기록  
BITOP AND result user:log-in:23-01-01 user:log-in:23-01-02
-- result출력
GETBIT result 123
```