FIFO의 자료구조로, 스택과 대비된다.  
원소의 삽입은 맨 뒤, 삭제는 맨 앞에서 이루어진다.  
구현은 보통 연결 리스트를 사용하며, 맨 앞의 원소를 빼내는 것과 뒤에 원소를 추가하는 기능만 구현하면 된다.  
원소를 넣는 것은 enqueue, 빼는 것은 dequeue라고 한다.

## 원형 큐
큐의 시작과 끝을 포인터로 가리키며 각각 front, rear 혹은 head, tail이라고 부른다.
#### 초기화
front와 rear를 -1로 초기화한다.
#### 삽입 (enqueue)
1. full이면 에러
2. empty면 front를 0으로 한다.
3. rear는 (rear + 1)/size
4. rear 위치에 원소를 넣는다.
#### 삭제 (dequeue)
1. empty면 에러
2. front 위치의 원소를 반환
3. front는 (front + 1)/size
4. 마지막 원소였으면 front와 rear를 -1로 한다.
#### empty
결과적으로 empty면 front와 rear 둘 다 -1이다.  
다만 삭제 과정에서 삭제한 원소가 마지막 원소였는지 판단할 때는,  
`front == rear`이면 마지막 원소를 삭제한 것이라고 결론지을 수 있다.
#### full
front가 rear보다 클 수 있으며 full 상태는 두 가지로 나눌 수 있다.
- (front == 0) && (rear == size - 1)
- front == rear + 1
### 다른 방법
공간을 하나 비워놓으면 좀 더 간단하게 구현할 수 있다.  
배열을 이용하는데, 배열은 삭제 시 맨 앞의 원소를 제거하므로 나머지 데이터들을 앞으로 밀어줘야 한다.  
이를 피하기 위해 원형 버퍼를 사용한다.  
이 경우, 비어있을 때와 가득 찼을 때의 두 포인터 위치가 같게 되는데, 이를 해결하기 위해 공간을 하나 비워놓는 것이다.  
empty와 full의 판단은 동일하다.
- empty: front == rear
- full
  - (front == 0) && (rear == size - 1)
  - (front == rear + 1)

## 기타
#### 우선순위 큐 (Priority Queue)
dequeue가 먼저 들어온 순서가 아니라 특정한 우선순위에 따라 결정된다.  
즉, 맨 앞에 우선순위가 가장 높은 원소가 들어있는 셈이며 보통 [힙][1] 구조로 구현된다.
#### 데크 (Double Ended Queue. Deque)
삽입과 삭제가 각각 앞뒤 모두에서 이루어질 수 있다.  
스택과 큐를 합친 것으로 볼 수 있다.


[1]: https://github.com/ipari3/CS/blob/main/Data%20Structure/Heap.md
