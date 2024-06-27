 

## Inflearn 강의 요약 <img src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=Redis&logoColor=white">
 [실전! Redis 활용](https://www.inflearn.com/course/%EC%8B%A4%EC%A0%84-redis-%ED%99%9C%EC%9A%A9/dashboard)  

##
[Mermaid.js 의 ZenUML](https://mermaid.js.org/syntax/zenuml.html) 을 시각자료로 활용함으로 해당 플러그인과 함께 보시는 것을 권장드립니다. 

```yaml
## docker-compose.yml
version: '3.8'

services:
  redis-stack:
    image: redis/redis-stack-server:latest
    ports:
      - "6378:6379"
      - "8001:8001"
    restart: no
```

```shell
    # project 내 docker-compose.yml 파일 사용
    $ docker-compose up -d
    $ redis-cli -h localhost -p 6378
```