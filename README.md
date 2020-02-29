# Learning-TCP-IP
TCP/IP 에 관하여 


# TCP/IP 란

연결지향이며, 자체적으로 오류를 처리하며, 네트워크 전송 중 순서가 뒤바뀐 메시지를 교정시켜주는 기능을 가지고 있다. 연결 지향적이란 말은 데이터를 전송하는 측과 데이터를 전송받는 측에서 전용의 데이터 전송 선로를 만든다는 의미이다. ( session, socket 같은). 데이터의 신회도가 중요하다고 판단 될때 주로 사용된

TCP/IP 가 나타난 이유 → 컴퓨터간 통신을 위해서. 

컴퓨터와 컴퓨터간의 지역네트워크 (LAN) 혹은 광역네트워크 (WAN)에서 원할한 통신을 가능하도록 하기위한 통신규약(Protocol) 으로 정의 할 수 있다. ( 최초 미국방성에서 구축한 ARPANET 에서 시작됨 ) 

TCP/IP 는 www, email, telnet, FTP 등 대부분이 TCP/IP 기반에서 만들어져있다. 

인터넷으로 연결된 수많은 컴퓨터와 통신을 위해서  TCP/IP를 선택한 이유는 그 개방성에 있다. 

→ 하드웨어, 운영체제, 접속매체에 관계없이 동작할 수 있다는 장점이 있다. 이것이 TCP/IP 가 인터넷 통신을 위한 핵심으로 선택된 큰 요인이였다. 

TCP/IP는 TCP와 IP의 2개의 프로토콜로 이루어져 있는데, 통상 IP 프로토콜 위에 TCP 프로토콜이 놓이게 되이므로 TCP/IP 라고 부르게 되었다. 

### IP 란

node(단말기)와 node - 이해하기 쉽게 컴퓨터와 컴퓨터 - 간의 데이터 패킷을 전송하기 위해서는 각 node 에 주소를 필요로 함. 4바이트로 이루어진 주소 번호를 사용하여 각각의 node를 구분하고 목적지를 찾아가게 된다. 우리는 이를 IP Address 하고 한다. 예: 192.168.100.100. 

IP는 Internet Protocol 의 줄임말이다. 숫자로  식별하기 까다롭기 때무넹 Domain 네임으로 변환 시켜주는 Domain Name 서비스를 이용한다. 

### TCP 란

서버와 클라이언트간에 데이터를 신회성있게 전달하기 위해 만들어진 프로토콜이다. 데이터는 네티워크 선로를 통해 전달되는 과정에서 손실되거나 순서가 뒤바뀌어서 전달 될 수있는데, TCP는 손실을 검색해내서, 이를 교정하고 재조합 할 수 있도록 해준다. 

TCP 는 Transmission Control Protocol 의 줄임말이다. 

데이터를 전송하기 전에 데이터 전송을 위한 연결을 만드는 연결지향 프로토콜이다. 

### TCP 의 핵심 기능

1. 패킷이 빠졌을 경우, 재전송을 요청하는 기능 
2. 패킷에 일련번호를 줌으로써 , 서로 다르게 도착될지도 모르는 패킷의 순서를 재조합하는 기능

# UDP 와 TCP

TCP 외에 UDP 라는 프로토콜도 존재란다. 

UDP는 User Datagram Protocol의 줄임말이다.

UDP는 비연결지향이며, 오류를 처리하거나 순서를 재좁하시켜주는 기능을 가지고 있지 않다. 단순히 데이터를 받거나, 전져주기만 하는 프로토콜이다. UDP는 특히 실시간 멀티미디어 정보를 처리하기 위해서 주로 사용한다. 

TCP를 실시간 멀티미디어 정보를 처리하는데 사용할 경우 TCP의 오류정정 특성상 메시지가 도착하지 않거나 할 경우 다음 메시지를 받지 않고, 메시지 재전송을 요구하므로, 실시간으로 전송하기에는 적당하지 않다. 반면 UDP를 사용하면 중간에 패킷이 소실되더라도 개의치 않고 다음 패킷을 받아들이므로 실시간 메시지 처리가 가능하다. 

물론 데이터 손실로 인해서 멀티미디어 데이터의 질이 떨어질 수 도 있으나, 화질이나 음질에 약간 손상이 있더라도 계속적으로 서비스가 되는게 훨씬 더 유리할 것이다. 전화를 하는데, 약간의 잡음이 섞인다고 해서, 잡음을 정정하기 위해서 서로 통화를 못하는 사태가 발생하는 안되는것과 같은 이치이다. 

# TCP/IP 를 이용한 컴퓨터간 데이터 통신

그렇다면, 각 컴퓨터간을 연결해주는 이더넷 카드를 통해서 어떻게 TCP/IP 메시지가 전달되는 것일까? 

이것을 이해하기 위해서는 OSI7에 대한 이해가 필요하다. OSI는 각종 시스템간의 연결을 위해서 ISO 에서 제안한 모델로써, 시스템에 상관없이 서로의 시스템이 연결될 수 있도록 만들어주는 모델이다. 

### OSI 7 계층

OSI는 Open System Interconnection Reference Model 의 줄임말이다.

OSI는 아래와 같이 7개의 계층으로 되어 있다.

 7. Application Layer

 6. Presentation Layer

 5. Session Layer

 4. Transport Layer

 3. Network Layer

 2. Data Link Layer

1. Physical Layer

컴퓨터와 컴퓨터사이의 데이터 전송을 위해서는 위의 7개의 계층을 직-간접적으로 거쳐서 전송이 되게 된다. 

7개의 계층으로 나눈 이유 → 각 계층에 대한 캡슐화와 은닉이 가능하기 때문 

서비스 개발자는 Application Layer 와 Presentation Layer 만 신경 쓰면 된다. 실제 어플리케이션 개발자는 Session Layer 와 Transport Layer 정도만 신경쓰면 될것이다. NetworkLayer 계층 아래는 운영체지가 알아서 챙겨주므로 거의 신경쓸 필요가 없다. 마찬가지로 하드웨어를 만드는 사람은 physical Layer 만 신경쓰면 되며, 그 위의 계층에 대해서는 신경 쓸 필요가 없다. ( 다 신경 써야 하는 개발자도 물론 존재한다 ) 

OSI 를 이렇게 계층별로 나눔으로써, 각 계층에서 필요한 부분만을 개발자들이 신경쓰게 되고 통신 서비스 개발시간을 줄일 수 있도록 도와준다. 

### TCP/IP 4계층

 4. Application Layer 

 3. Transport Layer

 2. Internet Layer 

 1. Physical Layer

