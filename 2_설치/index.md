# 설치 

https://redis.io/docs/getting-started/installation/install-redis-on-windows/

이미 설치 되어있는 redis-cli이용 예졍
https://github.com/microsoftarchive/redis/releases/tag/win-3.2.100

이었으나, 윈도우 msi 파일 다운로드시 저버전을 제공해 안정적인 실습을 위해 docker 환경으로실습   
Docker desktop 설치 이후 이미지로 설치 예정  

 - Docker desktop or Docker 다운로드 
   - 로컬환경 구성을 위해 설치함으로 Docker Desktop 으로 docker 환경 구성 https://docs.docker.com/desktop/install/windows-install/
   - 환경 구축 이후 docker-compose.yml 로 docker internet 6379 port -> 에서 윈도우 local의 6378으로 exopse
     - (이미 사용중인 저버전 레디스가 있어서)
    

```shell
 # project 내 docker-compose.yml 파일 사용
 $  docker-compose up -d
 $ redis-cli -h localhost -p 6378
```





```shell
#local redis
$ redis-cli  
```

```redis
PING
-- PONG
SET test-key test-value 
-- OK
GET test-key
-- "test-value"
DEL test-key
-- (integer) 1
GET test-key
-- (nil)
```