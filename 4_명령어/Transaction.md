# Redis 특수 명령어

## Transaction
 - 다수의 명령을 하나의 트랜잭션으로 처리 -> (원자성)
 - 중간에 에러 발생 시 모든 작업 Rollback
 - 하나의 트랜잭션이 처리되는 동안 다른 크라이언트 요청이 중간에 끼어들 수 없음

## 원자성(Atomicity)
 - All or Nothing / 모든작업 적용 or 하나도 적용되지 않거나

## vs. PipeLine
 - Pipeline 네트워크 퍼포먼스 향상(1요청 -> 다수의 명령어)
 - Transactional은 작업의 원자성을 보장 (다수의 명령어 -> 하나처럼)
 - Pipeline과 Transactional을 동시에 사용 가능

```redis
-- Transaction 시작
MULTI  
INCR foo
-- Rollback
DISCARD
-- Commit
EXEC
```
