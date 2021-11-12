## OSI 계층
#### (응용 프로세스)
#### 계층 7. 응용 계층 (Application Layer)
- 응용 프로세스와 직접 관계.
- 관련된 응용 프로세스들 사이의 전환을 제공.
- 네트워크 소프트웨어 UI 부분, 사용자의 입출력 부분
##### 요소
- HL7, Modbus, SIP
- HTTP, SMTP, SNMP, FTP, 텔넷, NFS, NTP (TCP/IP 스위트)
#### 계층 6. 표현 계층 (Presentation Layer)
- 코드 간의 번역을 담당.
- 사용자 시스템에서 데이터의 형식상 차이를 다루는 데 도움.
- 사용자의 명령어 완성 및 결과 표현, 포장/압축/암호화(인코딩)
##### 요소
- TDI, ASCII, EBCDIC, MIDI, MPEG
- XDR (TCP/IP 스위트)
#### 계층 5. 세션 계층 (Session Layer)
- 양 끝단의 응용 프로세스가 통신을 관리하는 방법 제공.
- 동시 송수신 방식(duplex), 반이중 방식(half-duplex), 전이중 방식(full duplex) 통신 등을 이용.
- 체크 포인팅, 유휴, 종료, 재시작 과정 등을 수행.
- TCP/IP 세션을 만들고 없애는 책임.
- 통신을 하기 위한 세션 확립, 유지, 중단 (운영체제가 해줌)
##### 요소
- FIFO(파이프), 넷바이오스, SAP, SDP, SSL, TLS
- TCP의 세션 관리 부분 (TCP/IP 스위트)
#### 계층 4. 전송 계층 (Transport Layer)
- 양 끝단의 사용자들이 신뢰성있는 데이터를 주고 받을 수 있도록 도움.
- 상위 계층들이 데이터 전달의 유효성이나 효율성을 생각하지 않도록 해줌.
- 시퀀스 넘버 기반의 오류 제어 방식 사용.
- 특정 연결의 유효성을 제어.
- 일부 프로토콜은 상태 개념이 있고(stateful), 연결 기반(connection oriented)이다.  
즉, 전송 계층이 패킷들의 전송이 유효한지 확인하고 전송 실패한 패킷들을 다시 전송한다.
- 종단간 통신을 다루는 최하위 계층이다.
- 종단간 신뢰성 있고 효율적인 데이터를 전송
- 오류검출, 복구, 흐름제어, 중복검사  
패킷생성: Assembly, Sequencing, Deassembly, Error detection, Request repeat, Flow control
- TCP가 이 계층에 속한다.
##### 요소
- NetBEUI
- TCP, UDP, RTP, SCTP (TCP/IP 스위트)
#### 계층 3. 네트워크 계층 (Network Layer)
- 노드를 거칠 때마다 경로를 찾아주는 역할.
- 네트워크를 통해 데이터를 전달하고, 전송 계층이 요구하는 서비스 품질(QoS)을 제공하기 위한 기능적, 절차적 수단 제공.
- IP주소와 같이, 네트워크 관리자가 직접 주소를 할당하며 계층적이다.
- 서브넷의 최상위 계층으로, 경로를 설정하고 청구 정보를 관리한다.
- 개방형 시스템 사이에서 네트워크 연결을 설정, 유지, 해제하는 기능을 부여한다.  
전송 계층 사이에 네트워크 서비스 데이터 유닛(Network Service Data Unit. NSDU)을 교환하는 기능을 제공한다.
- 라우팅, 흐름제어, 세그멘테이션, 오류제어, 인터네트워킹, 주소부여(IP)
- 라우터가 이 계층에서 동작한다.  
이 계층에서 동작하는 스위치도 있다.
##### 요소
- NetBEUI, Q.931
- IP, ICMP, IPsec, ARP, RIP, BGP (TCP/IP 스위트)
#### 계층 2. 데이터 링크 계층 (Data Link Layer)
- point-to-point 간 신뢰성있는 전송을 보장하기 위한 계층이다.
- CRC 기반의 오류 제어와 흐름 제어가 필요하다.
- 네트워크 상의 개체들 간 데이터를 전달.  
물리 계층에서 발생할 수 있는 오류 탐지 및 수정하기 위한 기능적, 절차적 수단 제공.
- MAC주소를 사용한다. 즉, 주소가 계층이 없는 단일 구조이다.
- 이더넷이 이 계층에 속한다.  
그 외에도 point-to-point 프로토콜(HDLC, ADCCP), 근거리 네트워크용 프로토콜(패킷 스위칭 네트워크 LLC, ALOHA)이 있다.
- 네트워크 브릿지와 대부분의 스위치가 이 계층에서 동작한다.  
이들은 직접 이어진 곳에만 연결할 수 있다.
- 프레임에 주소부여, 에러검출/재전송/흐름제어
##### 요소
- 이더넷, 토큰링, FDDI, PPP, HDLC, Q.921, 프레임 릴레이, ATM, Fibre Channel
#### 계층 1. 물리 계층 (Physical Layer)
- 기본 네트워크 하드웨어 전송 기술을 이룬다.
- 네트워크의 고수준 기능의 논리 데이터 구조를 기초로하는 필수 계층이다.
- 다양한 특징의 하드웨어 기술이 접목되어 있어, 가장 복잡한 계층으로 간주된다.
##### 요소
- RS-232, V.35, V.34, Q.911, T1, E1, 10BASE-T, 100BASE-TX, ISDM, SONET, DSL
#### (하드웨어)

