BFS와 DFS는 가중치가 없는 그래프에 대해, 주어진 시작점에서 특정 노드까지의 최단거리를 찾을 수 있다.
#### BFS
- 각 레벨의 끝까지 우선 탐색.  
- 보통 FIFO 방식인 큐를 이용한다.
- 최솟값이나 최댓값 같은 최적값을 찾는 데 적합하다.
#### DFS
- 각 리프 노드까지 우선 탐색.
- 보통 재귀함수로 구현하고, 단순 스택 배열을 이용하기도 한다.
- 미로의 길찾기 처럼 유일 해를 찾는 데 적합하다.  
완전 리프까지 가지 않고, 휴리스틱하게 돌아나올 수도 있다.  
(BFS에서도 가망 없는 쪽은 쳐내는 방법이 있는데, 이것을 가지치기라고 한다.)
## BFS
Breadth First Search. 너비 우선 탐색.
```
from collections import deque

# Given: graph, start
q = deque()
visited = set()
dist = dict()

q.append(start)
visited.add(start)
d = 1
while q:
    curr = q.popleft()
    for adj in graph[curr]:
        if adj in visited:
            continue
        q.append(adj)
        visited.add(adj)
        dist[adj] = d
    d += 1
```
- 파이썬에서 `queue.Qeueu`는 멀티쓰레드에서 메시지나 데이터의 큐를 처리하기 위한 클래스이고,  
일반적인 큐 자료구조는 `collections.deque`를 이용한다.  
덱이 아닌 큐로만 사용하는 경우, append와 popleft만 사용하면 된다.
- dist에는 시작점부터 다른 모든 노드까지의 최단거리를 담았다.
- 그래프가 너비는 작고 깊이가 클 때 저장 공간이 적게 필요하므로 적합하다.  
목표 노드가 얕은 곳에 있을 때 비교적 빨리 찾을 수 있을 것이다.
### 최선 우선 탐색 (Best First Search)
큐 대신 우선순위 큐를 사용하여, 우선순위가 높은 노드부터 꺼내서 탐색한다.
## DFS
Depth First Search. 깊이 우선 탐색.
```
# Given: graph, start
visited = set()
dist = dict()

def dfs(graph, curr):
    visited.add(start)
    for adj in graph[curr]:
        if adj not in visited:
            dfs(graph, adj)

# iterative method
s = []
visited = set()

s.append(start)
visited.add(start)
while s:
    curr = s.pop()
    for adj in graph[curr]:
        if adj in visited:
            continue
        s.append(adj)
        visited.add(adj)
```
- 위 코드는 단순히 순회만 하는 것으로, 최단거리를 저장하지는 않았다.  
시작점에서 모든 노드까지의 최단거리를 찾는 것은 완전탐색이므로 bfs와 크게 다르지 않지만,  
특정 노드까지의 최단거리만 찾는다면, bfs는 특정 노드를 최초로 찾았을 때가 최단거리이지만,  
dfs는 그렇지 않으며, 최초로 찾았다고 멈추지 말고 완전탐색을 해야 한다.
- 스택을 이용한 경우는 BFS에서 큐를 스택으로 바꾸고 popleft를 pop으로 바꾼 것과 동일하다.
- 그래프가 너비는 크고 깊이가 작을 때 저장 공간이 적게 필요하므로 적합하다.  
목표 노드가 깊은 곳에 있을 때 비교적 빨리 찾을 수 있을 것이다.

#### recursive vs. iterative
- 재귀적 방법은 정확히 리프 노드까지의 노드들만 저장한다.  
하지만 함수 호출에 따른 비용이 생기며, 콜 스택에 따른 오버플로우가 발생할 수 있다.
- 반복적 방법은 리프 노드까지의 인접 노드들까지 저장해놓는다.  
그래도 함수 호출 비용이 없으며, 무엇보다 힙 영역을 이용하므로 비교적 오버플로우 걱정이 적다.