Application Layer  → 네트워크를 사용하는 응용프로그램 (FTP, Telnet, SMTP) 등으로 이루어지며, OSI 계층의 Application Layer 와 Presentation Layer를 모두 포함한다. 

Transport Layer → 도착을 원하는 시스템까지 데이터를 전송하기 위한 일을 하는 계층이다. OSI 모델의 Session Layer 과 Transport Layer  를 포함하고 있으며, 각각의 시스템을 연결하고, TCP 프로토콜을 이용하여 데이터를 전송한다. 

Internet Layer → 데이터를 정의하고 데이터의 경로를 배정하는 일 (라우터)를 담당한다. 데이터를 정확히 라우팅 하기 위해서 IP 프로토콜을 사용한다. OSI의 Network Layer 과 Data Link Layer 를 포함한다. 

Physical Layer → 물리적 게층 즉 이더넷 카드와 같은 하드웨어를 말한다. 

### TCP/IP 4계층에 의한 데이터 전송

현재 가장 많 사용하는 인터넷 서비스중 하나인 www를 예를 들어 그림을 그려 보았다. 

www는 HTTP ( HyperText Transport Protocol ) 이라는 프로토콜을 이용한다. 

1. 사용자는 IE 나 Chrome 같은 브라우저를 사용하여 [www.naver.com](http://www.naver.com) 같은 URL 입력을 통해서 웹 페이지를 요청한다. 
2. 사용자의 요청 ( 문자 메시지가 될것이다 )은 인터넷상에서 전달되기 용이한 패킷으로 만들기 위해서 TCP 패킷으로 만들어지게 된다.
3. 이것은 다시 인터넷 상에서 원하는 주소로 이동할 수 있도록하기 위해 IP 패킷으로 다시 만들어 지고 ( IP 패킷에는 자신의 주소와, 도착해야될 상대방의 주소정보가 들어있을것이다) 
4. 이더넷 카드로 보내어져서 Internet 으로 나가게 된다. 
5. Internet 상에는 원하는 주소로 TCP/IP 패킷을 보내기 위한 여러가지 장치들이 존재하는데 (라우터, 토큰링 같은), 이들 장치를 통해서 [www.naver.com](http://www.naver.com) 의 이더넷 카드로 TCP/IP 패킷이 전달되게 된다. 
6. 이더넷 카드는 TCP/IP 패킷을 바로 윗 계층인 Internet Layer 로 보내는데, 여기에서는 IP 패킷을 분석해서, 이 패킷이 어디서 왔으며, 그 도착지가 어디인지를 판단하게 된다. ( IP 주소 기반으로 판단한다. ) 
7. 목적지가 자신이라면 이것을 다시 Transport Layer 로 보내고, TCP 프로토콜을 사용하여, 누락된게 있으면 다시 요청하고 순서를 재조합하는 등 통신 메시지를 검사해서 이것을 다시 Appliication Layer 엣게 보낸다. 
8. Application Layer 에서는 웹서버 (IIS, Apache 같은) 통신 메시지를 HTTP 프로토콜에 준하여, 감사를 하여서 사용자가 요청한 웹페이지를 읽어 들여서 Transport 계층으로 보낸다. 
9. 웹 페이지를 브라우저 까지 전송하는 과정은 위의 정 반대의 과정을 순차적으로 거치게 된다. 
10. 최종적으로 웹브라우저는 웹페이지를 받아서 HTTP 프로토콜에 준하여, 렌더링 작업을 거친 후 화면에 뿌려준다. 

앞의 설명을 잘 읽어 보면 각각의 계층은 각각의 계층만을 상관하고 있음을 알 수 있다. 즉 Application Layer에 위치하는 브라우저와 webserver 는 HTTP 프로토콜에 의해서 자신의 계층끼리만 통신하고, Transport Layer 역시 TCP 프로토콜에 의해서 Transport Layer 끼리 통신을 함을 알 수 있다. 말 그대로 계층적 구조를 가지며, 각 계층은 대응되는 상대편의 계층에 대해서만 상관한다. 

# TCP/IP 통신의 흐름

TCP/IP로 통신을 할 때 계층 순서를 거쳐 상대와 통신을 한다. 송신하는 측은 애플리케이션 계층에서 부터 내려가고, 수신하는 측은 애플리케이션 계층으로 올라간다. 

HTTP를 예로 들면 먼저 송신측 클라이언트의 애플리케이션 계층(HTTP)에서 어느 웹 페이지를 보고 싶다는 HTTP 리퀘스트를 지시한다. 그 다음에 있는 트랜스포트 계층(TCP)에서는 애플리케이션 계층에서 받은 데이터(HTTP 메시지)를 통신하기 쉽게 조각내어 안내 번호와 포트 번호를 붙여 네트워크 계층에 전달 한다.

네트워크 계층(IP)에서는 수신지 MAC 주소를 추가해서 링크 계층에 전달한다. 이로써 네트워크를 통해 송신할 준비가 된것이다.

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9f37cf3a-9e6f-4749-8a94-2a8798ab7d91/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9f37cf3a-9e6f-4749-8a94-2a8798ab7d91/Untitled.png)

각 계층을 거칠 때는 반드시 헤더로 불려지는 해당 계층마다 해당 계층에 필요한 정보를 추가한다. 반대로 수신측에서는 각 계층을 거칠 때마다 반드시 해당 계층마다 사용한 헤더를 삭제한다. 이렇게 정보를 감싸는것을 캡슐화라고 부른다.

# 연결지향이란?

TCP는 UDP와 달리 연결지향이라고 배웠다. 위의 과정에서 TCP/IP 에 의해서 데이터가 어떻게 전송되어 지는지를 알아봤는데, 데이터가 전송되지 전에, browser 과 server 간의 연결을 성립하는 과정이 데이터를 전송하는 과정 전에 이루어 지게 된다.  ( 데이터를 보내기전 서로가 연결되고 서로를 확인하는 작업 )

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/940aa145-536d-475e-a6bc-f9e8c56a6edd/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/940aa145-536d-475e-a6bc-f9e8c56a6edd/Untitled.png)

즉 데이터가 전송 되기 전에, browser 는 server 에게 SYN seq=x (서버 잘 있습니까?) 이라는 메시지를 보내고 server 는 다시 browser 에게 SYN seq=y, ACK x+1 ( 저는 준비 되어있으니, 데이터를 보내세요) 라는 메시지를 보내고 browser 는 다시 서버에게 ACK y+1 (네, 그럼 지금부터 데이터를 보내겠습니다) 라고 메시지를 보낸다. 그렇게 서로의 존재를 확인하는 절차를 수행한 후 정식 데이터를 교환하기 위한 통신 선로를 개설하게 된다. 통신선로를 하나 만들기 위해서는 3번의 데이터 전송이 일어나게 되므로, 이것을 three way handshake 라고 한다. 

