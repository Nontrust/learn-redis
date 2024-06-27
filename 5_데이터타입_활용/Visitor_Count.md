# 데이터 타입 활용

## Visitor Count
 - Visitor Count Approximation
   - 방문자 수를 대략적으로 추정하는 경우
   - 정확한 수치 필요 없이 대략적인 어림치만 알고자 하는 경우

```redis
PFADD {today}:users
    user:1:1693494070
    user:1:1693494071
    user:2:1693494071
    
 PFCOUNT {today}:users 
```