## SQL
```
SELECT 제조사, 제품명, 단가
FROM 제품
WHERE 단가 > ALL (SELECT 단가 FROM 제품 WHERE 제조사='H')
```
+ ALL 위치 다시 확인하기
+ count()에서 NULL 값인 것은 제외하고 카운팅한다.