이렇게 연결이 이루어지면 모든 정식 데이터는 연결된 통신 선로를 통해서 교환하게 되며, 이러한 이유로 TCP를 "연결 지향" 프로토콜이라고 부르는 것이다. UDP는 이러한 과정없이 단순히 데이터만을 전송함으로 "데이터그램" 프로토콜이라고 부른다.

왜 연결지향을 선택했나? → 연속적인 데이터 전송의 신회성을 위해서

# 데이터 단위

## 1. 비트 (bit)

컴퓨터는 단순히 데이터를 저장할 때 메모리와 이를 처리하는 연산장치 그리고 입출력 장치로 구성되어 있다.

2진수 한자리는 두가지 상태의 정보를 표현 가능하다. ( 1 과 0 ) 

### 8비트

1개의 비트는 단순히 2가지 상태만을 저장할 수 있기에 정보 저장에 있어서 매우 단편적이다. 

하지만 두자리 비트를 쓰면 4가지의 정보를 표현 할 수 있다. 그리고 컴퓨터는 보통 8개의 비트를 모아서 8비트를 자주 사용한다. 8비트는 0 에서 255개의 상태를 표현 할 수 있다. 

1바이트는 한개의 문자를 표현 할 수 있다. ( *영어권만, 정확히 말하면 7 비트만으로 표현이 가능하다. 0 ~ 127 개의 정보 표현으로 특수 문자 및 알파벳을 표현하고도 남는다 )

동양권의 문자를 표현 하기 위해서는 한 문자당 2바이트가 사용된다. 

## 2. 바이트 (byte)

8 비트를 1바이트라고 한다. 또 한 1 캐릭터 ( charactor ) 라고도 한다.





# TCP가 연결을 생성하고 종료하는 방법, 핸드쉐이크

 # 3 Way Handshake

연결을 생성할 때 거치는 핸드쉐이크 과정을 3 Way Handshake 라고 한다. 

이 과정을 거치면서 통신을 하는 양 종단은 내가 누구랑 통신하고 있는지, 내가 받아야할 데이터의 시퀀스 번호가 몇 번인지와 같은 정보를 주고 받으면서 연결 상태를 생성하게 된다. 

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/49de69eb-d784-43f4-8211-8296d83290be/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/49de69eb-d784-43f4-8211-8296d83290be/Untitled.png)

요청자는 연결 생성 요청을 먼저 보낸 쪽, 수신자는 연결 생성 요청을 받은 쪽을 의미한다. 클라이언트와 서버 둘 중 어느 쪽이든 자유롭게 먼저 연결 생성 요청을 보낼 수 있다. 

### CLOSED

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/72d6b8f5-1f3e-45c4-9581-91b71409a49e/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/72d6b8f5-1f3e-45c4-9581-91b71409a49e/Untitled.png)

아직 연결 요청을 시작하지 않았기 때문에 아무런 연결도 없는 상태이다. 

### LISTEN

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/cff8a1b5-7145-443a-a6a2-1279f7ec466d/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/cff8a1b5-7145-443a-a6a2-1279f7ec466d/Untitled.png)

수신자가 요청자의 연결 요청을 기다리고 있는 상태이다.  요청자의 연결 요청이 도착하기 전까지 이상태로 대기하게 된다. 즉, 적극적으로 상대방에게 대시하지 않는데 이 상태를 Passive Open ( 수동 개방 ) 이라 하고, 수신자를 Passive Opener 라고도 한다. 

** 소켓 프로그래밍을 할 때, 소켓 바인딩을 한 후 listen 함수를 호출하게 되면 수신자가 LISTEN 상태로 들어가게 된다.  이후 수신자는 요청자의 연결 요청이 확인되면 accept 함수를 호출하여 다음 단계로 넘어가게 된다. 

### SYN_SENT

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0afac9dc-c5e8-47ea-bbfe-a15229d99633/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0afac9dc-c5e8-47ea-bbfe-a15229d99633/Untitled.png)

요청자가 수신자에게 연결 요청을 하면서 랜덤한 숫자인 "시퀀스 번호" 를 생성해서 SYN 패킷에 담아 보낸다. 이제 요청자와 수신자는 이 시퀀스 번호를 사용하여 계속 새로운 값을 만들고 서로 확인하며 연결 상태와 패킷의 순서를 확인하게 된다. 

이 경우 요청자가 수신자에게 연결을 생성하자고 적극적으로 대시하는 상황이므로 이 상태를 능동 개방 ( Active Open ) 이라고 하고 요청자를 Active Opener 이라고도 한다. 

### SYN_RECV

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d07043ac-04e6-4fb8-ab6c-5903094a974c/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d07043ac-04e6-4fb8-ab6c-5903094a974c/Untitled.png)

SYN_RECV 는 요청자가 보낸 SYN 패킷을 수신자가 제대로 받은 상태를 의미한다. 

이후 수신자는 제대로 된 시퀀스 번호를 받았다는 확인의 의미인 승인 번호 ( Acknowledgement ) 값을 만들어서 다시 요청자에게 돌려줘야 한다. 이때 승인 번호는 처음 요청자가 보낸 "시퀀스 번호" + 1 이 된다. 

** 이 승인 번호 만드는 과정은 TCP를 사용하여 실제로 데이터를 주고 받을 때에는 상대방이 보낸 시퀀스 번호 + 상대 방이 보낸 데이터의 byte 를 합쳐서 승인 번호를 만들어 낸다. 즉 내가 여기까지 받았으니, 다음에는 여기부터 보내달라는 일종의 마킹인 것이다. 

그러나 이런 핸드쉐이크 과정에서는 아직 데이터를 주고 받지 않기 때문에 시퀀스 번호에 더할게 없다. 그렇다고 시퀀스 번호를 같은 번호로 주고 받자니 패킷의 순서를 구분할 수 없다. 그래서 + 1 을 하는 것이다. 

### ESTABISHED ( 요청자 )

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4b493839-eafb-427f-965e-17949e2c227d/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4b493839-eafb-427f-965e-17949e2c227d/Untitled.png)

요청자는 자신이 맨 처음에 보냈던 시퀀스 번호와 수신자가 응답으로 보내준 승인 번호, 즉 내 시퀀스 번호 + 1 을 사용하여 연결이 제대로 성립되었는지 확인할 수 있다. 

