# 데이터 타입 활용

## Geofencing
 - 위치를 활용하여 지도상의 가상의 경계 또는 지리적 영역을 정의하는 기술
 - 반경 탐색이 가능

```redis
GEOADD gang-nam:burgers 
    127.025705 37.501272 five-guys
    127.025599 37.502775 shake-shake
    127.028747 37.498668 mc-donalds
    127.027531 37.498847 burger-king    
-- GEOADD gang-nam:stations 127.027583 37.497928 0.5KM

GEORADIUS gang-nam:burgers 127.027583 37.497928 0.5 KM
GEORADIUS gang-nam:burgers 127.027583 37.497928 400 M
GEORADIUS gang-nam:burgers 127.027583 37.497928 600 M
```