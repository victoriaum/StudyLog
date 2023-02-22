## C
### 계산문제
```
// 📌 아래는 C언어의 2차원 배열 형태이다. field의 경우 2차원 배열 형태는 예시처럼 출력되므로, 이를 참고하여 mines의 2차원 배열 형태를 작성하시오.
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
`