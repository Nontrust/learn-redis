# 3. 데이터 타입 알아보기

## Streams
 - append-only log에 consumer groups과 같은 기능을 더한 자료 구조
 - unique id로 하나의 entry를 읽을 때 O(1) 시간 복잡도
   - consumer group을 통해 분산시스템에서 다수의 consumer가 event 처리

## 명령어

```redis
XADD events * action like user_id 1 product_id 1
XADD events * action like user_id 2 product_id 1

XRANGE events - +

XDEL events {ID}
```