** 자신이 보냈던 시퀀스 번호와 이번에 받은 승인 번호의 차가 1이라면 제대로 연결이 되었다고 판단하는 것이다. 

이후 요청자를 연결이 성립되었다고 판단하고 ESTABLISHED 상태로 들어가면서, 이번에는 수신자가 새롭게 만들어서 보내줬던 시퀀스 번호에 1을 더한 값을 다시 승인 번호로 사용하여 다시 수신자에게 보내준다.

### ESTABLISHED ( 수신자 )

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5d65202d-8686-4895-967a-0e0e2acf5726/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5d65202d-8686-4895-967a-0e0e2acf5726/Untitled.png)

요청자와 마찬가지로 수신자 또한 자신이 보냈던 시퀀스 번호와 이번에 받은 승인 번호의 차가 1이라면 제대로 연결이 되었다고 판단하고 ESTABLISHED 상태로 들어가게 된다. 여기까지 오면 요청자는 수신자는 안전하고 신뢰성있는 연결이 생성되었다고 판단하고 본격적인 통신을 시작할 수 있다.

---

# 4 Way Handshake

연결을 종료할 때는 4 Way Handshake 과정을 거쳐서 연결을 종료한다. 

한쪽에서 일방적으로 연결을 끊어버린다면 다른 한쪽은 연결이 끊어졌는지 지속되고 있는지 알 방법이 없다. 또 한 연결을 종료 하기 전에 아직 다 처리 못한 데이터가 있을 수 도 있기 때문에 양쪽이 다 정상적으로 연결을 종료할 준비가 되어있는지를 확인하는 과정이 필요한 것이다.

이때 요청자와 수신자가 총 4번의 통신 과정을 거치기 때문에, 이 과정을 4 way Handshake라고 부른다. 

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/95265995-571d-4529-b355-61d1f4969df1/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/95265995-571d-4529-b355-61d1f4969df1/Untitled.png)

클라이언트와 서버 중 먼저 종료 요청을 시작하는 쪽이 initiator 이다. 

4 Way Handshake 는 3 Way Handshake 처럼 순차적으로 주고 받는 방식이 아니라 상대방이 응답을 줄 때까지 대기하는 과정이 포함되어 있기 때문에 중간에 뭐 하나 어긋나가면 서로 대기만 하고 있는 데드락 (deadlock) 상황이 발생할 수도 있다. 

조건에 따라 일정 시간이 지나면 타임아웃이 되며 연결을 강제로 종료하거나 다음 단계로 넘어가게 할 수 있지만 그 시간동안 프로세스가 메모리와 포트를 점유하고 있으므로 트래픽이 많은 서버라면 이로인해 병목(bottle neck) 현상이 발생할 가능성이 있다.

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/11436ba5-27bd-4665-aea2-731836a79274/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/11436ba5-27bd-4665-aea2-731836a79274/Untitled.png)

먼저 연결을 종료하고자 하는 요청자가 FIN 패킷을 상대방에게 보내면서 FIN_WAIT_1 상태로 들어서게 된다.  이때 FIN 패킷에도 시퀀스 번호가 포함되어 있고 3 Way Handshake 와는 다르게 랜덤한 값으로 초기화된 시퀀스 번호가 아니라 자신이 이번에 보내야 할 순서에 맞는 시퀀스 번호를 사용하면 된다. 

이때 요청자가 먼저 적극적으로 연결 종료 요청을 보내는 것이기 때문에 요청자를 Active Closer (능동 폐쇄) 라고 한다.

하지만 연결 종료 요청 패킷을 캡처해보면 F플래그가 아니라 FIN + ACK를 의미하는 F. 플래그가 설정되있음을 알 수 있다. 

이론적으로는 FIN 패킷을 보내야하는 왜 승인 번호를 함께 묶어서 FIN + ACK로 보내고 있는 것일까?

 

### Half-Close 기법

요청자가 FIN + ACK 패킷을 보내는 이유는 바로 Half-close하는 기법을 사용하고 있기 때문이다. 이 기법은 연결을 종료하려고 할 때 완전히 종료 하는것이 아니라 반만 종료하는 것이다. 

Half-Close를 사용하면 요청자가 처음 보내는 FIN 패킷에 승인 번호를 함께 담아서 보내게 되는데 이때 승인 번호의 의미는 "일단 연결은 종료 할건데 귀는 열어둔다. 이 승인 번호 까지 처리 했으니까 마저 보낼 거 있으면 보내" 라는 의미가 된다. 

즉 반만 닫겠다 → 연결을 종료할 때 전송 스트림과 수신 스트림중 하나만 우선 닫겠다는 것을 의미한다. 

이 후 수신자는 미처 못 보낸 데이터가 있다면 보낼 것이고, 이에 요청자는 아직 살아있는 수신 스트림을 사용하여 데이터를 처리 한 후 ACK 패킷을 응답으로 보낼 수 있다. 이 후 수신자가 모든 데이터를 처리하고 나면 다시 요청자에게 FIN 패킷을 보냄으로써 모든 데이터가 처리되었다는 신호를 보내준다. 

그럼 그때 요청자는 나머지 반을 닫으면서 조금 더 안전하게 연결을 종료할 수 있는 것이다. 

** 소켓 프로그래밍을 할 때 연결 종료 함수로 close() 와 shutdown() 을 사용 할 수 있는데, 이때 shutdown() 함수를 사용하면 Half-Close를 사용할 수 있다. 

    shutdown(sockfd, SHUT_WR);

만약 half-close 방식을 선택한다면 호출 즉시 OS에게 소켓의 리소스를 반환하며 모든 스트림이 바기 되므로 FIN 패킷을 받은 수신자가 미처 못 보낸 데이터를 뒤늦게 전송 하더라도 더 이상 처리할 수 없는 상황이 된다. 

### CLOSE_WAIT

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e28be7f6-2e29-4015-b988-63db368982ee/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e28be7f6-2e29-4015-b988-63db368982ee/Untitled.png)

 요청자로부터 FIN패킷을 받은 수신자는 요청자가 보낸 시퀀스 번호 + 1 로 승인 번호를 만들어서 다시 요청자에게 응답해주면서 CLOSE_WAIT 상태로 들어간다. 

아까 요청자가 FIN 패킷의 시퀀스 번호로 701384376을 보냈으니 이번에 수신자가 응답해줄 승인 번호는 701384377이 되는 것이다.

이 후 수신자는 자신이 전송할 데이터가 남아있다면 이어서 계속 전송한 후, 모든 전송이 끝났다면 명시적으로 close() 나 shutdown() 과 같은 함수를 호출하여 다음 단계로 넘어갈 것이다. 

