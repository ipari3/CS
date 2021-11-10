<ins>정렬된 데이터</ins>에서 특정 값에 대한 적절한 위치를 찾을 때 사용하며,  
탐색 범위를 반씩 줄여나가 시간복잡도를 O(logN)으로 줄일 수 있다.
#### 기초 구현
arr에 val이 있을 때, val의 위치를 반환한다.  
없으면 -1을 반환한다.
```
def iterative_binary_search(arr, val, s, e):
    # idx in range(s, e)
    while s < e:
        mid = (s + e) // 2
        if arr[mid] == val:
            return mid
        elif arr[mid] < val:
            s = mid + 1
        else:
            e = mid
    return -1

def recursive_binary_search(arr, val, s, e):
    # idx in range(s, e)
    if s >= e:
        return -1
    mid = (s + e) // 2
    if arr[mid] == val:
        return mid
    elif arr[mid] < val:
        return recursive_binary_search(arr, val, mid+1, e)
    else:
        return recursive_binary_search(arr, val, s, mid)
```
#### 삽입할 위치: leftmost, rightmost
값을 넣을 가장 왼쪽/오른쪽의 자리를 반환한다.  
arr에 val이 여러 개 있거나 하나도 없어도 상관없다.
```
def binary_search_leftmost(arr, val, s, e):
    # idx in range(s, e)
    while s < e:
        mid = (s + e) // 2
        if arr[mid] < val:
            s = mid + 1
        else:
            e = mid
    return s

def binary_search_rightmost(arr, val, s, e):
    # idx in range(s, e)
    while s < e:
        mid = (s + e) // 2
        if arr[mid] <= val:
            s = mid + 1
        else:
            e = mid
    return s
```
두 함수의 차이점은 if 문의 조건에서 `<`와 `<=`의 차이다.
- leftmost는 `arr[mid] == val`일 때, mid를 감소시킨다. (e를 감소시킨다.)
- rightmost는 `arr[mid] == val`일 때, mid를 증가시킨다. (s를 증가시킨다.)

주의할 것은 둘 다 `val`의 위치가 `s`라는 것이다.
- arr에 val이 한 개 이상 있으면, leftmost는 첫 번째 val의 위치를 반환한다. (삽입 시, 이 val부터 한 칸씩 뒤로 밀릴 것이다.)  
rightmost는 마지막 val의 다음 위치를 반환한다.
- arr에 val이 하나도 없으면, 둘 모두 val보다 작은 값 중 가장 큰 값의 자리의 다음 위치를 반환한다.

##### 탐색 위치
val을 삽입하는 것이 아닌, val을 기준으로 하여 이보다 크지 않은 최댓값을 얻어야 한다고 하자.
- arr에 val이 있을 때, 반환값 s는 leftmost는 이보다 작은 값, rightmost는 이보다 큰 값의 위치이다.  
따라서 각각 s+1, s-1 위치의 값이 최댓값인 val이다.
- arr에 val이 없을 때, 반환값 s는 둘 모두 val보다 큰 값의 위치이며 s-1은 val보다 작은 값의 위치이다.
따라서 rightmost 함수를 사용하며, s-1 위치의 값이 val보다 크지 않은 최댓값이다.
```
def binary_search_max_ngt_val(arr, val, s, e):
    # return the pos of max which is not greater than val
    # idx in range(s, e)
    while s < e:
        mid = (s + e) // 2
        if arr[mid] <= val:
            s = mid + 1
        else:
            e = mid
    return s - 1
```
