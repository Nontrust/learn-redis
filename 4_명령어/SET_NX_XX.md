# Redis 특수 명령어

## SET 특수 명령어(NX/XX)
- NX : Key가 **존재하지 않는** 경우에만 SET 
- XX : Key가 **존재하는** 경우에만 SET
- Null Reply : SET이 동작하지 않은 경우 (nil)응답

```redis
SET greeting hello NX
SET greeting hello XX
```