즉 요청자는 언제 수신자의 데이터 처리가 끝날지 모르는 상태이기 때문에 수신자가 작업을 마치고 다시 연결 종료 승인을 의미하는 FIN 패킷을 보내줄 때까지 대기해야한다는 말이 된다. 

** 만약 이 단계에서 수신자의 데이터 처리가 끝나도 연결 종료 함수가 명시적으로 호출되지 않으면 다음 상태로 넘어갈 수 없기 때문에 데드락(deadlock) 이 발생할 가능성이 있다. 

이때 수신자는 상대방으로 부터 연결 종료 요청을 받은 후에야 수동적으로 연결을 종료할 준비를 하기 때문에 수신자를 Passive Closer, 이 상태를 수동폐쇄 라고 한다. 

### FIN_WAIT_2

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c5ba2aa9-3d5d-4669-b7d2-b4ded90f1fa6/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c5ba2aa9-3d5d-4669-b7d2-b4ded90f1fa6/Untitled.png)

요청자는 수신자로부터 승인 번호를 받고 자신이 보냈던 시퀀스 번호와 승인 번호의 차가 1이 맞는지 확인한다. 하지만 아직 수신자의 데이터 전소잉 전부 끝나지 않았을 수도 있기에 FIN_WAIT2 상태로 들어가서 수신자가 연결 종료를 허락하는 FIN 패킷을 보내줄 때까지 기다린다. 

** 여기서 부터 수신자가 다시 FIN패킷을 보내줄 때까지 요청자는 계속 대기하는 시간이다. 

하지만 CLOSE_WAIT와는 다르게 무한정 대기하는 것은 아니고 커널 파라미터로 타임아웃이 정해져 있는 경우, 일정 시간이 경과하면 자동으로 다음 단계로 넘어갈 수 있다. 

### LAST_ACK

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e0d90e5b-82d5-415f-8a5c-97d453a0e4ea/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e0d90e5b-82d5-415f-8a5c-97d453a0e4ea/Untitled.png)

수신자는 자신이 처리할 데이터가 더 이상 없다면 연결을 종료하는 함수를 명시적으로 호출하고, 아까 요청자가 보냈던 연결 종료 요청에 합의 한다는 의미로 요청자에게 다시 FIN 패킷을 보낸다. 

이때 수산자가 보내는 FIN 패킷에 담기는 시퀀스 넘버는 자신이 이번에 전송해야 하는 데이터의 시퀀스 번호를 그대로 사용하며, 승인 번호는 마지막으로 자신이 응답했던 승인 번호를 그대로 사용한다. 

이후 수신자는 LAST_ACK 상태로 들어가며 요청자가 다시 승인 번호를 보내줄때까지 대기한다. 

### TIME_WAIT

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5495f445-a376-43a7-9483-ff924247bdf0/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5495f445-a376-43a7-9483-ff924247bdf0/Untitled.png)

수신자가 보낸 FIN 패킷을 받은 요청자는 다시 수신자가 보낸 시퀀스 번호 + 1 로 승인 번호를 생성하여 수신자에게 ACK 패킷으로 응답한다. 이후 요청자는 TIME_WAIT 상태로 들어가고 실질적으로 연결 종료 과정에 들어가게 된다. 이떄 TIME_WAIT의 역할은 의도하지 않은 에러로 인해 연결이 데드락에 빠지는 것을 방지하는 것이다. 

TIME_WAIT에서 대기하는 시간은 2 MSL( Maximum Segement Lifetime) 으로 정의되어 있으며, 정확한 MSL의 시간 값은 커널 파라미터로 정의되어 있다. 

### CLOSED ( 수신자 )

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4c6853fc-123f-447b-a588-96298442bf64/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4c6853fc-123f-447b-a588-96298442bf64/Untitled.png)

요청자가 보낸 ACK 패킷을 받은 수신자는 CLOSED 상태로 들어가며 연결을 완전히 종료한다. 

### CLOSED ( 요청자 )

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c0d76561-4b8c-4d68-b949-26ccc2123766/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c0d76561-4b8c-4d68-b949-26ccc2123766/Untitled.png)

TIME_WAIT 상태에서 2MSL 만큼 시간이 지나면 요청자도 CLOSED 상태로 변경된다.


# TCP의 헤더에는 어떤 정보들이 담겨있는 걸까?

# TCP, Transmission Control Protocol

TCP (Transmission Control Protocol ) 은 OSI 7계층 중 전송( transport ) 계층에서 사용되고 있는 프로토콜로, 장비들 간의 통신 과정에서 정보를 안정적으로, 순서대로, 에러없이 교환 할 수 있도록 하는 것에 목적을 둔 프로토콜이다.

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0db28e26-2f18-480d-b19b-c41733c58fb5/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0db28e26-2f18-480d-b19b-c41733c58fb5/Untitled.png)

이때 우리에게 친숙한 HTTP, SMTP, FTP 와 같은 프로토콜들이 가장 높은 계층인 응용 ( aaplication ) 계층에 위치한다. 그에 비해 더 낮은 계층에 존재하는 TCP, UDP, IP 같은 프로토콜들은 상대적으로 접할 일이 많이 없다. 

이런 프로토콜들은 대부분 OS에서 알아서 처리해주기 때문에 상위 계층에서 프로그래밍을 하는 개발자가 굳이 여기서 일어나는 일까지 하나하나 신경 쓸 필요가 없기 때문이다. 

애초에 이게 레이어 모델이 존재하는 이유 중 하나이다. 네트워크라는 것이 수만흥ㄴ 기술의 집약체인 만큼 한명의 개발자가 모든것을 다 알긴느 힘들다. 그래서 각 계층 간 철저한 역할 분담을 통해 어떤 작업을 할 때 신경써야 하는 범위를 좁혀주는 것이다. 

덕분에 우리는 HTTP를 사용할 떄 DNS 는 어디를 사용할지, 패킷은 어떻게 처리할지 등 여러가지 작업을 한번에 신경쓸 필요가 없다. 

하지만 아무리 레이어가 나누어져 있다고 한들, 하위 레이어에서 일어나느 일을 전혀 모르고 있다면, 어플리케이션 레이어에서는 아무문제 없겠지만 하위 레이어에서 문제가 발생 했을 때 전혀 손도 못대는 케이스가 발생 할 수 있다. 

# TCP는 왜 만들어진걸까?

TCP 는 1970년 냉전 당시 미 국방성이 개발하던 알파넷 프로젝트의 일부로 개발되었는데, 그 당시 알파넷을 연구할 때 관심을 가진 주제 중 하나가 바로 '핵전쟁이 나도 살아남는 네트워크' 였다. 

