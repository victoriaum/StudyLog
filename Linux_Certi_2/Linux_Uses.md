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
### 네트워크의 개념
#### 통신망의 종류
+ LAN, MAN, WAN, SAN
  + LAN의 종류: Ethernet, Token Ring, FDD
  + SAN: 저장장치를 위해 설계된 고속 네트워크
#### 네트워크
+ LAN 토플로지
  + 스타형, 버스형, 링형, 트리형, 망형
+ 매체 접근 방식
  + CSMA/CD, Token Passing
#### 네트워크 장비
+ UTP vs. STP
  + UTP: 꼬임선들이 절연체로 차폐되어 있지 않음
  + STP: 차폐되어 있음
