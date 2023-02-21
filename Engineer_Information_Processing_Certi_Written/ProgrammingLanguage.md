# 프로그래밍 언어 활용

## C
### 변수선언
+ 변수명은 숫자로 시작하거나 숫자로만 구성할 수 없다. 공백불가. 예약어불가.
+ 📌 else는 예약어로 변수명으로 쓸 수 없다. True는 가능
### 문자열 처리함수
+ ```strcmp(s1, s2)```: 문자열을 비교하여 같다면 0을 반환하고, 다르면 음수를 반환하는 함수
+ ```strcat```: 두 문자열을 이어 붙여주는 기능을 한다.
### 연산문제
```
#include ＜stdio.h＞
    int main(int argc, char *argv[]) {
    int a=5, b=3, c=12;
    int t1, t2, t3;
    t1=a && b;
    t2=a || b;
    t3=!c;
    printf("%d", t1+t2+t3);
    return 0;
}
```
+ 📌 C언어에서 정수는 0이면 거짓이고 0이 아니면 참이다.
+ 따라서 a, b, c는 모두 참이다.
+ t1은 모두 참이므로 참인 1의 값을 갖는다.
+ t2는 모두 참이므로 하나라도 참이기 때문에 참인 1의 값을 갖는다.
+ t3는 참의 역인 거짓으로 0의 값을 갖는다.
<br>

```
#include ＜stdio.h＞
struct st{
    int a;
    int c[10];
};

int main (int argc, char *argv[]) {
    int i＝0;
    struct st ob1;
    struct st ob2;
    ob1.a＝0;
    ob2.a＝0;
    for(i＝0; i＜10; i++) {
        ob1.c[i]＝i;
        ob2.c[i]＝ob1.c[i]＋i;
    }
    for(i＝0; i＜10; i＝i＋2) {
        ob1.a＝ob1.a＋ob1.c[i];
        ob2.a＝ob2.a＋ob2.c[i];
    }
    printf("%d", ob1.a ob2.a);
    return 0;
}
```
+ 📌 두 번째 for문은 2씩 증가함에 유의하자
+ 첫 번째 for문에서 ob1.c는 0~9, ob2.c는 ob1.c보다 각각 2배의 값을 갖게 된다.
+ 두 번째 for문에서 ob1.a = 2+4+6+8 = 20, ob1.b = 4+8+12+16 = 40 이므로 전체 합은 60이 된다.
+ ❓ 마지막에 덧셈 표시가 별도로 없는데 더하는 것인가..?
<br>