왜냐하면 1970년대의 네트쿼는 회선 교환 방식을 사용하고 있었기 때문에 중계국이 폭격을 맞아서 박살나거나 중간에 연결된 선이 하나가 잘려나가면 그대로 통신이 끊어져 버렸기 떄문이다. 

그래서 나온 아이디어가 바로 패킷 교환 방식이다. 데이터를 하나의 회선을 사용하여 보내다가 해당 회선이나 중계국이 박살나면 전송되던 데이터와도 영원히 이별하게 되니, 데이터를 잘게 쪼갠 후 여러 개의 회선을 통해 보내자는 것이다. 

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fd8249cb-28db-4e5e-ba1f-4e50d8d84ee1/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fd8249cb-28db-4e5e-ba1f-4e50d8d84ee1/Untitled.png)

이렇게 되면 노드 하나가 박살나더라도 모든 데이터가 유실되진 않을 것이다. 

또한 하나의 회선을 잡아놓고 계속 통신하는 것이 아니라, 패킷에 목적지를 마킹 해놓고 그냥 보내기만 하면 되니, 회선의 사용 효율 또한 높아질 수 있다. 

이런 이유로 미 국방성은 이 아이디어를 채택하여 알파넷에 적용했고, 패킷 교환 방식의 실용성을 증명했다. 

이후 몇 개의 대학과 군에서만 사용되던 알파넷이 대중들에게 공개되고 전 세계적으로 연결되며 인터넷으로 발전하게 되었고, 덩달아 알파넷의 통신 프로토콜이었던 TCP도 함께 떡상 하게 된것이다. 

# 패킷 교환 방식의 문제점

하지만 패킷 교환 방식도 당연히 만능이 아니기에, 몇 가지 문제가 있다. TCP를 공부할 때 함께 따라오는 ARQ, SYN, ACK 등의 개념들이 바로 이런 문제들을 해결하기 위해 과거의 엔지니어들이 머리를 싸맨 결과이다. 

Q: 전송 중간에 패킷이 쥐도새도 모르게 사라지거나 훼손되면 어떡해요?A: **그럼 그 패킷만 다시 보내라고 해!(ARQ)**

Q: 송신 측이 패킷을 쪼갠 순서를 알아야 수신 측이 재조립할 수 있겠는데요?A: **그럼 순서번호를 패킷이랑 같이 보내!(시퀀스 번호)**

Q: 수신 측이 처리할 수 있는 속도보다 송신 측이 패킷을 빠르게 보내버리면 어떡하죠?A: **그럼 수신 측이 처리할 수 있는 양을 송신 측에 알려주고 그 만큼만 보내라고 해! (슬라이딩 윈도우)**

이런 기능들은 상대방이 보낸 세그먼트의 헤더에 들어있는 정보를 파악하여 작동하기 때문에, 이 기능들을 하나씩 알아보기 전에 TCP의 헤더에는 어떤 정보들이 들어있고, 이 정보들이 의미하는 것이 무엇인지 살펴보려고 한다. 

# TCP의 헤더

HTTP, TCP, IP 와 같은 프로토콜들은 각자 자신이 맡은 역할이 있고, 보내고자 하는 데이터에 자신의 헤더를 붙혀서 데이터의 정보를 표현한다. 

TCP는 전송의 신뢰송과 흐름 제어, 혼잡 제어 등의 역할을 맡고 있는 프로토콜이기 때문에, TCP 헤더에도 이러한 기능을 사용하기 위한 여러가지 값들이 담겨있다. 

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/3c0dfe8b-7554-4869-9be2-4e5f45665003/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/3c0dfe8b-7554-4869-9be2-4e5f45665003/Untitled.png)

TCP는 여러 개의 필드로 나누어진 20bytes, 즉 160bits의 헤더를 사용하며, 각 필드의 비트를 0 또는 1로 변경하여 전송하고자 하는 세그먼트의 정보를 나타낸다. 

하지만 20bytes는 아무런 옵션도 없는 기본적인 헤더 일 때의 용량이고 TCP의 여러가지 옵션들을 사용하면 헤더 맨 뒤에 옵션 필드들이 추가로 붙기 때문에 최대 40bytes가 더해진 60bytes까지도 사용 할 수 있다. 

### Source port, Destination port

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9995058d-6b05-4e19-b089-03e5defb7f4b/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9995058d-6b05-4e19-b089-03e5defb7f4b/Untitled.png)

이 필드들은 세그먼트의 출발지와 목적지를 나타내는 필드로, 각각 16bits 를 할당 받는다, 이때 출발지와 목적지의 주소를 판별하기 위해서는 IP 주소 와 포트번호가 필요하다. 

IP주소는 한 계층 밑인 네트워크 계층에 있는 IP의 헤더에 담기기 때문에, TCP 헤더에는 IP 주소를 나타내는 필드가 없고 포트를 나타내는 필드만 존재한다. 

### Sequence Number

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/376a8294-8d42-445e-a5c6-c42e109f1acd/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/376a8294-8d42-445e-a5c6-c42e109f1acd/Untitled.png)

시퀀스 번호는 전송하는 데이터의 순서를 의미하며, 32 bits 를 할당 받는다. 최대 4,294,967,296 까지의 수를 담을 수 있기 때문에 시퀀스 번호가 쉽게 중복되지 않는다. 

** 이 시퀀스 번호 덕분에, 수신자는 쪼개진 세그먼트의 순서를 파악하여 올바른 순서로 데이터를 재조립 할 수 있게 된다. 

송신자가 최초로 데이터를 전송할 때는 이 번호를 랜덤한 수로 초기화 하며, 이후 자신이 보낼 데이터의 1bytes 당 시퀀스 번호 1씩 증가 시키며 데이터의 순서를 표현하다 4,294,967,296을 넘어갈 경우 다시 0부터 시작한다. 

Acknowledgement Number

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e8eeff97-9280-47a3-a67f-0b603b800a82/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e8eeff97-9280-47a3-a67f-0b603b800a82/Untitled.png)

 승인 번호는 데이터를 받은 수신자가 예상하는 다음 시퀀스 번호를 의미하며, 32 bits 를 할당 받는다. 연결 설정과 연결을 해제 할 때 발생하는 핸드쉐이크 과정에서는 상대방이 보낸 시퀀스 번호 + 1 로 자신의 승인 번호를 만들어 내지만, 실제로 데이터를 주고 받을 때는 상대방이 보낸 시퀀스 번호 + 자신이 받은 데이터의 bytes로 승인 번호를 만들어 낸다. 

