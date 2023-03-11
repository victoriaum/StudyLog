# 리눅스 활용
<hr>

## Chapter 01. X 윈도
+ 리눅스 환경의 애플리케이션과 유틸리티에 대해 그래픽 사용자 인터페이스를 제공
+ 구성요소: Server/Client, X protocol, Xlib, Xtoolkit
### GNOME vs. KDE
+ GNOME
  + 그래픽 라이브러리로 GTK+를 사용하고, 기본 편집기는 gedit이다.
  + 기본 브라우저는 Web이고, 파일 탐색기로는 Nautilus를 사용한다.
  + 윈도 매니저는 Mutter 또는 Metacity를 사용한다.
+ KDE
  + 그래픽 라이브러리로 Qt를 사용하고, 기본 편집기는 kate이다.
  + 기본 브라우저는 konquerer이고, 파일 탐색기로는 Konquerer를 사용한다.
  + 윈도 매니저는 KWin를 사용한다.
### X 클라이언트 이용
+ xhost
  + X 서버에 접속할 수 있는 클라이언트를 지정하거나 해제하려는 명령어
+ xauth
  + '.Xauthority' 파일의 쿠키 내용을 추가, 삭제, 목록을 출력하는 명령어
  + MMC 기반 인증 방식

<br><br>
## Chapter 02. 인터넷 활용
### 네트워크 통신망의 종류
> LAN, MAN, WAN, SAN
+ LAN의 종류: Ethernet, Token Ring, FDD
+ SAN: 저장장치를 위해 설계된 고속 네트워크
+ LAN 토플로지
  + 스타형, 버스형, 링형, 트리형, 망형
+ 매체 접근 방식
  + CSMA/CD, Token Passing
### 네트워크 장비
> 케이블, UTP 케이블, LAN 카드, 리피터, 허브, 브리지, 스위치, 라우터, 게이트웨이
+ 케이블  
  + UTP vs. STP
    + UTP: 꼬임선들이 절연체로 차폐되어 있지 않음
    + STP: 차폐되어 있음
  + 

<br><br>
## Chapter 03. 
### 
+ 프로토콜
  + 구문, 의미, 타이밍
  + OSI 7계층
    + 응용: FTP, SSH, Telnet, SMTP, DHCP, TFTP, HTTP, POP3, IMAP, SNMP 
    + 표현 
    + 세션 
    + 전송: TCP 3-Way Handshake, TCP, UCP
    + 네트워크: IP, ICMP, IGMP, ARP, RARP
    + 데이터링크
    + 물리
+ IP 주소와 도메인
  + IPv4
    + 32비트, 약 43억개의 주소, IPSec 프로토콜 설치, 모바일 곤란, 웹 캐스팅 곤란, 비순차적 할당
    + 8비트 단위 4부분 10진수 표기
  + IPv6
    + 128비트, 거의 무한대 주소, 확장기능에서 기본적으로 보안기능 제공, 모바일, 웹 캐스팅 용이
    + 16비트 단위 8부분 16진수 표기
#### UTP vs. STP
+ UTP: 꼬임선들이 절연체로 차폐되어 있지 않음
+ STP: 차폐되어 있음
#### 프로토콜
+ 구문, 의미, 타이밍
+ OSI 7계층
  + 응용: FTP, SSH, Telnet, SMTP, DHCP, TFTP, HTTP, POP3, IMAP, SNMP 
  + 표현 
  + 세션 
  + 전송: TCP 3-Way Handshake, TCP, UCP
  + 네트워크: IP, ICMP, IGMP, ARP, RARP
  + 데이터링크
  + 물리
+ 📌 IPP
  + 인터넷상에서 원격으로 인쇄하기 위해 사용되는 프로토콜
#### IP 주소와 도메인
+ IPv4
  + 32비트, 약 43억개의 주소, IPSec 프로토콜 설치, 모바일 곤란, 웹 캐스팅 곤란, 비순차적 할당
  + 8비트 단위 4부분 10진수 표기
+ IPv6
  + 128비트, 거의 무한대 주소, 확장기능에서 기본적으로 보안기능 제공, 모바일, 웹 캐스팅 용이
  + 16비트 단위 8부분 16진수 표기
### 인터넷 서비스 종류 및 특징
+ 웹 서비스
+ 메일 서비스
+ FTP 서비스: 네트워크에서 컴퓨터 사이의 파일 송수신을 위한 프로토콜
+ DNS 서비스: 호스트의 도메인 이름을 IP주소로 변환하거나 변환을 수행할 수 있도록 개발
+ Telnet 서비스: TCP/IP 기반의 프로토콜로 원격지 시스템을 자신의 시스템처럼 사용할 수 있게 하는 원격 터미널 접속 서비스
+ SSH 서비스: 원격 호스트에 로그인하거나 원격 호스트에서 명령을 실행하고 다른 호스트로 파일을 복사할 수 있게 해주는 응용 프로그램 또는 프로토콜
+ SAMBA, NFS, RPC 서비스



  

