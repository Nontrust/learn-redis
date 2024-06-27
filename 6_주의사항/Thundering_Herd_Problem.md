# 주의사항

## Thundering Herd Problem
 - 병렬 요청이 공유자원에 대해 접근 시도
   - 많은 리소스를 요구하는 통계 데이터 캐싱
   - 해당 통계데이터가 만료
   - 캐시미스로 DB 재 조회
   - 급격한 과부화 발생


```mermaid
zenuml
@Actor Client as "많은 클라이언트"
@Server Server
@Database Redis
@Database Database

Client -> Server: (00:00:00) request 1
Client -> Server: (00:00:00) request 2
Client -> Server: (00:00:00) request 3
Client -> Server: (00:00:00) request 4
Client -> Server: (00:00:00) request 5
Server -> Redis: 1. get
Redis -> Server: 2. miss

Server -> Database: 3. Big query 🔥
Server -> Database: 3. Big query 🔥
Server -> Database: 3. Big query 🔥

Database -> Server: 3-1. GET Reuslts 🔥
Database -> Server: 3-1. GET Reuslts 🔥
Database -> Server: 3-1. GET Reuslts 🔥

Server -> Server: 4. amazing calculate🔥(1s)
Server -> Server: 4. amazing calculate🔥(1s)
Server -> Server: 4. amazing calculate🔥(1s)

Server -> Redis: 5. add
Server -> Redis: 5. add
Server -> Redis: 5. add

while(Thundering){
     Redis -> Redis: Single thread Overload 💣💣💣
}
```
Jitter 혹은 cron job으로 해당 캐시가 만료되지 않도록 설정

[해결방법](https://toss.tech/article/cache-traffic-tip)