예를 들어 1MB 짜리 데이터를 전송한다고 생각하자면 이렇게 큰 데이터를 한번에 전송 할 수 는 없으므로, 송신자는 이 데이터를 여러개의 세그먼트로 쪼개서 조금씩 전송해야 한다. 이때 송신자가 한번에 전송 할수 있는 양은 네티워크나 수신자의 상태에 따라 가변적이지만 100bytes 라고 가정해보자. 

송신자는 첫 전송에 100bytes 만큼만 데이터를 전송하며 시퀀스 번호를 0으로 초기화 한다. 시퀀스 번호는 1bytes 당 1씩 증가 하기 때문에 첫번 째 바이트 뭉치는 0, 두번째 바이트 뭉치는 1, 세번째 바이트 뭉치는 2 와 같은 순서대로 매겨질 것이다. 

즉 이번 전송을 통해 수신자는 0~99 까지 총 100개의 바이트 뭉치를 받았고, 그 다음 전송 때 받아야 할 시퀀스 번호는 2가 아닌 100이 되는 것이다. 

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/362e3d55-1982-46bc-aa0e-915179d9f60c/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/362e3d55-1982-46bc-aa0e-915179d9f60c/Untitled.png)

즉 승인 번호는 다음에 보내줘야 하는 데이터의 시작점을 의미한다는 것을 알 수 있다. 

### Data Offset

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8d151d14-a47e-4190-866d-3c5336020332/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8d151d14-a47e-4190-866d-3c5336020332/Untitled.png)

데이터 오프셋 필드에는 전체  세그먼트 중에서 헤더가 아닌 데이터가 시작되는 위치가 어디서 부터인지를 표시한다. 

이 오프셋을 표기할 때는 32비트 워드 단위를 사용하여, 32비트 체계에서 1Word = 4 bytes를 의미한다. 즉 이 필드의 값에 4를 곱하면 세그먼트에서 헤더를 제외한 실제 데이터의 시작 위치를 알 수 있는 것이다. 

이 필드에 할당된 4bits 로 표현 할 수 있는 값의 범위는 0000~1111, 즉 0 ~ 15 Word 이므로 기본적으로 0 ~ 60 bytes 의 오프셋까지 표현 할 수 있다. 하지만 옵션 필드를 제외한 나머지 필드는 필수로 존재해야하기 때문에 최소  값은 20bytes, 즉 5 Word 로 고정되어 있다. 

이 필드가 필요한 이유는, 밑에서 설명할 옵션 (Option) 필드의 길이가 고정되어 있지 않기 때문이다.

### Reserved (3bits)

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/801c73b5-b35a-4605-a5e6-a713c9c64fb0/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/801c73b5-b35a-4605-a5e6-a713c9c64fb0/Untitled.png)

미래를 위해 예약된 필드로, 모두 0으로 채워져야 한다. 상단의 헤더 그림에도 그냥 0 0 0 으로찍혀 있는 것을 확인해 볼 수 있다.

### Flags (NS ~ FIN)

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/820480b6-6588-488e-902d-fe62bf2274e8/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/820480b6-6588-488e-902d-fe62bf2274e8/Untitled.png)

9개의 비트 플래그 이다. 이 플래그들은 현재 세그먼트의 속성을 나타낸다. 기존에는 6개의 플래그만을 사용했지만, 혼잡 제어 기능의 향상을 위해 Reserved 필드를 사용하여 NS, CWR, ECE 플래그가 추가 되었다. 

먼저 기존에 존재하던 플래그들의 의미는 다음과 같다.

[Untitled](https://www.notion.so/4f4a4821500f45598a700205c5c1fc18)

ECN을 사용하지 않던 기존의 네트워크 혼잡 상황 인지 방법은 타임아웃을 이용한 방법이었다. 그러나 처리 속도에 민감한 어플리케이션에서는 이런 대기 시간 조차 아깝기 때문에, 송신자와 수신자에게 네트워크의 혼잡 상황을 명시적으로 알리기 위한 특별한 매커니즘이 필요하게 되었는데, 이것이 바로 `ECN`이다.

이때 `CWR`, `ECE`, `ECT`, `CE` 플래그를 사용하여 상대방에게 혼잡 상태를 알려줄 수 있는데, 이 중 `CWR`, `ECE`는 TCP 헤더에 존재하고 `ECT`, `CE`는 IP 헤더에 존재한다.

[Untitled](https://www.notion.so/d94eec12c7704a8eb178542184f75318)

### Window Size

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c5aeac8c-a082-4ac4-96b8-ee15b05a07e0/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c5aeac8c-a082-4ac4-96b8-ee15b05a07e0/Untitled.png)

윈도우 사이즈 필드에는 한번에 전송할 수 있는 데이터의 양을 의미하는 값을 담는다. 216=65535216=65535 만큼의 값을 표현할 수 있고 단위는 바이트이므로, 윈도우의 최대 크기는 `64KB`라는 말이 된다.

하지만 이 최대 크기는 옛날 옛적에 생긴 기준이라 요즘같이 대용량 고속 통신 환경에는 맞지 않는 경우도 있다. 그래서 비트를 왼쪽으로 시프트하는 방식으로 윈도우 사이즈의 최대 크기를 키울 수 있는 방식도 사용하고 있으며, 몇 번 시프트할 지는 옵션 필드의 `WSCALE` 필드를 사용하여 표기한다.

### CheckSum

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/641f7511-f715-4caf-b585-873a721af48d/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/641f7511-f715-4caf-b585-873a721af48d/Untitled.png)

체크섬은 데이터를 송신하는 중에 발생할 수 있는 오류를 검출하기 위한 값이다. 

TCP의 체크섬은 전송할 데이터를 16Bits씩 나눠서 차례대로 더해가는 방법으로 생성한다. 방식은 단순하지만 16bits의 덧셈을 그대로 보자니 숫자가 너무 길어질 것이 뻔함으로 간단하게 반토막인 8bits 로 설명 해보겠다. 

    	11010101
    + 10110100
    -----------
     110001001

앗, 8 bits인 두 수를 더 했더니 자리 수가 하나 올라가서 9 bits가 되었다. 이렇게 자리 수가 넘쳐버리면 체크섬 필드에 담을 수 없다.

이렇게 두 개의 수를 더했을 때 자리 수가 하나 올라간 부분을 `캐리(Carry)`라고 하는데, 계산 결과에서 이 부분만 떼어내서 다시 계산 결과에 더해주면 된다.

    	 10001001
    +         1 ( 방금 위에서 넘친 부분 )
    ------------
       10001010

