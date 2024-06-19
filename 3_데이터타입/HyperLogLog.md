# 3. 데이터 타입 알아보기

## HyperLogLog
 - 집합의 cardinality를 추정 할 수 있는 확률형 자료구조
 - 정확성 일부 포기(error 0.81%)-> 저장공간 효율적
 - 근사치만 알아도 될 때 사용
 - 해시 충돌 시 에러

## hyper log log와 hash table의 차이 
https://chatgpt.com/share/d9513bdf-c518-4aef-9461-95517d3f778f


## vs Set
 - 저장을 실질적으로 하지 않기 때문에 저장공간 효율적
 - 적은 메모리로 사용 가능
   
## 명령어
```redis
-- hyper log log set
PFADD fruits apple orange grape kiwi
-- count fruits
PFCOUNT fruits
```