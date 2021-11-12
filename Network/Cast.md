## Cast
데이터 혹은 패킷 스트림이 통신 채널을 통해 클라이언트(client)에서 수신자(recipient)로 전송되는 것이다.

### Unicast
단일 송신자(sender)와 단일 수신자(recipient)가 있는 전송으로,  
일대일 전송(one-to-one transmission)이라고 할 수 있다.  
네트워크에서 가장 일반적인 형식의 데이터 전송 방식이다.

### Broadcast
one-to-all 방식의 전송 기술로, 두 가지 타입으로 분류할 수 있다.
#### Limited Broadcasting
동일 네트워크 상의 모든 수신자에게 데이터를 전송한다.  
이를 위해 255.255.255.255를 덧붙인다. (IP 주소의 모든 32비트를 1로 만든다.)  
이는 Limited Bradcast Address라고 부른다.
#### Direct Broadcasting
다른 네트워크 상의 모든 수신자에게 데이터를 전송한다.  
이를 위해 모든 도착 주소의 호스트 ID 부분의 비트를 1로 만든다.  
이를 Direct Broadcast Address라고 부른다.  
  
이 모드는 텔레비전 네트워크에서 비디오와 오디오 분배에 사용된다.  
이 모드는 [Address Resolution Protocol(ARP)][1]가 필요하다.  
이 프로토콜을 이용하여 IP 주소를 물리(physical) 주소로 푼다(resolve).

### Multicast
one/many-to-one/many 방식으로, 송수신자의 수에 제한이 없다.  
서버가 direct single 복사할 수 있다.  
이는 요청한 호스트에게 라우팅된다.  
  
IP 멀티캐스트는 IGMP(Internet Group Management Protocol)이나 멀티캐스트 라우팅 같은 다른 프로토콜을 필요로 한다.  
또한 [클래스 IP 어드레싱][2]에서 클래스D는 멀티캐스트 그룹에 예약되어 있다.

[1]: https://www.geeksforgeeks.org/how-address-resolution-protocol-arp-works/
[2]: https://ko.wikipedia.org/wiki/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_%ED%81%B4%EB%9E%98%EC%8A%A4