이런 방식을 Warp Around라고 한다. 이제 마지막 계산 결과에 1의 보수를 취해주면 체크섬이 된다. 1의 보수라고 하면 뭐지 싶겠지만 그냥 비트를 반전하면 된다.

    10001010
    01110101 ( 1의 보수를 취한 모습 )

이제 `01110101`이 이 데이터의 체크섬이 되는 것이다. 이 예제에서는 8 bits를 가지고 진행했기 때문에 8 bits짜리 체크섬이 나왔지만, 실제로는 16 bits 단위로 데이터를 잘라서 이 과정을 진행하기 때문에 16 bits인 체크섬 필드에 딱 들어맞는 이쁜 값이 나온다.

수신 측은 데이터를 받으면 위의 과정을 동일하게 거치되 1의 보수를 취하지 않은 값인 `10001010`까지만 만든 다음, 이 값과 송신 측이 보낸 체크섬을 더해서 모든 비트가 1이라면 이 데이터가 정상이라고 판단할 수 있다.

    	10001010
    + 01110101
    -----------
      11111111

만약 이 값에 0이 하나라도 있으면 송신 측이 보낸 데이터에 뭔가 변조가 있었음을 알 수 있다.

### **Urgent Pointer**

![https://evan-moon.github.io/2019/11/10/header-of-tcp/header-urgent.png](https://evan-moon.github.io/2019/11/10/header-of-tcp/header-urgent.png)

말 그대로 긴급 포인터이다. URG 플래그가 1이라면 수신 측은 이 포인터가 가르키고 있는 데이터를 우선 처리한다.

### Options

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5303b10d-d0ea-4fd0-987c-121a64ed71ea/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5303b10d-d0ea-4fd0-987c-121a64ed71ea/Untitled.png)

옵션 필드는 TCP의 기능을 확장할 때 사용하는 필드들이며, 이 필드는 크기가 고정된 것이 아니라 가변적이다. 그래서 수신 측이 어디까지가 헤더고 어디서부터 데이터인지 알기 위해 위에서 설명한 데이터 오프셋 필드를 사용하는 것이다.

데이터 오프셋 필드는 `20 ~ 60 bytes`의 값을 표현할 수 있다고 했는데, 아무런 옵션도 사용하지 않은 헤더의 길이, 즉 Source Port 필드부터 Urgent Pointer 필드까지의 길이가 `20 bytes`이고, 옵션을 모두 사용했을 때 옵션 필드의 최대 길이가 `40 bytes`이기 때문이다.

만약 데이터 오프셋 필드의 값이 5, 즉 20 bytes보다 크지만 TCP의 옵션을 하나도 사용하고 있지 않다면, 초과한 bytes 만큼 이 필드를 0으로 채워줘야 수신 측이 헤더의 크기를 올바르게 측정할 수 있다.

대표적인 옵션으로는 윈도우 사이즈의 최대 값 표현을 확장할 수 있는 `WSCALE`, Selective Repeat 방식을 사용하기 위한 `SACK` 등이 있으며, 이외에도 거의 30개 정도의 옵션을 사용할 수 있기 때문에 이 친구들을 하나하나 설명하는 것은 조금 힘들 것 같다.

# 소켓이란?

네트워크 프로그래밍에서의 소켓(Socket)은 프로그램이 네트워크에서 데이터를 송수신할 수 있도록, "네트워크 환경에 연결할 수 있게 만들어진 연결부"가 바로 "네트워크 소켓(Socket)"입니다.

하지만 엄밀히 따지자면, "네트워크 소켓"이라는 용어가 정확한 표현은 아닙니다. 전기 소켓이 전기를 공급받기 위해 정해진 규격(110V, 220V 등)에 맞게 만들어져야 하듯, 네트워크에 연결하기 위한 소켓 또한 정해진 규약, 즉, 통신을 위한 프로토콜(Protocol)에 맞게 만들어져야 합니다. 보통 OSI 7 Layer(Open System Interconnection 7 Layer)의 네 번째 계층인 TCP(Transport Control Protocol) 상에서 동작하는 소켓을 주로 사용하는데, 이를 "TCP 소켓" 또는 "TCP/IP 소켓"이라고 부릅니다. (UDP에서 동작하는 소켓은 "UDP 소켓"이라고 합니다.)

# TCP/IP 소켓프로그래밍

### 클라이언트 소켓(Client Socket)과 서버 소켓(Server Socket)

두 개의 시스템(또는 프로세스)이 소켓을 통해 네트워크 연결(Connection)을 만들기 위해서는, 최초 어느 한 곳에서 그 대상이 되는 곳으로 연결을 요청해야 합니다.

두 개의 시스템(또는 프로세스)이 소켓을 통해 데이터 통신을 위한 연결(Connection)을 만들기 위해서는, 연결 요청을 보내는지 또는 요청을 받아들이는지에 따라 소켓의 역할이 나뉘게 되는데, 전자에 사용되는 소켓을 클라이언트 소켓(Client Socket), 후자에 사용되는 소켓을 서버 소켓(Server Socket)이라고 합니다.

### 소켓 API(Socket API) 실행 흐름.

클라이언트 소켓(Client Socket)은 처음 소켓(Socket)을 [1]생성(create)한 다음, 서버 측에 [2]연결(connect)을 요청합니다. 그리고 서버 소켓에서 연결이 받아들여지면 데이터를 [3]송수신(send/recv)하고, 모든 처리가 완료되면 소켓(Socket)을 [4]닫습니다(close).

서버 소켓(Server Socket)은 처리 과정이 조금 복잡합니다. 일단 클라이언트와 마찬가지로, 첫 번째 단계는 소켓(Socket)을 [1]생성(create)하는 것입니다. 그리고 서버 소켓이 해야 할 두 번째 작업은, 서버가 사용할 IP 주소와 포트 번호를 생성한 소켓에 [2]결합(bind)시키는 것입니다. 그런 다음 클라이언트로부터 연결 요청이 수신되는지 [3]주시(listen)하고, 요청이 수신되면 요청을 [4]받아들여(accept) 데이터 통신을 위한 소켓을 생성합니다. 일단 새로운 소켓을 통해 연결이 수립(ESTABLISHED)되면, 클라이언트와 마찬가지로 데이터를 [5]송수신(send/recv)할 수 있습니다. 마지막으로 데이터 송수신이 완료되면, 소켓(Socket)을 [6]닫습니다(close).

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d86d29fe-27b4-4d8e-a40c-bbd2377edcfc/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d86d29fe-27b4-4d8e-a40c-bbd2377edcfc/Untitled.png)