```
#include＜stdio.h＞
#include＜stdlib.h＞
int main(int argc, char *argv[] ) {
  int arr[2][3]＝{1,2,3,4,5,6};
  int (*p)[3]＝NULL;
  p＝arr;
  printf("%d, ", *(p[0]+1)+*(p[1]+2));
  printf("%d", *(*(p+1)+0)+*(*(p+1)+1));
  return 0;
}
// 8,9
```
+ [해설](https://www.youtube.com/watch?v=AQFNQjfsLmc&ab_channel=Hikcoding)
+ 처음 선언된 arr에는 첫 배열에 1,2,3이 들어가고, 두 번째는 4,5,6을 갖는 이차배열이다.
+ 여기서 ```*p```는 임의의 int 배열(3칸)을 가리키는 포인터인데, arr과 매칭하므로써 arr의 첫 인덱스부터 순서대로 1,2,3을 가리키게 된다.
+ 그럼 ```*p[1]```의 표현은 3칸을 한 묶음으로 보기 때문에 4를 첫 인덱스로 가리키게 된다.
+ ```*p+1```의 경우는 포인터에서 내부 배열 중 첫 인덱스 다음 값을 말한다.
+ ```printf("%d, ", *(p[0]+1)+*(p[1]+2));```
  + 여기서 ```*(p[0]+1)```부분은 포인터 위치 변경은 없고 내부 이동이므로 2의 주소를 참조한다.
  + 여기서 ```*(p[1]+2)```부분은 포인터 위치 변경으로 한 단계 내려간 4을 가리키는데 내부 2칸 이동으로 6의 주소를 참조한다.
  + 즉, 더해서 8이 된다.
+ ```printf("%d", *(*(p+1)+0)+*(*(p+1)+1))```
  + 위와 동일하게 ```*(*(p+1)+0)``` 부분은 포인터 1단계 이동 후 내부 이동은 없으므로 4의 주소를 참조한다.
  + ```*(*(p+1)+1))``` 부분은 포인터 1단계 이동 후 내부 이동 1칸이므로 5의 주소를 참조한다.
  + 즉, 더해서 9가 된다.
<br>

```
#include ＜stdio.h＞
#include ＜stdlib.h＞
int main(int argc, char *argv[] ) {
  char str1[20]="KOREA";
  char str2[20]="LOVE";
  char* p1=NULL;
  char* p2=NULL;
  p1=str1;
  p2=str2;
  str1[1]=p2[2];
  str2[3]=p1[4];
  strcat(str1, str2);
  printf("%c", *(p1＋2));
  return 0;
}
```
+ ```strcat```은 두 문자열을 이어 붙여주는 기능을 한다. 문제에서는 별 의미가 없지만..
+ 여기서 *p1, *p2의 위치는 새로 변경된게 없음에 유의하자.
+ ```p1=str1```를 하면, p1가 'K'의 값을 가리키고, ```p2=str2```를 하면, p2가 'L'을 가리킨다.
+ ```str1[1]=p2[2]```를 하면, p2에서 두 칸 이동한 'V'로 str1[1]인 "O"의 값을 대체한다.
+ ```str2[3]=p1[4]```를 하면, p1에서 네 칸 이동한 'A'로 str2[3]인 "E"의 값을 대체한다.
+ 결과적으로 ```printf("%c", *(p1＋2))```는 p2에서 두 칸 이동한 값인 'R'을 출력한다.
<br>

```
// C언어에서 정수 변수 a, b에 각각 1, 2가 저장되어 있을 때 다음 식의 연산 결과로 옳은 것?
a<b+2 && a<<1<=b
```
+ ```a<b+2```의 값은 대입하면, true 이다.
+ ```a<<1<=b```의 값은 대입하면, true 이다.
+ 결과적으로 양쪽 다 참이므로 1의 값을 갖는다.
<br>
  
```
#include <stdio.h>
#include <string.h>
int main(void) {
    char str[50]="nation";
    char *p2="alter";
    strcat(str, p2);
    printf("%s", str);
  return 0;
}
// nationalter
```  
+ ```strcat(str, p2);``` 두 개를 합친 문자열로 출력한다.
<br>

<br><br>
## Python
+ 귀도 반 로섬(Guido van Rossum)이 발표한 언어로 인터프리터 방식이자 객체지향적이며, 배우기 쉽고 이식성이 좋은 것이 특징인 스크립트 언어
### 데이터 타입
> 자료형, 문자열과 리스트, 튜플, 딕셔너리, 세트
+ [튜플](https://wikidocs.net/71)
  + 시퀀스(Sequence) 데이터 타입에 해당하며 다양한 데이터 타입들을 주어진 순서에 따라 저장할 수 있으나 저장된 내용을 변경할 수 없는 것
  + 내용을 변경하려고 하는 경우 리스트처럼 해당 부분의 내용을 바꿀 수 없어 나누어 변경, 저장해야 한다.
### 연산문제
+ if, elif, else
```
a＝["대", "한", "민 ", "국"]
for i in a：
print(i)
```
+ 📌 파이썬에서 ```print()```는 마지막에 줄바꿈이 있는 결과가 출력된다.
<br>
  
```
def cs(n);
  s＝0
  for num in range(n＋1);
    s＋＝num
  return s
print(cs(11)) // 66
```
+ 11까지가 아니라 12까지임에 유의하자
+ 0~12까지의 합

<br><br>
## JAVA
### 예외(Exception)
+ 오동작이나 결과에 악영향을 미칠 수 있는 실행 시간 동안에 발생한 오류
+ 배열의 인덱스가 그 범위를 넘어서는 경우 발생하는 오류
+ 존재하지 않는 파일을 읽으려고 하는 경우에 발생하는 오류
+ 📌 프로그래밍 언어의 문법적 오류는 '에러'에 해당한다.
### 연산자
+ 📌 우선순위가 가장 낮은 연산자는 대입연산자(=)이다.
### 연산문제
```java

```
+ 

<br><br>
## 모듈화
+ 소프트웨어의 모듈은 프로그래밍 언어에서 Subroutine, Function 등으로 표현될 수 있다.
+ 모듈의 수가 증가하면 상대적으로 각 모듈의 크기가 감소하고, 모듈 사이의 상호교류가 증가하여 과부하(Overload)현상이 나타난다.
+ 📌 모듈화는 시스템을 지능적으로 관리할 수 있도록 해주며, 복잡도 문제를 해결하는 데 도움을 준다. 
+ 모듈화는 시스템의 유지보수와 수정을 용이하게 한다

<br><br>
## 빌드툴
+ Ant, Maven, Gradle
+ 📌 Kerberos: "티켓"을 기반으로 동작하는 컴퓨터 네트워크 인증 암호화 프로토콜

<br><br>
## OSI 7계층
> 응용 > 표현 > 세션 > 전송 > 네트워크 > 데이터링크 > 물리
### 데이터링크 계층
+ 프로토콜: 📌 HDLC, PPP, LLC
### 응용 계층
+ 프로토콜: HTTP

<br><br>
## 네트워크 계층 프로토콜
### IP 프로토콜
+ 📌 Header Length는 IP 프로토콜의 헤더 길이를 32비트 워드 단위로 표시한다. 
+ 📌 Packet Length는 IP 헤더를 포함한 패킷 전체의 길이를 나타내며 최대 크기는 232－1비트이다. 
+ Time To Live는 송신 호스트가 패킷을 전송하기 전 네트워크에서 생존할 수 있는 시간을 지정한 것이다.
+ Version Number는 IP 프로토콜의 버전번호를 나타낸다.
+ 📌 주로 주소를 지정하고, 경로를 설정하는 기능을 한다.
+ 📌 체크섬(Checksum) 기능 제공
  + 체크섬 필드를 '0'으로 하여 계산한다.
  + IP, UDP, TCP의 헤더 포맷을 보면 checksum을 위한 공간이 존재한다. 
  + 이 부분은 패킷의 헤더가 전송되는 도중 데이터가 변조되거나 깨지는 경우를 확인하기 위해 사용된다.
  + 체크섬: 중복 검사의 형태로 송신된 자료의 무결성을 보호하는 방법
+ 📌 패킷을 분할, 병합하는 기능을 수행하기도 한다. 
+ 📌 비연결형 서비스를 제공한다. 
+ 📌 Best Effort 원칙에 따른 전송 기능을 제공한다.
#### [IP 주소체계](https://xn--3e0bx5euxnjje69i70af08bea817g.xn--3e0b707e/jsp/resources/ipv6Info.jsp)
+ IPv4
  + 표시방법: 8비트씩 4부분 10진수
  + IPv4는 호스트 주소를 자동으로 설정하며 유니캐스트(Unicast)를 지원한다.
  + IPv4는 클래스별로 네트워크와 호스트 주소의 길이가 다르다.
+ IPv6
  + 표시방법: 16비트씩 8부분 16진수
  + IPv4와 달리 IPv6의 패킷 헤더는 임의 길이일 수 있다.(확장헤더)
  + IPv6는 주소 자동 설정(Auto Configuration) 기능을 통해 손쉽게 이용자의 단말을 네트워크에 접속시킬 수 있다. 
  + 2<sup>128</sup>개의 주소를 표현할 수 있다. 
  + 등급별, 서비스별로 패킷을 구분할 수 있어 품질보장이 용이하다. 
  + 확장기능을 통해 보안기능을 제공한다.
+ IP 주소의 클래스
  + A 클래스
    + IP 범위는 0.0.0.0 ~ 127.255.255.255
    + 하나의 네트워크가 가질 수 있는 호스트 수가 제일 많은 클래스 
    + 맨 앞이 0이고 나머지는 0 또는 1로 구성
  + B 클래스
    + IP 범위는 128.0.0.0 ~ 191.255.255.255, 10으로 시작하는 네트워크
  + C 클래스
    + 📌 IP 범위는 192.0.0.0 ~ 223.255.255.255
    + 110으로 시작하는 네트워크 범위
    + 📌 계산문제
      ``` 
      192.168.1.0/24 네트워크를 FLSM 방식을 이용하여 4개의 Subnet으로 나누고 IP Subnet-zero를 적용했다. 이때
      Subnetting된 네트워크 중 4번째 네트워크의 4번째 사용가능한 IP는?
      // 192.168.1.196
      ```
      + 0/24 이 부분이 8자리가 가능하고 4개 subnet이므로 2<sup>2</sup>이므로 2개를 네트워크 아이디로 사용한다.
      + 따라서, 4번째 사용가능한 아이디는 11000000 ~ 11111111 이므로 192~255의 값을 갖고
      + 여기서 4번째 사용가능한 IP이므로 192(빼고), 193, 194, 195, 196이 된다. 
      + 브로드캐스트 IP일 경우 255
#### ICMP(Internet Control Message Protocol)
+ TCP/IP 계층 구조에서 IP의 동작 과정에서의 전송 오류가 발생하는 경우에 대비해 오류 정보를 전송하는 목적으로 사용하는 프로토콜
### TCP 프로토콜
#### TCP 헤더
+ 순서번호(Sequence Number): 전달하는 바이트마다 번호가 부여된다. 
+ 수신번호확인(Acknowledgement Number): 상대편 호스트에서 받으려는 바이트의 번호를 정의한다. 
+ 체크섬(Checksum): 데이터를 포함한 세그먼트의 오류를 검사한다.
+ 📌 윈도우 크기는 송수신 측의 버퍼 크기로 최대크기는 65,535 bytes 이다.

<br><br>
## 전송 계층 프로토콜
### TCP 프로토콜, 연결지향
+ 흐름제어(Flow Control), 오류제어(Error Control), 혼잡제어(Congestion Control)
+ 양방향 연결 서비스 제공
+ 가상 회선 연결(Virtual Circuit Connection)형태의 서비스를 제공한다
### UDP 프로토콜, 비연결지향
+ 단순한 헤더 구조로 오버헤드가 적다. 전송속도가 빠르다.
+ 📌 데이터의 순차적 전송을 보장하지 않는다.
+ 신뢰성 있는 TCP와는 달리 흐름제어(Flow Control), 오류제어(Error Control), 혼잡제어(Congestion Control) 등을 수행하지 않는다.
+ 한 번의 패킷 송수신으로 완료되는 서비스에 많이 사용된다.

<br><br>
## 라우팅 프로토콜
### RIP 라우팅 프로토콜
+ 라우팅 정보 관리를 위해 경유하는 라우터의 대수(Hop Count)에 따라 최단 경로를 동적으로 결정하는 거리 벡터 알고리즘을 사용
+ 📌 경로 선택 메트릭은 홉 카운트(Hop Count)이다.
+ 라우팅 프로토콜을 IGP와 EGP로 분류했을 때 EGP에 해당한다.
  + IGP 내부 경로 설정을 위한 프로토콜
  + EGP 외부에서 내부로 집입할 수 있는 경로 설정을 위한 프로토콜
+ 📌 최단 경로 탐색에 Bellman-Ford 알고리즘을 사용한다. 
+ 📌 각 라우터는 이웃 라우터들로부터 수신한 정보를 이용하여 라우팅 표를 갱신한다
+ 최적의 경로가 아닌 경우도 발생
+ 최대 15개까지만 거침
#### 홉 카운트(Hop Count)
+ 출발지와 목적지 사이에 위치한 경로의 한 부분
+ 홉 자체는 라우터라고 보면 된다.

<br><br>
## 프로세스
+ 프로그램, 프로세서, 프로세스 구분
+ 디스패치(Dispatch): 프로세스가 준비 상태에서 프로세서가 배당되어실행 상태로 변화하는 것을 라고 한다. 
+ 프로세스 제어 블록(PCB, Process Control Block): 프로세스 식별자, 프로세스 상태 등의 정보로 구성된다. 
+ 📌 문맥교환(Context Switching): 이전 프로세스의 상태 레지스터 내용을 보관하고다른 프로세스의 레지스터를 적재하는 과정
+ 📌 프로세스 안에 스레드가 존재.
### 프로세스 스케줄링
#### 선점 스케줄링
> SRT(Shortest Remaining Time), 라운드로빈 스케줄링, 다단계 큐(Mulit-level Queue), 다단계 피드백 큐 스케줄링
#### 비선점 스케줄링
> FCFS(First come first service), SJF(Shortest job first), 우선 순위, HRN(Highest response next)
+ 이미 할당된 CPU를 다른 프로세스가 강제로 빼앗아 사용할 수 없는 스케줄링 기법
+ HRN 스케줄링
  + 📌 최소 작업 우선(SJF) 기법의 약점을 보완한 비선점 스케줄링 기법
  + 우선순위 = (대기시간+서비스시간)/서비스시간
+ SJF 스케줄링
  + 큐 프로세스 중 수행시간이 짧은 것을 먼저 수행하는 방법으로 평균 대기시간을 감소시킨다.
+ 우선순위 스케줄링
  + 우선순위 순으로 수행하며, 응답속도 증가
  + 동적으로 우선순위를 부여할 경우, 구현이 복잡하고 오버헤드가 많다.

<br><br>
## 디스크 스케줄링
> FCFS 스케줄링, SSTF 스케줄링, SCAN 및 LOCK 스케줄링, C-SCAN 스케줄링
###  SSTF 스케줄링
+ 현재 헤드에서 가장 가까운 거리의 요청을 먼저 서비스하는 기법

<br><br>
## 파일 디스크립터(File Descriptor)
+ Unix OS에서 네트워크 소켓과 같은 파일이나 기타 입력/출력 리소스에 액세스하는 데 사용되는 추상표현이다
+ 파일 관리를 위해 시스템이 필요로 하는 정보를 가지고 있다. 
+ 보조기억장치에 저장되어 있다가 파일이 개방(open)되면 주기억장치로 이동된다. 
+ 📌 시스템으로 부터 할당받은 파일이나 소켓을 대표하는 정수다.
+ 파일 제어 블록(File Control Block)이라고도 한다.

<br><br>
## 운영체제
### UNIX
+ 하나 이상의 작업에 대하여 백그라운드에서 수행이가능하다. 
+ 📌 다중 사용자, 다중 작업을 지원한다.
+ 📌 트리 구조의 파일 시스템을 갖는다.
+ 이식성이 높으며 장치 간의 호환성이 높다.
+ 대부분 C언어로 되어 있으며, 이식성이 높다.
#### 구성
+ 하드웨어 > 커널 > 쉘 > 유틸리티 > 사용자
+ 쉘의 주요기능
  + 사용자 명령을 해석하고 커널로 전달하는 기능을 제공한다.
  + 반복적인 명령 프로그램을 만드는 프로그래밍 기능을 제공한다. 
  + 초기화 파일을 이용해 사용자 환경을 설정하는 기능을 제공한다.
+ 커널의 주요기능
  + 쉘 프로그램 실행을 위해 프로세스와 메모리를 관리한다.

<br><br>
## 응집도와 결합도
> 📌 응집도는 높게 결합도는 낮게 설계한다.
### 응집도(Cohesion)
> 기능적 > 순차적 > 통신적 > 절차적 > 일시적(시간적) > 논리적 > 우연적
+ 응집도는 모듈의 독립성을 나타내는 개념으로, 모듈 내부 구성요소 간 연관 정도
#### 일시적 응집도
+ 모듈 내 구성 요소들이 서로 다른 기능을 같은 시간대에 함께 실행하는 경우
### 결합도(Coupling)
> 내용 > 공통 > 외부 > 제어 > 스탬프 > 자료(데이터)
+ 결합도는 모듈 내부가 아닌 외부의 모듈과의 연관도 또는 모듈 간의 상호의존성을 나타내는 정도
+ 모듈들이 변수를 공유하여 사용하게 하거나 제어 정보를 교류하게 하면 결합도를 높아진다.
#### 내용결합도
  + 한 모듈이 다른 모듈의 내부 기능 및 그 내부 자료를 참조하는 경우

<br><br>
## 자동 반복 요청(ARQ, Automatic Repeat Request)
### 📌 오류 제어
+ Stop-and-wait ARQ: 하나씩 ACK 받을 때까지 대기하다가 전송
+ Go-back-N ARO: 한번에 여러 개를 보낸후 하나의 긍정 확인응답(ACK)을 받고, 후속 데이터 전송
+ Selective-Repeat ARQ: 오류부분만 재전송
+ Adaptive ARQ: 적응적으로 ARQ 횟수를 줄여 전송 효율을 높이는 방식


<br><br>
## 상호 배제 기법
+ 공유자원을 어느 시점에서 단지 한 개의 프로세스만이 사용할 수 있도록 하며, 다른 프로세스가 공유자원에 대해 접근하지 못하게 하는 기법
+ 여러 프로세스가 동시에 공유 자원을 사용할 때 각 프로세스가 번갈아 가며 공유자원을 사용하도록 하는 것. 임계구역을 유지하는 방법
+ 데커(Dekker) 알고리즘
  + 교착상태가 없도록 보장, 상호배제 보장, 별도 명령어 없이 소프트웨어로 해결

<br><br>
## 동기화 기법
### 세마포어(Semaphore)
+ 공유된 자원의 데이터 혹은 임계영역(Critical Section) 등에 여러 Process 혹은 Thread가 접근하는 것을 막아줌(즉, 동기화 대상이 하나 이상)
```
// 📌 임계 구역의 접근을 제어하는 상호배제 기법
P(S) : while S＜=0 do skip；
S :＝S－1；
V(S) : S :＝S＋1；
```
### 뮤텍스(Mutex)
+ 공유된 자원의 데이터 혹은 임계영역(Critical Section) 등에 하나의 Process 혹은 Thread가 접근하는 것을 막아줌(즉, 동기화 대상이 하나)

<br><br>
## 기억장치 배치 전략
### 최초 적합 first-fit
+ 주기억 장치에서 첫 번째 가능 공간을 찾아 할당하는 기법
###최적 적합 best-fit
+ 가능한 공간 중 가장 작은 공간을 사용
### 최악 적합 worst-fit
+ 가장 큰 것을 사용하는 방식
#### 관련 용어
+ 내부단편화: 분할하고 남은 공간의 크기
+ 외부단편화: 프로그램보다 작은 크기가 발생해 만들어진 공간
```
빈 기억공간의 크기가 20KB, 16KB, 8KB, 40KB일 때 기억장치 배치 전략으로 “Best Fit"을 사용하여 17KB의 프로그램을 적재할 경우 내부단편화의 크기는 얼마인가?
>> 17KB 프로그램이므로 가능한 공간 중 가장 작은 공간인 20KB를 선택하게 되고, 내부 단편화의 크기는 남는 공간이므로 3KB가 된다.
```

<br><br>
## 페이지 교체 알고리즘
### FIFO 페이지 교체 알고리즘
### Optional 페이지 교체 알고리즘
### LRU 페이지 교체 알고리즘
+ 최근에 가장 오랫동안 사용하지 않은 페이지를 교체하는 기법
+ 📌 https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=botemi11&logNo=220062848209


