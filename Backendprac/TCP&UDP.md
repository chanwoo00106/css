# TCP, UDP 차이

TCP와 UDP는 데이터를 보내기 위해 사용하는 프로토콜이다.

결론부터 보자면

비교 대상|TCP|UDP
---|---|---
연결방식|연결형서비스|비 연결형 서비스
패킷 교환 방식|가상 회선 방식|데이터그램 방식
전송 순서|전송 순서 보장|전송 순서가 바뀔 수 있음
수신 여부 확인|수신 여부를 확인함|수신 여부를 확인하지 않음
통신 방식|1:1 통신만 가능|1:1 / 1:N / N:N 통신 모두 가능
신뢰성|높음|낮음
속도|느림|빠름    


## TCP
TCP(Trasmission Control Protocol)는 `연결 지향적` 프로토콜입니다.<br>
연결 지향 프로토콜이란 클라이언트와 서버가 `연결된 상태`에서 데이터를 주고받는 프로토콜을 의미합니다.<br>
클라이언트가 연결 요청(SYN 데이터 전송)을 하고, 서버가 연결을 수락하면 통신 선로가 고정되고,<br>
모든 데이터는 고정된 통신 선로를 통해서 순차적으로 전달됩니다.<br>
그렇기 때문에 TCP는 데이터를 `정확`하고 `안정`적으로 전달할 수 있습니다.

## UDP
UDP(User Datagram Protocol)는 전송계층의 `비연결 지향적` 프로토콜입니다.<br>
비연결 지향적이란 데이터를 주고받을 때 `연결 절차를 거치지 않고` 발신자가 일방적으로 데이터를 발신하는 방식을 의미합니다.<br>
연결 과정이 없기 때문에 TCP보다는 `빠른 전송`을 할 수 있지만 데이터 전달의 `신뢰성은 떨어집니다.`<br>
UDP는 발신자가 데이터 패킷을 순차적으로 보내더라도 이 패킷들은 서로 다른 통신 선로를 통해 전달 될 수 있습니다.<br>
먼저 보낸 패킷이 느린 선로를 통해 전송될 경우 나중에 보낸 패킷보다 늦게 도착할 수 있으며<br>
최악의 경우 잘못된 선로로 전송되어 `유실`될 수도 있습니다.<br>
이럴 경우 TCP와는 다르게 UDP는 중간에 패킷이 유실이나 변조가 되어도 `재전송을 하지 않습니다.` 