## 계층별 프로토콜
### 계층 7. 응용 계층
#### 모드버스 (Modbus)
- 시리얼 통신 프로토콜
- 제조공장이나 놀이공원 등의 기계 자동화 및 제어를 위한 PLC들과의 통신
- 산업용, 공개 및 무료 프로토콜, 성치와 유지보수가 용이, 비트아 워드(16비트) 단위의 정보조작이 용이
#### SIP (Session Initiation Protocol. 세션 개시 프로토콜)
- 시그널링 프로토콜
- 음성과 화상 통화같은 멀티미디어 세션 제어
- 전화, 인터넷 컨퍼런스, 인스턴트 메신저 등의 지능형 단말들이 서로 식별하고 세션을 생성, 삭제, 수정
- TCP와 UDP에 모두 사용 가능, 이메일 주소와 비슷한 SIP URL 사용(IP주소에 종속되지 않음)
- HTTP와 SMTP의 많은 부분 차용, 텍스트 기반, 유연성과 확장성.
#### HTTP (HyperText Transfer Protocol)
- W3 상에서 정보를 주고받기 위한 프로토콜.  
클라이언트와 서버 사이에 이루어지는 요청/응답(request/response) 프로토콜.
- 주로 TCP 사용, HTTP/3부터 UDP 사용.  
80번 포트를 사용한다.
#### SMTP (Simple Mail Transfer Protocol. 간이 우편 전송 프로토콜)
- 인터넷에서 이메일을 보내기 위해 사용하는 프로토콜.
- TCP 포트번호는 25번이다.
#### SNMP (Simple Network Management Protocol. 간이 망 관리 프로토콜)
- IP 네트워크상의 장치로부터 정보를 수집, 관리, 수정
- 이를 지원하는 장치로는 라우터, 스위치, 서버, 워크스테이션, 프린터, 모뎀 랙 등이 있다.
#### FTP (File Transfer Protocol. 파일 전송 프로토콜)
- TCP/IP 프로토콜을 가지고 서버와 클라이언트 사이의 파일 전송.
- 보안에 취약하다.
- FTPS, SSH FTP, TFTP(Trivial FTP), SFTP(Simple FTP) 등의 프로토콜이 파생되었다.
#### TELNET (텔넷)
- 인터넷이나 로컬 영역 네트워크 연결에 쓰이는 프로토콜.
- 보안 문제 때문에 사용륭이 감소했으며, 원격 제어를 위해 SSH로 대체되기도 하였다.
#### NFS (Network File System)
- 클라이언트 컴퓨터의 사용자가 직접 연결된 스토리지에 접근하는 방식과 비슷한 방식으로  
네트워크 상의 파일에 접근하도록 도와주는 프로토콜.
#### NTP (Network Time Protocol)
- 컴퓨터 시스템 간 시간 동기화를 위한 프로토콜.
- 패킷 교환(packet switching)과 가변 레이턴시 데이터 네트워크를 이용한다.
## 계층 6. 표현 계층
#### TDI (Tabbed Document Interface)
- 하나의 창 안에 여러 탭을 생성해서, 각 탭을 통해 브라우징하는 것.
- 웹 브라우저, 웹 애플리케이션, 문서 편집기, 워드 프로세서, 스프레드시트 등에서 사용된다.
#### ASCII (American Standard Code for Information Interchange. 아스키)
- 영문 알파벳을 사용하는 7비트 문자 인코딩. (총 128 문자)
#### EBCDIC (Extended Binary Coded Decimal Interchange Code. 확장 이진화 십진법 교환 부호. 엡시딕)
- 8비트 문자 인코딩
#### MIDI (Musical Instrument Digital Interface. 악기 디지털 인터페이스. 미디)
- 전자 악기끼리 디지털 신호를 주고받기 위해 각 신호를 규칙화한 규약.
#### MPEG (Moving Picture Experts Group. 엠펙)
- 영상 압축 방법
- 손실 압축 방식을 사용한다.
## 계층 5. 세션 계층
#### NetBIOS (Network Basic Input/Output System. 넷바이오스)
- LAN 기술을 이용한 통신 소프트웨어요 API
- 애플리케이션들이 근거리 통신망을 통해 통신할 수 있게 한다.
#### SAP (Service Advertising Protocol. 서비스 광고 프로토콜)
- 넷웨어(NetWare)의 네트워크층 프로토콜인 IPX의 상위 계층에서 동작하는 통신 규약.  
넷웨어는 네트워크 운영 체제(NOS)이다.
- 넷웨어의 서버와 클라이언트 사이에서 주소 정보나 그 서버가 제공하는 파일 서버, 프린터 서버 등의 서리스를 알린다.
#### TLS (Transport Layer Security. 전송 계층 보안)
- 과거 명칭은 SSL(Secure Sockets Layer. 보안 소켓 레이어)이다.  
SSL이 표준화되면서 TLS로 명칭이 변경되었다.  
다만 IETF(국제 인터넷 표준화 기구)에 의해 구식(deprecate)으로 간주되어있다.
- 네트워크에 통신 보안을 제공하기 위해 설계된 암호 규약.
- 전송계층 종단간 보안과 데이터 무결성을 확보해준다.
- 웹 브라우징, 전자 메일, 인스턴트 메신저, VoIP(voice-over-IP) 등에서 적용되고 있다.
## 계층 4. 전송 계층
#### NetBEUI (NetBIOS Extended User Interface. 넷뷰)
- 넷바이오스 에뮬레이터  
PC 네트워크 상에서 넷바이오스를 인식하는 애플리케이션들이 새로운 디자인에서 동작할 수 있게 한다.  
기본 넷바이오스 API를 확장하면서 토큰 링의 노드 능력을 확대시킨다.
#### TCP (Transmission Control Protocol. 전송 제어 프로토콜)
- 네트워크에 연결된 컴퓨터에서 실행되는 프로그램 간에 데이터를 교환할 때  
안정적으로, 순서대로, 에러없이 교환할 수 있게 한다.
#### UDP (User Datagram Protocol. 사용자 데이터그램 프로토콜)
- TCP의 안정성이 필요하지 않은 애플리케이션에서 주로 사용한다.
- 오버헤드가 작고 지연시간이 짧다.
#### RTP (Real-time Transport Protocol. 실시간 전송 프로토콜)
- IP 네트워크 상에서 오디오와 비디오를 전달하기 위한 프로토콜.
- 전화, WebRTC, 텔레비전 서비스, 화상 통화 등의 스트리밍 미디어를 수반하는 통신에 사용된다.
- 일반적으로 UDP로 동작한다.
- RTCP(TRP Control Protocol)와 결합하여 사용된다.  
RTCP는 전송 통계와 QoS르르 모니터링하고 다중 스트림의 동기화를 도와준다.
#### SCTP (Stream Control Transmission Protocol)
- TCP나 UDP와 비슷한 역할을 한다.
- 프로토콜 번호 132를 사용한다.
## 계층 3. 네트워크 계층
#### IP (Internet Protocol. 인터넷 프로토콜. 아이피)
- 송수신 호스트가 정보를 주고받는 데 사용하는 규약.
- 호스트의 주소 지정, 패킷 분할 및 조립 등의 기능.
- 비신뢰성: 흐름에 관여하지 않아, 송신한 정보가 제대로 수신됐는지 보장하지 않는다.  
비연결성: 
