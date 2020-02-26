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

