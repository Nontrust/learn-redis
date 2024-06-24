# Redis 특수 명령어

## Pub/Sub
 - Publisher와 Subscriber가 서로 알지 못해도 통신 가능
   - Decoupling 장점 
 - Publisher는 Subscriber가 직접 메시지를 보내지 않음
   - Channel에 Publish
   - Subscriber는 관심이 있는 Channel을 필요에 따라 Subscribe 하며 메시지 수신

## VS. Stream
 - Stream : 메시지 보관
 - Pub/Sub : Subscribe 하지 않을 때 발행된 메시지 수신 불가

```redis
SUBSCRIBE ch:order ch:payment
PUBLISH ch:order new-order
PUBLISH ch:payment new-payment
```