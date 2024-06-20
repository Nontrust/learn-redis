# 3. 데이터 타입 알아보기

## BloomFilter
 - element가 집합안에 포함되었는지 확인
 - 확률형 자료구조 (membership test)
 - 정확성을 포기, 저장공간 효율적으로 사용
 - false positive
   - 집합에 포함되지 않는 element를 포함되었다고 예측 하는 현상
## HyperLogLog vs Bloom Filter 내부 구조
```mermaid
graph TB
  subgraph HyperLogLog
      direction LR
    A1[데이터 입력]
    A2[해시 함수 적용]
    A3[비트 스트림 업데이트]
    A4[Max 비트 길이 추적]
    A5[고유 항목 수 추정]
    
    A1 --> A2
    A2 --> A3
    A3 --> A4
    A4 --> A5
  end
```
```mermaid
graph TB
  subgraph Bloom Filter
    direction LR
    B1[데이터 입력]
    B2[여러 해시 함수 적용]
    B3[비트 배열 업데이트]
    B4[항목 존재 여부 확인]
    
    B1 --> B2
    B2 --> B3
    B3 --> B4
  end

```

## vs Set
 - 저장을 실질적으로 하지 않기 때문에 저장공간 효율적
 - 적은 메모리로 사용 가능
   
## 명령어
```redis
-- hyper log log set
BF.MADD fruits apple orange
BF.EXISTS fruits apple
```

