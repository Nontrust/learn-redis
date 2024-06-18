# 3. 데이터 타입 알아보기

## Lists
- String을 Linked List 로 저장 (이중 연결 리스트)
  - push/pop 에 최적화 O(1) 
  - Queue / Stack에 구현에 사용
  - message broker 응용 가능
- 명령어
```redis
-- queue push pop(LPUSH / RPOP)
LPUSH queue job1 job2 job3
RPOP queue

-- stack push pop(LPUSH / LPOP)
LPUSH stack job1 job2 job3
LPOP stack

-- queue handling (우측 인덱스부터 사용 시 음수로)
LPUSH queue2 job1 jo2 job3
LRANGE queue2 -2 -1
LTRIM queue2 0 0
```