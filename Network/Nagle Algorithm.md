IP 네트워크에서 데이터에 포함되는 헤더 크기가 작지는 않다.  
정보 데이터가 적은 경우에는 헤더가 더 커지는 경우도 발생하며, 이는 비효율적인다.  
따라서 데이터를 패킷으로 만들 때, 전송을 지연시키고 모아서 큰 패킷으로 만든다.  
다만 전송 속도는 더 느리다.
```
# MSS = maximum_segment_size
if new_data: # new data to send
    if (window_size >= MSS) and (data_size >= MSS):
        send(data)
    else:
        if not confirmed(q):
            q.append(data)
        else:
            send(data)
```
