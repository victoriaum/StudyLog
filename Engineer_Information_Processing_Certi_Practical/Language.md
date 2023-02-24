## C
```
❓ 
// 아래는 C언어의 2차원 배열 형태이다. field의 경우 2차원 배열 형태는 예시처럼 출력되므로, 이를 참고하여 mines의 2차원 배열 형태를 작성하시오.
void main{
 
field {{0,1,0,1},{0,0,0,1},{1,1,1,0},{0,1,1,1}};
mines {{0,0,0,0},{0,0,0,0},{0,0,0,0},{0,0,0,0}}; 
 
int w = 4, h = 4;
  for(y=0; y<h; y++) {
    for(x=0; x<w; x++) {  
      if(field[y][x] == 0) continue;
      for(i=y-1; i<=y+1; i++) {
        for(j=x-1; j<=x+1; j++) {
          if(calculate(w,h,j,i) == 1) {
            mines[i][j] += 1;
          }  
        }
      }   
    }
  }
  for(y=0; y<h; y++){
    for(x=0; x<w; x++)
      printf("%d", mines[y][x]);
      printf("\n");
  }
 
}
 
int calculate(w,h,j,i) {
  if (i >= 0 && i < h && j >= 0 && j < w) return 1;
  return 0;
}


1 1 3 2
3 4 5 3 
3 5 6 4
3 5 5 3
```
<br>

```
int main(int argc, char *argv[]) {
    int a[4] = {0, 2, 4, 8};
    int b[3] = {};
    int i = 1;
    int sum = 0;
    int *p1;
     
    for (i; i < 4; i++) {
        p1 = a + i;
        b[i-1] = *p1 - a[i-1];
        sum = sum + b[i-1] + a[i];
    }
     
    printf("%d", sum);
    return 0;
}

// 22
```
+ 
<br>

<br><br>
## Java
```java
void main{
    int []result = int[5];
    int []arr = [77,32,10,99,50];
    
    for(int i = 0; i < 5; i++) {
        result[i] = 1;
        for(int j = 0; j < 5; j++) {
            if(arr[i] <arr[j]) result[i]++;
        }
    }
    
    for(int k = 0; k < 5; k++) {
        printf(result[k]);
    }
}

// 출력값: 24513
```
+ 모든 초기 값에는 1이 들어간다.
+ 여기서 arr[i]의 값보다 큰 arr[?]의 수를 더해주면 된다.
+ arr[0]은 현재 1이 들어가있고, 77보다 큰 수는 '99' 1개이므로 2가 된다.
+ arr[1]은 현재 1이 들어가있고, 32보다 큰 수는 3개이므로 4가 된다.
+ 이하동일.
<br>

```java
public static void main(String args[]){
  
  int i = 3; int k = 1; 
  switch(i) { 
    case 1: k += 1;
    case 2: k++;
    case 3: k = 0; 
    case 4: k += 3; 
    case 5: k -= 10; 
    default: k--; 
  }
  System.out.print(k); 
  
}

// -8
```

<br><br>
## Python
```
a = "REMEMBER NOVEMBER"
b = a[:3] + a[12:16];
c = "R AND %s" % "STR";
print(b+c);
// REMEMBER AND STR
```

<br><br>
## 네트워크 주소 분할
```
❓ 
첫번째 네트워크 주소가 192.168.1.0/26일때 FLSM 3개로 분할했을때 
두번째 네트워크 브로드캐스드 IP를 10진수로 변환한 값을 작성하시오.
// 192.168.1.127
```
<br>

```
❓ 
IP 주소가 139.127.19.132이고 서브넷마스크 255.255.255.192일 때 아래의 답을 작성하시오.
// (1) 괄호안에 들어갈 네트워크 주소 : 139.127.19.(128)
// (2) 해당 네트워크 주소와 브로드캐스트 주소를 제외한 호스트 개수 : 62
```